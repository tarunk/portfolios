# portfolios

portfolio managements
Here are some details:
- /api/bonds <br>
To create bond: http://localhost:8080/api/bonds (post call)<br>
to change bond same put call <br>
{<br>
	"userId": "tarun",<br>
	"bondName": "mumbaiGold20",<br>
	"description": "Mumbai Gold",<br>
	"pricing": 100.00,<br>
	"avgReturn" : 12.0,<br>
	"profitPre": 5.0<br>
}<br>
the user id is important, here tarun is "ADMIN" in user table, it can be created via SQL statements exist in resource dir<br>


- seller request: http://localhost:8080/bond/seller/portfolios (post call)<br>
{<br>
	***"seller": "arun",<br>
	***"bondName": "gold200",<br>
	***"count": 20,<br>
	***"sellPrice": 11.12<br>
}<br>

in user table user should be "SELLER"<br>

- buyer request to buy bond: http://localhost:8080/bond/buyer/portfolios<br>
{<br>
	***"buyer": "tonu",<br>
	***"bondName": "gold24",<br>
	***"count": 10,<br>
	***"sellPrice": 12.12<br>
}<br>
in user table buyer should be "CUSTOMER"<br>

- /bonds/{bondName}<br>
to delete bond : http://localhost:8080/api/bonds/silver200 (delete call)<br>
here silver200 we want to delete<br>
{<br>
	***"userId": "tarun",<br>
	***"bondName": "silver200"<br>
}<br>
userid tarun need to be ADMIN<br>

- to see the Sellers sales: http://localhost:8080/bond/sales/seller/arun<br>
here Arun is sellers<br>

- /portfolios/customer/{customerName}<br>
to see the Customer tonu portfolios: http://localhost:8080/bond/portfolios/customer/tonu<br>

- /api/customers/bond/{bondName}/{admin}<br>
admin can see the bond owned by customer: http://localhost:8080/api/customers/bond/gold24/tarun<br>
here tarun is 'ADMIN'<br>
gold24 is bond<br>

- /api/report/{frq}/{admin}<br>
to generate report: http://localhost:8080/api/report/monthly/tarun<br>
here tarun is ADMIN<br>
"monthly" is a frequency<br>

## Important points:
-   all buying and selling requests are handled Async.
-   H2 in-memory database.
-   Code is written in Java-8 with spring boot
-   it is compiling and running perfectly.
-   tried to add MockMvc unit test case but I am facing some issues so, left with a few.
-  used IntelliJ IDE
