In Java, **Path,** and **File** both are classes. They belong to different packages but perform the same mechanism. We can say that the **Java Path class** is the advanced version of the **File class**. We use both the classes for the File I/O operations. In this section, we will learn the **differences between path and file.**

## Java File Class

In [Java](https://www.tpointtech.com/java-tutorial), **File** is the class that belongs to the java.io package. It is an abstract representation of the file and directory pathnames. It is used for the file I/O, but have many drawbacks.

## Java Path Class

It is the same as the File class or we can say that it is a substitute class of the Java File class. It can perform all the operations that can be done with the help of the File class. Java Path class belongs to the java.nio.file package. It is a part of the modern java.nio.file library. It is usually used for creating new projects.

## Path Vs File

Prior to the [Java SE](https://www.tpointtech.com/java-se) 1.7 release, we used to java.io.File class for file I/O. But the File class has several drawbacks. Many methods of the File class did not throw exceptions, even they are failed to produce the desired output. So, it was difficult to obtain a useful error message.

Suppose, a file is to be deleted and a program that implements the file deletion functionality becomes fail to delete a file. The program shows the failure message deletion failed. But it was unable to identify the failure reason. The file deletion failure reason may file did not exist or wrong file path or the user does not have permission or some other reason.

The other drawback is that the [Java File class](https://www.tpointtech.com/java-file-class) does not support the symbolic links (also known as symlink or soft link), and the rename() method does not work consistently across the platform. In File I/O, we required more support for metadata that was poor in the File class. The metadata may include permissions, file owner, and security attributes.

The methods of the file class did not scale. The request of a large directory listing may cause the server in a hang. It may also cause memory resource problems that can lead to DoS (Denial of Service).

Therefore, the Java File class has so many drawbacks and there is no reason to use this class for new project development.

Oracle gives hint to use the Path class if we have the legacy code that uses the java.io.File class. It gives the advantage of the Path class with minimal impact on the code.

The Java File class provides the toPath() method to convert an old-style file into a java.nio.file.Path instance. For example:

[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)

1. Path input = file.toPath();  

It provides the advanced and rich features available in the Java Path class. Suppose, we want to delete a file:

[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)

1. file.delete();  

We can modify the above statement by using the delete() method of the Files class, as follows:

[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)[](https://www.tpointtech.com/java-path-vs-file#)

1. Path fp = file.toPath();  
2. Files.delete(fp);  

When we compare these two classes, we found that the **java.nio.file.Path is better than the java.io.File class.**

The Java Path class is better nevertheless java.io.File class is not deprecated in the new versions. The android framework still uses the File class for its basic file handling features.

## Mapping java.io.File Functionality to java.nio.file.Path

In Java SE 1.7 release, the file I/O architecture has been completely re-designed. We cannot swap one method for another method. If you are developing a new project related to file I/O and want to use rich functionality provided by java.nio.file package uses the toPath() method of the File class. It is ok to use the functionality of the Path class but if you are not satisfied and it does not fulfill your needs, you should rewrite the file I/O code.

The following table summarizes an overview of what functionality in the java.io.File API maps to the java.nio.file API.

|java.io.File Functionality|java.nio.file Functionality|Uses|
|---|---|---|
|java.io.File|java.nio.file.Path|It is used to specify the packages.|
|java.io.RandomAccessFile|The SeekableByteChannel functionality.|It is used if we want to randomly access a file.|
|File.canRead, canWrite, canExecute|Files.isReadable, Files.isWritable, and Files.isExecutable.  <br>On UNIX file systems, the Managing Metadata (File and File Store Attributes) package is used to check the nine file permissions.|It is used to check the permission granted to the file.|
|File.isDirectory(), File.isFile(), and File.length()|Files.isDirectory(Path, LinkOption...), Files.isRegularFile(Path, LinkOption...), and Files.size(Path)|It is used to retrieve the file's metadata.|
|File.lastModified() and File.setLastModified(long)|Files.getLastModifiedTime(Path, LinkOption...) and Files.setLastMOdifiedTime(Path, FileTime)|
|The File methods that set various attributes: setExecutable, setReadable, setReadOnly, setWritable|These methods are replaced by the Files method setAttribute(Path, String, Object, LinkOption...).|
|new File(parent, "newfile")|parent.resolve("newfile")|It performs the Path operations.|
|File.renameTo|Files.move|It is used to move a file to the directory.|
|File.delete|Files.delete|It is used to delete a file or directory.|
|File.createNewFile|Files.createFile|It is used to create new files.|
|File.deleteOnExit|Replaced by the DELETE_ON_CLOSE option specified in the createFile method.|
|File.createTempFile|Files.createTempFile(Path, String, FileAttributes<?>), Files.createTempFile(Path, String, String, FileAttributes<?>)|It creates a new file and also writes to the file by using the Stream I/O. Also performs reading and writing operations by using the Channel I/O.|
|File.exists|Files.exists and Files.notExists|It checks or verifies if the file exists or not.|
|File.compareTo and equals|Path.compareTo and equals|It is used to compare two paths.|
|File.getAbsolutePath and getAbsoluteFile|Path.toAbsolutePath|It converts the path|
|File.getCanonicalPath and getCanonicalFile|Path.toRealPath or normalize|It is used to normalize (remove redundancies) the path and also convert the path into a real path.|
|File.toURI|Path.toURI|It converts the path to the URI.|
|File.isHidden|Files.isHidden|It is used to retrieve information about the file.|
|File.list and listFiles|Path.newDirectoryStream|It is used to enlist the content of a directory.|
|File.mkdir and mkdirs|Files.createDirectory|It is used to create a directory.|
|File.listRoots|FileSystem.getRootDirectories|It is used to enlist the files of the system's root directory.|
|File.getTotalSpace, File.getFreeSpace, File.getUsableSpace|FileStore.getTotalSpace, FileStore.getUnallocatedSpace, FileStore.getUsableSpace, FileStore.getTotalSpace|It is used to store the file attributes.|

Some other comparisons are:

- The File class is more object-oriented than the Path class.
- Path API based I/O stream is less expensive than the File class, from the GC point of view.
- Often, the Path class throws the IOException and returns a Boolean value when any operation is done.