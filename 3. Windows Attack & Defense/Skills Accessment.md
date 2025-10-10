1. Use the `"empire"` index and the `"bro:http:json"` sourcetype. Identify beaconing activity by modifying the Splunk search of the `"Detecting Beaconing Malware"` section and enter the value of the `"TimeInterval"` field as your answer.
Answer: 

```shell
index="empire" sourcetype="bro:http:json" 
| sort 0 _time
| streamstats current=f last(_time) as prevtime by src, dest, dest_port
| eval timedelta = _time - prevtime
| eventstats avg(timedelta) as avg, count as total by src, dest, dest_port
| eval upper=avg*1.1
| eval lower=avg*0.9
| where timedelta > lower AND timedelta < upper
| stats count, values(avg) as TimeInterval by src, dest, dest_port, total
| eval prcnt = (count/total)*100
| where prcnt > 80 AND total > 10
```

![](Image/Pasted%20image%2020251008004129.png)

---

2. Use the `"printnightmare"` index and the `"bro:dce_rpc:json"` sourcetype to create a Splunk search that will detect possible exploitation of the `PrintNightmare` vulnerability. Enter the IP included in the `"id.orig_h"` field as your answer.
Answer: `192.168.1.149`

```shell
index="printnightmare" sourcetype="bro:dce_rpc:json"
| bin _time span=1m
| where operation IN ("RpcAddPrinterDriverEx", "RpcRemoteFindFirstPrinterChangeNotificationEx", "RpcAddPrinterDriver", "RpcOpenPrinter", "RpcEnumPrinterDrivers", "RpcAddPrinter")
| stats count values(operation) as operation_values dc(operation) as unique_operations by _time, id.orig_h, id.resp_h
| where unique_operations >= 1 AND count > 1
```

![](Image/Pasted%20image%2020251008005104.png)

---

3. Use the `"bloodhound_all_no_kerberos_sign"` index and the `"bro:dce_rpc:json"` sourcetype to create a Splunk search that will detect possible BloodHound activity (https://www.lares.com/blog/active-directory-ad-attacks-enumeration-at-the-network-layer/). Enter the IP included in the `"id.orig_h"` field as your answer.
Answer: `192.168.109.105`

- RPCs were used by SharpHound to feed into BloodHound.

![](Image/Pasted%20image%2020251008010820.png)

```
index="bloodhound_all_no_kerberos_sign" sourcetype="bro:dce_rpc:json"
| bin _time span=1m
| where operation IN (
    "SamrConnect5",
    "NetrSessionEnum",
    "NetWkstaUserEnum",
    "SamrOpenAlias",
    "SamrGetMembersInAlias",
    "OpenUsers",
    "BaseRegQueryInfoKey",
    "SamrCloseHandle",
    "NetShareEnum",
    "NetUserEnum",
    "NetUserGetInfo",
    "NetGroupEnum",
    "NetLocalGroupEnum",
    "NetServerEnum"
  )
| stats count values(operation) as operation_values dc(operation) as unique_operations by _time, id.orig_h, id.resp_h
| where unique_operations >= 1 AND count > 1
| table _time, id.orig_h, id.resp_h, operation_values, unique_operations
```

![](Image/Pasted%20image%2020251008011654.png)

---
