Java Socket programming is used for communication between the applications running on different JRE.

Java Socket programming can be connection-oriented or connection-less.

Socket and ServerSocket classes are used for connection-oriented socket programming and DatagramSocket and DatagramPacket classes are used for connection-less socket programming.

The client in socket programming must know two information:

1. IP Address of Server, and
2. Port number.

Here, we are going to make one-way client and server communication. In this application, client sends a message to the server, server reads the message and prints it. Here, two classes are being used: Socket and ServerSocket. The Socket class is used to communicate client and server. Through this class, we can read and write message. The ServerSocket class is used at server-side. The accept() method of ServerSocket class blocks the console until the client is connected. After the successful connection of client, it returns the instance of Socket at server-side.

![Socket Programming in Java](https://images.tpointtech.com/core/images/socket-programming.png)

---

## Socket class

A socket is simply an endpoint for communications between the machines. The Socket class can be used to create a socket.

### Important methods

|Method|Description|
|---|---|
|1) public InputStream getInputStream()|returns the InputStream attached with this socket.|
|2) public OutputStream getOutputStream()|returns the OutputStream attached with this socket.|
|3) public synchronized void close()|closes this socket|

## ServerSocket class

The ServerSocket class can be used to create a server socket. This object is used to establish communication with the clients.

### Important methods

|Method|Description|
|---|---|
|1) public Socket accept()|returns the socket and establish a connection between server and client.|
|2) public synchronized void close()|closes the server socket.|

## Example of Java Socket Programming

**Creating Server:**

To create the server application, we need to create the instance of ServerSocket class. Here, we are using 6666 port number for the communication between the client and server. You may also choose any other port number. The accept() method waits for the client. If clients connects with the given port number, it returns an instance of Socket.

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. ServerSocket ss=new ServerSocket(6666);  
2. Socket s=ss.accept();//establishes connection and waits for the client   

**Creating Client:**

To create the client application, we need to create the instance of Socket class. Here, we need to pass the IP address or hostname of the Server and a port number. Here, we are using "localhost" because our server is running on same system.

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. Socket s=new Socket("localhost",6666);  

Let's see a simple of Java socket programming where client sends a text and server receives and prints it.

File: MyServer.java

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. import java.io.*;  
2. import java.net.*;  
3. public class MyServer {  
4. public static void main(String[] args){  
5. try{  
6. ServerSocket ss=new ServerSocket(6666);  
7. Socket s=ss.accept();//establishes connection   
8. DataInputStream dis=new DataInputStream(s.getInputStream());  
9. String  str=(String)dis.readUTF();  
10. System.out.println("message= "+str);  
11. ss.close();  
12. }catch(Exception e){System.out.println(e);}  
13. }  
14. }  

File: MyClient.java

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. import java.io.*;  
2. import java.net.*;  
3. public class MyClient {  
4. public static void main(String[] args) {  
5. try{      
6. Socket s=new Socket("localhost",6666);  
7. DataOutputStream dout=new DataOutputStream(s.getOutputStream());  
8. dout.writeUTF("Hello Server");  
9. dout.flush();  
10. dout.close();  
11. s.close();  
12. }catch(Exception e){System.out.println(e);}  
13. }  
14. }  

To execute this program open two command prompts and execute each program at each command prompt as displayed in the below figure.

After running the client application, a message will be displayed on the server console.

![Java Networking Programming](https://images.tpointtech.com/images/networking.jpg)

---

## Example of Java Socket Programming (Read-Write both side)

In this example, client will write first to the server then server will receive and print the text. Then server will write to the client and client will receive and print the text. The step goes on.

File: MyServer.java

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. import java.net.*;  
2. import java.io.*;  
3. class MyServer{  
4. public static void main(String args[])throws Exception{  
5. ServerSocket ss=new ServerSocket(3333);  
6. Socket s=ss.accept();  
7. DataInputStream din=new DataInputStream(s.getInputStream());  
8. DataOutputStream dout=new DataOutputStream(s.getOutputStream());  
9. BufferedReader br=new BufferedReader(new InputStreamReader(System.in));  

10. String str="",str2="";  
11. while(!str.equals("stop")){  
12. str=din.readUTF();  
13. System.out.println("client says: "+str);  
14. str2=br.readLine();  
15. dout.writeUTF(str2);  
16. dout.flush();  
17. }  
18. din.close();  
19. s.close();  
20. ss.close();  
21. }}  

File: MyClient.java

[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)[](https://www.tpointtech.com/socket-programming#)

1. import java.net.*;  
2. import java.io.*;  
3. class MyClient{  
4. public static void main(String args[])throws Exception{  
5. Socket s=new Socket("localhost",3333);  
6. DataInputStream din=new DataInputStream(s.getInputStream());  
7. DataOutputStream dout=new DataOutputStream(s.getOutputStream());  
8. BufferedReader br=new BufferedReader(new InputStreamReader(System.in));  

9. String str="",str2="";  
10. while(!str.equals("stop")){  
11. str=br.readLine();  
12. dout.writeUTF(str);  
13. dout.flush();  
14. str2=din.readUTF();  
15. System.out.println("Server says: "+str2);  
16. }  

17. dout.close();  
18. s.close();  
19. }}