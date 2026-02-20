C# BinaryWriter class is used to write binary information into stream. It is found in System.IO namespace. It also supports writing string in specific encoding.

### C# BinaryWriter Example

Let's see the simple example of BinaryWriter class which writes data into dat file.

[](https://www.tpointtech.com/c-sharp-binarywriter#)[](https://www.tpointtech.com/c-sharp-binarywriter#)[](https://www.tpointtech.com/c-sharp-binarywriter#)

1. using System;  
2. using System.IO;  
3. namespace BinaryWriterExample  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             string fileName = "e:\\binaryfile.dat";  
10.             using (BinaryWriter writer = new BinaryWriter(File.Open(fileName, FileMode.Create)))  
11.             {  
12.                 writer.Write(2.5);  
13.                 writer.Write("this is string data");  
14.                 writer.Write(true);  
15.             }  
16.             Console.WriteLine("Data written successfully...");    
17.         }  
18.     }  
19. }  

Output:

Data written successfully...