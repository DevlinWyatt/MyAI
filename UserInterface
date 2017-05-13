
package aiapplication;
/*
 *
 * @author Devlin Wyatt
 */
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.io.File;
import java.io.PrintWriter;
import java.util.Scanner;
import java.io.IOException;
import java.util.logging.Level;
import java.util.logging.Logger;

public class UserInterface extends JFrame {

    // Constants for set up of the note taking area
    public static final int WIDTH = 800; //Width of the JFrame
    public static final int HEIGHT = 150; //Height of the JFrame
    public static final int LINES = 1; //Lines in theText
    public static final int CHAR_PER_LINE = 30; //Chars in theText

    // Objects in GUI
    private JTextArea userText, aiText; // Text area to take notes
    private JMenuBar mBar;     // Horizontal menu bar
    private JPanel textPanel;  // Scrolling text area panel

    private JMenu fileMenu;   // Vertical menu for notes
    private JLabel studentMessage;

    //Objects i've made use of
    private JMenu langMenu; // Vertical menu for language
    //private JScrollPane scrolledText;   // Scroll bars

    public UserInterface() throws IOException {
        // Create a closeable JFrame with a specific size
        super("Simple AI");
        setSize(WIDTH, HEIGHT); //JFrame constructor
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //Closes JFrame

        // Get contentPane and set layout of the window
        Container contentPane = getContentPane();
        contentPane.setLayout(new BorderLayout());

        // Creates the vertical menus
        createFile();

        // Creates horizontal menu bar and
        // adds vertical menus to it
        mBar = new JMenuBar();
        mBar.add(fileMenu); // Notes menu bar

        setJMenuBar(mBar); //Implements the menu bar

        // Creates a panel to take notes on
        textPanel = new JPanel(); //creates the JPanel
        textPanel.setBackground(Color.gray); //Background colour

        userText = new JTextArea(LINES, CHAR_PER_LINE); //creates the text box
        userText.setBackground(Color.white); //Text box background colour

        JScrollPane scrolledText = new JScrollPane(userText);//Scroll bar object based off theText parameters
        textPanel.add(scrolledText); //adds scrolledText to the textPanel
        contentPane.add(textPanel, BorderLayout.WEST);
        setLayout(new FlowLayout(FlowLayout.LEFT));

        aiText = new JTextArea(LINES, CHAR_PER_LINE); //creates the text box
        aiText.setBackground(Color.LIGHT_GRAY); //Text box background colour
        JScrollPane scrolledText2 = new JScrollPane(aiText);//Scroll bar object based off theText parameters
        textPanel.add(scrolledText2); //adds scrolledText to the textPanel
        contentPane.add(textPanel, BorderLayout.EAST);

        JButton button1 = new JButton("Submit");
        button1.addActionListener(new MenuListener());
        add(button1, BorderLayout.SOUTH);
        userText.setText("This is a test.");
        studentMessage = new JLabel("Welcome to my AI program. \n\n"
                + "The program works best if you use small words and short statments.");

        add(studentMessage);

    }

    public void createFile() {
        fileMenu = new JMenu("File");
        JMenuItem item;

        item = new JMenuItem("Clear");
        item.addActionListener(new MenuListener());
        fileMenu.add(item);

        item = new JMenuItem("Exit");
        item.addActionListener(new MenuListener());
        fileMenu.add(item);
    }

    private class MenuListener implements ActionListener {

        public void actionPerformed(ActionEvent e) {
            String actionCommand = e.getActionCommand();
            if (actionCommand.equals("Clear")) {
                userText.setText("");
                aiText.setText("");

                StoreResults bla = new StoreResults();
                /*
                    Pressing the Submit button will pass the string in the user
                    text box to the Ai class. the Ai class results will be
                    printed into the Ai text box.
                 */
            } else if (actionCommand.equals("Exit")) {
                System.exit(0);
            } //Starting Language Menu
            else if (actionCommand.equals("French")) {

            } else if (actionCommand.equals("English")) {

            } else if (actionCommand.equals("Submit")) {
                StoreResults bla = new StoreResults();
                try {
                    aiText.setText(bla.UserString(userText.getText()));
                } catch (IOException ex) {
                    Logger.getLogger(UserInterface.class.getName()).log(Level.SEVERE, null, ex);
                }
            }
        }
    }

    public static void main(String[] args) throws IOException {

        UserInterface gui = new UserInterface(); //Creates a new NoteTaker Object named gui
        gui.setVisible(true); //Makes the gui visible
    }
}
