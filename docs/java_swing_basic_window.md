# Java swing base

```java
import java.awt.*;
import java.swing.*;

public class Window extends JFrame {
    private static final Dimension SCREEN_SIZE = java.awt.Toolkit.getDefaultToolkit().getScreenSize();
    private static final int SCREEN_HEIGHT = (int) SCREEN_SIZE.getHeight() / 2;
    private static final int SCREEN_WIDTH = (int) SCREEN_SIZE.getWidth() / 2;

    public Window() {
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        
        setVisible(true);
        setSize(SCREEN_WIDTH, SCREEN_HEIGHT);
    }
}
```
