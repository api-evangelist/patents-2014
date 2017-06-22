---

title: Method and system for implementing in-app software development kits
abstract: The invention refers to technical methods and systems to easily provide existing software applications, for example Android applications built for In-App Billing with Google Play application programming interface (“API”), with compatibility with other alternative payment platforms, preferably direct carrier billing, with no additional development effort.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09250882&OS=09250882&RS=09250882
owner: BUONGIORNO S.P.A.
number: 09250882
owner_city: Parma
owner_country: IT
publication_date: 20141224
---
This application is based upon and claims the benefit of priority to U.S. Provisional Application No. 61 921 287 filed Dec. 27 2013. The disclosure of the prior application of which is hereby incorporated in its entirety by reference.

The present invention relates to methods for the development of proprietary software development kits hereafter SDKs to enable existing software applications hereafter apps preferably Android apps to plug in to alternative app payment methods and specifically direct carrier billing functionalities thus being able to distribute said apps out of a single app market store for example in alternative markets to Google Play store with effortless integration. The invention also relates to systems configured for implementing said methods.

Google Play is an app marketplace managed by Google where users can upload their Android compatible applications. Third party developers using Android software development toolkit can build applications as packaged binary application package files APKs and upload them to Google Play store for distribution to end users.

Through Google Play those apps can be found by end users downloaded and installed on Android based devices. Google additionally provides a set of services useful to implement common functionalities in Android apps such as messaging asynchronous notification application upgrade and in app payment. We will call these as Proprietary Google Services or PGS. The same typically applies to other proprietary services PS owned by other companies.

Google Play is not the only possible distribution platform for Android apps. There are alternative marketplaces such as Amazon Store and alternative payment methods. Developers that want to also distribute through these alternative channels are forbidden to use PGS and therefore have to build a different APK package linked to alternative implementations of those services. This requires additional development efforts that usually discourage the use of alternative platforms and becomes a technical barrier to Google competitors.

The present invention provides a proprietary SDK development method to build alternative APK files with automated algorithms to dynamically change behavior depending on context such as country mobile operator or required opt in flow and minimal effort for the developer simplifying the technical process to publish Android applications in alternative distribution channels.

One object of the invention refers to a method for implementing in app software development kits comprising 

In a preferred embodiment of the invention the additional proprietary support libraries included comprise one or more of the following function methods 

A further object of the invention refers to a system for implementing in app software development kits comprising software hardware and or middleware means configured to carry out a method according to any of the embodiments described in the present document.

In a preferred embodiment of the invention the system comprises a server middleware implemented on a cluster of application servers configured to dispatching commands to one or more of the following components 

As an example related to Google proprietary services although also applicable to other app proprietary services by introducing the corresponding modifications related to programming languages operating systems and specific market store specifications and APK requirements the technical process involved in producing an APK file for upload to Google Play includes the following steps 

Through this method a competitor of Google in the field of Android apps distribution can easily convince application developers to engage in distribution in the competitor s marketplace.

As an example related to an embodiment of the invention applied to proprietary Google services the proposed method can be implemented through at least one support library that is compatible at application programming interface API level with the one provided by Google Play plus a server side platform implementing functionalities similar to the ones provided by Google for instance for in app payment. Those functionalities can be connected to different back ends and for example the in app payment can be implemented with operator billing instead of credit card transactions. The support library will preferably comprise the following function methods see for an example of a complete purchasing process according to the invention 

Through the above function methods the support API will interact with a Global Server Middleware see for an example of the SDK and Middleware architecture according to the invention which is a server system connected via JSON REST queries over the network. This system is implemented on a cluster of application servers dispatching commands to different backend components and payment providers. All communications will be protected and encrypted with HTTPS protocol using a pair of public key generated certificates where the public key will part of the support library files and the private key stored on the global middleware servers.

The IsBillingSupported function can be implemented collecting information from the operating system of a phone such as the IMSI code of a SIM card or the IP address and with this parameters calling the middleware to compute which country and operator the user belongs to who is the user for example via 3G number recognition or mapping IMSI to MSISDN or to email address with a database lookup and if ultimately the kind of transaction one off or subscription is allowed in this context. This call also allows identifying the user and having authorization codes needed for the other methods.

The global middleware manages tables with the inventory of purchasable items for each app separate price tables for each mobile operator lists of already purchased items for each user of each app lists of installed apps.

The GetPurchases and GetSkuDetails methods can be implemented calling the middleware to lookup the inventory tables and the item details and reporting a JSON document with the list of all the items owned by the user. Users are identified by their email account provided by Android operating system and applications are identified by their package name string and certificate. The combination of the three elements defines the set of items to be extracted by the tables.

