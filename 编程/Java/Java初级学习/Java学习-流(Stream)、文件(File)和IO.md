 Java学习-流(Stream)、文件(File)和IO 

标签（空格分隔）： #Java

---

Java.io包几乎包含了所有操作输入输出需要的类。这些流类代表了输入源和输出源目标。Java.io包中的流支持多种格式。流可以理解为一个数据序列。输入流表示从一个源读取数据，输出流表示向一个目标写数据。Java为I/O提供了强大而灵活的支持，使其更广泛的应用到文件传输和网络编程中。

### 读取控制台输入 ###
Java的控制台输入有System.in完成。
为了获得一个绑定到控制台的字符流，可以把System.in包装在一个BufferedReader对象中来创建一个字符流。
下面是创建BufferedReader的基本语法：

    BufferedReader br = new BufferedReader(new 
                          InputStreamReader(System.in));

BufferedReader对象被创建后，我们便可以用read()方法从控制台读取一个字符，或者用readLine()方法读取一个字符串。

### 从控制台读取多字符输入 ###

从BufferedReader对象读取一个字符要使用read()方法，其语法如下：
int read() throws IOException
每次调用read()方法，他从输入流中读取一个字符并把该字符作为整数值返回。当流结束时返回-1该方法抛出IOException。下面程序示范了用read()方法从控制台不断读取字符直至用户输入q。

    import java.io.*;
     
    public class BRRead {
        public static void main(String[] args) throws IOException {
            char c;
            // 使用 System.in 创建 BufferedReader
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            System.out.println("输入字符, 按下 'q' 键退出。");
            // 读取字符
            do {
                c = (char) br.read();
                System.out.println(c);
            } while (c != 'q');
        }
    }

### 控制台输出 ###

在此前已经介绍过，控制台的输出有print()和println()完成。这些方法都由类PrintStream定义，System.out是对该类对象的一个引用。
PrintStream继承了OutputStream类，并实现了方法write()。这样，write()也可以用来往控制台写操作。
PrintStream定义write()的最简单格式如下所示：

    void write(int byteval)

该方法将byteval的低八位字节写到流中。

### 读写文件 ###

如前所述，一个流被定义为一个数据序列。输入流用于从源读取数据，输出流用于向目标写入数据。
输入输出流的类层次图：
![输入输出流的类层次图][1]

### [[FileInputStream与FileOutputStream类]] ###

FileInputStream用于读写文件，其对象可以用关键字new来创建。有多种方法可以用于创建对象。
可以使用字符串类型的文件名来创建一个输入流对象来读取文件：

    InputStream f = new FileInputStream("C:/java/hello");

也可以使用一个文件对象来创建以恶搞输入流对象来读取文件。首先使用File()方法来创建一个文件对象：

    File f = new File("C:/java/hello");
    InputStream in = new FileInputStream(f);

创建了InputStream对象，就可以使用下面的方法读取流或者进行其他流操作。

1.public void close() throw IOException{}
关闭此文件输入流并释放与此流有关的所有系统资源。抛出IOException异常。
2.protected viod finalize() throws IOException{}
这个方法清除与该文件的连接。确保在不再引用文件输入流时调用其close方法。抛出IOException异常。
3.public int read(int r) throws IOException{}
这个方法从InputStream对象读取指定字节的数据。返回为整数值。返回下一字节数据，如果已经返回到结尾则返回-1。
4.public int read(byte[] r) throws IOException{}
这个方法从输入流读取r.length长度的字节。返回读取的字节数。如果是文件结尾则返回-1。
5.public int available() throws IOException{}
返回下一次对此输入流调用的方法可以不受阻塞地从此输入流中读取的字节数。返回一个整数值。

FileOutputStream用于创建一个文件并向文件中写入数据。
如果该流在打开文件进行输出前，目标文件不存在，那么该流则会先创建该文件。一般有两种构造方法可以用来创建FileOutputStream对象。
使用字符串类型的文件名来创建一个输出流对象：

    OutputStream f = new FileOutputStream("C:/java/hello")

也可以使用一个文件对象来创建一个输出流来写入文件。首先使用File()方法来创建一个文件对象：

    File f = new File("C:/java/hello");
    OutputStream fOut = new FileOutputStream(f);

创建OutputStream对象完成后，就可以使用下面的方法来写入流或者进行其他的流操作。
1.public void close() throws IOException{}
关闭此文件输入流并释放与此流有关的所有系统资源。抛出IOException异常。
2.protected void finalize() throw IOException{}
这个方法清除与该文件的连接。确保在不再引用文件输入流时调用其close方法。抛出IOException异常。
3.public void write(int w) throws IOException{}
这个方法把指定的字节写到输出流中。
4.public void write(byte[] w)
把指定数组中w.length长度的字节写入到OutputStream中。

### 文件和I/O ###
一些关于文件和I/O的类。

 - File Class
 - FileReader Class
 - FileWriter Class

### Java中的目录 ###
创建目录：
File类中有两个方法可以用于创建文件夹：

 - mkdir()方法创建一个文件夹，成功则返回true，失败则返回false。失败表明File对象指定的路径已经存在，或者由于整个路径还不存在，该文件夹不能被创建。
 - mkdirs()方法船舰一个文件夹和它所有的父文件夹。
Java在Unix和Windows自动按约定分辨文件路径分隔符。

### 读取目录 ###
一个目录其实就是一个File对象，他包含其他文件和文件夹。
如果创建一个File对象并且他是一个目录，那么调用isDirectory()方法会返回true。可以通过调用该对象上的list()方法，来提取他包含的文件和文件夹的列表。

### 删除目录或文件 ###
删除文件可以使用java.io.File.delete()方法。
一下代码会删除目录/tmp/java/，需要注意的是当删除某一目录时，必须保证该目录下没有其他文件才能正确删除，否则将删除失败。

实例：

    import java.io.File;
     
    public class DeleteFileDemo {
        public static void main(String[] args) {
            // 这里修改为自己的测试目录
            File folder = new File("/tmp/java/");
            deleteFolder(folder);
        }
     
        // 删除文件及目录
        public static void deleteFolder(File folder) {
            File[] files = folder.listFiles();
            if (files != null) {
                for (File f : files) {
                    if (f.isDirectory()) {
                        deleteFolder(f);
                    } else {
                        f.delete();
                    }
                }
            }
            folder.delete();
        }
    }



  [1]: https://www.runoob.com/wp-content/uploads/2013/12/iostream2xx.png
