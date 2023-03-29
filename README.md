**Taxi/Rental-service**

Taxi/Rental-service web-application designed to manage cars and drivers in taxi service or renting cars business.
Application has registration/authentication, basic CRUD operations and use as storage MySQL database.

**Features**:
1. Registration/Authentication as driver;
2. Create/Add/Delete drivers;
3. Create/Add/Delete cars;
4. Create/Add/Delete manufacturer of car; 
5. Add/Delete drivers to specific cars;
6. Make reports about drivers, cars, manufacturers; 
7. Display detailed information about car and drivers who assigned for this car.

**Structure:**
taxi - root directory for project;
controller - package for HttpServlet controller each in separate folder: car, driver, manufacture;
dao - package for DAO interface for MySQL database;
exception - package for exceptions;
lib - package Injector class for creating objects;
model - package for entity models: Car, Driver, Manufacturer;
service - package for service interfaces;
util - package for credential to database;
web.filter - package for Filters;
webapp - package for JSP pages and css style;

**Technology**:
1. Java - JDK 11
2. Web server - Tomcat 9.0.58
3. Database - MySQL 8.0.32
4. Driver for DB - mysql-connector-java 8.0.32 
5. Java Servlet API - javax.servlet-api 4.0.1 
6. JSP Standard Tag Library - jstl 1.2

**Getting started**
Installation instruction:
1. Make new directory for Taxi/Rental-service application, for example taxi
2. In command line clone code from repository to taxi directory
   git@github.com:o-shyshkan/taxi-service.git
3. Open taxi project in your favorite IDE
4. In pom.xml file check actual version of these library:
   + mysql-connector-java 8.0.32 or higher
   + javax.servlet-api 4.0.1 or higher
   + jstl 1.2 or higher
   + jdk.version 11 or higher
5. Set up connection to your MySQL database in file [ConnectionUtil.java](src/main/java/taxi/util/ConnectionUtil.java)
   public class ConnectionUtil {
   private static final String URL = "jdbc:mysql://localhost:3306/taxi";
   private static final String USERNAME = "your name";
   private static final String PASSWORD = "your password";
6. Run SQL script [init_db.sql](src/main/resources/init_db.sql)to create database tables for application
7. In menu Run-Edit Configuration set up Run Configuration for Tomcat
You need Tomcat version 9.0.58 or higher
add artifacts taxi-service:war exploded
check that this artifact will be in deploy at the server start up
8. Run program 
9. Type in browser url your webserver with path /drivers/add
for example http://localhost:8080/drivers/add
10. Add driver with login and password
11. Make authentication on page /login with login and password
12. Get access for home page application with path /index
