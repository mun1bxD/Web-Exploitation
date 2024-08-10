<img src="images/image1.png" alt="third" width="500">

**Step1:**

Append url with /robots.txt

<img src="images/image2.png" alt="third" width="500">

Now add the disclosed path to url  /administrator-panel

<img src="images/image3.png" alt="third" width="500">

Delete user carlos

<img src="images/image4.png" alt="third" width="500">

**Step1**

View page source

<img src="images/image5.png" alt="third" width="500">

If a person is admin then move to /admin-jz8l8o

Append url with the above path and delete user carlos

<img src="images/image6.png" alt="third" width="500">

And lab is solved

<img src="images/image7.png" alt="third" width="500">

Type /admin in url

<img src="images/image8.png" alt="third" width="500">

Now if we view cookies value it is set to false

<img src="images/image9.png" alt="third" width="500">

Turn false to true

<img src="images/image10.png" alt="third" width="500">

Click on my account

We can see admin panel

<img src="images/image11.png" alt="third" width="500">

Simply delete user carlos

<img src="images/image12.png" alt="third" width="500">

**Step1:**

Login in and update email

**Step2:**

Send POST /my-account/email to repeater

<img src="images/image13.png" alt="third" width="500">

**Step3:**

Adding a role id parameter to json object

<img src="images/image14.png" alt="third" width="500">

**Step4:**

Now our role is of administrator

Refresh page or click on my account

<img src="images/image15.png" alt="third" width="500">

Now go to admin panel and delete user carlos

<img src="images/image16.png" alt="third" width="500">

**Step1:**

Login with username and password

<img src="images/image17.png" alt="third" width="500">

**Step2:**

Change the name from wiener to carlos

<img src="images/image18.png" alt="third" width="500">

And we are log in as carlos

<img src="images/image19.png" alt="third" width="500">

Submit API key to solve the lab

<img src="images/image20.png" alt="third" width="500">

**Step1:**

Go to post3 which is of author carlos

<img src="images/image21.png" alt="third" width="500">

Click on carlos

<img src="images/image22.png" alt="third" width="500">

Copy this user id and pass in your account section

And finally submit the API key

<img src="images/image23.png" alt="third" width="500">

**Step1:**

Login to account using given credential

<img src="images/image24.png" alt="third" width="500">

**Step2**

Change id to carlos from wiener

<img src="images/image25.png" alt="third" width="500">

In burp we  have redirected request

<img src="images/image26.png" alt="third" width="500">

Send the request to repeater and in response we have api key

<img src="images/image27.png" alt="third" width="500">

Submit API key.

<img src="images/image29.png" alt="third" width="500">

**Step1:**

Go to live chat and click on view transcript

<img src="images/image30.png" alt="third" width="500">

**Step2:**

In burp send the request of GET /download-transcript/ to repeater

<img src="images/image31.png" alt="third" width="500">

**Step3:**

Send the request to repeater and change filename to 1.txt

<img src="images/image32.png" alt="third" width="500">

Log in with username carlos and password in response

<img src="images/image33.png" alt="third" width="500">

**Step1**

Login to account using given credential

<img src="images/image34.png" alt="third" width="500">

Now change the username to administrator

<img src="images/image35.png" alt="third" width="500">

So there is a password

**Step2:**

To see password we send request to repeater and see password

<img src="images/image36.png" alt="third" width="500">

Login as administrator and delete user carlos

<img src="images/image37.png" alt="third" width="500">

**Step1:**

Enter random number in username and password

<img src="images/image38.png" alt="third" width="500">

**Step2:**

Send the post login request to repeater

<img src="images/image39.png" alt="third" width="500">

**Step3:**

Now add X-Original-Url: /admin

<img src="images/image40.png" alt="third" width="500">

**Step4:**

Remove last line and add  /?username=carlos and send the request

<img src="images/image41.png" alt="third" width="500">

And user carlos is deleted successfully
