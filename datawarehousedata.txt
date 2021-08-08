create database companyDW;
use  companyDW;
create table dimemp(
 empId int identity(100,1) primary key,
 empName varchar(50) not null,
 gender varchar(10),
 hiredate date not null,
 mailId varchar(50),
 contactNum varchar(10),
 city varchar(50),
 stateName varchar(50),
 country varchar(50)
);

create table dimposition(
positionId int identity(1000,1) primary key,
positionName varchar(50),
);
create table dimlocation(
locationId int identity(10,2) primary key,
locationName varchar(50)
);
create table dimreportingManager(
managerId int identity primary key,
managerName varchar(50),
contact varchar(10),
mailId varchar(50)
);
create table dimdatetime(
date_time_key int identity(50,2) primary key,
workingDate date ,
day_name varchar(10),
starttime time,
endtime time,
daysOff int,
extrahours int,
);
create table dimdepartment(
departmentId int identity primary key,
departmentName varchar(50)
);
create table dimfact(
factId int identity(2,2) primary key,
empId int  foreign key references dimemp(empId),
positionId int  foreign key references dimposition(positionId),
managerId int  foreign key references dimreportingManager(managerId),
departmentId int  foreign key references dimdepartment(departmentId),
locationId int  foreign key references dimlocation(locationId),
timekey int  foreign key references dimdatetime(date_time_key),
anualsalary int,
quartersalary int,
medianworkinghoursinday int,
medianworkingdaysinmonth int,
medianworkingdaysinyear int,
emp_status varchar(50),
employee_experience varchar(50),
Emp_performance_Q1 varchar(50),
Emp_performance_Q2 varchar(50)
);