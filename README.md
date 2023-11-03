# 实验四 学生选实验4学生选课模拟系统之文件输入输出

# 实验目的
掌握文件输入输出；了解对象序列化方法。
# 业务要求
在实验三（学生选课模拟系统）的基础上，利用文件保存选课结果，
实现方法以下三选一：
1.采用自定义格式化方法写入文本文件，并从该文件中读取及解析。
2.Excel文件，基于POI或者JXL类库
3.对象序列化1)采用对象序列化的writeObject方法把选课结果存到硬盘文件系统中；
2)采用对象序列化的readObject方法从文件中恢复对象，并操作学生的选课课表，实现退课操作。
3)打印课程对象信息，采用覆盖定义toString（）方法的方式。
# 实验要求
提交源程序到gitee或github，代码仓库命名为“实验4学生选课模拟系统之文件输入输出”写实验报告文件（readme.md），
# 解题思路
1.本次实验通过对对象序列化Serializable接口的实现。
2.使用输出流构造ObjectOutputStream对象，然后用writeObject()方法将对象写入到文件中。
3.使用输入流构造ObjectInputStream对象，然后用readObject()方法读取文件内容。
4.通过把文件内容赋给新实例化对象，然后实现退课操作。
5.利用toString()方法并分别返回需要输出的信息。
# 流程图
![image](https://github.com/77ldh/experiment4-File-input-and-output-of-student-course-selection-simulation-system/assets/145440886/6b209983-b2ef-451c-b6d7-f1c5eed61c5c)

# 解题思路
1.使用输出流构造ObjectOutputStream对象，然后用writeObject()方法将对象写入到文件中。

FileOutputStream in = new FileOutputStream("C:\\Users\\70757\\Desktop\\shiyan6.txt");
ObjectOutputStream inin = new ObjectOutputStream(in);
inin.writeObject(liu);
inin.writeObject(zhao);

2.使用输入流构造ObjectInputStream对象，然后用readObject()方法读取文件内容。

FileInputStream out=new FileInputStream("C:\\Users\\70757\\Desktop\\shiyan6.txt");
ObjectInputStream otot = new ObjectInputStream(out);
try {
    sOut1= (Student)otot.readObject();
    sOut2= (Student)otot.readObject();
} catch (ClassNotFoundException e) {
    e.printStackTrace();
}
        
3.输出

System.out.println(sOut1.toString());
        for(int i = 0; i<sOut1.course.length; i++){
            System.out.println(sOut1.course[i].toString());
        }

        System.out.println("\n"+sOut2.toString());
        for(int i = 0; i<sOut2.course.length; i++){
            System.out.println(sOut2.course[i].toString());
        }

# 程序运行截图


![image](https://github.com/77ldh/experiment4-File-input-and-output-of-student-course-selection-simulation-system/assets/145440886/de113d1e-0867-4c18-8758-ea742bdfe0f4)


# 感想与体会

本次实验的内容学会了文件的输入和输出。我从实验中却受益匪浅，
通过本学期的实验课，我熟练掌握到代码的编写以及遇到不会的知识点和程序错误
从网络上和书本中寻找解决方法，提高了自己解决问题的能力,为我之后的解决类似问题奠定了基础。
