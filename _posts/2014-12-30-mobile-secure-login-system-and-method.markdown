---

title: Mobile secure login system and method
abstract: A mobile secure login method comprises steps of 1) displaying a machine readable graphic form encoded with a sign in URL and a unique token on a browser, wherein the said machine readable graphic form comprises at least one of a 1D barcode, a 2D barcode, a PDF417, an QR code, a Data Matrix code, an Aztec code, and OCR symbol; 2) scanning the said machine readable graphic form using a mobile device; 3) transmitting the sign in credential with the said unique token to a server at the said sign in URL from the said mobile device, wherein the said sign in credential comprises at least one of a username, a password, and a PKI signed challenge; 4) authenticating the said sign in credential at the said server to enable the said browser login to a secure website automatically.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09426149&OS=09426149&RS=09426149
owner: 
number: 09426149
owner_city: 
owner_country: 
publication_date: 20141230
---
Identity fraud on the Internet has become more prevalent in recent years. The source of fraud is primarily due to insecure passwords phishing and keyloggers. To address the issue of insecure passwords many websites have now encouraged users to include combinations of letters numbers and symbols into their password. Therefore creating and remembering multiple secure passwords is a huge burden for a typical Internet user especially for seldom used accounts. However these secure passwords can be undermined by keyloggers malware that record everything that a user types on a computer.

Although there are plenty of browsers that offer to remember your usernames and passwords in the browser this practice is usually not recommended by security experts as the computers and browsers are vulnerable to attacks by viruses and other malware.

Other secure Apps on a mobile phone such as eWallet Password ABC etc. cannot sign in a user to a website open in a browser on another device such as a PC. Mobile apps such as Password ABC only allows the device to login the website on the same mobile device. But if a user wishes to login to a website on a separate device such as a PC the user still needs to search for the proper username and password in these Apps and then manually type in the username and password into the PC website to login the site. If a user would like to use a public PC to login a secure site there is no guarantee that her his username and password will remain private as it could be captured by a keystroke logging malware for example. Thus rendering these secure mobile apps no more secure than a user s own memory.

In one aspect the invented secure mobile login method enables the user to login to a secure website on a computer e.g. a Personal Computer without manually entering a username and password. This is accomplished by using a mobile device to scan a barcode displayed on the webpage.

Additionally after using a mobile device to scan a barcode displayed on the webpage the invented method automatically matches the website with a proper credential that is securely stored in the mobile device and upon user s permission then transmits to the website server for authentication.

Furthermore once the website server has authenticated the mobile secure login credentials transmitted from a user mobile device the current invented method enables the browser or client on the computer to be notified through either a pushing or pulling message to automatically advance into a secure webpage without a key press or a mouse click on the computer that is without human intervention.

In another aspect the invented secure mobile login method does not require a user to type in his her credentials e.g. a username and a password on a computer therefore it would not be subject to keylogging attacks.

Yet another aspect the invented secure mobile login method will automatically check the validity of the website before submitting the user credentials to the website server thus avoiding a potential phishing attack.

Furthermore the current invented method enables extremely long periodically random generated password as a mobile secure login credential which is almost impossible for a human being to remember thus enhancing security dramatically.

Additionally the invented method enables the use of Public Key Infrastructure PKI signed challenge as a mobile secure login credential which also significantly enhances the login security.

Referring to and a user may run a web browser in the computer to login a secure web site at the server . A typical way of login to a secure website for example is to type in a username and a password at the sign in page and click on Sign in button as shown in . The current invention method provides an alternative secure way to login to the secure web site without typing in a username a password and clicking the Sign in button in the computer . Instead a user can pull out her his mobile device such as a smart phone and scan a barcode displayed in the web browser running on the computer .

Referring to the after a user scans the barcode as shown in a mobile device displays for example two accounts John Doe J. H. Doe for the user to select to login to the secure website.

Referring to the and once the user selects John Doe on the mobile device the browser in the computer automatically advances the user into the secure website with greeting message to John Doe and a private message for the user s account summary for example.

In step a typical way of login to a secure website the browser is activated by clicking Sign in button . Then it goes to step to submit the username and the password filled in by the user in the sign in form together with the unique token to the server at the sign in URL.

In step alternatively in parallel of step the browser running in the computer will automatically check the server in the background periodically to see if the session associated with the unique token has been authenticated or not. If not yet the browser will go to step and wait for a predetermined period of time in the background for example a second and then tries the step again. If the session associated with the unique token has been authenticated then it will go to step to submit an empty sign in form with the unique token to the sign in URL. One of the preferred embodiments of step is to use jQuery.Ajax Asynchronous HTTP request as shown in the example Code List 1 below. Another preferred embodiment is to use Comet model. When a particular token has been authenticated by a mobile device the server can push the authenticated event to notify the browser.

In step the app searches through the database in the mobile device for a sign in credential associated with the sign in URL. If more than one credential found to associate with the sign in URL for example a list of account names e.g. John Doe J. H. Doe is presented as shown in for the user to select. If no credential is found to associate with the sign in URL for example a sign in form will be presented to request the user to fill in a username and a password on the mobile device . The username and the password will be stored in the database in the app as a credential associated with the sign in URL.

In step the mobile device transmits the sign in credential for example a username and a password and the unique token to a server at the sign in URL. Another preferred embodiment of a credential is PKI Public Key Infrastructure signed challenge. For example the server can generate a random number as a challenge to request the mobile device to digitally sign it using its private key. The signed challenge will be transmitted in step as the sign in credential.

In step the server authenticates the sign in credential. For example in one of the preferred embodiments if a username and a password are received as the sign in credential the server will look up a user database using the username as a key and verify if the password hash is the same as the one stored in the database. If it is the same it will go to step otherwise go to step . In another preferred embodiment a username and a PKI signed challenge is received as the sign in credential the server will look up a user database using username as a key and retrieve the user s public key to verify the PKI signed challenge. If the verification is passed then it will go to step otherwise go to step .

In step the server sets the authenticated flag equal to True in a securelogin database. The authenticated flag in the securelogin database is associated to the token and the sign in credential which is received at step .

In step the server sets the authenticated flag equal to False in a securelogin database. The authenticated flag in the securelogin database is associated to the token and the sign in credential which is received at step . In another preferred embodiment the server simply associates the sign in credential to the token in the securelogin database if the authenticated flag was created with a default value of False.

In step if the server receives an empty sign in credential and a token then the server will use the token as the key to look up the securelogin database for the associated authenticated flag and the associated sign in credential e.g. a username . If the authenticated flag is True then go to step otherwise go to step . If the server receives a non empty sign in credential for example a username and a password then the server will look up a user database using username as a key and verify if the password hash is the same as stored in the database. If it is the same then it will go to step otherwise go to step .

In step the server renders a new sign in page again with an error message for example Invalid username password combination as shown in .

The flow diagrams depicted herein are just examples. There may be many variations to these diagrams or the steps or operations described therein without departing from the spirit of the disclosure. For instance the steps may be performed in a differing order or steps may be added deleted or modified.

While embodiments have been described it is understood that those skilled in the art both now and in the future may make various improvements and enhancements.

