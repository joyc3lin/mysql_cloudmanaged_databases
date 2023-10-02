# mysql_cloudmanaged_databases
HHA 504 assignment 4a

# MySQL Setup: 

## GCP

+ In [google cloud](https://cloud.google.com/), entered the individual project created under the AHI_GCP folder and selected SQP from the navigation menu on the left
+ Selected the create instance option, and chose MySQL as the database engine
+ Gave the new instance an ID and a password
+ The following steps were taken in order to lower the cost of the instance:
  + Switched Cloud SQL edition to 'Enterprise'
  + Under that, switched preset to 'Sandbox' in the dropdown menu
  + Switch zonal avaliability to 'single zone'
  + Clicked 'show configuration options' to further customzie the instance
  + In Machine Configuration: switched to 'shared core' in drop down menu
    + Selected '1 vCPU, 0.614 GB'
  + In Storage: selected '10 GB'
+ In order to allow inbound traffic from the world wide web:
  + In Connections: selected 'ADD A NETWORK'
  + Gave the connection a name: Allow All 
  + Set network to <code>0.0.0.0/0</code>
  + Click 'done'
+ Scrolled to the bottom and clicked 'Create Instance'
  
**Setting up in MySQL Workbench**

+ Created a new connection
+ Named the connection to indicate it was for GCP
+ Switched Hostname to the Public IP address provided in the created instance
+ Port: 3306
+ For Password, selected 'Store in Vault...' and pasted in password for the created instance
+ At the bottom, clicked 'Test Conenction' to ensure the workbench was connected to the GCP instance
+ Click 'OK' to create connection

## Azure

+ In [Microsoft Azure](https://portal.azure.com/#home), under azure services, selected 'Azure Database for MySQL servers'
+ clicked '+create'
+ Selected the Flexible server to create
+ In Basics: 
  + Selected 'Azure for Students' as the Subscription the individual resource group created
  + Named the server and selected 'for development or hobby projects' as workload type
  + For compute + storage: 'Burstable, B1ms'
  + created an admin username and password
+ In Networking:
  + Under firewall rules: selected '+add 0.0.0.0 - 255.255.255.255'
  + Clicked 'continue' for pop-up message
+ Created server

**Setting up in MySQL Workbench**

+ Created a new connection
+ Named the connection to indicate it was for GCP
+ Switched Hostname to the Server Name provided in the created instance
+ Port: 3306
+ For Username, made sure it matched the server admin login name created in the azure server
+ For Password, selected 'Store in Vault...' and pasted in password for the created server
+ At the bottom, clicked 'Test Conenction' to ensure the workbench was connected to the azure server
+ Click 'OK' to create connection

# MySQL Workbench Interaction

+  For both GCP and Azure:
+ in Query file: created a database named 'patients'
+ ran <code>use `patients`;</code> in order to create tables in the database
+ In an SQL file, created tabled with <code>CREATE TABLE</code>
  + Specific code can be found in their respective files: [GCP](https://github.com/joyc3lin/mysql_cloudmanaged_databases/blob/main/GCP/create.sql) , [Azure](https://github.com/joyc3lin/mysql_cloudmanaged_databases/blob/main/Azure/code.sql)

**To create ERD**

+ In workbench, under Database, selected Reverse Engineer Database
  + For stored Connection, selected the respective connection that is being used: [GCP](https://github.com/joyc3lin/mysql_cloudmanaged_databases/blob/main/GCP/Screenshot%202023-10-01%20225125.png) , [Azure](https://github.com/joyc3lin/mysql_cloudmanaged_databases/blob/main/Azure/Screenshot%202023-10-01%20225014.png)


# Errors/Challenges
