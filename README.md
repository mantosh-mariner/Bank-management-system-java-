# Bank-management-system-java-
# how to run in your system -
Download and Extract the Project:

Download the project ZIP file from the GitHub repository or use:
bash
Copy code
git clone https://github.com/your-username/your-repo-name.git
Replace your-username and your-repo-name with the actual details.
Extract the ZIP file if you downloaded it as a compressed file.
Open the Project in IntelliJ IDEA:

Launch IntelliJ IDEA.
Click on File > Open.
Navigate to the folder where you extracted the project and select it.
Click OK to open the project.
Add the MySQL Connector:

Download the MySQL Connector JAR if you don't have it.
In IntelliJ, go to File > Project Structure > Modules.
Select Dependencies.
Click on + and choose JARs or directories.
Locate and add the MySQL Connector JAR file.
Click Apply and OK.
Update the Database Configuration in Code:

Open the Java class (e.g., Bank.java).
Ensure the database connection details (DB_URL, USER, PASS) match your MySQL setup.
Create the Database and Tables in MySQL:

Open your MySQL client or MySQL Workbench.
Run the following SQL commands to set up the Bank database and tables:
sql
Copy code
CREATE DATABASE Bank;
USE Bank;

CREATE TABLE accountmaster (
  accno int NOT NULL AUTO_INCREMENT,
  name varchar(40) NOT NULL,
  address varchar(60) NOT NULL,
  date date NOT NULL,
  pan char(10) NOT NULL,
  phone varchar(20) DEFAULT NULL,
  email varchar(50) DEFAULT NULL,
  balance decimal(10,2) NOT NULL,
  PRIMARY KEY (accno)
) ENGINE=InnoDB AUTO_INCREMENT=1001 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE transaction (
  tid int NOT NULL AUTO_INCREMENT,
  accno int NOT NULL,
  date date NOT NULL,
  type varchar(20) NOT NULL,
  amount decimal(10,2) NOT NULL,
  balance decimal(10,2) NOT NULL,
  PRIMARY KEY (tid),
  KEY accno (accno),
  CONSTRAINT transaction_ibfk_1 FOREIGN KEY (accno) REFERENCES accountmaster (accno)
) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
Run the Project:

Click on Run > Run....
Select the Java class (e.g., Bank).
Ensure there are no errors and that the MySQL connector is in place.
The project should run, and output should display in the console.
Check Database Records:

Use these commands in your MySQL client to view the data:
sql
Copy code
SELECT * FROM accountmaster;
SELECT * FROM transaction;
By following these steps, you can set up and run the project successfully in IntelliJ IDEA
