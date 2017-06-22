---

title: Object-oriented system for creating and managing websites and their content
abstract: The invention teaches a method for creating and managing a website as an object oriented system, comprising: providing on a system server a plurality of hierarchical classes of objects, each of the classes representing one aspect of the storage, presentation and logic of a website; providing on a web server an interface operable to present representations of objects instantiating the plurality of hierarchical classes and receive commands meant to one of: instantiate a new object, destroy a presented object, and change a property of a presented object; and storing on a database server objects as a traversable tree in accordance with the plurality of hierarchical classes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09195437&OS=09195437&RS=09195437
owner: salesforce.com, inc.
number: 09195437
owner_city: San Francisco
owner_country: US
publication_date: 20140520
---
This United State continuation patent application claims the benefit of U.S. patent application Ser. No. 12 935 890 filed Sep. 30 2010 which claims the benefit of Section 371 National Stage Application of International Application No. PCT CA2009 000569 filed Apr. 28 2009 which claims the benefit of U.S. Provisional Application No. 61 048 516 filed Apr. 28 2008 the entire contents of which are incorporated herein by reference.

The present invention is directed to ways to create and manage websites and their content. More particularly the invention is directed to an object oriented way to create and manage dynamic websites and their content.

Today web pages and their content are typically created managed and delivered using a variety of tools and systems. Programming tools e.g. Adobe Dreamweaver are commonly used for web page creation and authoring tools e.g. Microsoft Word or Adobe PhotoShop are commonly used for content creation. Content Management Systems e.g. Drupal or OpenCMS may also be used for controlling and transforming content after it has been created and version control systems and database and web servers are used for storing and delivering the web pages and their content to end user browsers.

While in some cases it may be valuable from a separation of concerns perspective i.e. having the creative department use one set of tools and the IT department use others the use of tools and systems that are not integrated makes it necessary to integrate the work product of each department in a separate final step to permit a given web page and its content to be published to the Internet. One problem with this approach is that it is time consuming and this problem is exacerbated by the tendency that websites and their content are rarely static. Almost all websites change frequently being updated constantly to reflect changes in the organization or individual publishing the website or in its or his her environment.

The absence of an integrated system makes creating and revising content and a set of web pages on a website or on any given web page of a website unduly difficult in terms of both effort and complexity. Once design mock ups and digital assets e.g. art photos and videos have been developed the website s web pages are built with these design elements using HTML CSS and JavaScript programming languages to achieve the effects called for in the design. Next or in parallel news articles product data sheets and other information are developed to form the content for the site.

At this point the user faces a choice of whether or not to use a Content Management System a CMS . Content Management Systems are typically employed if the content on a web site is expected to change frequently. If not then the website publisher will typically hard code the content directly into each web page file.

If a CMS approach is chosen the next step is to place all content items into a relational database and to turn each web page file via programming into a page template that is bound to the CMS. The CMS then dynamically or in some systems statically during a compilation process creates individual web pages of a website by combining the content in the database with the layout presentation and behavior defined in the web page template. At this point the final web page is ready for delivery to an end user s browser.

A significant problem with the technologies and processes described above is that it is very difficult to build and integrate all of the content and web page i.e. layout presentation and behavior components needed for a sophisticated website. If a CMS is employed to manage content changes the initial build is even more difficult and even if a CMS is employed it is still very difficult to make subsequent changes to site structure site map and web page components without involving considerable programming.

Without a CMS combining content and web page visual aspects layout presentation and behavior may be done like this using HTML and JavaScript 

The above code would produce a section on a web page with a yellow background color layout and presentation as well as set up some code to handle mouse clicks etc. behavior . Finally it would display the line This is some text content on the page.

The term Content is a variable whose value e.g. This is some text is defined and stored in a database that is populated by the website publisher. If the value of Content is indeed This is some text then the CMS code above would produce from the end user browser s perspective exactly the same web page and content as the non CMS code above. However note that by implementing the CMS the content in the database could be changed to any value say for example Hello World and this would be automatically displayed on the web page the next time it is rendered.

The CMS approach therefore provides an improvement relative to the hard coding of all content into individual web pages in situations where the content is expected to change relatively frequently. However the CMS approach also has significant drawbacks in that it does not facilitate changes in web page visual aspects. What if for example a website publisher wants to change the background color or more interestingly to change what happens when the end user browser clicks or hovers on certain elements within a web page How would the publisher add an entirely new web page to display new content 

Changes of this sort are examples of changes to web page visual aspects including structure layout presentation and behavior and cannot be implemented using current technologies without additional programming.

The following summary provides a simplified overview of the subject matter that is described herein and is not intended to identify any critical elements nor to delineate the scope of the described or claimed subject matter. The sole purpose of the summary is to outline in a simplified form the aspects of tile subject matter that will be described in greater detail below.

