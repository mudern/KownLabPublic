# Java学习-[[Scanner类]]

标签（空格分隔）： #Java

---

java.util.Scanner是Java5后增添的新特征，可以通过其获取用户输入。创建Scanner对象的基本语法：

    Scanner s = new Scanner(System.in);

下面是一个应用Scanner类解决数据输入问题的模板，通过Scanner类的next()nextLine()方法来获取输入字符串，在读取前需要使用hasNext与hasNextLine()判断是否还有输入数据。

### next方法###

    import java.util.Scanner; 
     
    public class ScannerDemo {
        public static void main(String[] args) {
            Scanner scan = new Scanner(System.in);
            // 从键盘接收数据
     
            // next方式接收字符串
            System.out.println("next方式接收：");
            // 判断是否还有输入
            if (scan.hasNext()) {
                String str1 = scan.next();
                System.out.println("输入的数据为：" + str1);
            }
            scan.close();
        }
    }

### nextLine方法###


    import java.util.Scanner;
     
    public class ScannerDemo {
        public static void main(String[] args) {
            Scanner scan = new Scanner(System.in);
            // 从键盘接收数据
     
            // nextLine方式接收字符串
            System.out.println("nextLine方式接收：");
            // 判断是否还有输入
            if (scan.hasNextLine()) {
                String str2 = scan.nextLine();
                System.out.println("输入的数据为：" + str2);
            }
            scan.close();
        }
    }

### next()与nextLine()区别

next():
 - 只有读到有效字符后才可结束输入
 - 输入有效字符前遇到的空白，next()会自动将其去掉。
 - 只有输入有效字符后才将其后面的输入的空白作为分隔符或者结束符。
 - next不能获得带有空格的字符串。

 nextLine():
  - 以Enter作为结束符，返回Enter前所有字符
  - 可以获得空白

int与flot类型数据，Scanner类中也有支持，输入前最好使用hasNext相关方法验证。

想要持续获得输入，应使用while方法

