# portfolios

portfolio managements
Here are some details:
- To create bond: http://localhost:8080/api/bonds (post call)
to change bond same put call
{
	"userId": "tarun",
	"bondName": "mumbaiGold20",
	"description": "Mumbai Gold",
	"pricing": 100.00,
	"avgReturn" : 12.0,
	"profitPre": 5.0
}
the user id is important, here tarun is "ADMIN" in user table, it can be created via SQL statements exist in resource dir


- seller request: http://localhost:8080/bond/seller/portfolios (post call)
{
	"seller": "arun",
	"bondName": "gold200",
	"count": 20,
	"sellPrice": 11.12
}

in user table user should be "SELLER"

- buyer request to buy bond: http://localhost:8080/bond/buyer/portfolios
{
	"buyer": "tonu",
	"bondName": "gold24",
	"count": 10,
	"sellPrice": 12.12
}
in user table buyer should be "CUSTOMER"

- to delete bond : http://localhost:8080/api/bonds/silver200 (delete call)
here silver200 we want to delete
{
	"userId": "tarun",
	"bondName": "silver200"
}
userid tarun need to be ADMIN

- to see the Sellers sales: http://localhost:8080/bond/sales/seller/arun
here Arun is sellers

- to see the Customer tonu portfolios: http://localhost:8080/bond/portfolios/customer/tonu

- to admin can see the bond owned by customer: http://localhost:8080/api/customers/bond/gold24/tarun
here tarun is 'ADMIN'
gold24 is bond

- to generate report: http://localhost:8080/api/report/monthly/tarun
here tarun is ADMIN
"monthly" is a frequency

## Important points:
-   all buying and selling requests are handled Async.
-   H2 in-memory database.
-   Code is written in Java-8 with spring boot
-   it is compiling and running perfectly.
-   tried to add MockMvc unit test case but I am facing some issues so, left with a few.
-  used IntelliJ IDE
