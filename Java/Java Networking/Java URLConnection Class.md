The **Java URLConnection** class represents a communication link between the URL and the application. It can be used to read and write data to the specified resource referred by the URL.

### What is the URL?

- URL is an abbreviation for Uniform Resource Locator. An URL is a form of string that helps to find a resource on the World Wide Web (WWW).
- URL has two components:

1. The protocol required to access the resource.
2. The location of the resource.

### Features of URLConnection class

1. URLConnection is an abstract class. The two subclasses HttpURLConnection and JarURLConnection makes the connetion between the client Java program and URL resource on the internet.
2. With the help of URLConnection class, a user can read and write to and from any resource referenced by an URL object.
3. Once a connection is established and the Java program has an URLConnection object, we can use it to read or write or get further information like content length, etc.

### Constructors

|Constructor|Description|
|---|---|
|1) protected URLConnection(URL url)|It constructs a URL connection to the specified URL.|

### URLConnection Class Methods

|Method|Description|
|---|---|
|void addRequestProperty(String key, String value)|It adds a general request property specified by a key-value pair|
|void connect()|It opens a communications link to the resource referenced by this URL, if such a connection has not already been established.|
|boolean getAllowUserInteraction()|It returns the value of the allowUserInteraction field for the object.|
|int getConnectionTimeout()|It returns setting for connect timeout.|
|Object getContent()|It retrieves the contents of the URL connection.|
|Object getContent(Class[] classes)|It retrieves the contents of the URL connection.|
|String getContentEncoding()|It returns the value of the content-encoding header field.|
|int getContentLength()|It returns the value of the content-length header field.|
|long getContentLengthLong()|It returns the value of the content-length header field as long.|
|String getContentType()|It returns the value of the date header field.|
|long getDate()|It returns the value of the date header field.|
|static boolean getDefaultAllowUserInteraction()|It returns the default value of the allowUserInteraction field.|
|boolean getDefaultUseCaches()|It returns the default value of an URLConnetion's useCaches flag.|
|boolean getDoInput()|It returns the value of the URLConnection's doInput flag.|
|boolean getDoInput()|It returns the value of the URLConnection's doOutput flag.|
|long getExpiration()|It returns the value of the expires header files.|
|static FileNameMap getFilenameMap()|It loads the filename map from a data file.|
|String getHeaderField(int n)|It returns the value of nth header field|
|String getHeaderField(String name)|It returns the value of the named header field.|
|long getHeaderFieldDate(String name, long Default)|It returns the value of the named field parsed as a number.|
|int getHeaderFieldInt(String name, int Default)|It returns the value of the named field parsed as a number.|
|String getHeaderFieldKey(int n)|It returns the key for the nth header field.|
|long getHeaderFieldLong(String name, long Default)|It returns the value of the named field parsed as a number.|
|Map<String, List<String>> getHeaderFields()|It returns the unmodifiable Map of the header field.|
|long getIfModifiedSince()|It returns the value of the object's ifModifiedSince field.|
|InputStream getInputStream()|It returns an input stream that reads from the open condition.|
|long getLastModified()|It returns the value of the last-modified header field.|
|OutputStream getOutputStream()|It returns an output stream that writes to the connection.|
|Permission getPermission()|It returns a permission object representing the permission necessary to make the connection represented by the object.|
|int getReadTimeout()|It returns setting for read timeout.|
|Map<String, List<String>> getRequestProperties()|It returns the value of the named general request property for the connection.|
|URL getURL()|It returns the value of the URLConnection's URL field.|
|boolean getUseCaches()|It returns the value of the URLConnection's useCaches field.|
|Static String guessContentTypeFromName(String fname)|It tries to determine the content type of an object, based on the specified **file** component of a URL.|
|static String guessContentTypeFromStream(InputStream is)|It tries to determine the type of an input stream based on the characters at the beginning of the input stream.|
|void setAllowUserInteraction(boolean allowuserinteraction)|It sets the value of the allowUserInteraction field of this URLConnection.|
|static void setContentHandlerFactory(ContentHandlerFactory fac)|It sets the ContentHandlerFactory of an application.|
|static void setDefaultAllowUserInteraction(boolean defaultallowuserinteraction)|It sets the default value of the allowUserInteraction field for all future URLConnection objects to the specified value.|
|void steDafaultUseCaches(boolean defaultusecaches)|It sets the default value of the useCaches field to the specified value.|
|void setDoInput(boolean doinput)|It sets the value of the doInput field for this URLConnection to the specified value.|
|void setDoOutput(boolean dooutput)|It sets the value of the doOutput field for the URLConnection to the specified value.|

## How to get the object of URLConnection Class

The openConnection() method of the URL class returns the object of URLConnection class.

**Syntax:**

[](https://www.tpointtech.com/urlconnection-class#)[](https://www.tpointtech.com/urlconnection-class#)[](https://www.tpointtech.com/urlconnection-class#)

1. public URLConnection openConnection()throws IOException{}    

## Displaying Source Code of a Webpage by URLConnecton Class

The URLConnection class provides many methods. We can display all the data of a webpage by using the getInputStream() method. It returns all the data of the specified URL in the stream that can be read and displayed.

### Example of Java URLConnection Class

[](https://www.tpointtech.com/urlconnection-class#)[](https://www.tpointtech.com/urlconnection-class#)[](https://www.tpointtech.com/urlconnection-class#)

1. import java.io.*;    
2. import java.net.*;    
3. public class URLConnectionExample {    
4. public static void main(String[] args){    
5. try{    
6. URL url=new URL("http://www.javatpoint.com/java-tutorial");    
7. URLConnection urlcon=url.openConnection();    
8. InputStream stream=urlcon.getInputStream();    
9. int i;    
10. while((i=stream.read())!=-1){    
11. System.out.print((char)i);    
12. }    
13. }catch(Exception e){System.out.println(e);}    
14. }    
15. }