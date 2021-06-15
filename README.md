# GUI Game Programming with Java

<!-- ![]() -->
 This repository will act as a guide for you throughout the webinar.

## Materials for the Session

It doesn't matter if you join our webinar a little late or you prefer to do it at your own pace, we have you covered. In this repository, you'll find everything you need.

- Webinar youtube link
- Slide deck
- [Whatsapp group chat](http://bit.ly/STS-1-WA)
- [Polling during session](https://www.menti.com/)

> *You need to have a basic knowledge of Java language. If not, don't worry. Learn more about it [here](https://www.youtube.com/watch?v=gzoMqjwO6Wo).* 

## Participation Certificate

- To get the participation certificate, you will have to fill the feedback form which will be floated at end of the session.
- All the details in the Feedback form will be used for generating the certificates. So please check it before submitting. No consideration will be there afterwards.  

> ***Note:** The Registration of the participants will be validated before providing them with the certificates.*

## Table of Contents
- [General info](#general-info)
- [Installation of JDK and Eclipse IDE](#installation-of-jdk-and-eclipse-ide)
- [Introduction to GUI](#introduction-to-gui)
- [APIs in GUI](#apis-in-gui)
- [AWT v/s Swing](#awt-vs-swing)
- [What is Java Swing](#what-is-java-swing)
- [What is Component class](#what-is-component-class)
- [Methods of Component class](#methods-of-component-class)
- [What is Container class](#what-is-container-class)
- [Swing Components](#swing-components)
- [Tic Tac Toe Game Code](#tic-tac-toe-game-code)

## General info

## Installation of JDK and Eclipse IDE

- **Java Development Kit** (JDK) is a software development environment used for developing Java applications and applets. It includes the Java Runtime Environment (JRE), an interpreter/loader (Java), a compiler (javac), an archiver (jar), a documentation generator (Javadoc) and other tools needed in Java development.
- **Eclipse** is an open-source Integrated Development Environment (IDE) supported by IBM. The Eclipse platform can be used to develop rich client applications, integrated development environments and other tools. It is popular for Java application development and Android apps, but can be used as an IDE for any programming language for which a plug-in is available. Eclipse is cross-platform and runs under Windows, Linux and macOS. 364 companies reportedly use Eclipse in their tech stacks, including Accenture, ViaVarejo, and Zalando.  
We are going to use them to devlop our GUI game.
> To Download Standard Edition of JDK14 click [here](https://www.oracle.com/java/technologies/javase-jdk14-downloads.html#license-lightbox)  
> To Download Eclipse IDE 2021-03 click [here](https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2021-03/R/eclipse-inst-jre-win64.exe)

- _[Here is a video to help in downloading them](https://user-images.githubusercontent.com/85074532/122014794-2492d080-cddd-11eb-9595-672432b43686.mp4)_


[Back to table of contents](#table-of-contents)

## Introduction to GUI

GUI stands for Graphical User Interface, a term used not only in Java but in all programming languages that support the development of GUIs. A program's graphical user interface presents an easy-to-use visual display to the user. It is made up of graphical components (e.g., buttons, labels, windows) through which the user can interact with the page or application. GUI is a software platform that presents the back-end data visually to users. 

A GUI includes a range of user interface elements — which just means all the elements that display when you are working in an application. These can include:

- Input controls such as buttons, dropdown lists, checkboxes, and text fields.
- Informational elements such as labels, banners, icons, or notification dialogs.

[Back to table of contents](#table-of-contents)

## APIs in GUI
API stands for Application Program Interface, which has a set of routines and protocols that let your machines talk directly to other machines. An API is the brains of a GUI.

- **Java AWT:** AWT(Abstract Window Toolkit) is an API to develop GUI or window-based applications in java. Java AWT components are platform-dependent i.e., components are displayed according to the view of operating system. AWT is heavyweight i.e., its components are using the resources of OS.
- **Java Swing:** Swing in Java is a lightweight GUI toolkit which has a wide variety of widgets for building optimized window-based applications. It is a part of the JFC (Java Foundation Classes). It is built on top of the AWT API and entirely written in java. It is platform independent unlike AWT and has lightweight components.
- **Java FX:** JavaFX is a Java library used to develop Desktop applications as well as Rich Internet Applications (RIA). The applications built in JavaFX, can run on multiple platforms including Web, Mobile and Desktops.

[Back to table of contents](#table-of-contents)

## AWT v/s Swing

<table>
<thead>
	<tr>
		<td> <strong>No.</strong> </td>
		<td> <strong>Java AWT</strong> </td>
		<td> <strong>Java Swing</strong> </td>
	</tr>
</thead>
<tbody>
	<tr>
		<td> 1. </td>
		<td> AWT components are platform-dependent. </td>
		<td> Swing components are platform-independent. </td>
	</tr>
	<tr>
		<td> 2. </td>
		<td> AWT components are heavyweight </td>
		<td> Swing components are lightweight </td>
	</tr>
	<tr>
		<td> 3. </td>
		<td> AWT doesn't support pluggabe look and feel </td>
		<td> Swing supports pluggabe look and feel </td>
	</tr>
	<tr>
		<td> 4. </td>
		<td> AWT provides less components than Swing </td>
		<td> Swing providees more powerful components such as tables, lists, scrollpanes, colorchooser, tabbedpane etc. </td>
	</tr>
	<tr>
		<td> 5. </td>
		<td> AWT doesn't follow MVC(model view controller) where model represents data, view represents presentation, and controller act as an interface between model and view </td>
		<td> Swing follow MVC </td>
	</tr>
</tbody>
</table>

[Back to table of contents](#table-of-contents)

## What is Java Swing

Java Swing is a set of APIs that provides a graphical user interface (GUI) for the java programs. The Java Swing was developed based on earlier APIs called Abstract Windows Toolkit (AWT). The Java Swing provides richer and more sophisticated GUI components than AWT. The GUI components are ranging from a simple level to complex tree and table. The Java Swing provides the pluggable look and feels to allow look and feel of Java programs independent from the underlying platform.

- _Example code for Java Swing._
```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
// model part
class Model {
   private int x;
   public Model() {
      x = 0;
   }
   public Model(int x) {
      this.x = x;
   }
    public void setX(){
      x++;
   }
   public int getX() {
      return x;
   }
}
// view part
class View {
   private JFrame frame;
   private JLabel label;
   private JButton button;
   public View(String text) {
      frame = new JFrame("View");
      frame.getContentPane().setLayout(new BorderLayout());
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.setSize(200,200);
      frame.setVisible(true);
      label = new JLabel(text);
      frame.getContentPane().add(label, BorderLayout.CENTER);
      button = new JButton("Button");
      frame.getContentPane().add(button, BorderLayout.SOUTH);
   }
   public JButton getButton() {
      return button;
   }
   public void setText(String text) {
      label.setText(text);
   }
}
// controller part
class Controller {
   private Model model;
   private View view;
   private ActionListener actionListener;
   public Controller(Model model, View view) {
      this.model = model;
      this.view = view;
   }
   public void contol() {
      actionListener = new ActionListener() {
         public void actionPerformed(ActionEvent actionEvent) {
            linkBtnAndLabel();
         }
      };
      view.getButton().addActionListener(actionListener);
   }
   private void linkBtnAndLabel() {
      model.setX();
      view.setText(Integer.toString(model.getX()));
   }
}
// main class
public class SwingExample {
   public static void main(String[] args) {
      SwingUtilities.invokeLater(new Runnable() {
         @Override
         public void run() {
            try {
// Look and Feel, Java Look and Feel
               UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());
            } catch (Exception ex) { }
            Model model = new Model(0);
            View view = new View("-");
            Controller controller = new Controller(model,view);
            controller.contol();
         }
      });
   }
}
```

[Back to table of contents](#table-of-contents)

## What is Component class

A _component_ is an object having a graphical representation that can be displayed on the screen and that can interact with the user. Examples of components are the buttons, checkboxes, and scrollbars of a typical graphical user interface.

## Methods of Component class

The methods of Component class are widely used in java swing that are given below.

1.	**public void add(Component c)** - add a component on another component.
2.	**public void setSize(int width,int height)** - sets size of the component.
3.	**public void setLayout(LayoutManager m)** - sets the layout manager for the component.
4.	**public void setVisible(boolean b)** - sets the visibility of the component. It is by default false.

[Back to table of contents](#table-of-contents)

## What is Container class

A Container class can be described as a special component that can hold the gathering of the components. The important methods of the Container class are add(), invalidate() and validate().

[Back to table of contents](#table-of-contents)

## Swing Components
Swing components are the interactive elements in a Java application.

### JFrame
JFrame works like the main window where components like labels, buttons, textfields are added to create a GUI.

#### Constructor of JFrame are: 

1.	**JFrame()** - It constructs a new frame that is initially invisible.
2.	**JFrame(GraphicsConfiguration gc)** - It creates a Frame in the specified GraphicsConfiguration of a screen device and a blank title.
3.	**JFrame(String title)** - It creates a new, initially invisible Frame with the specified title.
4.	**JFrame(String title, GraphicsConfiguration gc)** - It creates a JFrame with the specified title and the specified GraphicsConfiguration of a screen device.

- _Example code for JFrame_
```java
import java.awt.FlowLayout;  
import javax.swing.JButton;  
import javax.swing.JFrame;  
import javax.swing.JLabel;  
import javax.swing.*;  
public class JFrameExample {  
    public static void main(String s[]) {  
        JFrame frame = new JFrame("JFrame Example");  
        JPanel panel = new JPanel();  
        panel.setLayout(new FlowLayout());  
        JLabel label = new JLabel("JFrame By Example");  
        JButton button = new JButton();  
        button.setText("Button");  
        panel.add(label);  
        panel.add(button);  
        frame.add(panel);  
        frame.setSize(200, 300);  
        frame.setLocationRelativeTo(null);  
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);  
        frame.setVisible(true);  
    }  
}
```
### JPanel
JPanel, a part of Java Swing package, is a container that can store a group of components. The main task of JPanel is to organize components, various layouts can be set in JPanel which provide better organisation of components, however it does not have a title bar.

#### Constructor of JPanel are: 
 
1.	**JPanel()** - creates a new panel with flow layout
2.	**JPanel(LayoutManager l)** - creates a new JPanel with specified layoutManager
3.	**JPanel(boolean isDoubleBuffered)** - creates a new JPanel with a specified buffering strategy
4.	**JPanel(LayoutManager l, boolean isDoubleBuffered)** - creates a new JPanel with specified layoutManager and a specified buffering strategy

- _Example code for JPanel_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JPanelExample extends JFrame {
 
    // JFrame
    static JFrame f;
 
    // JButton
    static JButton b, b1, b2;
 
    // label to display text
    static JLabel l;
 
    // main class
    public static void main(String[] args)
    {
        // create a new frame to store text field and button
        f = new JFrame("panel");
 
        // create a label to display text
        l = new JLabel("panel label");
 
        // create a new buttons
        b = new JButton("button1");
        b1 = new JButton("button2");
        b2 = new JButton("button3");
 
        // create a panel to add buttons
        JPanel p = new JPanel();
 
        // add buttons and textfield to panel
        p.add(b);
        p.add(b1);
        p.add(b2);
        p.add(l);
 
        // setbackground of panel
        p.setBackground(Color.CYAN);
 
        // add panel to frame
        f.add(p);
 
        // set the size of frame
        f.setSize(300, 300);
 
        f.show();
    }
}
```
### JButton
The JButton class is used to create a labeled button that has platform independent implementation. The application result in some action when the button is pushed. It inherits AbstractButton class.

#### Constructor of JButton are:

1.	**JButton()** - It creates a button with no text and icon.
2.	**JButton(String s)** - It creates a button with the specified text.
3.	**JButton(Icon i)** - It creates a button with the specified icon object.

- _Example code for JButton_
```java
import javax.swing.*;    
public class JButtonExample {  
public static void main(String[] args) {  
    JFrame f=new JFrame("Button Example");  
    JButton b=new JButton("Click Here");  
    b.setBounds(50,100,95,30);  
    f.add(b);  
    f.setSize(400,400);  
    f.setLayout(null);  
    f.setVisible(true);   
}  
}
```
### JLabel
JLabel is a class of java Swing . JLabel is used to display a short string or an image icon. JLabel can display text, image or both . JLabel is only a display of text or image and it cannot get focus . JLabel is inactive to input events such a mouse focus or keyboard focus. By default labels are vertically centered but the user can change the alignment of label.

#### Constructor of the class are: 
 
1.	**JLabel()** - creates a blank label with no text or image in it.
2.	**JLabel(String s)** - creates a new label with the string specified.
3.	**JLabel(Icon i)** - creates a new label with a image on it.
4.	**JLabel(String s, Icon i, int align)** - creates a new label with a string, an image and a specified horizontal alignment

- _Example code for Jlabel_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JLabelExample extends JFrame {
 
    // frame
    static JFrame f;
 
    // label to display text
    static JLabel l;
 
    // default constructor
    JLabelExample()
    {
    }
 
    // main class
    public static void main(String[] args)
    {
        // create a new frame to store text field and button
        f = new JFrame("label");
 
        // create a label to display text
        l = new JLabel();
 
        // add text to label
        l.setText("label text");
 
        // create a panel
        JPanel p = new JPanel();
 
        // add label to panel
        p.add(l);
 
        // add panel to frame
        f.add(p);
 
        // set the size of frame
        f.setSize(300, 300);
 
        f.show();
    }
}
```
### JRadioButton
The JRadioButton class is used to create a radio button. It is used to choose one option from multiple options. It is widely used in exam systems or quiz.

#### Constructors of JRadioButton are:

1.	**JRadioButton()** - Creates an unselected radio button with no text.
2.	**JRadioButton(String s)** - Creates an unselected radio button with specified text.
3.	**JRadioButton(String s, boolean selected)** - Creates a radio button with the specified text and selected status.

- _Example code for JRadioButton_
```java
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;
  
class Demo extends JFrame {
  
    // Declaration of object of JRadioButton class.
    JRadioButton jRadioButton1;
  
    // Declaration of object of JRadioButton class.
    JRadioButton jRadioButton2;
  
    // Declaration of object of JButton class.
    JButton jButton;
  
    // Declaration of object of ButtonGroup class.
    ButtonGroup G1;
  
    // Declaration of object of  JLabel  class.
    JLabel L1;
  
    // Constructor of Demo class.
    public Demo()
    {
  
        // Setting layout as null of JFrame.
        this.setLayout(null);
  
        // Initialization of object of "JRadioButton" class.
        jRadioButton1 = new JRadioButton();
  
        // Initialization of object of "JRadioButton" class.
        jRadioButton2 = new JRadioButton();
  
        // Initialization of object of "JButton" class.
        jButton = new JButton("Click");
  
        // Initialization of object of "ButtonGroup" class.
        G1 = new ButtonGroup();
  
        // Initialization of object of " JLabel" class.
        L1 = new JLabel("Qualification");
  
        // setText(...) function is used to set text of radio button.
        // Setting text of "jRadioButton2".
        jRadioButton1.setText("Under-Graduate");
  
        // Setting text of "jRadioButton4".
        jRadioButton2.setText("Graduate");
  
        // Setting Bounds of "jRadioButton2".
        jRadioButton1.setBounds(120, 30, 120, 50);
  
        // Setting Bounds of "jRadioButton4".
        jRadioButton2.setBounds(250, 30, 80, 50);
  
        // Setting Bounds of "jButton".
        jButton.setBounds(125, 90, 80, 30);
  
        // Setting Bounds of JLabel "L2".
        L1.setBounds(20, 30, 150, 50);
  
        // "this" keyword in java refers to current object.
        // Adding "jRadioButton2" on JFrame.
        this.add(jRadioButton1);
  
        // Adding "jRadioButton4" on JFrame.
        this.add(jRadioButton2);
  
        // Adding "jButton" on JFrame.
        this.add(jButton);
  
        // Adding JLabel "L2" on JFrame.
        this.add(L1);
  
        // Adding "jRadioButton1" and "jRadioButton3" in a Button Group "G2".
        G1.add(jRadioButton1);
        G1.add(jRadioButton2);
    }
}
  
class JRadioButtonExample {
    // Driver code.
    public static void main(String args[])
    { // Creating object of demo class.
        Demo f = new Demo();
  
        // Setting Bounds of JFrame.
        f.setBounds(100, 100, 400, 200);
  
        // Setting Title of frame.
        f.setTitle("RadioButtons");
  
        // Setting Visible status of frame as true.
        f.setVisible(true);
    }
}
```
### JTextField
JTextField is a part of javax.swing package. The class JTextField is a component that allows editing of a single line of text. JTextField inherits the JTextComponent class and uses the interface SwingConstants.

#### Constructors of JTextField are: 
 
1.	**JTextField()** - constructor that creates a new TextField
2.	**JTextField(int columns)** - constructor that creates a new empty TextField with specified number of columns.
3.	**JTextField(String text)** - constructor that creates a new empty text field initialized with the given string.
4.	**JTextField(String text, int columns)** - constructor that creates a new empty textField with the given string and a specified number of columns .
5.	**JTextField(Document doc, String text, int columns)** - constructor that creates a textfield that uses the given text storage model and the given number of columns.

- _Example code for JTextField_
```java
import java.awt.event.*;
import javax.swing.*;
class JTextFieldExample extends JFrame implements ActionListener {
    // JTextField
    static JTextField t;
 
    // JFrame
    static JFrame f;
 
    // JButton
    static JButton b;
 
    // label to display text
    static JLabel l;
 
    // default constructor
    JTextFieldExample()
    {
    }
 
    // main class
    public static void main(String[] args)
    {
        // create a new frame to store text field and button
        f = new JFrame("textfield");
 
        // create a label to display text
        l = new JLabel("nothing entered");
 
        // create a new button
        b = new JButton("submit");
 
        // create a object of the text class
        JTextFieldExample te = new JTextFieldExample();
 
        // addActionListener to button
        b.addActionListener(te);
 
        // create a object of JTextField with 16 columns
        t = new JTextField(16);
 
        // create a panel to add buttons and textfield
        JPanel p = new JPanel();
 
        // add buttons and textfield to panel
        p.add(t);
        p.add(b);
        p.add(l);
 
        // add panel to frame
        f.add(p);
 
        // set the size of frame
        f.setSize(300, 300);
 
        f.show();
    }
 
    // if the button is pressed
    public void actionPerformed(ActionEvent e)
    {
        String s = e.getActionCommand();
        if (s.equals("submit")) {
            // set the text of the label to the text of the field
            l.setText(t.getText());
 
            // set the text of field to blank
            t.setText("  ");
        }
     }
}
```
### JTextArea
JTextArea is a part of java Swing package . It represents a multi line area that displays text. It is used to edit the text .
JTextArea inherits JComponent class. The text in JTextArea can be set to different available fonts and can be appended to new text . A text area can be customized to the need of user .

#### Constructors of JTextArea are:

1.	**JTextArea()** - constructs a new blank text area .
2.	**JTextArea(String s)** - constructs a new text area with a given initial text.
3.	**JTextArea(int row, int column)** - constructs a new text area with a given number of rows and columns.
4.	**JTextArea(String s, int row, int column)** - constructs a new text area with a given number of rows and columns and a given initial text.

- _Example code for JTextArea_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JTextAreaExample extends JFrame implements ActionListener {
  
    // JFrame
    static JFrame f;
  
    // JButton
    static JButton b;
  
    // label to display text
    static JLabel l;
  
    // text area
    static JTextArea jt;
  
    // default constructor
    JTextAreaExample()
    {
    }
  
    // main class
    public static void main(String[] args)
    {
        // create a new frame to store text field and button
        f = new JFrame("textarea");
  
        // create a label to display text
        l = new JLabel("nothing entered");
  
        // create a new button
        b = new JButton("submit");
  
        // create a object of the text class
        JTextAreaExample te = new JTextAreaExample();
  
        // addActionListener to button
        b.addActionListener(te);
  
        // create a text area, specifying the rows and columns
        jt = new JTextArea(10, 10);
  
        JPanel p = new JPanel();
  
        // add the text area and button to panel
        p.add(jt);
        p.add(b);
        p.add(l);
  
        f.add(p);
        // set the size of frame
        f.setSize(300, 300);
  
        f.show();
    }
  
    // if the button is pressed
    public void actionPerformed(ActionEvent e)
    {
        String s = e.getActionCommand();
        if (s.equals("submit")) {
            // set the text of the label to the text of the field
            l.setText(jt.getText());
        }
    }
}
```
### JCheckBox
JCheckBox is a part of Java Swing package . JCheckBox can be selected or deselected . It displays it state to the user . JCheckBox is an implementation to checkbox . JCheckBox inherits JToggleButton class.

#### Constructor of the class are:

1.	**JCheckBox()** - creates a new checkbox with no text or icon
2.	**JCheckBox(Icon i)** - creates a new checkbox with the icon specified
3.	**JCheckBox(Icon icon, boolean s)** - creates a new checkbox with the icon specified and the boolean value specifies whether it is selected or not.
4.	**JCheckBox(String t)** - creates a new checkbox with the string specified
5.	**JCheckBox(String text, boolean selected)** - creates a new checkbox with the string specified and the boolean value specifies whether it is selected or not.
6.	**JCheckBox(String text, Icon icon)** - creates a new checkbox with the string and the icon specified.
7.	**JCheckBox(String text, Icon icon, boolean selected)** - creates a new checkbox with the string and the icon specified and the boolean value specifies whether it is selected or not.

- _Example code for JCheckBox_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JCheckBoxExample extends JFrame {
  
    // frame
    static JFrame f;
  
    // main class
    public static void main(String[] args)
    {
        // create a new frame
        f = new JFrame("frame");
  
        // set layout of frame
        f.setLayout(new FlowLayout());
  
        // create checkbox
        JCheckBox c1 = new JCheckBox("checkbox 1");
        JCheckBox c2 = new JCheckBox("checkbox 2");
  
        // create a new panel
        JPanel p = new JPanel();
  
        // add checkbox to panel
        p.add(c1);
        p.add(c2);
  
        // add panel to frame
        f.add(p);
  
        // set the size of frame
        f.setSize(300, 300);
  
        f.show();
    }
}
```
### JComboBox
JComboBox is a part of Java Swing package. JComboBox inherits JComponent class . JComboBox shows a popup menu that shows a list and the user can select a option from that specified list . JComboBox can be editable or read- only depending on the choice of the programmer.

#### Constructor of the JComboBox are: 
 
1.	**JComboBox()** - creates a new empty JComboBox .
2.	**JComboBox(ComboBoxModel M)** - creates a new JComboBox with items from specified ComboBoxModel
3.	**JComboBox(E \[ \] i)** - creates a new JComboBox with items from specified array.
4.	**JComboBox(Vector items)** - creates a new JComboBox with items from the specified vector

- _Example code for JComboBox_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JComboBoxExample extends JFrame implements ItemListener {
 
    // frame
    static JFrame f;
 
    // label
    static JLabel l, l1;
 
    // combobox
    static JComboBox c1;
 
    // main class
    public static void main(String[] args)
    {
        // create a new frame
        f = new JFrame("frame");
 
        // create a object
        JComboBoxExample s = new JComboBoxExample();
 
        // set layout of frame
        f.setLayout(new FlowLayout());
 
        // array of string containing cities
        String s1[] = { "Jalpaiguri", "Mumbai", "Noida", "Kolkata", "New Delhi" };
 
        // create checkbox
        c1 = new JComboBox(s1);
 
        // add ItemListener
        c1.addItemListener(s);
 
        // create labels
        l = new JLabel("select your city ");
        l1 = new JLabel("Jalpaiguri selected");
 
        // set color of text
        l.setForeground(Color.red);
        l1.setForeground(Color.blue);
 
        // create a new panel
        JPanel p = new JPanel();
 
        p.add(l);
 
        // add combobox to panel
        p.add(c1);
 
        p.add(l1);
 
        // add panel to frame
        f.add(p);
 
        // set the size of frame
        f.setSize(400, 300);
 
        f.show();
    }
    public void itemStateChanged(ItemEvent e)
    {
        // if the state combobox is changed
        if (e.getSource() == c1) {
 
            l1.setText(c1.getSelectedItem() + " selected");
        }
    }
}
```
### JDialog
JDialog is a part Java swing package. The main purpose of the dialog is to add components to it. JDialog can be customized according to user need .

#### Constructor of the class are: 
 
1.	**JDialog()** - creates an empty dialog without any title or any specified owner
2.	**JDialog(Frame o)** - creates an empty dialog with a specified frame as its owner
3.	**JDialog(Frame o, String s)** - creates an empty dialog with a specified frame as its owner 
and a specified title
4.	**JDialog(Window o)** - creates an empty dialog with a specified window as its owner
5.	**JDialog(Window o, String t)** - creates an empty dialog with a specified window as its owner and specified title.
6.	**JDialog(Dialog o)** - creates an empty dialog with a specified dialog as its owner
7.	**JDialog(Dialog o, String s)** - creates an empty dialog with a specified dialog as its owner and specified title.

- _Example code for JDialog_
```java
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
class JDialogExample extends JFrame implements ActionListener {
 
    // frame
    static JFrame f;
 
    // main class
    public static void main(String[] args)
    {
        // create a new frame
        f = new JFrame("frame");
 
        // create a object
        JDialogExample s = new JDialogExample();
 
        // create a panel
        JPanel p = new JPanel();
 
        JButton b = new JButton("click");
 
        // add actionlistener to button
        b.addActionListener(s);
 
        // add button to panel
        p.add(b);
 
        f.add(p);
 
        // set the size of frame
        f.setSize(400, 400);
 
        f.show();
    }
    public void actionPerformed(ActionEvent e)
    {
        String s = e.getActionCommand();
        if (s.equals("click")) {
            // create a dialog Box
            JDialog d = new JDialog(f, "dialog Box");
 
            // create a label
            JLabel l = new JLabel("this is a dialog box");
 
            d.add(l);
 
            // setsize of dialog
            d.setSize(100, 100);
 
            // set visibility of dialog
            d.setVisible(true);
        }
    }
}
```
[Back to table of contents](#table-of-contents)

## Tic Tac Toe Game Code

[Back to table of contents](#table-of-contents)

##  The End

> _**The repository will get updated during the session.**_
