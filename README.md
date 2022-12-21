
# RedShift connection with SQL

Amazon Redshift uses SQL to analyze structured and semi-structured data across data warehouses, operational databases, and data lakes using AWS-designed hardware and machine learning to deliver the best price-performance at any scale.


SQL Workbench/J is a free, DBMS-independent, cross-platform SQL query tool. While there are a number of systems supported by SQL Workbench, this guide will focus on connecting to your Amazon Redshift instance. 

Step-by-Step Guide

### Step 1: Install SQL Workbench 

```bash
https://www.sql-workbench.eu/
```

![image](https://user-images.githubusercontent.com/62830716/208801740-9ab25394-025b-47c4-9dbc-308408bf6cf1.png)


### Step 2: Download Driver 

Download the latest Amazon Redshift JDBC-compatible driver. This can be found here: https://docs.aws.amazon.com/redshift/latest/mgmt/jdbc20-download-driver.html

```bash
https://docs.aws.amazon.com/redshift/latest/mgmt/jdbc20-install-driver.html
```
### Step 3: Launch SQL Workbench

![image](https://user-images.githubusercontent.com/62830716/208801433-8fa23153-f865-4eb5-ab67-a97a4a2a50c9.png)



Open SQL Workbench and click ‘File’ from the toolbar and select ‘Connect window’ from the drop-down menu:

### Step 4: Create a Connection Profile

Click the leftmost icon in the toolbar to ‘Create a new connection profile

### Step 5: Select Redshift Drivers

Click the ‘Manage Drivers’ button in the lower left corner. Enter a name for the driver in the Name box and select ‘Amazon Redshift JDBC Driver’ from the list of drivers on the left.

![image](https://user-images.githubusercontent.com/62830716/208801578-cd64fd27-c618-494b-aab4-6d0fd21bf971.png)


### Step 6: Configure Database Connection Details

Replace ‘host’, ‘port’, and ‘name_of_database’ in the sample URL string provided with the hostname, port, and database name from the connection details provided by Openbridge when you created your Amazon Redshift instance.

At the end of the resulting URL string you will need to paste the following string to enable connection via SSL: 

```bash
?ssl=true&sslfactory=com.amazon.redshift.ssl.NonValidatingFactory
```

```bash
jdbc:postgresql://sample.redshift.openbridge.io:5439/sample_database?
```
![image](https://user-images.githubusercontent.com/62830716/208801612-6ff9187e-0c49-4355-b549-18d97ea3e746.png)

Enter the ‘Username’ and ‘Password’ values that you were provided in the connection details from Openbridge, check the ‘Autocommit’ box, and click ‘OK’.

### Step 7: Sample Test To Validate Connection
You can test your connection by running the following query in one of the ‘Statement’ tabs

![image](https://user-images.githubusercontent.com/62830716/208801802-3ba90865-d12b-4eb5-93ba-0ad6d4afe3b2.png)

```select * from information_schema.tables;```

If your connection is successful, you will see a list of tables in your database in the ‘Results’ tab
