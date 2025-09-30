/*
       =============================
        CREATE Database and schemas
       =============================
Script purpose:
   this script creates a new  database
   named 'DataWareHouse' after checking if it exsits.If the database exsits , it will drop an recreate.
  Additionally, the script sets up three schemas within the database :'bronze', 'silver','gold'.
 
 Warning:
  Running this script will drop the entire 'DataWareHouse' database if it exsits. 
  all data in the database will be permanently deleted. 
  proceed caution and ensure you have backups before running this script.
*/

USE master;
GO

-- Drop and recreate 'DataWareHouse'
IF exists (SELECT 1 FROM sys.databases WHERE name = 'DataWareHouse')
BEGIN
    ALTER DATABASE DataWareHouse set SINGLE_USER WITH ROLLBACK IMMEDIATE;
    DROP DATABASE DataWareHouse
END
GO

-- create database 'DataWareHouse'
CREATE DATABASE DataWareHouse;
GO

use DataWareHouse;
GO 

-- create schemas

--- create bronze schema 
CREATE SCHEMA bronze;
Go
--- create silver schema 
CREATE SCHEMA silver;
--- create gold schema 
Go
CREATE SCHEMA gold;


