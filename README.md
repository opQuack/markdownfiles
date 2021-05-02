# Table Creation Statements

```sql
CREATE TABLE User(
	UserID int PRIMARY KEY,
	UserName varchar(100) NOT NULL,
	EmailID varchar(100) NOT NULL,
	FirstName varchar(100) NOT NULL,
	LastName varchar(100) NOT NULL
);

CREATE TABLE Relation(
	User1ID int,
User2ID int,
Relation int,
FOREIGN KEY(User1ID) REFERENCES User(UserID),
FOREIGN KEY(User2ID) REFERENCES User(UserID)
);

CREATE TABLE Post(
	PostID int PRIMARY KEY,
	Time timestamp,
	Caption varchar(100),
	ImageURL varchar(100) NOT NULL,
	UserID int, 
FOREIGN KEY(UserID) REFERENCES User(UserID)
);

CREATE TABLE Likes(
	PostID int,
	UserID int,
FOREIGN KEY(PostID) REFERENCES Post(PostID),
FOREIGN KEY(UserID) REFERENCES User(UserID)
);

CREATE TABLE Comment(
	CommentID int PRIMARY KEY,
	Time timestamp,
	Content varchar(100),
	UserID int, 
	PostID int,
FOREIGN KEY(UserID) REFERENCES User(UserID),
FOREIGN KEY(PostID) REFERENCES Post(PostID)
);
```

