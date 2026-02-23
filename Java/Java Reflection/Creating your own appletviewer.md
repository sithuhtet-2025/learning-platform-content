As you know well that appletviewer tool creates a frame and displays the output of applet in the frame.You can also create your frame and display the applet output.

### Example that works like appletviewer tool

Let's see the simple example that works like appletviewer tool. This example displays applet on the frame.

[](https://www.tpointtech.com/creating-appletviewer-tool#)[](https://www.tpointtech.com/creating-appletviewer-tool#)[](https://www.tpointtech.com/creating-appletviewer-tool#)

1. import java.applet.Applet;  
2. import java.awt.Frame;  
3. import java.awt.Graphics;  

4. public class MyViewer extends Frame{  
5.   public static void main(String[] args) throws Exception{  
6.     Class c=Class.forName(args[0]);  

7.     MyViewer v=new MyViewer();  
8.     v.setSize(400,400);  
9.     v.setLayout(null);  
10.     v.setVisible(true);  

11.     Applet a=(Applet)c.newInstance();  
12.     a.start();  
13.     Graphics g=v.getGraphics();  
14.     a.paint(g);  
15.     a.stop();  

16.   }  

17. }  

[](https://www.tpointtech.com/creating-appletviewer-tool#)[](https://www.tpointtech.com/creating-appletviewer-tool#)[](https://www.tpointtech.com/creating-appletviewer-tool#)

1. //simple program of applet  

2. import java.applet.Applet;  
3. import java.awt.Graphics;  

4. public class First extends Applet{  

5.     public void paint(Graphics g){g.drawString("Welcome",50, 50);}  
6. }  

### Output:

![Example that works like appletviewer tool](https://images.tpointtech.com/images/myviewer1.JPG) ![Example that works like appletviewer tool](https://images.tpointtech.com/images/myviewer2.JPG)