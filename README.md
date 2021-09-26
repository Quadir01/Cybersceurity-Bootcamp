# Cybersceurity-Bootcamp

What is in this repository ?

In this repository you will find 

•	Ansible YML Scripts from Cloud week

•	Bash Scripts from Linux week

•	Network Diagrams

In this repository I am going to have multiple folders, in these folders will be records of scripts and network diagrams that we've accumulated throughout the course we are taking up to this point. Below is a diagram that shows the layout of the network that we've set up.To use the virtual network that I have set up in Azure, I must first start the virtual machines, when all virtual machines have started, I need to start running git bash. In get bash SSH command is sent to one of our first Vm’s which is named jump box. Jump box contains a nested VM system called a container which in turn has a docker on it which is used to remotely configure to multiple other VM's, web 2, web 3, and web 4. These VM's are going to serve as web servers DVMA which all three run something called an ansible playbook which are set up to have vulnerabilities. 

To control traffic to and from all webserver Vm’s I used a load balancer that is configured to work with the firewall set up in my network group for security which allows the servers to run on HTTP port 80. One last server was set up on a different network group called an Elk stack. This server was configured slightly different form the web servers but and is not behind a load balancer however is accessible from outside the network just like the DVMA webservers. 
You may ask, if you find a server running HTTP on port 80, despite compliance guidelines requiring encryption in motion. What do you do? Well in this project this was done for simulated attack reason for leaning purposes only. In the real world the way we would allow HTTP traffic to flow safely is by not allowing port 80 to be open. Why? Port 80 is the default port for HTTP and unfriendly company know that this is a very easy way to find their way to the webservers they are looking for. The way to properly configure HTTP port is to block all traffic by default and explicitly enable only specific traffic to known services. Which is why a load balancer was used and configured to run all traffic through to the webservers on the network. This will allow one point of entry for all traffic.

Be that as it may there are pros and cons to it Easy to configure and understand DNS based cluster don’t require multiple network interface cards. Each machine can have a single NIC with a unique IP address. Multiple IP addresses can be assigned to the host record. The DNS server can rotate this address and the workload gets divided equally among the members of the Server cluster. Load balancing pools for various geographic regions are established. The administrator can take advantage of infrastructure dispersed geographically and improve performance by reducing the distance between the receivers.

The cons to this is there is no failure detection or fault tolerance, no dynamic load re-balancing. No capability other than round-robin. No way to ensure connection to the same server twice, if required cannot tell if a server has become unavailable. Cannot consider the unknown percentage of users who have DNS data, with varying amounts of Time to Live TTL left. So, when TTL times out, visitors may still be directed to the wrong server. Load may not be evenly shared as DNS cannot tell how much load is present on the servers. Each server requires a public IP address.


![Untitled Diagram](https://user-images.githubusercontent.com/91102756/134803928-779fbee9-17fc-4198-8882-c8f5683e0bfc.jpg)
