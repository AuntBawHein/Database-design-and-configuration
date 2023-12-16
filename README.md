# Database-design-and-configuration

The scope of this project is to design “Myanmar hospital database projects”.
The tools used are white online sketch board =>
PROBLEM STATEMENT/IDEA:
1.	To design and create ER diagram
2.	Automate the query and store procedures.
3.	Pencil and white paper to sketch my idea before implementation.
4.	Finally, test run each table to make that ER diagrams are in place.

Step 1: I’m going to create and define lots of objects here. 
These are all my objects. Hospitals, Doctor, Nurse, Medicine, Car and Motorcycle,. 
Step 2: I’m going to create lots of tables called Hospital, Patient, Doctor, Nurse, Medicine, Car and Motorcycle.

These are all tables I have created here.

CREATE TABLE Hospital (
    hospital_id INT PRIMARY KEY,
    hospital_name VARCHAR(100),
    hospital_building_color VARCHAR(100),
    hospital_type VARCHAR(100),
    hospital_total_people INT,
    hospital_payment_method VARCHAR(100),
    hospital_clothes VARCHAR(100),
    hospital_computer INT,
    hospital_cctv INT,
    hospital_sitting_chairs INT
);

-- Create a Patient table
CREATE TABLE Patient (
    patient_id INT PRIMARY KEY,
    patient_firstname VARCHAR(100),
    patient_middlename VARCHAR(100),
    patient_lastname VARCHAR(100),
    patient_age INT,
    patient_gender VARCHAR(100),
    patient_nationality VARCHAR(100),
    patient_email VARCHAR(100),
    patient_address VARCHAR(100),
    patient_mobile_ph VARCHAR(100),
    patient_blood_type VARCHAR(100)
);

-- Creating a Doctor table
CREATE TABLE Doctor (
    doctor_id INT PRIMARY KEY,
    doctor_firstname VARCHAR(100),
    doctor_middle_name VARCHAR(100),
    doctor_lastname VARCHAR(100),
    doctor_age INT,
    doctor_gender VARCHAR(100),
    doctor_nationality VARCHAR(100),
    doctor_email VARCHAR(100),
    doctor_address VARCHAR(100),
    doctor_date_of_interview DATE,
    doctor_working_experience INT,
    doctor_salaries DECIMAL (10, 2),
    patient_id INT,
    FOREIGN KEY (patient_id) REFERENCES Patient (patient_id)
);

-- Creating Nurse table
CREATE TABLE Nurse (
    nurse_id INT PRIMARY KEY,
    nurse_firstname VARCHAR(100),
    nurse_middlename VARCHAR(100),
    nurse_lastname VARCHAR(100),
    nurse_age INT,
    nurse_gender VARCHAR(100),
    nurse_nationality VARCHAR(100),
    nurse_email VARCHAR(100),
    nurse_address VARCHAR(100),
    nurse_date_of_interview DATE,
    nurse_working_experience INT,
    nurse_salaries DECIMAL (10, 2),
    patient_id INT,
    FOREIGN KEY (patient_id) REFERENCES Patient (patient_id)
);

-- Creating a Medicine table
CREATE TABLE Medicine (
    medicine_id INT PRIMARY KEY,
    medicine_name_type VARCHAR(100),
    medicine_color VARCHAR(100),
    medicine_manufactured_date DATE,
    medicine_expired_date DATE
);

-- Creating a Car table
CREATE TABLE Car (
    car_id INT PRIMARY KEY,
    car_owner_name VARCHAR(100),
    car_brand VARCHAR(100),
    car_color VARCHAR(100),
    car_og_country VARCHAR(100),
    car_price DECIMAL(10, 2),
    car_manufacturer_year INT,
    car_speed INT,
    car_seats INT,
    car_wheels INT,
    patient_id INT, -- Replace with the correct foreign key
    FOREIGN KEY (patient_id) REFERENCES Patient (patient_id)
);

-- Creating a Motorcycle table
CREATE TABLE Motorcycle (
    motorcycle_id INT PRIMARY KEY,
    motorcycle_owner_name VARCHAR(100),
    motorcycle_brand VARCHAR(100),
    motorcycle_color VARCHAR(100),
    motorcycle_og_country VARCHAR(100),
    motorcycle_price DECIMAL (10,2),
    motorcycle_manufacturer_year INT,
    motorcycle_speed INT,
    motorcycle_seats INT,
    motorcycle_wheels INT
);

Step 3: I’m going to insert data into Hospital, Patient, Doctor, Nurse, Medicine, Car and Motorcycle.
These are all data that I have insert here.

-- Insert data into Hospital table
INSERT INTO Hospital VALUES
(1, 'Yangon General Hospital', 'White', 'Public', 500, 'Credit Card', 'Scrubs', 10, 20, 100);

-- Insert data into Patient table
INSERT INTO Patient VALUES
(1, 'Aung', 'Mingalar', 'Myat', 30, 'Male', 'Myanmar', 'aung.myat@email.com', '123 Main St', '091-234-5678', 'A'),
(2, 'May', 'Hnin', 'Thiri', 25, 'Female', 'Myanmar', 'may.thiri@email.com', '456 Oak St', '098-765-4321', 'B'),
(3, 'Kyaw', 'Zaw', 'Htet', 40, 'Male', 'Myanmar', 'kyaw.htet@email.com', '789 Pine St', '076-543-2109', 'O');

-- Insert data into Doctor table
INSERT INTO Doctor VALUES
(1, 'Dr. Zaw', 'Myo', 'Tun', 35, 'Male', 'Myanmar', 'zaw.tun@email.com', '321 Elm St', '2022-01-01', 8, 120000, 1),
(2, 'Dr. Su', 'Mon', 'Lwin', 45, 'Female', 'Myanmar', 'su.lwin@email.com', '654 Birch St', '2022-02-01', 12, 150000, 2),
(3, 'Dr. Hla', 'Moe', 'Ko', 38, 'Male', 'Myanmar', 'hla.ko@email.com', '987 Cedar St', '2022-03-01', 10, 130000, 3);

