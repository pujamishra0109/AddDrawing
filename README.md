# Nulab_Assignment
Application- Search Application 

Minimum requirements to test the application 
- An IDE (preferably Eclipse (2018-09 (4.9.0))
- Java 1.8

Steps to run :-
 It is a Spring boot Application with maven plugin
1. Please change the apiKey for a particualar user of cacaoo to use Cacaoo API. in the application.properties 
2.Currently,given server port is 8080 in the application.properties,to change the port,you need to change it in the application.properties.
2.maven clean
3.maven install
4.Run app.java file as a Java Application.



This application enables the user to search amongst her diagrams on Cacoo for a particular keyword and a given range of dates. 

1. url :https://localhost:8080/searchDate?str={SearchString}
	
- It accepts a keyword as an input {SearchString} and returns all the diagrams of the user where the keyword appears in the Title or the description
eg: https://localhost:8080/searchDate?str=diagram
	
Response : 
	[{"createdDate":"Mon Aug 19 01:49:48 CEST 2019","url":"https://cacoo.com/diagrams/4GYJT2K6Uk8rMmtg","description":"","title":"New Diagram","diagramId":"4GYJT2K6Uk8rMmtg"},
	 {"createdDate":"Mon Aug 19 01:48:31 CEST 2019","url":"https://cacoo.com/diagrams/KlY01tYMfH9QvEwg","description":"","title":"New Diagram","diagramId":"KlY01tYMfH9QvEwg"},
	 {"createdDate":"Mon Aug 19 01:40:55 CEST 2019","url":"https://cacoo.com/diagrams/b5MWqWY5X1dEV6Ft","description":"","title":"Marketing Diagram","diagramId":"b5MWqWY5X1dEV6Ft"},{"createdDate":"Mon Aug 19 01:40:50 CEST 2019","url":"https://cacoo.com/diagrams/6l7puvSuVaZ25pWf",
		 "description":"","title":"New Diagram","diagramId":"6l7puvSuVaZ25pWf"},
	]
			
2.	url :https://localhost:8080/searchDate?str={SearchString}&&startDate={startDate}&&endDate={endDate}	
- It accepts a start date {startDate} and end date {endDate} in the format of dd-mm-yyyy, which defines the date range for the search, and returns only the diagrams that were created within these dates (both inclusive) along with the search string.
https://localhost:8080/searchDate?str=diagram&&startDate= 10-02-2018&&endDate=17-08-2019
	
	[{"createdDate":"Mon Aug 19 01:49:48 CEST 2019","url":"https://cacoo.com/diagrams/4GYJT2K6Uk8rMmtg","description":"","title":"New Diagram","diagramId":"4GYJT2K6Uk8rMmtg"},
	 {"createdDate":"Mon Aug 19 01:48:31 CEST 2019","url":"https://cacoo.com/diagrams/KlY01tYMfH9QvEwg","description":"","title":"New Diagram","diagramId":"KlY01tYMfH9QvEwg"}]


3.url :https://localhost:8080/searchDate?str={SearchString}&&startDate={startDate}
	  https://localhost:8080/searchDate?str=SearchString}&&endDate={endDate}
-It also has the ability to accept only a start date {startDate} or end date {endDate} as a parameter in the dd-mm-yyyyformat along with search string. It returns all the diagrams that have been created on or after that date

 Url : 
		https://localhost:8080/searchDate?str=diagram&&startDate=10-02-2018
			
		https://localhost:8080/searchDate?str=diagram&&endDate=10-02-2020
    
    
	Response: 
		[{"createdDate":"Mon Aug 19 01:49:48 CEST 2019","url":"https://cacoo.com/diagrams/4GYJT2K6Uk8rMmtg","description":"","title":"New Diagram","diagramId":"4GYJT2K6Uk8rMmtg"},
		 {"createdDate":"Mon Aug 19 01:48:31 CEST 2019","url":"https://cacoo.com/diagrams/KlY01tYMfH9QvEwg","description":"","title":"New Diagram","diagramId":"KlY01tYMfH9QvEwg"}]
