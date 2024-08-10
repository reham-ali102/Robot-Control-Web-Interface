# Robot-Control-and-Command-Monitoring-Interface
# **Robot Control Web Interface**

This project is a web-based interface that allows users to control a robot's movement by sending directional commands. The commands are stored in a MySQL database for tracking and later retrieval. The web interface is built using HTML, CSS, JavaScript, and PHP.

## **Features**

- **Command Buttons**: The interface provides buttons for sending commands such as "Forward", "Backward", "Left", "Right", and "Stop".
- **Command Storage**: Every command sent through the interface is stored in a MySQL database.
- **Feedback**: After sending a command, a message is displayed to indicate the success or failure of the operation.

## **Project Structure**

```bash
robot_control/
├── index.html             # Main web interface for controlling the robot
├── send_command.php       # Backend script to process and store commands
├── get_last_five_values.php # Backend script to retrieve the last five commands (used in second task)
└── README.md              # This readme file
```

## **Setup Instructions**

### **1. Prerequisites**

- **XAMPP** or any other local server environment with Apache and MySQL support.
- Basic understanding of HTML, CSS, JavaScript, and PHP.

### **2. Database Setup**

1. Open **phpMyAdmin** (or your preferred database management tool).
2. Create a new database named `robot_control`.
3. Create a table named `robot_commands` using the following SQL query:

```sql
CREATE TABLE `robot_commands` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `command` varchar(255) NOT NULL,
  `timestamp` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
);
```
### **3. Project Setup**

1. Download or clone the repository into your local server’s root directory (e.g., `C:/xampp/htdocs/robot_control/`).

2. Place the project files (`index.html`, `send_command.php`, `get_last_five_values.php`) in the `robot_control` directory.

3. Ensure that your Apache server is running.

### **4. Running the Project**

1. Open your web browser.
2. Navigate to the control interface by entering the following URL:
   ```
   http://localhost/robot_control/index.html
   ```
3. Use the buttons on the interface to send directional commands to the robot.

### **5. File Descriptions**

- **index.html**: The main user interface where users can send commands to the robot. It includes buttons for each movement direction and displays feedback after a command is sent.
### image for interface
![Web Interface Screenshot](https://github.com/reham-ali102/Robot-Control-and-Command-Monitoring-Interface/blob/main/Interfase.PNG)
- **send_command.php**: This PHP script processes the command sent from the interface and stores it in the `robot_commands` table in the MySQL database.
### Image for database
![Database Table Structure](https://github.com/reham-ali102/Robot-Control-and-Command-Monitoring-Interface/blob/main/Database.PNG)

### **6. Customization**

- **Command Buttons**: You can easily modify the `index.html` file to add more commands or change existing ones.
- **Database**: The project currently stores commands as simple text in the `command` column of the `robot_commands` table. You can extend this by adding more columns to store additional data such as user IDs, command parameters, etc.

### **7. Troubleshooting**

- **404 Not Found**: Ensure that all files are correctly placed in the `htdocs` directory and that your URL is correctly pointing to `http://localhost/robot_control/index.html`.
- **CORS Issues**: Make sure you are accessing the HTML file via `http://localhost/...` and not directly from the file system (e.g., `file:///...`).
- **Database Connection Errors**: Verify your MySQL connection details in `send_command.php`. Ensure the MySQL service is running and the database credentials are correct.

### **8. Next Steps**

- **Enhancements**: Implement additional commands, add user authentication, or create a dashboard to display command history and analytics.
- **Integration**: Integrate this interface with actual robot hardware using appropriate APIs or communication protocols.

### **9. License**

This project is licensed under the MIT License. Feel free to use and modify it for your own projects.

E provides all the necessary information to set up, run, and customize the project. It should be sufficient for anyone with basic web development and server management knowledge to get started.
