# Sality Botnet Protocol Dissector
Network protocol dissector script that detects, decrypts and parses messages of the peer-to-peer botnet Sality.

Invoke it like this: `wireshark -X lua_script:sality.lua traffic.pcap`.

![Decoded Packet Content in Wireshark](https://github.com/tillmannw/sality-dissector/blob/master/wireshark.png)

Or use tshark for command line packet processing:

```
$ tshark -X lua_script:sality.lua -nr traffic.pcap
  1 205.037516 192.168.1.25 -> 96.56.17.58  Sality 62 URL Pack Exchange
  2 205.148691  96.56.17.58 -> 192.168.1.25 Sality 365 URL Pack Exchange, version 380 (4 URLs)
  3 205.159347 192.168.1.25 -> 96.56.17.58  Sality 88 Hello, port 8279, id 1 (request)
  4 205.189369  96.56.17.58 -> 192.168.1.25 Sality 68 Hello, port 8279, id 12340448 (natted)
  5 206.247286 192.168.1.25 -> 95.226.112.151 Sality 85 URL Pack Exchange
  6 206.473060 95.226.112.151 -> 192.168.1.25 Sality 63 URL Pack Exchange
  7 206.473917 192.168.1.25 -> 95.226.112.151 Sality 59 Peer Exchange
  8 206.709481 95.226.112.151 -> 192.168.1.25 Sality 82 Peer Exchange, 114.42.48.153:6070 19660835
```
