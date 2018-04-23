## Integrating MOLPay with Python SDK
Version 1.0.0

### Pre-Requisite
1. Python 3.
2. Flask.
3. hashlib.
4. pycurl.
5. MOLPay Development or Production ID.
6. MOLPay General API.

### Installation
1. Download `MOLPayPython.zip` folder.
2. Extract the zip file.
3. Open terminal, navigate into `MOLPayPython` folder.
4. Run `python sdk.py` at the terminal.

### Usage
1. Set which type of enviroment with either **sandbox** or **production**
```Python
enviroment = "sandbox" #or "production"
```
### Payment Page integration
Set these needed objects that will send the buyer infromation to MOLPay hosted payment page.
```Python
#Value set are examples
merchant_id = '' #Insert merchant id here
vkey = '' #Insert Verify Key here
amount = '61.01' #Insert amount here
orderid = '601' #Insert order id here
```
It is not needed to set all the Endpoint URLs. If not set,by default the Endpoint URLs would be taken from Merchant Portal's End Point settings.
```html
<!-- Value set are examples -->
<input type="hidden" name="returnurl" id="returnurl" value="http://127.0.0.1:5000/returnurl">
```
### Payment endpoint integration
Set the values received from MOLPay's payment page.
```Python
tranID=request.form['tranID']
orderid=request.form['orderid']
status=request.form['status']
domain=request.form['domain']
amount=request.form['amount']
currency=request.form['currency']
appcode=request.form['appcode']
paydate=request.form['paydate']
skey=request.form['skey']
vkey = '' #Insert Private vKey here
```
#### IPN(Instant Payment Notification)
Additional object must be set when using IPN
```Python
treq = "1" #Value is always 1. Do not change
```
Call the IPN function
```Python
IPN()
```
#### Notification & Callback URL with IPN 
Set additional object for Notification & Callback URL 
```Python
nbcb=request.form.get('nbcb')
```
Support
-------

Merchant Technical Support / Customer Care : support@molpay.com <br>
Marketing Campaign : marketing@molpay.com <br>
Channel/Partner Enquiry : channel@molpay.com <br>
Media Contact : media@molpay.com <br>
R&D and Tech-related Suggestion : technical@molpay.com <br>
Abuse Reporting : abuse@molpay.com

Disclaimer
----------
Any amendment by your end is at your own risk.

Changelog
----------
1. 2018-04-23 - v1.0.0 - Initial Release
