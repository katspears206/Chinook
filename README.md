# Chinook

This is where I am storing the answers to my Chinook SQL queries.

1. SELECT FirstName, LastName, CustomerID, Country 
    FROM Customer
    WHERE Country != "USA"

2. SELECT FirstName, LastName, CustomerID, Country 
    FROM Customer
    WHERE Country == "Brazil"

3.SELECT FirstName, LastName, Invoice.CustomerID, InvoiceID, BillingCountry, InvoiceDate
    FROM Invoice
    JOIN Customer ON Customer.CustomerID = Invoice.CustomerID
    WHERE BillingCountry == "Brazil"
    
4.SELECT *
    FROM Employee
    WHERE Title == "Sales Support Agent"
    
5.SELECT DISTINCT BillingCountry
    FROM Invoice
    ORDER BY BillingCountry
    
6.SELECT Employee.FirstName, Employee.LastName, EmployeeId, InvoiceId
    FROM Customer
    JOIN Employee ON Employee.EmployeeId = Customer.SupportRepId
    JOIN Invoice ON Invoice.CustomerId = Customer.CustomerId
    ORDER BY EmployeeId, InvoiceId
    
7.SELECT Customer.FirstName, Customer.LastName, Employee.FirstName, Employee.LastName, Customer.Country, InvoiceId, Total
    FROM Customer
    JOIN Employee ON Employee.EmployeeId = Customer.SupportRepId
    JOIN Invoice ON Invoice.CustomerId = Customer.CustomerId
    
8.SELECT COUNT(InvoiceId)
    FROM Invoice
    WHERE [InvoiceDate] >= '2009-01-01' AND [InvoiceDate] < '2011-12-31'
  Answer 249
  
  SELECT SUM(Total)
    FROM Invoice
    WHERE [InvoiceDate] >= '2009-01-01' AND [InvoiceDate] < '2011-12-31'
  Answer 1400.49
  
9. SELECT COUNT(), InvoiceId
    FROM InvoiceLine
    WHERE InvoiceId = 37

10.SELECT InvoiceId , COUNT()
    FROM InvoiceLine
    GROUP BY InvoiceId
    
11.SELECT Track.Name, InvoiceId, InvoiceLineId
    FROM Track
    JOIN InvoiceLine ON InvoiceLine.TrackId = Track.TrackId
    
12.SELECT Track.Name, Artist.Name, InvoiceId, InvoiceLineId
    FROM Track
    JOIN InvoiceLine ON InvoiceLine.TrackId = Track.TrackId
    JOIN Album ON Album.AlbumId = Track.AlbumId
    JOIN Artist ON Artist.ArtistId = Album.ArtistId
    
13.SELECT BillingCountry, COUNT(InvoiceId) AS NumberOfInvoices
    FROM Invoice
    GROUP BY  BillingCountry
    
14.SELECT Playlist.Name, Count(PlaylistTrack.TrackId)
    FROM Playlist
    JOIN PlaylistTrack ON PlaylistTrack.PlaylistId = Playlist.PlaylistId
    GROUP BY Playlist.Name
    
15.SELECT Track.Name, Album.Title, MediaType.Name AS MediaType, Genre.Name AS Genre
    FROM Track
    JOIN Album ON Album.AlbumId = Track.AlbumId
    JOIN MediaType ON MediaType.MediaTypeId = Track.MediaTypeId
    JOIN Genre ON Genre.GenreId = Track.GenreId
    
16.SELECT Invoice.InvoiceId , COUNT(InvoiceLineId)
    FROM InvoiceLine
    JOIN Invoice ON Invoice.InvoiceId = InvoiceLine.InvoiceId
    GROUP BY Invoice.InvoiceId
    
17.SELECT Employee.FirstName, Employee.LastName , SUM(Invoice.Total)
    FROM Invoice
    JOIN Customer ON Customer.CustomerId = Invoice.CustomerId
    JOIN Employee ON  Employee.EmployeeId = Customer.SupportRepId
    GROUP BY Employee.EmployeeId
    
18.