# Table Insertion Commands
```sql
Insert into User values(1,'bvalder0','bvalder0@microsoft.com','Birch','Valder');
Insert into User values(2,'kthoumas1','kthoumas1@networkadvertising.org','Katy','Thoumas');
Insert into User values(3,'femptage2','femptage2@narod.ru','Frank','Emptage');
Insert into User values(4,'abrideaux3','abrideaux3@senate.gov','Alaster','Brideaux');
Insert into User values(5,'lgarrick4','lgarrick4@ameblo.jp','Layton','Garrick');
Insert into User values(6,'kmortimer5','kmortimer5@cpanel.net','Kylie','Mortimer');
Insert into User values(7,'dmedeway6','dmedeway6@bloomberg.com','Dorena','Medeway');
Insert into User values(8,'jshovelin7','jshovelin7@netlog.com','Julianne','Shovelin');
Insert into User values(9,'gstops8','gstops8@fastcompany.com','Giralda','Stops');
Insert into User values(10,'hkerrane9','hkerrane9@facebook.com','Haroun','Kerrane');
Insert into User values(11,'cskipa','cskipa@miitbeian.gov.cn','Carmelita','Skip');
Insert into User values(12,'kbrigstockb','kbrigstockb@spiegel.de','Katy','Brigstock');
Insert into User values(13,'locurneenc','locurneenc@networksolutions.com','Lyssa','OCurneen');
Insert into User values(14,'tcomollid','tcomollid@cisco.com','Tallia','Comolli');
Insert into User values(15,'gantonie','gantonie@e-recht24.de','Grissel','Antoni');
Insert into User values(16,'dbarnardof','dbarnardof@eepurl.com','Dannel','Barnardo');
Insert into User values(17,'kkubang','kkubang@csmonitor.com','Kile','Kuban');
Insert into User values(18,'lupstellh','lupstellh@homestead.com','Lelia','Upstell');
Insert into User values(19,'rmadgetti','rmadgetti@newsvine.com','Rickert','Madgett');
Insert into User values(20,'aheckj','aheckj@theguardian.com','Ashlin','Heck');


Insert into Relation values(13, 19, -1);
Insert into Relation values(15, 16, -1);
Insert into Relation values(15, 19, 1);
Insert into Relation values(1, 9, 1);
Insert into Relation values(5, 10, 1);
Insert into Relation values(4, 13, -1);
Insert into Relation values(11, 17, 1);
Insert into Relation values(17, 18, 1);
Insert into Relation values(3, 19, -1);
Insert into Relation values(3, 15, -1);
Insert into Relation values(11, 14, 1);
Insert into Relation values(9, 17, 1);
Insert into Relation values(3, 8, 1);
Insert into Relation values(4, 17, 1);
Insert into Relation values(1, 5, 1);
Insert into Relation values(12, 14, 1);
Insert into Relation values(4, 6, 1);
Insert into Relation values(2, 7, 1);
Insert into Relation values(1, 3, 1);
Insert into Relation values(11, 16, 1);
Insert into Relation values(13, 16, -1);
Insert into Relation values(5, 20, 1);
Insert into Relation values(5, 6, 1);
Insert into Relation values(3, 12, 1);
Insert into Relation values(3, 10, 1);
Insert into Relation values(2, 16, -1);
Insert into Relation values(1, 20, 1);
Insert into Relation values(16, 17, 1);
Insert into Relation values(5, 15, 1);
Insert into Relation values(1, 2, 1);

Insert into Post values(1,'2020-11-10 17:19:04','in','http://dummyimage.com/121x100.png/dddddd/000000', 1);
Insert into Post values(2,'2021-03-26 9:55:25','magna at','http://dummyimage.com/208x100.png/cc0000/ffffff', 2);
Insert into Post values(3,'2020-07-11 3:43:36','feugiat et','http://dummyimage.com/161x100.png/cc0000/ffffff', 2);
Insert into Post values(4,'2020-10-30 7:41:28','','http://dummyimage.com/126x100.png/5fa2dd/ffffff', 4);
Insert into Post values(5,'2020-07-27 19:04:05','tincidunt','http://dummyimage.com/173x100.png/5fa2dd/ffffff', 5);
Insert into Post values(6,'2021-03-11 7:30:12','et ultrices','http://dummyimage.com/137x100.png/ff4444/ffffff', 6);
Insert into Post values(7,'2020-05-21 21:19:12','diam in magna bibendum imperdiet','http://dummyimage.com/182x100.png/ff4444/ffffff', 6);
Insert into Post values(8,'2021-02-11 13:14:30','adipiscing lorem','http://dummyimage.com/229x100.png/5fa2dd/ffffff', 6);
Insert into Post values(9,'2021-03-22 12:31:22','ipsum primis in','http://dummyimage.com/149x100.png/ff4444/ffffff', 7);
Insert into Post values(10,'2020-05-17 5:04:22','sed sagittis nam congue risus','http://dummyimage.com/146x100.png/ff4444/ffffff', 8);
Insert into Post values(11,'2020-10-05 1:24:51','primis','http://dummyimage.com/165x100.png/cc0000/ffffff', 10);
Insert into Post values(12,'2021-01-09 9:49:47','lacinia','http://dummyimage.com/186x100.png/cc0000/ffffff', 13);
Insert into Post values(13,'2020-08-30 22:23:40','mi pede malesuada in imperdiet et','http://dummyimage.com/230x100.png/ff4444/ffffff', 13);
Insert into Post values(14,'2021-02-09 15:36:58','in faucibus orci luctus et ultrices','http://dummyimage.com/191x100.png/dddddd/000000', 14);
Insert into Post values(15,'2020-06-04 23:32:24','congue eget semper rutrum nulla nunc','http://dummyimage.com/238x100.png/5fa2dd/ffffff', 14);
Insert into Post values(16,'2020-07-18 12:01:24','amet cursus id turpis integer','http://dummyimage.com/224x100.png/5fa2dd/ffffff', 15);
Insert into Post values(17,'2021-02-12 23:30:10','amet diam in magna bibendum imperdiet','http://dummyimage.com/191x100.png/5fa2dd/ffffff', 15);
Insert into Post values(18,'2021-02-02 1:02:15','primis in','http://dummyimage.com/231x100.png/dddddd/000000', 16);
Insert into Post values(19,'2020-06-06 4:03:02','turpis nec','http://dummyimage.com/192x100.png/cc0000/ffffff', 19);
Insert into Post values(20,'2021-01-02 9:50:31','ullamcorper augue a','http://dummyimage.com/128x100.png/dddddd/000000', 20);

Insert into Likes values(1, 6);
Insert into Likes values(1, 9);
Insert into Likes values(2, 1);
Insert into Likes values(2, 14);
Insert into Likes values(3, 7);
Insert into Likes values(3, 9);
Insert into Likes values(4, 9);
Insert into Likes values(6, 13);
Insert into Likes values(6, 6);
Insert into Likes values(6, 10);
Insert into Likes values(7, 6);
Insert into Likes values(7, 13);
Insert into Likes values(8, 9);
Insert into Likes values(8, 20);
Insert into Likes values(9, 4);
Insert into Likes values(9, 7);
Insert into Likes values(9, 9);
Insert into Likes values(9, 16);
Insert into Likes values(12, 13);
Insert into Likes values(12, 15);
Insert into Likes values(13, 4);
Insert into Likes values(13, 18);
Insert into Likes values(14, 8);
Insert into Likes values(15, 12);
Insert into Likes values(15, 14);
Insert into Likes values(15, 20);
Insert into Likes values(17, 5);
Insert into Likes values(19, 10);
Insert into Likes values(19, 16);
Insert into Likes values(20, 3);

Insert into Comment values( 1 , '2020-05-19 13:23:43', 'Donec semper sapien a libero.', 3, 12);
Insert into Comment values( 2 , '2021-02-09 22:54:03', 'Vestibulum bibendum. Morbi non quam nec dui luctus rutrum.', 14, 1);
Insert into Comment values( 3 , '2020-05-20 9:58:36', 'Nulla facilisi. Cras non velit nec nisi vulputate nonummy.', 1, 2);
Insert into Comment values( 4 , '2021-02-27 12:01:15', 'Nulla tempus. Vivamus in felis eu sapien cursus vestibulum. Proin eu mi.', 1, 3);
Insert into Comment values( 5 , '2020-06-29 7:33:54', 'Cras in purus eu vestibulum sagittis sapien.', 4, 9);
Insert into Comment values( 6 , '2021-04-16 10:51:20', 'In hac habitasse platea dictumst eros.', 5, 19);
Insert into Comment values( 7 , '2021-02-01 20:10:48', 'Nulla pellentesque. Quisque porta volutpat erat.', 20, 20);
Insert into Comment values( 8 , '2020-09-17 0:33:18', 'Vestibulum orci luctus et ultrices posuere cubilia Curae; Nulla dapibus dolor vel est.', 7, 10);
Insert into Comment values( 9 , '2020-11-07 8:10:59', 'Integer ac leo. Pellentesque augue, a suscipit nulla elit ac nulla. Sed viverra dapibus.', 7, 15);
Insert into Comment values( 10 , '2020-05-22 15:43:59', 'Nunc interdum venenatis, turpis enim blandit mi, in porttitor pede justo eu massa.', 17, 19);
Insert into Comment values( 11 , '2021-01-25 11:25:48', 'Praesent blandit. Nam nulla. Suspendisse ornare consequat lectus.', 18, 3);
Insert into Comment values( 12 , '2020-08-16 20:41:24', 'In eleifend quam a odio. In lorem. Quisque ut erat.', 14, 16);
Insert into Comment values( 13 , '2021-01-18 7:07:21', 'Nulla ac enim. In tempor, turpis necaliquam convallis nunc.', 7, 15);
Insert into Comment values( 14 , '2020-11-15 22:55:56', 'Aliquam augue consectetuer eget, rutrum at, lorem. Integer tincidunt ante vel ipsum.', 16, 6);
Insert into Comment values( 15 , '2020-11-06 14:31:06', 'Mauri. Nullam sit amet turpis elementum ligula vehicula consequat. Morbi a ipsum. Integer a nibh.', 5, 4);
Insert into Comment values( 16 , '2020-08-19 10:56:38', 'Cras pellentesque volutpat dui. Maecenas tristique, est et tempus semper, est quam.', 4, 20);
Insert into Comment values( 17 , '2020-12-03 12:26:51', 'Aenean fermentum. Donec ut mauris nibh. Quisque id justo sit amet sapien dignissim vestibulum.', 16, 2);
Insert into Comment values( 18 , '2020-09-11 15:04:28', 'Donec ut dolor.', 17, 4);
Insert into Comment values( 19 , '2020-07-21 16:25:50', 'Integer non velit. Donec tortor Duis bibendum.', 5, 1);
Insert into Comment values( 20 , '2020-06-20 16:20:02', 'Aliquam Aliquam sed, tincidunt eu, felis. Fusce posuere felis sed lacus.', 7, 6);

```
