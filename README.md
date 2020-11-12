# trainapp-mockdb
  ###create new database
  
    create database trainapp_db;
    
  ###To use create database
  
    use trainapp_db;
    
  ###To create users table
    create table users(id int primary key auto_increment,
    name varchar(50), 
    email varchar(50),
    gender char (1),
    dob date,
    password varchar(20),
    role char(10),
    unique (email),
    check (gender in ('m','f'))
    );
 
  ###To insert values into users table
     insert into users(name,email,gender,dob,password,role) values('sai','s@gmail.com','f','1999-04-27','sai','admin');
     insert into users(name,email,gender,dob,password,role) values('abc','abc@gmail.com','m','2000-05-2','abc','user');
     insert into users(name,email,gender,dob,password,role) values('suresh','suresh@gmail.com','f','2010-12-08','suresh','user');
     
  ###Selecting all values 
     select * from users;
     
  ###login query
     select * from users where email='s@gmail.com' and password = 'sai';
     
  ###create trains table
     create table trains( trainnumber int not null,
     trainname varchar(50) not null,
     source char(40) not null,
     destination char(40) not null);
     
  ###Inserting values into trains table
     insert into trains(trainnumber,trainname,source,destination) values(1234,'vaigai','chennai','madurai');
     insert into trains(trainnumber,trainname,source,destination) values(4567,'nellai','trichy','chennai');
     insert into trains(trainnumber,trainname,source,destination) values(7864,'rajdhani','delhi','madurai');
     
  ###selecting values
     select * from trains
     
 ###search trains by source
    select * from trains where source='chennai';
    
 ###create table bookings
    create table bookings(ticketID bigint primary key auto_increment,
    name char(20),
    fromstation char(30) not null,
    tostation char(30) not null,
    journeydate date not null,
    travellers int not null,
    class varchar(20),
    bookeddate timestamp not null default current_timestamp,
    status boolean default 1 );
    
 ###insert values into the bookings table
    insert into bookings(name,fromstation,tostation,journeydate,travellers,class) values('sai','chennai','madurai','2020-12-2',3,'sleeper');
    insert into bookings(name,fromstation,tostation,journeydate,travellers,class) values('abc','trichy','madurai','2020-12-27',1,'AC');
    
 ###selecting values
    select * from bookings;
    
 ###altering bookings table
    alter table bookings add trainnumber varchar(50) not null;
    
 ###updating booking table values
    update bookings set trainnumber='4567' where ticketID in (1);
    
 ###To get the total number of bookings done
    select count(*) from bookings;
    
 ###TO select a particular user's booking
    select * from bookings where name='sai';

              
