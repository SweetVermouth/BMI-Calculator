-- Create the database
CREATE DATABASE BMICalculator;

-- Use the newly created database
USE BMICalculator;

-- Create the Users table
CREATE TABLE Users (
    UserID INT AUTO_INCREMENT PRIMARY KEY,
    Username VARCHAR(50) NOT NULL,
    PasswordHash VARCHAR(255) NOT NULL,
    Email VARCHAR(100) NOT NULL,
    DateOfBirth DATE,
    Gender ENUM('Male', 'Female', 'Other'),
    CreatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Create the BMIRecords table
CREATE TABLE BMIRecords (
    RecordID INT AUTO_INCREMENT PRIMARY KEY,
    UserID INT,
    Height DECIMAL(5,2) NOT NULL, -- Height in centimeters
    Weight DECIMAL(5,2) NOT NULL, -- Weight in kilograms
    BMIScore DECIMAL(5,2) GENERATED ALWAYS AS (Weight / (Height/100 * Height/100)) STORED,
    RecordedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (UserID) REFERENCES Users(UserID) ON DELETE CASCADE
);
