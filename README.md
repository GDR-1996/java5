学生选课系统
============================
关键词：方便，快捷，选课信息，选择，管理
============================
实验目的
============================
1分析学生选课系统

2使用GUI常规及其组件设计常规

3完成学生选课过程业务逻辑编程

4根据文件保存并读取数据

实验要求
============================
设计一个关于学生选课方便简捷的程序，从而达到学生能够快速的选到课程

1、设计GUI窗体，支持学生注册、课程新加、学生选课、学生退课、打印学生选课列表

2、基于事件模型对业务逻辑编程，实现在界面上支持上述操作

3、针对操作过程中可能会出现的各种异常，做异常处理

4、基于输入、输出编程，支持学生，课程，教师等数据的读写操作

5、基于Github.com提交实验，包括实验SRC源文件夹程序、README.MD实验报告文档

核心代码
==============================
主界面窗体选课信息
===================


     public class CourseF extends JFrame {

	private JPanel contentPane;
	private JTextField textField;
	private JTextField textField_1;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					CourseF frame = new CourseF();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

文件写入
======================
		JButton btnNewButton = new JButton("选课");
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String s ;
				String name = textField.getText();
				String	id  = textField_1.getText();
				String  c1  = comboBox.getSelectedItem().toString();
				String  c2  = comboBox_1.getSelectedItem().toString();
			   s = name + id + c1 + c2 ;
			   try {
		        	FileWriter writer = new FileWriter("F://JAVA.txt", true);
		        	writer.write(s);
		        	writer.flush();
		        	writer.close();
		        } catch (IOException e2) {
		            e2.printStackTrace();
		        }
				JOptionPane.showMessageDialog(null, "选课成功");
				
			}
		});
	
		

跳转
====================

		JButton btnNewButton_2 = new JButton("查询");
		btnNewButton_2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				CourseCx frame = new CourseCx();
				frame.setVisible(true);
			}
		});
		
	}
}


跳转页面当前选课信息
==============================

public class CourseCx extends JFrame {

	private JPanel contentPane;
	private JTextField textField;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					CourseCx frame = new CourseCx();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	
	
	
文件读取
===========
	
	try {
            BufferedReader bufferedReader =new BufferedReader(new FileReader("F://JAVA.txt"));
            String s1 =textField.getText();
            while(null !=(s1=bufferedReader.readLine())) {
            	
            	textField.setText(s1);
            
            }
        }catch (IOException e) {
            e.printStackTrace();
            	
        }
       
		JLabel label = new JLabel("当前选课信息");
		label.setBounds(10, 22, 97, 15);
		contentPane.add(label);
	}

}


流程图
========================
![t](https://github.com/GDR-1996/java5/blob/master/6.png)

结果图
========================
![s](https://github.com/GDR-1996/java5/blob/master/1.png)

![d](https://github.com/GDR-1996/java5/blob/master/2.png)

![f](https://github.com/GDR-1996/java5/blob/master/3.png)

![g](https://github.com/GDR-1996/java5/blob/master/4.png)

![h](https://github.com/GDR-1996/java5/blob/master/5.png)


实验感想
==========================
通过这几天的程序及报告编写，我也发现了自己的很多不足，自己知识的很多漏洞，看到了自己的实践经验还是比较缺乏，理论联系实际的能力还是比
较脆弱。尤其是编写大型的程序所要拥有的知识和技能比较缺乏。程序编好了，还要经过调试和修改，这步也很关键，好的程序是经过了无数次的修改和调试才
产生的。在同学的帮助下我的程序基本上能够满足要求，但还有一些地方需要改进，在今后我应该在多看书的同时还要加强实践的练习，才能进一步提高自己的
编程能力。







