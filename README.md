Imports:

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.text.SimpleDateFormat;
import java.util.Date;
These lines import necessary classes from Java's Swing library and other packages for handling dates and events.

Main Class:


public class SimpleDigitalClock {
The main class is named SimpleDigitalClock.

Main Method:

public static void main(String[] args) {
This is the starting point of the program.

GUI Setup:

SwingUtilities.invokeLater(() -> {
    JFrame frame = new JFrame("Digital Clock");
    JLabel timeLabel = new JLabel();
    timeLabel.setFont(new java.awt.Font("Arial", java.awt.Font.PLAIN, 24));
    frame.add(timeLabel);
SwingUtilities.invokeLater ensures that GUI components are handled on the event dispatch thread.
JFrame creates a window titled "Digital Clock".
JLabel creates a label to display the time.
setFont sets the font for the label.
Timer Setup:


    Timer timer = new Timer(1000, new ActionListener() {
        @Override
        public void actionPerformed(ActionEvent e) {
            updateTime(timeLabel);
        }
    });
    timer.start();
Timer triggers an event every 1000 milliseconds (1 second).
ActionListener specifies what to do when the timer event occurs.
updateTime updates the time on the label.
timer.start() starts the timer.
Frame Configuration:

java

    frame.setSize(200, 100);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setLocationRelativeTo(null);
    frame.setVisible(true);
setSize sets the dimensions of the window.
setDefaultCloseOperation closes the program when the window is closed.
setLocationRelativeTo centers the window on the screen.
setVisible makes the window visible.

Update Time Method:

private static void updateTime(JLabel timeLabel) {
    Date now = new Date();
    SimpleDateFormat dateFormat = new SimpleDateFormat("HH:mm:ss");
    timeLabel.setText(dateFormat.format(now));
}
updateTime method gets the current time and formats it as "HH:mm:ss".
The formatted time is set as the text of the label.

Closing Braces:

});
}
}
These lines close the main method and the main class.

That's it! This program creates a simple digital clock window that updates every second.
