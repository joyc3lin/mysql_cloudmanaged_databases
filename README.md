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
  + In Connections: select 'ADD A NETWORK'
  + Give the conenction a name
  + Set network to <code>0.0.0.0/0</code>
  + Click 'done'

## Azure


# MySQL Workbench Interaction

# Errors/Challenges