-- Insert data into Nurse table
INSERT INTO Nurse VALUES
(1, 'Nurse Khin', 'Thandar', 'Win', 28, 'Female', 'Myanmar', 'khin.win@email.com', '456 Maple St', '2022-04-01', 5, 80000, 1),
(2, 'Nurse Mg', 'Aye', 'Kyaw', 32, 'Male', 'Myanmar', 'mg.kyaw@email.com', '789 Pine St', '2022-05-01', 7, 90000, 2),
(3, 'Nurse Su', 'Myat', 'Thu', 29, 'Female', 'Myanmar', 'su.thu@email.com', '123 Oak St', '2022-06-01', 6, 85000, 3);

-- Insert data into Medicine table
INSERT INTO Medicine VALUES
(1, 'Paracetamol', 'White', '2022-01-01', '2023-01-01'),
(2, 'Ibuprofen', 'Yellow', '2022-02-01', '2023-02-01'),
(3, 'Aspirin', 'Red', '2022-03-01', '2023-03-01');

-- Insert data into Car table
INSERT INTO Car VALUES
(1, 'Maung Myat', 'Toyota', 'Blue', 'Japan', 20000, 2022, 120, 5, 4, 1),
(2, 'May Myo', 'Honda', 'Red', 'Japan', 25000, 2021, 130, 5, 4, 2),
(3, 'Kyaw Htet', 'Ford', 'Black', 'USA', 18000, 2023, 110, 5, 4, 3);

-- Insert data into Motorcycle table
INSERT INTO Motorcycle VALUES
(1, 'Hla Win', 'Harley-Davidson', 'Black', 'USA', 30000, 2022, 150, 2, 2),
(2, 'Su Myat', 'Ducati', 'Yellow', 'Italy', 28000, 2021, 140, 2, 2),
(3, 'Kyaw Zaw', 'BMW', 'White', 'Germany', 32000, 2023, 160, 2, 2);


Questions:
1.	Why do we use Join statement here for no. 1? 
= We use JOIN to ensure that we have details about patients combine with a specific hospital.

Step 4: I’m going to join the table based on sql codes that I have done.
These are all codes

-	-1. Join Hospital with Patient
SELECT *
FROM Hospital
 JOIN Patient ON Hospital.hospital_id = Patient.patient_id;









2.	Why do we use Left Outer Join here for no. 2? 
= Because a Left Outer Join ensures we get all information from the "left" side (Medicine, Car, Motorcycle), even if there are no matching patients. 
These are all codes
-- Left Outer Join Doctor with Patient and Hospital
SELECT *
FROM Doctor
LEFT JOIN Patient ON Doctor.patient_id = Patient.patient_id
LEFT JOIN Hospital ON Patient.patient_id = Hospital.hospital_id;




3.	Why do we use Right Outer Join here? 
= Because a Right Outer Join ensures that we will get the information from the right side (Medicine, Car, Motorcycle).
These are all codes

-- Right Outer Join Nurse with Patient and Hospital.
SELECT *
FROM Nurse
RIGHT OUTER JOIN Patient ON Nurse.patient_id = Patient.patient_id
RIGHT OUTER JOIN Hospital ON Patient.patient_id = Hospital.hospital_id;




4.	Why do we use Left Outer Join for no.4? 
= Because a Left Outer Join ensures that we include all information from the "left" side (Medicine) will the match or combine the Patient table.
These are all codes.
-- Join Medicine with Patient
SELECT *
FROM Medicine
LEFT JOIN Patient ON Medicine.medicine_id = Patient.patient_id;


5.	Why do we use Full join for no.5? 
= Because a Full Join combines information from both tables (Car and Patient) , show all record from both sides.
These are all codes.
-- Join Car with Patient
SELECT *
FROM Car
FULL JOIN Patient ON Car.patient_id = Patient.patient_id;


Seperate Questions 
[seperate_questions_word_hospital_database_myanmar.docx](https://github.com/AuntBawHein/Database-design-and-configuration/files/13692063/seperate_questions_word_hospital_database_myanmar.docx)





6.	Why do we use only JOIN Statement here for no.6? 
= Because we want to join and see two tables of Motorcycle with Patient. 
These are all codes.
-- Join Motorcycle with Patient
SELECT *
FROM Motorcycle
JOIN Patient ON Motorcycle.motorcycle_id = Patient.patient_id;

Step 5: I want to make my own questions based on sql codes.
Questions: 
7.	Why do we have to create Myanmar Hospital table diagram? 
= Because creating a table diagram for the Hospital Myanmar database project is like drawing a map for our information. It helps everyone in the hospital team understand how different pieces of data connect or link, making it easier to find and use information about patients, doctors, medicines, and more.

8.	Why do we have to create Myanmar Hospital database projects? 
= Because creating Myanmar Hospital is like building a smart system to organize and manage the information. It helps doctors, nurses, and staff keep track of patients, their treatments, and the hospital's resources too.


Step 6: I want to show you my  table diagram of all objects and entities here.
= ![table_diagram_hospital_myanmar](https://github.com/AuntBawHein/Mini-IT-Firm-Database-Design/assets/150255399/5b1412e6-2118-4e17-a779-21adf8a33a05)


Step 7: I’m going to show you SQL myanmar_hospital_database_projects
[hospital_myanmar_database_projects_word.docx](https://github.com/AuntBawHein/Database-design-and-configuration/files/13692067/hospital_myanmar_database_projects_word.docx)
