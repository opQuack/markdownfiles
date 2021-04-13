```java

import java.awt.*;
import java.applet.*;

public class Applet2 extends Applet implements ActionListener{
    JLabel title, Team1, Team2, Players1, Players2, Players3;

    public void init(){
        title = new JLabel("IPL Teams");
        Team1 = new JLabel("Bangalore");
        Team2 = new JLabel("Mumbai");
        Team3 = new JLabel("Delhi");
        Players1 = new JLabel("1. PA\n2. PB\n2. PC\n2. PD\n2. PE\n2. PF\n2. PG");
        Players2 = new JLabel("1. PA\n2. PB\n2. PC\n2. PD\n2. PE\n2. PF\n2. PG");
        Players3 = new JLabel("1. PA\n2. PB\n2. PC\n2. PD\n2. PE\n2. PF\n2. PG");
        title.setBounds(10, 10, 100, 100);
        Team1.setBounds(100, 10, 100, 100);
        Team1.setBounds(300, 10, 100, 100);
        Team1.setBounds(500, 10, 100, 100);
        add(title);
        add(Team1);
        add(Team2);
        add(Team3);
        add(Players1);
        add(Players2);
        add(Players3);
    }

    public void paint(Graphics G){
        g.drawRectangle(0, 0, 100, 100);
        g.setColor(Color.GREEN);
        g.drawRectangle(0, 100, 100, 100);
        g.setColor(Color.RED);
        g.drawRectangle(0, 100, 200, 100);
        g.setColor(Color.BLUE);
        g.drawRectangle(0, 100, 300, 100);
        g.setColor(Color.ORANGE);
    }

}

```
