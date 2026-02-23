The **Java URL** class represents an URL. URL is an acronym for Uniform Resource Locator. It points to a resource on the World Wide Web. For example:

[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)

1. java-tutorial  

![URL in Java](https://images.tpointtech.com/core/images/java-url-class.png)

A URL contains many information:

1. **Protocol:** In this case, http is the protocol.
2. **Server name or IP Address:** In this case, www.javatpoint.com is the server name.
3. **Port Number:** It is an optional attribute. If we write http//ww.javatpoint.com:80/sonoojaiswal/ , 80 is the port number. If port number is not mentioned in the URL, it returns -1.
4. **File Name or directory name:** In this case, index.jsp is the file name.

---

## Constructors of Java URL class

**URL(String spec)**

Creates an instance of a URL from the String representation.

**URL(String protocol, String host, int port, String file)**

Creates an instance of a URL from the given protocol, host, port number, and file.

**URL(String protocol, String host, int port, String file, URLStreamHandler handler)**

Creates an instance of a URL from the given protocol, host, port number, file, and handler.

**URL(String protocol, String host, String file)**

Creates an instance of a URL from the given protocol name, host name, and file name.

**URL(URL context, String spec)**

Creates an instance of a URL by parsing the given spec within a specified context.

**URL(URL context, String spec, URLStreamHandler handler)**

Creates an instance of a URL by parsing the given spec with the specified handler within a given context.

## Commonly used methods of Java URL class

The java.net.URL class provides many methods. The important methods of URL class are given below.

|Method|Description|
|---|---|
|public String getProtocol()|it returns the protocol of the URL.|
|public String getHost()|it returns the host name of the URL.|
|public String getPort()|it returns the Port Number of the URL.|
|public String getFile()|it returns the file name of the URL.|
|public String getAuthority()|it returns the authority of the URL.|
|public String toString()|it returns the string representation of the URL.|
|public String getQuery()|it returns the query string of the URL.|
|public String getDefaultPort()|it returns the default port of the URL.|
|public URLConnection openConnection()|it returns the instance of URLConnection i.e. associated with this URL.|
|public boolean equals(Object obj)|it compares the URL with the given object.|
|public Object getContent()|it returns the content of the URL.|
|public String getRef()|it returns the anchor or reference of the URL.|
|public URI toURI()|it returns a URI of the URL.|

## Example of Java URL class

[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)

1. //URLDemo.java  
2. import java.net.*;  
3. public class URLDemo{  
4. public static void main(String[] args){  
5. try{  
6. URL url=new URL("http://www.javatpoint.com/java-tutorial");  

7. System.out.println("Protocol: "+url.getProtocol());  
8. System.out.println("Host Name: "+url.getHost());  
9. System.out.println("Port Number: "+url.getPort());  
10. System.out.println("File Name: "+url.getFile());  

11. }catch(Exception e){System.out.println(e);}  
12. }  
13. }  

[Test it Now](https://www.tpointtech.com/opr/test.jsp?filename=URLDemo)

Output:

Protocol: http
Host Name: www.javatpoint.com
Port Number: -1
File Name: /java-tutorial

Let us see another example URL class in Java.

[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)[](https://www.tpointtech.com/url-class#)

1. //URLDemo.java  
2. import java.net.*;    
3. public class URLDemo{    
4. public static void main(String[] args){    
5. try{    
6. URL url=new URL("https://www.google.com/search?q=javatpoint&oq=javatpoint&sourceid=chrome&ie=UTF-8");    

7. System.out.println("Protocol: "+url.getProtocol());    
8. System.out.println("Host Name: "+url.getHost());    
9. System.out.println("Port Number: "+url.getPort());    
10. System.out.println("Default Port Number: "+url.getDefaultPort());    
11. System.out.println("Query String: "+url.getQuery());    
12. System.out.println("Path: "+url.getPath());    
13. System.out.println("File: "+url.getFile());    

14. }catch(Exception e){System.out.println(e);}    
15. }    
16. }    

Output:

Protocol: https
Host Name: www.google.com
Port Number: -1
Default Port Number: 443
Query String: q=javatpoint&oq=javatpoint&sourceid=chrome&ie=UTF-8
Path: /search
File: /search?q=javatpoint&oq=javatpoint&sourceid=chrome&ie=UTF-8