Briefly described the subject matter disclosed herein relates in various embodiments to systems and methods that support the creation and lifecycle management of all the attributes and methods contained within a typical website in a completely object oriented manner such that traditional web programming languages version control and content management systems are not required. A three tier approach is applied providing a presentation tier a logic tier and a storage tier.

In contrast to existing website production and delivery systems the system and method described herein allows each object to be managed created updated versioned separately from each other while retaining the relationships containment parent child sibling is a etc. between the objects. For example a content display object and its relationship to content items and pages that may contain it.

With this object oriented design objects within a website can be created and changed independently from each other without requiring textual programming. Objects are created and configured via a drag drop or fill in the blank metaphor as are their behaviors and inter relationships e.g. Page to element Form to table table to fields etc. .

According to one aspect of the present invention there is taught a method of creating and managing websites and their content by providing on a system server a plurality of hierarchical classes of objects each of the classes representing one aspect of the storage presentation and logic of a website providing on a web server an interface operable to present representations of objects instantiating the plurality of hierarchical classes and receive commands meant to one of instantiate a new object destroy a presented object and change a property of a presented object and storing on a database server objects as a traversable tree in accordance with the plurality of hierarchical classes.

The method further provides for rendering a requested portion of the website by traversing the corresponding portion of the object tree and generating a dynamic webserving in response to the properties of the traversed objects.

Providing an interface might include providing a user interface or even providing a WYSIWYG user interface. In that regard presenting representations of objects might include presenting symbolic representations of objects.

Throughout this specification the term web page refers to the visual aspects of any given page of a website including layout e.g. the size and location of visual elements or widgets on each page presentation e.g. style colors and format of widgets and behavior e.g. what happens when a user moves a mouse clicks a button or menu hovers etc. 

The term content refers to the information e.g. text and graphics such as for example a news article that is delivered to an end user browser via the web pages of a given website.

The term webserving means a portion of code generally some combination of HTML CSS and JavaScript sent from a web server to a web browser to direct the browser to perform desired functionality such a presenting a webpage or a portion of a webpage.

Those skilled in the art will understand that in an internetworked system an action is often the result of coordinated activities occurring at multiple nodes in the system . In the case of a system built on the Internet these nodes arc often distributed ad hoc and unpredictably across multiple jurisdictions. The act ions as described and claimed herein arc intended to encompass at least a actions performed directly and completely within the jurisdiction of the patent b actions coordinated within the jurisdiction but with at least some activities performed outside the jurisdiction c actions coordinated outside the jurisdiction but with at least some activities performed within the jurisdiction and d actions performed for the benefit of a node within the jurisdiction or a person using that node. An example of such coordination would be serving a layout for a web page from one node and serving content for insertion into the layout from one or more other nodes including through the use of server side scripting client side scripting and AJAX techniques.

Each of the clients might be a duly configured general purpose programmable computer or a more purpose specific device such as a smartphone a microbrowser or portable media viewer with a wireless modem.

A server might similarly be a duly configured general purpose programmable computer but might also be a farm of such computers or one or more virtualized computers embodied as processes operating on a physical general purpose programmable computer. Such farmed or virtualized computers might themselves be distributed over their own local or wide area network not shown.

In essence the servers and the clients are roles or functions performed in the system by properly configured devices . Multiple roles or functions could be performed by one device and one role or function could be distributed over multiple devices . The specific character of a device and more generally the hardware and the network topology is important to the extent that it supports the performance of the assigned roles or functions.

The web server system server and database server may be connected together in three tier fashion to serve the presentation logic and data aspects of dynamic websites the web server and the system server communicating in HTML CSS and JavaScript and the system server and the database server communicating in SQL.

The clients may communicate with the web server using the HTTP protocol to interact with the websites. More particularly the creator s client may communicate to create a website the manager s client may communicate to manage a website and the end user s client may communicate to use a website.

To implement this arrangement the devices each host an operating system that provides an execution Environment supporting the required functionality. The operating systems might also support distributed execution among the devices .

In this way the clients each support a browser component to implement communication with the web server for example such as Microsoft Internet Explorer Firefox Safari or Opera . The creator s client and the manager s client might also support an editor applet component to better implement communication with the system server for editing website objects as will be discussed further below.

Similarly the servers have dedicated components supported by the operating system execution environment. The web server has a web server component that instructs it on how to perform its role as a web server for example Apache Apache Microsoft Internet Information Services or Google Google Web Server . The system server has an object editor component and an object renderer component that respectively instruct it on how to create modify and destroy objects that represent aspects of a website and to render the objects into webservings that can be communicated by the web server . The database server has a database management system component that instructs it on how to create store search maintain and destroy objects that represent aspects of a website drawn from a website package of classes which will be described further with respect to .

