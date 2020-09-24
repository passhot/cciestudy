# cciestudy
Learn with us and pass the CCIE exam together.

<a href="https://www.passhot.com/ccnadumps/ccna_200_301.html" target="_blank" style="color: #ffffff;">Latest Cisco CCIE CCNP CCNA Exam Dumps</a>


Learn network port mirroring technology in 3 minutes

Today we come to understand the network port mirroring technology.



Port mirroring is to copy the packets of the specified port (source port), VLAN (source VLAN) or CPU (source CPU) to other ports (destination ports). The destination port will be connected to the data monitoring device, and the user will use these data to monitor The device analyzes the packets copied to the destination port for network monitoring and troubleshooting. Without seriously affecting the normal throughput of the source port, the network traffic can be monitored and analyzed through the mirror port.



Source port: It is the monitored port, and the user can monitor and analyze the packets passing through the port.

Source VLAN: It is the VLAN to be monitored. Users can monitor and analyze the packets passing through all ports of this VLAN.

Source CPU: The CPU on the monitored board. The user can monitor and analyze the packets passing through the CPU.

Destination port: It can also be called a monitoring port. This port forwards the received message to the data monitoring device for monitoring and analysis of the message.



Mirror direction:

Incoming direction: Only the packets received from the source port/source VLAN/source CPU are mirrored.

Outgoing direction: Only the packets sent from the source port/source VLAN/source CPU are mirrored.

Bidirectional: Mirror the packets received and sent from the source port/source VLAN/source CPU.

 

According to the division of mirroring functions, port mirroring is divided into two types:

Flow mirroring: If ACL is configured and enabled on the port, it is considered to be flow mirroring. Flow mirroring only collects data packets filtered by ACL, otherwise it is regarded as pure port mirroring. For ACL traffic collection methods, it is supported to bind standard access lists and extended access lists in the direction of the port (outgoing, incoming, and bidirectional).

Pure port mirroring: mirror the traffic in and out of the port.

 

According to the scope of mirroring work, port mirroring is divided into two types:

Local mirroring: The source port and destination port are on the same router.

Remote mirroring: The source port and the destination port are distributed on different routers, and the mirrored traffic is encapsulated to achieve cross-router transmission.



The implementation of local port mirroring:

Local port mirroring can mirror all messages (including protocol messages and data messages). It is realized by a local mirroring group, that is, the source port/port in the source VLAN/source CPU and destination port are mirrored locally In the group, the device copies the packets from the source port (or source VLAN) and forwards them to the destination port. The local mirroring group supports cross-board mirroring, that is, the destination port and the source port/port/source CPU in the source VLAN can be on different boards of the same device.



Remote mirroring is divided into cross-layer 2 remote port mirroring and cross-layer 3 remote port mirroring:

Cross-Layer 2 remote port mirroring:

Cross-Layer 2 remote port mirroring can mirror all messages except protocol messages. It is realized by the cooperation of the remote source mirroring group and the remote destination mirroring group.



The user creates a remote source mirroring group on the source device and a remote destination mirroring group on the destination device. The source device copies the source port/source VLAN/source CPU message, broadcasts it in the remote mirroring VLAN through the reflection port, and sends it to the destination device via the intermediate device. After the destination device receives the message, if its VLAN ID is the same as the VLAN ID of the remote mirroring VLAN of the remote destination mirroring group, it forwards it to the destination port.



In this way, the data monitoring device connected to the destination port can monitor and analyze the source port/source VLAN/source CPU packets on the source device. The user needs to ensure the interoperability of the Layer 2 network between the source device and the destination device in the remote mirroring VLAN.



Since the source port/source VLAN/source CPU message will be broadcast in the remote mirroring VLAN of the source device, the local port mirroring function can be realized by adding other ports on the source device to the remote mirroring VLAN.



Mirroring across three layers of remote ports:

Cross-Layer 3 remote port mirroring can mirror all messages except protocol messages. It is realized by the cooperation of remote source mirroring group, remote destination mirroring group and GRE tunnel.
