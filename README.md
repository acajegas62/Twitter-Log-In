# Twitter-Log-In
A simple GUI project using awts 
import java.awt.*;
import java.awt.event.*;
/**
 *
 * @author acajegas62
 */
public class TwitterLogin extends Frame implements ActionListener {
    
    private Label usernameLabel, passwordLabel;
    private TextField usernameField, passwordField;
    private Button loginButton, createButton;
    
    public TwitterLogin() {
        super("Twitter Login");
        
        // set custom color
        Color customColor = new Color(29, 161, 242);
        this.setBackground(customColor);
        
        usernameLabel = new Label("Username:");
        passwordLabel = new Label("Password:");
        
        usernameField = new TextField(20);
        passwordField = new TextField(20);
        passwordField.setEchoChar('*');
        
        loginButton = new Button("Login");
        loginButton.addActionListener(this);
        
        createButton = new Button("Create Account");
        createButton.addActionListener(this);
        
        // set layout
        setLayout(new GridLayout(4, 2, 10, 10));
        
        // add components to frame
        add(usernameLabel);
        add(usernameField);
        add(passwordLabel);
        add(passwordField);
        add(new Label());
        add(loginButton);
        add(new Label());
        add(createButton);
        
        // set frame size and visibility
        setSize(300, 200);
        setVisible(true);
    }
    
    @Override
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == loginButton) {
            String username = usernameField.getText();
            String password = passwordField.getText();
            
            // code to log in to Twitter with given username and password
            // For example, you can use a Twitter API library like Twitter4j to authenticate the user
            
            // clear fields
            usernameField.setText("");
            passwordField.setText("");
            
            // show welcome message
        WelcomePage welcomePage = new WelcomePage();
        this.dispose();
        }
        
        if (e.getSource() == createButton) {
            CreateAccount createAccount = new CreateAccount();
        }
    }
    
    public class CreateAccount extends Frame implements ActionListener {
    
    private Label nameLabel, emailLabel, passwordLabel;
    private TextField nameField, emailField, passwordField;
    private Button createButton, cancelButton;
    
    public CreateAccount() {
        super("Create New Account");
        
        // set custom color
        Color customColor = new Color(29, 161, 242);
        this.setBackground(customColor);
        
        nameLabel = new Label("Name:");
        emailLabel = new Label("Email:");
        passwordLabel = new Label("Password:");
        
        nameField = new TextField(20);
        emailField = new TextField(20);
        passwordField = new TextField(20);
        passwordField.setEchoChar('*');
        
        createButton = new Button("Create Account");
        createButton.addActionListener(this);
        
        cancelButton = new Button("Cancel");
        cancelButton.addActionListener(this);
        
        // set layout
        setLayout(new GridLayout(5, 2, 10, 10));
        
        // add components to frame
        add(nameLabel);
        add(nameField);
        add(emailLabel);
        add(emailField);
        add(passwordLabel);
        add(passwordField);
        add(new Label());
        add(createButton);
        add(new Label());
        add(cancelButton);
        
        // set frame size and visibility
        setSize(300, 200);
        setVisible(true);
    }
    
    public void actionPerformed(ActionEvent e) {
    if (e.getSource() == createButton) {
        String name = nameField.getText();
        String email = emailField.getText();
        String password = passwordField.getText();
        
        // code to create a new Twitter account with given name, email and password
        // For example, you can use a Twitter API library like Twitter4j to create a new account
        
        // clear fields
        nameField.setText("");
        emailField.setText("");
        passwordField.setText("");
        
        // open welcome page
        WelcomePage welcomePage = new WelcomePage();
        this.dispose(); // dispose of the create account frame
    }
    
    if (e.getSource() == cancelButton) {
        this.dispose();
    }
}
}
    public class WelcomePage extends Frame {
    
    private Label welcomeLabel;
    
    public WelcomePage() {
        super("Welcome to Twitter");
        
        // set custom color
        Color customColor = new Color(29, 161, 242);
        this.setBackground(customColor);
        
        welcomeLabel = new Label("Welcome to Twitter!");
        
        // set layout
        setLayout(new BorderLayout());
        
        // add components to frame
        add(welcomeLabel, BorderLayout.CENTER);
        
        // set frame size and visibility
        setSize(300, 200);
        setVisible(true);
        
    }   
}

    public static void main(String[] args) {
        TwitterLogin twitterLogin = new TwitterLogin();
    }
}
