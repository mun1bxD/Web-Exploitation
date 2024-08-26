  
## Information Disclosure

<img src="images/image1.png" alt="third" width="500">

**Step1**

click on view product


**Step2:**

Send the post request to repeater

<img src="images/image2.png" alt="third" width="500">

**Step3:**

Change product id to any character other then number

<img src="images/image3.png" alt="third" width="500">

And we have answer 2 2.3.31

<img src="images/image4.png" alt="third" width="500">

**Step1**

Click on view product on home page

**Step2**

Now we have to find all comment from a site

For this in target> sitemap right click on website id and go to engagement tool > search for comment

<img src="images/image5.png" alt="third" width="500">

**Step3:**

Copy this link and send the get request to repeater

<img src="images/image6.png" alt="third" width="500">

In repeater we have output

<img src="images/image7.png" alt="third" width="500">

<img src="images/image8.png" alt="third" width="500">


**Step1:**

Append /robots.txt  to url

<img src="images/image9.png" alt="third" width="500">

**Step2:**

Now replace /robots.txt with /backup

<img src="images/image10.png" alt="third" width="500">


**Step3:**

Open link

<img src="images/image11.png" alt="third" width="500">

Submit the answer

<img src="images/image12.png" alt="third" width="500">

**Step1:**

when we access admin panel by adding /admin in url it shows message.

<img src="images/image13.png" alt="third" width="500">

**Step2:**

On the other hand if we render the response of GET /admin we can see clearly two user. but we are not able to delete them

<img src="images/image14.png" alt="third" width="500">

**Step3:**

when we replace GET with TRACE we can see in response we have a `X-Custom-IP-Authorization` parameter.

<img src="images/image15.png" alt="third" width="500">

**Step4:**

in order to pass this we simple set the custom Ip to local host for this we Go to proxy-> then http history and in match and replace we add X-Custom-IP-Authorization:127.0.0.1

<img src="images/image16.png" alt="third" width="500">

now when we refresh the main page we have access of admin panel.

<img src="images/image17.png" alt="third" width="500">

Go and delete user carlos.  

<img src="images/image18.png" alt="third" width="500">

**Step1:**

in this app when we type `/.git` in URL we have access to git history

**Step2:**

Simply install them using `wget -r lab-id/.git`

**Step3:**

Install a tool for version control. In this lab we use git cola for GUI.

**Step4:**

open the downloaded folder in git cola.

<img src="images/image19.png" alt="third" width="500">
  

uncommit the last change

we can see password here.

<img src="images/image20.png" alt="third" width="500">
