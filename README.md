<h1>Configuring IP Addresses</h1>


<h2>Description</h2>

To configure this network, IP addresses are assigned to the PCs and routers as shown in the diagram, ensuring the default gateways are set on the PCs. Static routes are configured on the routers to enable communication between the two subnets. A static route is a manually configured routing entry that directs traffic to a specific destination via a predefined path. Each router has static routes pointing to the next hop address to connect to the other subnet. This allows PC1 to successfully ping PC2.

<h2>Languages and Utilities Used</h2>

- <b>Cisco Command Line Interface</b> 

<h2>Environments Used </h2>

- <b>Cisco Packet Tracer</b>

<h2>Things Learned/Troubleshooting</h2>
When trying to display the running configuration, there is different ways to type in the command depending on which mode you are in. For example, when in privileged EXEC mode the command would be do show running-config vs when in user EXEC mode the command would be show running-config. 

<h2>Program walk-through:</h2>

The default gateway for a PC in a subnet is the router's IP address. In this case, R1's IP address is the default gateway for PC1. 
![Screenshot 2025-01-06 235103](https://github.com/user-attachments/assets/47e432b7-05cd-446a-9f05-33351a9b46c5)

The IP address and subnet mask are configured on PC1. The /24 prefix is what makes the subnet 255.255.255.0.
![Screenshot 2025-01-06 235147](https://github.com/user-attachments/assets/c8a8b150-79bd-482d-a88c-84d4db87219d)

Each interface on each router is configured to allow connectivity throughout the network. In this case, R1's g0/0 interface and g0/1 interface is confugured. The 'no shutdown' command is imperative, as without it, the route will not be added to the routing table. 
![Screenshot 2025-01-06 235431](https://github.com/user-attachments/assets/253a344d-52de-41a3-b84c-4343082e6dca)

The command 'do show ip route' displays the connected routes that have been configured for interface g0/0 and g0/1.
![Screenshot 2025-01-07 002400](https://github.com/user-attachments/assets/b0daf6dc-24b0-46b7-8b95-0c6b717d220c)

R2's g0/1 interface needs to be configured. Once it is, it can be checked with the command "do show ip int brief." 
![Screenshot 2025-01-07 002619](https://github.com/user-attachments/assets/aa53693f-a5a6-4ade-996f-658b1f9f69f0)

R2's g0/0 interface's ip address was incorrect and had to be reconfigured to have the correct IP address. 
![Screenshot 2025-01-07 003428](https://github.com/user-attachments/assets/3341bfb0-96f6-4a12-b3c2-b49eddfe4474)

Although R2's g0/1 interface is in the routing table, it says administratively down. This is fixed by configuring interface g0/1 with a "no shutdown" command. 
![Screenshot 2025-01-07 003841](https://github.com/user-attachments/assets/84e733ac-d3bd-42e1-b037-049e1f7a5da9)

R3's g0/0 and g0/1 interface are configured with the proper IP address.
![Screenshot 2025-01-06 235958](https://github.com/user-attachments/assets/5fdbb91b-dbc6-4a1e-9e11-bb89f95e1232)

To check if the routes have been correctly added to the router, the commands "do show ip int brief" and "do show ip route" are used.
![Screenshot 2025-01-07 004125](https://github.com/user-attachments/assets/abea8da7-4591-4509-b697-66526bcbf98c)

To ensure connectivity, PC1 pings PC2. This shows that all routers and PCs have been properly configured. 
![Screenshot 2025-01-07 004229](https://github.com/user-attachments/assets/c5523fc7-c61f-426c-a035-33c94b4a6993)


