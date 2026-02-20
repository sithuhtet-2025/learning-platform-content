The System.IO namespace consists of IO related classes, structures, delegates and enumerations. These classes can be used to reads and write data to files or data streams. It also contains classes for file and directory support.

### C# System.IO Namespace Classes

Following are the classes reside into System.IO namespace.

| Class                           | Description                                                                                                                              |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| BinaryReader                    | It is used to read primitive data types as binary values in a specific encoding.                                                         |
| BinaryWriter                    | It is used to write primitive types in binary to a stream.                                                                               |
| BufferedStream                  | It is used to add a buffering layer to read and write operations on another stream. It is a sealed class.                                |
| Directory                       | It is used to expose static methods for creating, moving and enumerating through directories and subdirectories. It is a sealed class.   |
| DirectoryInfo                   | It is used to expose instance methods for creating, moving and enumerating through directories and subdirectories. It is a sealed class. |
| DirectoryNotFoundException      | It is used to handle exception related to the file or directory cannot be found.                                                         |
| DriveInfo                       | It is used to access the information on a drive.                                                                                         |
| DriveNotFoundException          | It is used to handle drive not found exception.                                                                                          |
| EndOfStreamException            | It is used to handle end of stream exception.                                                                                            |
| ErrorEventArgs                  | It provides data for the FileSystemWatcher.Error event.                                                                                  |
| File                            | This class provides static methods for the creation, copying, deletion, moving and opening of a single file.                             |
| FileFormatException             | It is used to handle file format exception.                                                                                              |
| FileInfo                        | It is used to provide properties and instance methods for the creation, copying, deletion, moving and opening of files.                  |
| FileLoadException               | It is used to handle file load exception.                                                                                                |
| FileNotFoundException           | It is used to handle file load exception.                                                                                                |
| FileNotFoundException           | It is used to handle file not found exception.                                                                                           |
| FileStream                      | It provides a Stream for a file, supporting both synchronous and asynchronous read and write operations.                                 |
| FileSystemEventArgs             | It provides data for the directory events.                                                                                               |
| FileSystemInfo                  | It provides the base class for both FileInfo and DirectoryInfo objects.                                                                  |
| FileSystemWatcher               | It listens to the file system change notifications and raises events when a directory or file in a directory, changes.                   |
| InternalBufferOverflowException | This class is used to handle internal buffer overflow exception.                                                                         |
| InvalidDataException            | It is used to handle invalid data exception.                                                                                             |
| IODescriptionAttribute          | It sets the description visual designers can display when referencing an event, extender or property.                                    |
| IOException                     | It is an exception class that handles I/O errors.                                                                                        |
| MemoryStream                    | It is used to create a stream whose backing store is memory.                                                                             |
| Path                            | It performs operations on String instances that contain file or directory path information.                                              |
| PathTooLongException            | It is an exception class and used to handle path too long exception.                                                                     |
| PipeException                   | This exception class is used to handle pipe related exception.                                                                           |
| RenamedEventArgs                | It is used to provide data for the Renamed event.                                                                                        |
| Stream                          | It is used to provide a generic view of a sequence of bytes. It is an abstract class.                                                    |
| StreamReader                    | It is used to implement a TextReader that reads characters from a byte stream.                                                           |
| StringReader                    | It is used to implement a TextReader that reads from a string.                                                                           |
| StringWriter                    | It is used to implement a TextWriter for writing information to a string. The information is stored in an underlying StringBuilder.      |
| TextReader                      | This class is used to represent a reader that can read a sequential series of characters.                                                |
| TextWriter                      | This class is used to represent a writer that can write a sequential series of characters.                                               |
| UnmanagedMemoryAccessor         | It is used to provide random access to unmanaged blocks of memory from managed code.                                                     |
| UnmanagedMemoryStream           | It is used to get access to unmanaged blocks of memory from managed code.                                                                |

### System.IO Namespace Structures

Following are the structures reside into the System.IO Namespace.

|Structure|Description|
|---|---|
|WaitForChangedResult|It contains information on the change that occurred.|

### System.IO Namespace Delegates

The System.IO Namespace contains the following delegates.

|Delegates|Description|
|---|---|
|ErrorEventHandler|It represents the method that will handle the Error event of a FileSystemWatcher object.|
|FileSystemEventHandler|It represents the method that will handle the Changed, Created or Deleted event of a FileSystemWatcher class.|
|RenamedEventHandler|It represents the method that will handle the renamed event of a FileSystemWatcher class.|

### System.IO Namespace Enumerations

The following table contains the enumerations reside into the System.IO namespace.

|Enumeration|Description|
|---|---|
|DriveType|It is used to define constants for drive types including CDRom, Fixed, Network etc.|
|FileAccess|It is used to define constants for read, write or read/write access to a file.|
|FileAttributes|It is used to provide attributes for files and directories.|
|FileMode|It is used to specify how the operating system should open a file.|
|FileOptions|It is used to represents advanced options for creating a FileStream object.|
|FileShare|It is used to contain constants for controlling the kind of access other FileStream objects can have to the same file.|
|HandleInheritability|It specifies whether the underlying handle is inheritable by child processes.|
|NotifyFilters|It is used to specify changes to watch for in a file or folder.|
|SearchOption|It is used to specify whether to search the current directory or the current directory and all subdirectories.|
|SeekOrigin|It is used to specify the position in a stream to use for seeking.|
|WatcherChangeTypes|It changes that might occur to a file or directory.|