The global middleware also maintains connections with core network and payment systems of several mobile operators in many countries implementing their proprietary communication protocols and automatically adapting the communication so that all operators are presented to the support library as one unique and uniform API. The purchase flow is described in these API as a finite state machine with arbitrary number of steps where is step represent one input action requested to the user in the opt in flow.

The GetBuyIntent calls the middleware to start a purchase session passing the stock keeping unit SKU of the item to be purchased and receiving a session. User interaction is managed with an Android Activity implemented in the support library as either a native form or a webview. The session is contextualized to the particular payment method and mobile operator and the look and feel of the form adapted accordingly. The support library can call the middleware at every step to send acquired information to the server and get back instructions on what needs to be performed in the next step what kind of form comes next which information is to be acquired in order to proceed . Obtained information is incrementally stored at the middleware end in a session table and only when the set is complete the transaction is performed sending appropriate commands different for each payment method and mobile operator to the relevant backends. When the session is complete the middleware will return a success code and the purchase Activity will close returning control to the game.

The ConsumePurchase method can be implemented with a call to the middleware with the Sku ID and will make the item as used so that in the table of items owned by the user it will no longer appear as owned and a new purchase for that Sku ID will become possible. This is particularly useful for those items that are consumable or repeatable meaning that users can buy them more than once.

A server side administration interface can provide to the developer the ability to configure parameters of the additional distribution method or the ability to auto provision the APK binary in the alternative store. A white label version of this administration interface can power different marketplaces under different brands.

In particular for in app payment based on operator billing additional complexity has to be addressed because different operators require different purchase experience flows and they frequently change the requirements to comply with ever changing national policies and regulations.

An application meant for global distribution would be connected with more than 100 different operators all requiring slightly different flows. Each of those operators would usually update the local requirements on a yearly basis meaning that the set of flows built in the app has to be updated very often.

The support library can overcome this complexity by dynamically loading step by step instructions on the specific purchase experience flow required by the operator that the phone running the app is connected to and automatically adapting the purchase experience to comply with local regulation. A typical session might go through these steps 

This way the purchase experience is automatically localized up to date with latest policies and works with variable number and type of steps depending on context.

All PGS can be implemented in the alternative support library as fully compatible alternative implementation making the app fully functional outside of Google Play marketplace.

The support library will automatically detect country and mobile operator of the handset querying the operating system API to retrieve IMSI code and decompose that in Mobile Country Code and Mobile Network Code according to ITU standards.

Using this information the support library will automatically relate the handset to a particular mobile operator and reconfigure the purchase experience according to the technical capabilities and the policy requirements of that mobile operator. This might include for example 

When needed user identification will be performed automatically by the support library without any need of user interaction using these steps 

The support library can be plugged in the original application code by the application developer and the new APK built using the same tool chain used for normal APK compilations for example within Eclipse. Through this method the original developer can create alternative versions of the APK and use them for distribution outside of Google Play or to provide users alternative in app payment methods.

In an alternative embodiment using a unique software algorithm an automated procedure can patch automatically the original APK binary to replace Google support library with the alternative support library effectively building the new APK automatically without the intervention of the original developers. This algorithm requires the following steps 

Similar automated build procedure can be also used to automatically plug in the manifest file an identification code that can be used to tag different instances of the APK file and track them to different distribution channels.

The support library can also provide a method for tracking installations from different promotional campaign and relate each in app purchase to the specific advertising partner that generated the app install. When installation of the APK is promoted a specific CampaignID is associated with the source of traffic and advertising partner.

When a user enters the promotional campaign browsing a specific URL a set of parameters that characterize the handset are collected and combined in a fingerprint value that is stored in a temporary table managed by the global middleware along with the Campaign ID.

This fingerprinting method is not related to cookies local storage and other tagging methods that only working inside the browser and therefore once the app is downloaded installed and opened the method can be applied again obtaining the same fingerprint. The first time the app is opened the fingerprint is generated again and used to retrieve the CampaignID from the temporary table. This CampaignID is then stored inside the installed app and used to track back to the global middleware each interesting event including completed installation of the app the start of a purchase session and each step of the same session. A table of events is maintained at the global middleware and used to track the history of each user and to notify advertising partners of the events belonging to them.

The support library can also provide a listener for incoming unsolicited notifications generated by the middleware. This listener periodically polls the middleware even when the app is not open and retrieves a list of new notifications. Once a new notification arrives this notification is immediately displayed to the user trough the operating system notification system. This messaging channel can be used to wake up the user and encourage additional interaction to provide useful information to dispatch advertising messages to signal that a new version of the APK is available.

The middleware will maintain a table of already installed apps along with the currently installed version. When a new APK for that app is uploaded in the middleware the middleware will automatically create notifications for each handset that has a previous version of the app installed. The support library can automatically intercept notifications related to new APK versions and trigger a download of the new APK binary to automatically upgrade the app.

