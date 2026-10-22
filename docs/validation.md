# Packet Tracer validation checklist

These checks are pending unless explicitly supported by the historical screenshots. Do not use production credentials in the lab.

## Configuration inventory

Record the Packet Tracer version and the date of testing. Save a working copy so the original topology remains available.

| Check | Suggested evidence | Current status |
|---|---|---|
| Devices and links | Logical topology screenshot and interface status | Historical topology image supplied |
| VLAN membership | `show vlan brief` on core and access switches | Pending |
| Trunks and allowed VLANs | `show interfaces trunk` | Pending |
| Router subinterfaces | `show ip interface brief`, relevant running configuration | Pending |
| Routes | `show ip route` | Pending |
| Host addressing and gateways | IP Configuration or `ipconfig` for each VLAN | Pending |
| DHCP availability | Lease acquisition and pool configuration, if implemented | Pending |
| DNS and HTTP | Server settings plus name lookup and browser request, if implemented | Pending |
| Access restrictions | ACL configuration and both permitted/denied tests | Pending |

## Connectivity

For each host, ping its gateway first, then a host on another subnet. Repeat the ping after the first run, recording transmitted/received counts rather than only the last successful reply.

Recheck the report's targets: Administration to 192.168.20.10, Administration to 192.168.30.10 and Library to 192.168.10.10. Verify source and target addresses in the actual topology before testing. The historical images show packet loss in the first two tests and no loss in the third.

If connectivity fails, check IP/mask/gateway, VLAN access assignment, trunk state, router subinterfaces and routing. Only treat first-packet loss as address-resolution behavior if repeated results and simulation events support that diagnosis.

## Completion evidence

Keep sanitized configuration exports, screenshots and a result table with date, source, target, expected behavior, actual behavior and pass/fail. Avoid presenting the proposed server VLAN or internet connectivity as implemented until these checks prove it.
