# NC_Packet_Loss_Test
FileMaker Packet Loss Test

utility to ping from filemaker

requires base elements

https://community.claris.com/en/s/article/dep006---under-the-hood--server-performance---jon-thatcher

#Mac
ping -c 10 -s 1500 marion.neocodesoftware.com

#Windows
ping -n 10 -l 500 marion.neocodesoftware.com
 
#Background
Under the Hood:   Server Performance
 
COR001
Jon Thatcher
Senior Architect, FileMaker, Inc.
© 2016 FileMaker, Inc.

#Slide 35
DO: Plan for the WAN
Latency
- Time delay in the network between request and response
- WAN may have 100 millisecond latency per round trip (vs 2ms on LAN)
TCP/IP default packet size is 1500 bytes
- 266000 bytes sent to client / 1500 bytes per packet = 177 round trips! - 177 round trips * 100ms latency = 17.7 seconds to send data!
 
 NOTE: This is a gross over-simplification and probably an over estimate!
TCP/IP will send multiple 1500 byte packets at once, without waiting for acknowledgement of each packet
In most cases there are many fewer full round trips than this, but it’s still a decent rule of thumb for estimating transfer time