The hardware layer provides the device with computing and communication hardware including a a processor to execute processes of instructions and compute data b user input hardware such as a keyboard and a selection device for example a mouse to receive input from a user c user output hardware such as a video display to provide information to a user d mass storage such as electromagnetic optical or nonvolatile solid state media to store data and processing instruction s e memory such as read only memory and random access memory to store data and processing instructions and f a network interface to support communication with other devices in accordance with known protocols such as TCP IP all interconnected by buses such as address and data buses and control lines such as interrupt and clock lines and such other connections and components as is conventionally required and known in the art.

Stored in a portion of the read only memory and the mass storage arc the components of the operating system layer for example LINUX or Microsoft Windows Server for a device such as general purpose programmable computer configured as a server or LINUX or Microsoft Windows VISTA for a device configured as a client or even Microsoft Windows CE for a portable such client device . The operating system layer provides the basic instructions to direct the processor how to interact with the other hardware described above and more generally how to perform the functions of a communication and computing device including storing accessing and computing data and communicating with other devices .

The operating system layer also presents an application program interface to the application program layer so the processor can execute more sophisticated combinations of processes under the direction of higher level application programs stored in mass storage and loaded into RAM for execution for example the components described in .

The storage tier package could also include a Digital Assets class for representing digital assets and a Databases class for representing databases. The Databases class could include a number of aggregate classes including a User Defined Tables class for representing the data structure including for example fields represented by a User Fields class a Search Queries class for representing search queries and a Search Query Results class for representing query results. The storage tier package might also include an Object Configuration class for representing the configuration of objects including for example object persistence as represented by an Object Persistence class . Additionally the storage tier package might include classes for representing content for the website for example a Content Lists class that represents a cataloguing of content items as represented by a Content Items class . The Content Items class might in turn include a number of aggregate classes such as a User Data Nonstructured class representing unstructured data and a User Data Structured class representing structured data for example data having an author title and body as respectively represented by an Author class a Title class and a Body class .

Those skilled in the art will recognize the hierarchical nature of the classes and packages contained in the Website package such that traversing the tree of the hierarchy will produce a definition of the website or of that portion defined by the portion of the tree traversed.

Thus graphically depict the types of classes within an exemplary system and the relationships between them. Many sites as well as their child objects can be hosted and managed by the system at once. As shown a site object can contain one or more page objects which in turn can contain one or more widgets page elements etc.

Each of the objects of the system has a defined set of behaviors properties and events. Once a site object has been created the manager can create update and delete styles pages content lists database tables workflows and digital assets completely independently from each other. All object configurations are stored in the database management system to enforce data integrity versioning search and retrieval.

After a site and its related objects have been configured the system is ready to serve data to client browser requests. When a browser requests data e.g. a particular web page the system dynamically creates the data necessary for the web browser to render the page accurately to the end user. This is done by traversing the object tree associated with a given request reading the correct version of each object from the database binding all object data together and lastly creating an HTML representation of the requested data. This technique allows all of a web site s objects to be treated and handled in a truly object oriented manner on the server side while ultimately transforming them into the structural elements HTML CSS Image files needed by a web browser to render and interact with end users of the website.

The GUI includes four main regions a WYSIWYG design region an objects catalog region an object property table region and a button pad region .

The catalog region includes an existing objects list that catalogs all objects that currently exist to represent aspects of the website and an object palette that catalogs all available classes for representing aspects of a website for which objects may be instantiated.

The design region provides a what you see is what you get area for laying out the presentation aspects of a portion of a website for example placing and sizing content item objects widgets . A context menu may be available to conveniently set various common properties of a selected one of the content item objects .

The object property table provides a way to inspect and modify the properties of a selected object including objects that may not be conveniently represented in the design region such as objects instantiating classes in the logic tier package or the storage tier package .

The button pad region provides a create button a destroy button and a modify button . The create button instantiates an object selected from the object palette and presents it for inspection and modification in the object property table . The destroy button destroys the selected object. The modify button presents the selected object in the object property table from inspection and modification.

In operation a website creator or website manager creates or manages a website through the GUI described in . He can select from the existing objects catalog any of the objects that currently represent aspects of the website and the selected object will be presented in the object property table and in the case of objects that can be represented by the WYSIWYG paradigm selected in the design region . The properties of the selected object can be modified in the object property table upon pressing the modify button . Alternatively common properties of objects presented in the design region can be modified using the context menu .

Objects in the WYSIWYG design area can be selected moved resized reflowed etc. as directed by the mouse or another user input device . New objects can be dragged from the object palette and placed as desired onto the design area.

