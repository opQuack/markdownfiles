```java

import java.awt.*;

import javax.swing.JLabel;

import java.applet.Applet.*;

public class Applet1 extends Applet {
    Image p1, p2, p3;
    JLabel info1, info2, info3;
    private static final long serialVersionUID = 1L;
    public void init(){
        add(info1);
        add(info2);
        add(info3);
        info1.setBounds(10, 50, 50, 50);
        info2.setBounds(100, 50, 50, 50);
        info3.setBounds(200, 50, 50, 50);
        info1 = new JLabel("Smiling Face 1");
        info2 = new JLabel("Smiling Face 2");
        info3 = new JLabel("Smiling Face 3");
        p1 = getImage(getDocumentBase(), "smilingface1.jpg");
        p2 = getImage(getDocumentBase(), "smilingface2.jpg");
        p3 = getImage(getDocumentBase(), "smilingface3.jpg");
        p1.addActionListener(new ActionListener(){
            info1.setVisible(true);
            info2.setVisible(false);
            info3.setVisible(false);
        });
        p2.addActionListener(new ActionListener(){
            info1.setVisible(false);
            info2.setVisible(false);
            info3.setVisible(true);
        });
        p2.addActionListener(new ActionListener(){
            info1.setVisible(false);
            info2.setVisible(true);
            ino3.setVisible(false);
        });   
        setLayout(null);
    }

    public void paint(Graphics g){
        g.drawImage(p1,10, 10, this);
        g.drawImage(p2,10, 10, this);
        g.drawImage(p3,10, 10, this);
    }
}


```
