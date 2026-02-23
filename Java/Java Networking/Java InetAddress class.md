**Java InetAddress** class represents an IP address. The java.net.InetAddress class provides methods to get the IP of any host name _for example_ www.javatpoint.com, www.google.com, www.facebook.com, etc.

An IP address is represented by 32-bit or 128-bit unsigned number. An instance of InetAddress represents the IP address with its corresponding host name. There are two types of addresses: Unicast and Multicast. The Unicast is an identifier for a single interface whereas Multicast is an identifier for a set of interfaces.

Moreover, InetAddress has a cache mechanism to store successful and unsuccessful host name resolutions.

## IP Address

- An IP address helps to identify a specific resource on the network using a numerical representation.
- Most networks combine IP with TCP (Transmission Control Protocol). It builds a virtual bridge among the destination and the source.

There are two versions of IP address:

### 1. IPv4

IPv4 is the primary Internet protocol. It is the first version of IP deployed for production in the ARAPNET in 1983. It is a widely used IP version to differentiate devices on network using an addressing scheme. A 32-bit addressing scheme is used to store 232 addresses that is more than 4 million addresses.

**Features of IPv4:**

- It is a connectionless protocol.
- It utilizes less memory and the addresses can be remembered easily with the class based addressing scheme.
- It also offers video conferencing and libraries.

### 2. IPv6

IPv6 is the latest version of Internet protocol. It aims at fulfilling the need of more internet addresses. It provides solutions for the problems present in IPv4. It provides 128-bit address space that can be used to form a network of 340 undecillion unique IP addresses. IPv6 is also identified with a name IPng (Internet Protocol next generation).

**Features of IPv6:**

- It has a stateful and stateless both configurations.
- It provides support for quality of service (QoS).
- It has a hierarchical addressing and routing infrastructure.

## TCP/IP Protocol

- TCP/IP is a communication protocol model used connect devices over a network via internet.
- TCP/IP helps in the process of addressing, transmitting, routing and receiving the data packets over the internet.
- The two main protocols used in this communication model are:
    1. TCP i.e. Transmission Control Protocol. TCP provides the way to create a communication channel across the network. It also helps in transmission of packets at sender end as well as receiver end.
    2. IP i.e. Internet Protocol. IP provides the address to the nodes connected on the internet. It uses a gateway computer to check whether the IP address is correct and the message is forwarded correctly or not.

## Java InetAddress Class Methods

|Method|Description|
|---|---|
|public static InetAddress getByName(String host) throws UnknownHostException|It returns the instance of InetAddress containing LocalHost IP and name.|
|public static InetAddress getLocalHost() throws UnknownHostException|It returns the instance of InetAdddress containing local host name and address.|
|public String getHostName()|It returns the host name of the IP address.|
|public String getHostAddress()|It returns the IP address in string format.|

## Example of Java InetAddress Class

Let's see a simple example of InetAddress class to get ip address of www.javatpoint.com website.

**InetDemo.java**

[](https://www.tpointtech.com/inetaddress-class#)[](https://www.tpointtech.com/inetaddress-class#)[](https://www.tpointtech.com/inetaddress-class#)

1. import java.io.*;  
2. import java.net.*;  
3. public class InetDemo{  
4. public static void main(String[] args){  
5. try{  
6. InetAddress ip=InetAddress.getByName("www.javatpoint.com");  

7. System.out.println("Host Name: "+ip.getHostName());  
8. System.out.println("IP Address: "+ip.getHostAddress());  
9. }catch(Exception e){System.out.println(e);}  
10. }  
11. }  

[Test it Now](https://www.tpointtech.com/opr/test.jsp?filename=InetDemo)

**Output:**

Host Name: www.javatpoint.com
IP Address: 172.67.196.82

### Program to demonstrate methods of InetAddress class

**InetDemo2.java**

[](https://www.tpointtech.com/inetaddress-class#)[](https://www.tpointtech.com/inetaddress-class#)[](https://www.tpointtech.com/inetaddress-class#)

1. import java.net.Inet4Address;  
2. import java.util.Arrays;  
3. import java.net.InetAddress;  
4. public class InetDemo2  
5. {  
6. public static void main(String[] arg) throws Exception  
7. {  
8. InetAddress ip =  Inet4Address.getByName("www.javatpoint.com");  
9. InetAddress ip1[] = InetAddress.getAllByName("www.javatpoint.com");  
10. byte addr[]={72, 3, 2, 12};  
11. System.out.println("ip : "+ip);  
12. System.out.print("\nip1 : "+ip1);  
13. InetAddress ip2 =  InetAddress.getByAddress(addr);  
14. System.out.print("\nip2 : "+ip2);  
15. System.out.print("\nAddress : " +Arrays.toString(ip.getAddress()));  
16. System.out.print("\nHost Address : " +ip.getHostAddress());  
17. System.out.print("\nisAnyLocalAddress : " +ip.isAnyLocalAddress());  
18. System.out.print("\nisLinkLocalAddress : " +ip.isLinkLocalAddress());  
19. System.out.print("\nisLoopbackAddress : " +ip.isLoopbackAddress());  
20. System.out.print("\nisMCGlobal : " +ip.isMCGlobal());  
21. System.out.print("\nisMCLinkLocal : " +ip.isMCLinkLocal());  
22. System.out.print("\nisMCNodeLocal : " +ip.isMCNodeLocal());  
23. System.out.print("\nisMCOrgLocal : " +ip.isMCOrgLocal());  
24. System.out.print("\nisMCSiteLocal : " +ip.isMCSiteLocal());  
25. System.out.print("\nisMulticastAddress : " +ip.isMulticastAddress());  
26. System.out.print("\nisSiteLocalAddress : " +ip.isSiteLocalAddress());  
27. System.out.print("\nhashCode : " +ip.hashCode());  
28. System.out.print("\n Is ip1 == ip2 : " +ip.equals(ip2));  
29. }  
30. }  

**Output:**

![Inet Address Class](https://images.tpointtech.com/core/images/java-inet-address-class.png)

In the above Java code, the various boolean methods of InetAdress class are demonstrated.