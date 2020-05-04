# mysql-on-docker

Setup mysql on docker container along with docker volumes(for persistence).

Prerequisite:

    * Docker installed on your machine/VM


Steps:

1) Clone the project:

    * git clone https://github.com/mosesalphonse/mysql-on-docker.git
    
2) Run Docker Compose

    * docker-compose.yml up -d
    
3) Login into MySQL and very default schema and tables;
    
    a) Login as Root User using terminal: (Refer docker-compose.yml file for password)
    
        * docker exec -it mysql-on-docker_db_1 mysql -uroot -p
        
    b) Login as normal user using terminal  :(Refer docker-compose.yml file for password)
    
        * docker exec -it mysql-on-docker_db_1 mysql -uuser -p

4) To verify Volumes, you may create some database, tables and insert some records, then you may kill docker and bring up again, make sure your data should be available after spin up your MYSQL container again;

    you may refer the below script to create some table and its values;
    
    
    * create database db1;

    * use db1;

    * CREATE TABLE emp(  
        emp_id INT NOT NULL AUTO_INCREMENT,  
        emp_firstname VARCHAR(100) NOT NULL,  
        emp_surname VARCHAR(100) NOT NULL,  
        PRIMARY KEY ( emp_id )  
    );  

    * insert into emp(emp_firstname, emp_surname) values('user1','A');
    * insert into emp(emp_firstname, emp_surname) values('user2','B');
