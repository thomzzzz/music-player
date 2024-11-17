# Musical-World
Musical World is a web application that allows users to ulpoad their own songs listen to pre uploaded songs and also add their songs into their favorite list.
This project contains admin side as well as user side.
User has to first register at the portal before uploading songs.
The account verification mechanism has been included in the project to verify user authentication.

*create database named "project2" at back-end and import the code tables.sql file inside databse folder to get access to database*

Before running the application create a trigger and a procedure at back-end(xampp or wamp any application).

Code for triggers and procedure are given below.

****Trigger code****

*trigger to keep track of user contributions*
```mysql
CREATE TRIGGER `IncrementCount` AFTER INSERT ON `upload_albums`
 FOR EACH ROW update user set user.contributions = user.contributions + 1 where new.singer_id = user.user_id
 ```
 ****procedure code****
 
 *stored procedure to upload songs*
 ```mysql
 DELIMITER $$
CREATE DEFINER=`root`@`localhost` PROCEDURE `uploadsongs`(IN `singer_id` INT(11), IN `song_name` VARCHAR(255), IN `song_format` VARCHAR(255), IN `singer_name` VARCHAR(255), IN `song_image` VARCHAR(255), IN `audio_file` VARCHAR(255))
    NO SQL
INSERT INTO upload_albums(`singer_id`,`song_name`,`song_format`,`singer_name`,`song_image`,`audio_file`) VALUES(singer_id,song_name,song_format,singer_name,song_image,audio_file)$$
DELIMITER ;
```
```
Admin Panel Username and Password
username:admin@gmail.com
password:password
```
#  Note: do not forget to add your email credentials validate.php and activate_email.php file so as to send email notifications