Pressing the create button instantiates an object selected from the object palette and presents it for inspection and modification in the object property table . Pressing the destroy button destroys the selected object.

In general the object editor presented in a standard web browser hosts web pages and objects that form the user interface for creating and managing websites including pages forms tables and structured content. All user interface elements within the object editor can be hosted in an AJAX standard web browser with no client side plug ins. The object editor sends user input and receives and renders system responses via standard internet technologies namely using the AJAX design pattern along with XHMTL compatible data all transferred via http to a standard web server .

The web server redirects all traffic from the object editor or from the client s browser to the system server . In simplest terms the system server is responsible for storing page and content data changes received from configuration tool or from display and returning data changes in a manner that is compatible for a browser to properly render it visually. All data changes are stored and retrieved from relational database . In this regard the web server provides an interface operable to present representations of and functions as means for representing objects instantiating the plurality of hierarchical classes and to receive commands meant to one of 1 instantiate a new object 2 destroy a presented object and 3 change a property of a presented object. As embodied this interface includes a user interface and in fact a WYSIWYG user interface this representation includes symbolic representation and the commands include user input.

The database server performs standard database tasks for the system including persistence and retrieval indexing and search transactions and rollback enforcement of data typing and relational integrity as well as replication and archiving.

At a deeper level the system server consists of a complete or partial set of the objects that define a website with one topmost Website object for each user s web site as well as objects for each page table content item etc. that a given site may contain. Each object is derived from a set of hierarchical classes and sub classes that allow each object to 

In this regard system server provides and functions as means for providing a plurality of hierarchical classes of objects each of the classes representing one aspect of the storage presentation and logic of a website.

By using object orientation new object in stances or classes of objects can be added to the system or changed without affecting other objects in the system . Further new objects can be derived from existing objects thereby inheriting the features of the base object while still allowing customization of the new object. For example a blog object can be created that is based upon the content list object thereby inheriting its storage and enumeration mechanism while allowing its own encapsulated version control. In this regard the database server stores and functions as means for storing objects as a traversable tree in accordance with the plurality of hierarchical classes.

Referring now to when a website end user wants to use a website he directs the browser component on his device to the web server to request presentation of a particular portion of the website. That portion might be a webpage or a lesser portion for example in the case of AJAX techniques.

The web server component on the web server receives this request and conveys it to the system server where the object renderer component receives it.

In a receipt and parsing step the request for webserving is parsed to determine what is being requested and what portion of the website the request relates to.

In a define webserving step the objects that define the portion of the website relevant to the request are read by traversing the tree hierarchy of the objects.

In a render webserving step a webserving is assembled in HTML CSS and JavaScript code that renders requested portion of the website as defined in the relevant objects.

In a transmit webserving step the webserving is transmitted to the web server for transmission to the browser component of the end user.

Thus the system server renders and functions as means for rendering a requested portion of a website by traversing the corresponding portion of the object tree and generating a dynamic webserving in response to the properties of the traversed objects.

In greater detail referring back to when the end user requests a given web page within a given site the request via an URL e.g. http yoursite.com page1 is transferred via the web server and http to the system server . Within the system server the top level website object locates requested page object from the object repository in the DBMS . Next the published version of the page object enumerates all of the published versions of each widget object s contained within the requested page object and tells them to create themselves. Note that the page object has no knowledge of the internals of each widget their versioning information data format on disk or how they behave is all encapsulated within each widget object. Note also that any changes to the page e.g. new deleted updated widgets would automatically be reflected each time a page is requested.

Once each page widget is created in memory it is activated allowing each widget to run its own specific code and bind to its data. In the case of content block widgets or list viewers the data is retrieved by binding to and reading from content list objects. Each widget on a given page binds its own data source for example with reference to the page binds the content block widget and the other widget and the other widget binds its data source.

Once a content list object is requested by a content block widget it enumerates and creates its child objects content item s . Again each list item is an object encapsulating the knowledge of its internal versions and state information as well as how to read process and present its data within itself.

Once each page widget object has been created performed its initialization and received its data from it data sources e.g. content lists it renders itself within the page container for viewing in the end user s browser . That is each widget dynamically produces the HTML CSS and JavaScript necessary within the requested page for rendering in the web browser and processing of user input.

Lastly the system server sends the fully rendered page or only the changed portion of the page if the page is already loaded within the end user s browser back to the end user s browser for presentation and user input.

Obviously many modifications and variations of the present invention are possible in light of the above teachings and may be practiced otherwise than as specifically described while within the scope of the appended claims. In addition the reference numerals in the claims are merely for convenience and are not to be read in any way as limiting.

