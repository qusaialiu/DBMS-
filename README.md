CREATE TABLE Employees (
    EMID INT PRIMARY KEY,
    Person-Name VARCHAR(255) NOT NULL,
    Street VARCHAR(255) NOT NULL,
    City VARCHAR(255) NOT NULL
);

CREATE TABLE Work (
    Work-ID INT PRIMARY KEY,
    Company-Name VARCHAR(255) NOT NULL,
    Salary VARCHAR(255) NOT NULL  
);

CREATE TABLE Company (
    Company-Name VARCHAR(255) PRIMARY KEY,
    City VARCHAR(255) NOT NULL
);

CREATE TABLE Manages (
    Manage-ID INT PRIMARY KEY,
    EMID INT ,
        CONSTRAINT FK_EMID FOREIGN KEY (EMID) REFERENCES Employees (EMID),
);


SELECT Cus-ID
FROM Customers c
JOIN Borrower b ON c.Cus-ID = b.Cus-ID
WHERE l._Loan-ID IS NULL;

SELECT Cus-ID
FROM Customers
WHERE Street = (SELECT Street FROM Customers WHERE Cus-ID = '12345')
  AND City = (SELECT City FROM Customers WHERE Cus-ID = '12345');


SELECT BranchName
FROM Branches b
JOIN Accounts a ON b.BranchName = a.BranchName
JOIN Customers c ON a.Cus-ID = c.Cus-ID
WHERE c.City = 'Harrison';


SELECT SUM(Amount) FROM Loans;

SELECT *
    FROM Branches 
    WHERE branch.City = 'Brooklyn'
