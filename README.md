# docker-config
Overrides for systemd docker service

By default, docker creates a network bridge "docker0".  Facter uses alphabetized 
interface list to determine ipaddress.  So docker0 ends up ahead of em/eno/eth, 
creating issues with puppet modules.  Working example:

```
$> facter | grep docker
interfaces => eno16780032,lo,zdocker0
ipaddress_zdocker0 => 172.17.0.1
macaddress_zdocker0 => 7e:f6:b8:c5:04:eb
mtu_zdocker0 => 1500
netmask_zdocker0 => 255.255.0.0
network_zdocker0 => 172.17.0.0
```
