**Apache Web Server**
=====================

The last thing on our list is to configure the Apache Web Server. Apache is one of the most popular web services on the Internet today, with close to 50% of websites running on it. There are other options as well, such as nginx and Microsoft's IIS.

Web services, like Apache, allow users to connect to servers through the Hypertext Transfer Protocol (HTTP), which defines how messages from websites are formatted and transmitted. Website files are often formatted in the Hypertext Markup Language (HTML).

Apache does allow for other languages and services to be utilized as well. Some examples include CSS, Javascript, PHP, JSON, etc.

**Personalizing HTML File**
-------------------------

We have already done most of the work needed to get our website up and running. We installed the Apache software (`httpd`), started and enabled the service (`httpd`), and even copied over the website files to the `/share/Developers` directory. The only thing left to do is make a few small edits to the HTML file and a small change to our configuration file.

* Open the `index.html` file you copied earlier with "vi":




sudo vi /share/Developers/index.html




Edit the following lines, replacing the stand-in text with your name:



html
￼



<title>Your Name here</title>
<h1>UserName's Test HTML Page</h1>





* Save and close the file.

**Configuring Apache**
----------------------

By default, Apache looks for website files in the directory `/var/www/html`, but we want to change this to our `Developers` directory. To do this, we need to change the `DocumentRoot` setting in the Apache configuration file.

* Open the Apache configuration file with "vi":




sudo vi /etc/httpd/conf/httpd.conf




This configuration file is quite long and has many settings. Unlike the Samba configuration file, we need most of the default settings for our Web server to work. Scroll down through the file and look for the `DocumentRoot` setting.

* Edit the line `DocumentRoot "/var/www/html"`, replacing the path with `/share/Developers`.
* Under the comment `#Further relax access to the default document root`, edit the `Directory` to `/share/Developers`.

* Save and close the file.
* For the changes to take effect, restart the Apache service:




sudo systemctl restart httpd




**Testing Our Website**
----------------------

Everything should be set. Let's test our website.

* Open a browser window and enter: `http://<computername>` (replacing `<computername>` with your computer name.)
* You should see a page!