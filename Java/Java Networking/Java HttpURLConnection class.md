The **Java HttpURLConnection** class is http specific URLConnection. It works for HTTP protocol only.

By the help of HttpURLConnection class, you can retrieve information of any HTTP URL such as header information, status code, response code etc.

The java.net.HttpURLConnection is subclass of URLConnection class.

## HttpURLConnection Class Constructor

|Constructor|Description|
|---|---|
|protected HttpURLConnection(URL u)|It constructs the instance of HttpURLConnection class.|

## Java HttpURLConnection Methods

|Method|Description|
|---|---|
|void disconnect()|It shows that other requests from the server are unlikely in the near future.|
|InputStream getErrorStream()|It returns the error stream if the connection failed but the server sent useful data.|
|Static boolean getFollowRedirects()|It returns a boolean value to check whether or not HTTP redirects should be automatically followed.|
|String getHeaderField(int n)|It returns the value of nth header file.|
|long getHeaderFieldDate(String name, long Default)|It returns the value of the named field parsed as a date.|
|String getHeaderFieldKey(int n)|It returns the key for the nth header file.|
|boolean getInstanceFollowRedirects()|It returns the value of HttpURLConnection's instance FollowRedirects field.|
|Permission getPermission()|It returns the SocketPermission object representing the permission to connect to the destination host and port.|
|String getRequestMethod()|It gets the request method.|
|int getResponseCode()|It gets the response code from an HTTP response message.|
|String getResponseMessage()|It gets the response message sent along with the response code from a server.|
|void setChunkedStreamingMode(int chunklen)|The method is used to enable streaming of a HTTP request body without internal buffering, when the content length is not known in advance.|
|void setFixedLengthStreamingMode(int contentlength)|The method is used to enable streaming of a HTTP request body without internal buffering, when the content length is known in advance.|
|void setFixedLengthStreamingMode(long contentlength)|The method is used to enable streaming of a HTTP request body without internal buffering, when the content length is not known in advance.|
|static void setFollowRedirects(boolean set)|It sets whether HTTP redirects (requests with response code) should be automatically followed by HttpURLConnection class.|
|void setInstanceFollowRedirects(boolean followRedirects)|It sets whether HTTP redirects (requests with response code) should be automatically followed by instance of HttpURLConnection class.|
|void setRequestMethod(String method)|Sets the method for the URL request, one of: GET POST HEAD OPTIONS PUT DELETE TRACE are legal, subject to protocol restrictions.|
|abstract boolean usingProxy()|It shows if the connection is going through a proxy.|

## How to get the object of HttpURLConnection class

The openConnection() method of URL class returns the object of URLConnection class.

**Syntax:**

[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)

1. public URLConnection openConnection()throws IOException{}  

You can typecast it to HttpURLConnection type as given below.

[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)

1. URL url=new URL("http://www.javatpoint.com/java-tutorial");    
2. HttpURLConnection huc=(HttpURLConnection)url.openConnection();  

## Java HttpURLConnection Example

[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)[](https://www.tpointtech.com/java-http-url-connection#)

1. import java.io.*;    
2. import java.net.*;    
3. public class HttpURLConnectionDemo{    
4. public static void main(String[] args){    
5. try{    
6. URL url=new URL("http://www.javatpoint.com/java-tutorial");    
7. HttpURLConnection huc=(HttpURLConnection)url.openConnection();  
8. for(int i=1;i<=8;i++){  
9. System.out.println(huc.getHeaderFieldKey(i)+" = "+huc.getHeaderField(i));  
10. }  
11. huc.disconnect();   
12. }catch(Exception e){System.out.println(e);}    
13. }    
14. }    

[Test it Now](https://www.tpointtech.com/opr/test.jsp?filename=HttpURLConnectionDemo)

**Output:**

Date = Thu, 22 Jul 2021 18:08:17 GMT
Server = Apache
Location = java-tutorial
Cache-Control = max-age=2592000
Expires = Sat, 21 Aug 2021 18:08:17 GMT
Content-Length = 248
Keep-Alive =timeout=5, max=1500
Connection = Keep-Alive

  
![DatagramSocket and DatagramPacket](https://images.tpointtech.com/core/images/java-datagramsocket-and-datagrampacket3.png)