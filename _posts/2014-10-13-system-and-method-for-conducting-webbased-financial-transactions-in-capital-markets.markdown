---

title: System and method for conducting web-based financial transactions in capital markets
abstract: The present invention provides a system and method that enables users, such as institutional investors and financial institutions, to interactively engage in capital market transactions, including the trading of Over-the-Counter financial products, via the Internet (including the World Wide Web). The system includes a variety of servers, applications, and interfaces that enable users to interactively communicate and trade financial instruments among one another. Interactive communications supported by the system include: requesting price quotes, monitoring and reviewing quote requests, issuing price quotes, monitoring and reviewing price quotes, negotiation between users, acceptance of price quotes, reporting, portfolio management, analysis of financial information and market data, and communications among users via an automated processor. Such automated communications enable connectivity with users' internal, back-end systems to execute automated, straight-through processing, including transaction pricing, payment scheduling and journaling, derivatives trading, trade confirmation, and trade settlement.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09412134&OS=09412134&RS=09412134
owner: INTEGRAL DEVELOPMENT CORPORATION
number: 09412134
owner_city: Palo Alto
owner_country: US
publication_date: 20141013
---
This application is a divisional of U.S. patent application Ser. No. 10 105 084 having a filing date of Mar. 22 2002 entitled SYSTEM AND METHOD FOR CONDUCTING WEB BASED FINANCIAL TRANSACTIONS IN CAPITAL MARKETS which is a continuation in part application of U.S. patent application Ser. No. 09 703 198 filed Oct. 31 2000 entitled SYSTEM AND METHOD FOR CONDUCTING WEB BASED FINANCIAL TRANSACTIONS IN CAPITAL MARKETS . This application incorporates by reference i U.S. Provisional Patent Application Ser. No. 60 139 113 filed Jun. 14 1999 entitled SYSTEM AND METHOD FOR AN XML VOCABULARY FOR CAPITAL MARKETS ii U.S. Provisional Patent Application Ser. No. 60 162 873 filed Nov. 1 1999 entitled METHOD AND APPARATUS FOR WEB BASED MANAGEMENT OF FINANCIAL RISK AND PRICING AND TRADING OF FINANCIAL PRODUCTS iii U.S. patent application Ser. No. 09 593 324 filed Jun. 13 2000 entitled SYSTEM AND METHOD FOR CONDUCTING WEB BASED FINANCIAL TRANSACTIONS IN CAPITAL MARKETS now U.S. Pat. No. 6 347 307 and iv U.S. patent application Ser. No. 09 703 198.

This invention relates generally to the field of interactive and automated Web based financial transaction applications and in particular to interactive and automated systems and methods for conducting financial transactions and managing portfolios and related financial information in capital markets.

During the evolution of the Internet including the World Wide Web there has been a continual introduction of applications and services to enable individuals and organizations to conduct financial research manage their financial portfolios and engage in certain types of financial transactions. The wide array of applications and services ranges from on line banking to stock quote and financial information services to sites that enable users to engage in on line real time market trades involving various instruments such as stocks stock options bonds and mutual funds. The trading services for example E TRADE Securities Inc. s E TRADE Charles Schwab Co. Inc. s Schwab.com and Fidelity Brokerage Services Inc. s Fidelity.com permit trading of standard instruments in recognized markets. In such services the investor uses credit or an account set up through the trade service to engage in trades through the service s proprietary system and interfaces. Such services which are geared towards individual investors do not permit seamless integration with users internal or back end systems or the creation and trading of customized transactions. These services and many others like them do not enable trading between parties in currency derivatives or foreign exchange or the pricing and modeling of other capital market transactions.

Some steps have been taken to tap into the potentially vast market of institutional investors wishing to engage in complex transactions via the Internet. The Open Financial Exchange Intuit Inc. Microsoft Corp. CheckFree Corp. was created to provide a common specification for the electronic exchange of financial data between financial institutions businesses and consumers via the Internet that enables financial data exchange among disparate systems in order to support online banking bill payment and presentment and the trading of stocks bonds and mutual funds. The Open Financial Exchange does not however provide a vocabulary platform and communication protocol to enable the creation negotiation and execution of complex capital market transactions among financial institutions and institutional investors.

What is needed is a system and method that enables institutional investors and financial institutions to seamlessly create price negotiate execute settle and analyze complex capital market transactions including interest and currency derivatives foreign exchange loans and deposits and fixed income instruments in an online environment using a standard vocabulary and messaging system that enables seamless integration with the proprietary existing systems of the users.

The present invention provides a system and method that enables users such as Members e.g. institutional investors and Providers e.g. banks financial institutions to engage in capital market transactions including the trading of Over the Counter financial products via the Internet including the World Wide Web . The system includes a variety of servers applications and interfaces that enable users to interactively communicate and trade financial instruments among one another and to manage their portfolios. Interactive communications supported by the system include establishing credit relationships structuring financial transactions requesting price quotes monitoring and reviewing transaction requests issuing price quotes monitoring and reviewing price quotes negotiations between Members and Providers acceptance and confirmation of price quotes reporting portfolio management analysis of financial information and market data and communications among Members Providers and or system administrators including e mail chat and message boards.

The present invention also supports communications with the server side in an automated manner via an automated processor the Connect Processor and Connect Messaging Server . Such automated communications enable connectivity with users internal back end systems to execute automated straight through processing including transaction pricing payment scheduling and journaling derivatives trading trade confirmation and trade settlement. Such communications are facilitated using a novel XML based syntax FinXML and XSL based processing language FinScript . FinXML provides a standard data interchange language for capital market transactions and supports a broad set of elements and attributes that represent a wide variety of financial transactions reference data and market data. The common description of the FinXML syntax can be used for all aspects of straight through processing including deal creation confirmation settlement payment risk management and accounting.

The technology of the present invention can be embodied in various forms to provide a platform for conducting interactive and automated financial transactions and management of portfolios and related financial information in capital markets. The platform enables members including end users and providers of financial products and services to engage in the trading of standard and customized financial instruments in capital markets. System functionality includes capture and pricing of financial instrument trades presentation of real time market data saving of completed trades to a portfolio management of trading workflow transmission of trades to end users proprietary back end systems for pricing trading payment processing confirmation and settlement performance of portfolio analysis performance of risk management analysis and inter user communications.

In the present embodiment of the invention the system includes both server side and client side functionality. The server side functionality enables system users to interactively and seamlessly engage in financial instrument trades perform portfolio management analysis and reporting obtain real time market data and news communicate with the system and other users via electronic mail chat and message boards and maintain a calendar. The server side includes interactive system servers that host such user activities as well as one or more system databases and an automated messaging server that controls communication with the automated back end systems of clients.

The client side functionality includes an automated processor that communicates with the automated messaging server of the system side and serves as a seamless interface to the automated back end systems and proprietary databases of clients. Thus the system enables organizations with disparate systems and data to engage in transactions using the common functionality and interfaces of this invention. The client side also includes client web browsers that enable interactive communication with the system servers.

The invention described herein provides a standard XML based vocabulary to represent and facilitate the financial transactions as well as a system and method for converting users data and information to from the standard vocabulary and communicating such information through the system in an automated manner.

When a company and bank decide to engage in financial transactions the parties first establish their relationship by executing certain standardized agreements step . Such agreements govern the rules of engagement rate sources confirmation and settlement ocedures and other information that can be reused over a series of transaction between the parties. The International Swaps and Derivatives Association Inc. ISDA provides certain standardized agreements e.g. 1992 ISDA Master Agreement that may be used by the parties for these purposes. The company and bank may engage in multiple iterations of this step depending upon the number of standardized agreements that the parties will execute.

Next the company and bank negotiates one or more lines of credit to be assigned by the bank to the company for future transactions step . In assigning a credit line to a company the bank analyzes the company s asset portfolio credit ratings and type of financial transactions to be executed by company.

Once the company and bank have established their relationship and negotiated a credit line the company can commence the process of engaging in a financial transaction. The company must decide on the type of transaction it wishes to execute e.g. Foreign Exchange Spot Foreign Exchange Forward Interest Rate Swap etc. and structure the desired transaction step including the various details and parameters. For example the company might specify a Foreign Exchange Spot transaction in which the company desires to buy 1 million Euro currency for U.S. Dollars with the transaction request set to expire on Dec. 1 2000 at 11 59 P.M. Pacific Standard Time.

After structuring the transaction the company communicates a request for pricing of the transaction to one or more banks step . Each such bank in turn receives and reviews the company s pricing request step . If interested in the company s transaction the bank can create a pricing offer for the transaction step and submit the pricing offer i.e. price quote to the requesting company step . Each pricing offer typically has an expiration period because of constantly changing market conditions and the bank may submit modified pricing offers to the company based on market conditions and negotiations.

The company receives and reviews any pricing offers submitted by banks step . The company selects one or more pricing offers step and negotiates with the particular bank s who provided the offer s . The number of iterations of negotiations depends upon the market volatility and other conditions. Upon completion of such negotiations regarding pricing offers the company accepts a pricing offer and communicate its acceptance to the offering bank step .

Upon receipt of the company s acceptance of its pricing offer the bank sends confirmation of the transaction to the company step including specific terms payment dates and amounts. Following confirmation the company and bank schedule settlement of the transaction and future payments related to the transaction step .

In describing the present embodiment of this invention the descriptive terms Member and Provider are used to identify the parties on the opposite sides of financial transactions e.g. buyer and seller of foreign exchange . In this and other embodiments of this invention however users defined as Members can engage in transactions with other Members and users defined as Providers can engage in transactions with other Providers in such transactions one user will occupy the position of Member and utilize the Member functionality and the other user will occupy the position of Provider and utilize the Provider functionality.

The server side sometimes referred to as the CFOWeb System in this embodiment communicates with the client side consisting of users known as Members e.g. corporations and institutional investors and Providers e.g. financial institutions via the Internet including the World Wide Web . The server side includes a variety of interactive system servers that provide functionality to users. Web server enables communications through the Internet via a transfer protocol such as e.g. HyperText Transfer Protocol HTTP or TCP IP between users who connect to the server side through their web browsers and the various system servers. Trading server provides a graphic user interface and applications that enable users to interactively trade financial derivatives among each other. Portfolio management server provides a graphic user interface and applications that enable users to manage their portfolios of financial derivatives. Reports server provides a graphic user interface and applications that enable users to run and produce standard and customizable reports regarding their portfolios including mark to market upcoming events and trade lists. Analysis server provides a graphic user interface and applications that enable users to run analytics against their portfolios including valuation and interest rate sensitivity. Calendar server provides a graphic user interface and applications that enable users to automatically calendar key dates regarding settlement payments cash flows and other details related to their financial derivative transactions and portfolios. News and research server provides a graphic user interface and applications that enable users to obtain real time market data and financial and other news as well as proprietary third party data feeds. News and research server includes connections to real time market data feeds and news services and third party data feeds .

The interactive system servers also include servers that enable communication among system users and administrators. Chat server provides real time chat thus enabling users to engage in discussion forums related to financial derivatives. Paging server enables users to build a messaging community and determine which users are online and available to receive messages at a given instance i.e. instant messaging . E mail server provides an intra system electronic mail vehicle enabling communications among users and system administrators including all aspects of a financial trade from quote requests to settlement. Message boards server provides an arena for users and system administrators to post and read system wide messages as well as quote requests and quotes.

Automated messaging server sometimes referred to as the Connect Messaging Server in this embodiment controls communications through the Internet via a transfer protocol e.g. HTTP or TCP IP between the various system servers of the server side and users whose internal back end systems execute automated processes that require communication with the server side. Such automated processes could include transaction pricing payment scheduling and journaling derivatives trading trade confirmation and trade settlement . Communications between Connect Messaging Server and the client side pass through automated processor sometimes referred to as the Connect Processor in this embodiment which shares the same functionality as automated messaging server and automated message broker and are facilitated using the FinXML vocabulary and the FinScript processing language as described below.

The CFOWeb System includes one or more system databases which store data related to the processing of financial transactions as well as user communications and interactions with the system servers.

The client side includes functionality that enables users Members and Providers to communicate either interactively or in an automated manner with the various system servers. Web browser enables interactive communications through the Internet via a transfer protocol e.g. HTTP or TCP IP between users and the CFOWeb System with connection made on the server side at web server . Interactive communications might include requesting price quotes Members monitoring and reviewing quote requests Providers issuing price quotes Providers monitoring and reviewing price quotes Members negotiation between Members and Providers acceptance of price quotes Members reporting portfolio management analysis of financial information and market data calendaring and communications among Members Providers and or system administrators including e mail chat and message boards.

Alternatively users can communicate with the server side in an automated manner via Connect Processor and automated message broker which communicates through the Internet via a transfer protocol e.g. HTTP or TCP IP with Connect Messaging Server . Such automated communications enable users internal back end systems which include one or more back end databases to execute automated processes which could include transaction pricing payment scheduling and journaling derivatives trading trade confirmation and trade settlement . Such communications are facilitated using the FinXML vocabulary and the FinScript processing language as described below.

For system users Members and Providers the functionality included in an embodiment of this invention can be categorized as follows pre transaction transaction post transaction and general. The present invention i automates and or ii provides an interactive interface for such functionality.

Members and Providers or in other embodiments of this invention Members and Members that engage in a financial transaction of a type enabled by this invention proceed through a series of steps illustrated in . When a Member and Provider decide that they may engage in financial transactions in the future the parties establish their relationship by executing certain agreements step . Such agreements e.g. 1992 ISDA Master Agreement govern the rules of engagement rate sources confirmation and settlement procedures and other information that can be reused over a series of transaction between the parties. The parties can carry out this step by using the interactive e mail function of the system provided by e mail server in to exchange information to be included in the agreements. In addition by combining off the shelf electronic signature software with the system the parties can electronically sign and exchange the standardized agreements. Members and Providers may engage in multiple iterations of this step depending upon the number of standardized agreements that the parties will execute.

Next the Member and Provider will negotiate one or more lines of credit to be assigned by the Provider to the Member for future transactions step . Each Member will negotiate such line s of credit with each Provider with which the Member intends to engage in future transactions. In assigning a credit line to a Member the Provider will analyze the Member s asset portfolio credit ratings and type of financial transactions to be executed by Member. The parties can carry out this step via the Credit Relationships interactive user interface shown in described below in which a Member can specify one or more Providers to receive electronic requests via the system to establish credit relationships. Alternatively the parties can carry out this step using the interactive e mail function of the system provided by e mail server in the paging instant messaging function of the system provided by paging server in or the chat function of the system provided by e mail server in to exchange information during the credit line negotiations.

Once the Member and Provider have established their relationship and negotiated a credit line the Member can commence the process of engaging in a financial transaction. The Member must decide on the type of transaction it wishes to execute e.g. Foreign Exchange Spot Foreign Exchange Forward Interest Rate Swap etc. and structure the desired transaction step . In this step the Member will use the interactive trading function of the system provided by trading server in including graphic user interfaces and tools. Depending upon the type of transaction the structure might include pricing variables an expiration period a list of Providers to whom the Member would like to request pricing and any other particulars specific to the Member and the desired transaction. For example a Member might specify a Foreign Exchange Spot transaction in which the Member desires to buy 1 million Euro currency for U.S. Dollars with the transaction request set to expire on Jul. 30 2000 at 11 59 P.M. Pacific Standard Time.

After structuring the transaction the Member submits a request for pricing of the transaction to one or more Providers step using the interactive trading function of the system provided by trading server in . Alternatively the Member might communicate a request for pricing directly to a particular Provider using the interactive e mail function of the system provided by e mail server in . Such an e mail communication would include a URL to the structured transaction and request for pricing.

Providers monitor and review the Member s pricing request step via communications between the automated messaging server and automated processor as will be described below. Such communications result in the posting of pricing requests on a request monitoring interface hosted by the system. Upon reviewing the transaction and pricing request on the interactive monitoring interface including information about the particular Member unless the Member s identity was not disclosed a Provider can create and submit a pricing offer i.e. price quote to the requesting Member step . The Provider creates the pricing offer using the interactive interfaces described below controlled by trading server . The submission of the pricing offer occurs via a communication between the automated processor and automated messaging server as will be described below. Each pricing offer typically has an expiration period because of constantly changing market conditions and the Provider may submit multiple iterations of modified pricing offers to the Member. In some embodiments of this invention the Provider can modify the structure of the Member s transaction e.g. change the transaction amount step before creating and submitting the pricing offer to the Member. Such modification may proceed through multiple iterations.

The Member can monitor and review any pricing offers submitted by Providers step on an interactive monitoring interface hosted by the system. The Member will select one or more pricing offers step and negotiate with the particular Provider s who provided the offer s . In the present embodiment such negotiations may occur using the interactive e mail function of the system provided by e mail server in the paging instant messaging function of the system provided by paging server in or the chat function of the system provided by chat server in or through traditional methods e.g. telephone calls . The number of iterations of negotiations will depend upon the market volatility and other conditions. In other embodiments of this invention such negotiations may be unnecessary if certain parameters are met by a Provider s pricing offer. Note that at this stage in the process the Member may decide to modify the structure of the Member s original transaction e.g. change the transaction amount step and submit a new pricing request to one or more Providers step . Such modification may proceed through multiple iterations.

Following negotiations regarding pricing offers the Member will accept the best pricing offer step and communicate its acceptance to the Provider using the interactive trading function of the system provided by trading server in . The Provider will receive the Member s acceptance via communications between the automated messaging server and automated processor as will be described below. Such communications result in the posting of the Member s acceptance of the pricing offer on the request monitoring interface hosted by the system.

Upon receipt of the Member s acceptance the Provider sends confirmation of the transaction to the Member step including specific terms payment dates and amounts. The Provider sends the confirmation information to the Member via communications between the automated processor and the automated messaging server as will be described below. The Provider s back end system provides automated processing of this information.

Following confirmation the Member and Provider will submit the transaction to their respective back end systems step for purposes including internal accounting and payment scheduling. This step can be handled by the system via an automated connection between the automated processor and the back end system . Using their respective back end systems the Member and Provider schedule settlement of the transaction and future payments step .

Interactive system functionality that can be accessed and implemented at any time by the Member and Provider includes reporting portfolio management risk management analysis of financial information and market data e mail communication with Members Providers and system administrators chat with Members and Providers message boards calendaring and paging. This functionality is made available to Members and Providers via buttons and or pull down menus on the system s interactive user interfaces described below .

The present embodiment of this invention supports financial transactions between Members and Providers by providing automated processing and transfer of the underlying financial information between the messaging server of the server side and the automated processor of the client side. The system enables such processing and transfer by using a novel tag based language FinXML that describes financial instrument trades including transaction specific data reference data and market data. FinXML conforms to the Extensible Markup Language XML 1.0 Recommendation Feb. 10 1998 World Wide Web Consortium Massachusetts Institute of Technology Institut National de Recherche en Informatique et en Automatique Keio University . The XML Recommendation describes a set of rules for conforming documents that is based around the use of element tags which mark the components of a document or describe the structure of data files as textual documents.

FinXML also conforms to the 1991 ISDA Definitions and 1998 Supplement of the International Swaps and Derivatives Association Inc. ISDA . The ISDA Definitions provide a set of standard terms for use in privately negotiated financial derivatives transactions. The element tags and attribute names and values defined in FinXML as described below correspond to the terms defined in the ISDA Definitions.

FinXML as a type of XML vocabulary is ideally suited to electronic transmission over corporate intranets extranets and the Internet including the World Wide Web using a transfer protocol such as HTTP or TCP IP. The HTTP protocol is intended to transmit text documents such as the HyperText Markup Language HTML documents used to describe the pages to be displayed in a Web browser. XML documents and thus FinXML documents are similar to HTML documents in that both types of documents are text based both consist of a mixture of element tags and data content and both may include references to other external material.

In a basic financial transaction between two organizations a financial transaction encoded in XML is sent using a transfer protocol such as HTTP or TCP IP from a client application of one organization to a server of the other organization. The server in turn sends back a response that is also encoded in XML.

As will be described below the present embodiment of this invention includes a novel method of encoding decoding financial objects to from FinXML or other XML documents using the automated processor also known as Connect Processor and automated messaging server also known as Connect Messaging Server . In a financial transaction between two organizations one organization e.g. a Member submits a Java object to automated processor which as will be described below uses a XML mapping and FinScript proprietary stylesheets created in Extensible Stylesheet Language XSL to create a FinXML or other XML document that can be sent using a transfer protocol such as HTTP or TCP IP to the automated messaging server for conversion to an object and processing on the server side. Following processing the automated messaging server converts objects to a FinXML or other XML document and sends the document to the automated processor which as will be described below uses FinScript to create a JavaScript program from the FinXML or other XML document. In turn Java objects are created from the JavaScript program and sent to the other organization e.g. a Provider . XSL which serves as the foundation for FinScript is described in the Extensible Stylesheet Language XSL Version 1.0 Mar. 27 2000 World Wide Web Consortium Massachusetts Institute of Technology Institut National de Recherche en Informatique et en Automatique Keio University .

In the present embodiment of this invention FinXML documents are distributed between servers in order to communicate the details of financial transactions and related data. The FinXML syntax provides a general structure for all financial transactions. The financial transactions in turn consist of underlying elements each of which contains attributes and or other elements.

The basic financial transaction element of the FinXML syntax is a Trade of which there are multiple types described below . The Trade element is the root element for the description of each financial transaction object. The Trade element is contained within the Connect message payload component described below .

Each Trade Type element represents a different type of financial transaction which will be described separately below. Note that other embodiments of this invention may include combinations of one or more of the Trade Type elements described herein as well other trade types.

The FinXML syntax describes various types of data that comprise a financial transaction including transaction data reference data and market data. Each of these types of data includes elements and attributes. Note that the elements attributes and definitions of the types of data described herein are illustrative of one embodiment of this invention other embodiments of this invention may include some or all of these elements attributes and or definitions as well as other elements attributes and or definitions to describe the included types of data.

Transaction data describes the various components of a financial transaction or trade. These components include Counterparty elements Trade Type elements Trade Specific elements Financial Event elements and Calculation elements.

In a financial transaction of the type described by FinXML there are typically two parties also referred to as counterparties . As described above FinXML describes such parties to a transaction with Counterparty element as shown in including an Internal Party element and an External Party element. In the present embodiment of this invention Counterparty element has the following XML definition 

In each transaction from the perspective of an organization that organization is the internal party and the other unrelated organization is the external party e.g. a corporation and a third party bank that engages in a foreign exchange transaction. Alternatively where a corporation engages in a transaction with a subsidiary legal entity within the corporation the subsidiary is also an internal party.

Disclosed Party element represents a party to a transaction e.g. a Member whose details including corporate identification are fully known to the other party to the transaction. Each Disclosed Party element includes the following sub elements described in greater detail below in the discussion regarding Reference Data elements Organization Contact Information Address and Credit Rating . In the present embodiment of this invention Disclosed Party element has the following XML definition 

Undisclosed Party element represents a party that remains anonymous to the other party the only information disclosed is the party s credit rating. Thus each Undisclosed Party element includes the Credit Rating element described in greater detail below in the discussion regarding Reference Data elements . In the present embodiment of this invention Undisclosed Party element has the following XML definition 

As shown in Trade element includes Trade Type element . Each Trade Type element in turn includes a Trade Type sub element that describes one type of financial transaction or trade.

A Foreign Exchange Spot FX Spot transaction is one in which one party acquires a specified quantity of one currency in exchange for another currency from another party to be paid or settled as soon as is standard i.e. usually two days in the foreign exchange market. For example a Member buys from a Provider 2 million Euro for U.S. Dollars to be paid in two days.

The FX Spot element represents such a transaction and includes the following sub elements and attributes 

 Value Date the date on which the traded currencies will be exchanged i.e. the trade will be settled .

 Base Units the number of units of the Base Currency against which the currency to be acquired will be quoted usually one unit .

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

A Foreign Exchange Forward FX Forward transaction is one in which one party acquires a quantity of one currency in exchange for a specified amount of another currency from another party with the amounts to be paid on a specified future date. For example a Member buys from a Provider 2 million Euro for U.S. Dollars to be paid 60 days from the trade date.

The FX Forward element represents such a transaction and includes the following sub elements and attributes 

 Value Date the date on which the traded currencies will be exchanged i.e. the trade will be settled .

 Base Units the number of units of the Base Currency against which the currency to be acquired will be quoted usually one unit .

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

An Interest Rate Fixed Float Swap is a type of interest rate swap in which two parties exchange periodic payment streams where one payment stream is based on a fixed interest rate and the other payment stream is based on a floating rate index e.g. LIBOR with each payment stream in the same currency. For example a Member buys from a Provider a fixed payment stream in Euro in exchange for a floating payment stream in Euro based on the LIBOR index.

The Interest Rate Fixed Float Swap element represents such a transaction and includes the following sub elements and attributes 

 Events the various payment and calculation events in the swap transaction including cash payment principal payment interest payment interest calculation compound interest calculation and interest rate reset information.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Interest Rate Fixed Float Swap element has the following XML definition 

An Interest Rate Float Float Swap is a type of interest rate swap in which two parties exchange periodic payment streams where each payment stream is based on a floating rate index e.g. LIBOR with each payment stream in the same currency. For example a Member buys from a Provider a floating payment stream in Euro in exchange for a floating payment stream in Euro where each payment stream is based on the LIBOR index.

The Interest Rate Float Float Swap element represents such a transaction and includes the following sub elements and attributes 

 Float Leg Details the details of the floating interest payments separate information for each of the two floating legs.

 Events the various payment and calculation events in the swap transaction including cash payment principal payment interest payment interest calculation compound interest calculation and interest rate reset information.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Interest Rate Float Float Swap element has the following XML definition 

A Cap transaction is one in which one party in exchange for a premium payment acquires from another party the right to receive a payment stream i.e. a series of options Caplet from the other party with respect to a specified quantity of one currency if on the scheduled payment dates the level of a specified rate or index exceeds an agreed strike rate for the period involved. For example a Member purchases from a Provider an interest rate cap at a strike rate of 8 percent on U.S. Dollars based on the 3 month LIBOR for a period of 12 months in order to hedge its exposure to increasing interest rates on a 10 million U.S. Dollars floating rate loan based on the 3 month LIBOR.

The Cap element represents such a transaction and includes the following sub elements and attributes 

 Premium Details the details of the premium to be paid as either a percentage Premium Percentage or a specified amount Premium Amount and the payment date Premium Date .

 Strike Rate the rate that if exceeded will trigger the settlement of a single payment Caplet within the Cap transaction.

 Writer the recipient of the premium for the option to be exercised this is a reference to a Counterparty element.

 Volatility Spread the spread over the volatility calculated using the volatility surface an additional spread for pricing the cap transaction.

 Rate Reset Calendar the calendar to be used for reference to business holidays for interest rate resets.

 Anchor Date the date to which the payment schedule is anchored i.e. the end date of the first interest period or specific date of first payment could be the start of the last interest period if dates generated in reverse.

 Amortization Details details regarding how the payment cashflow should be amortized including amortization method e.g. single payment at end equal payments over term of stream .

 Compounding Details details regarding how the interest should be compounded including calculation frequency and rate.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

A Floor transaction is one in which one party in exchange for a premium payment acquires from another party the right to receive a payment stream i.e. a series of options Floorlet from the other party with respect to a specified quantity of one currency if on the scheduled payment dates the level of a specified rate or index is less than an agreed strike rate for the period involved. For example a Member purchases from a Provider an interest rate floor at a strike floor level of 8 percent on U.S. Dollars based on the 3 month LIBOR for a period of 12 months in order to protect its investment returns on a 10 million U.S. Dollars money market investment based on the 3 month LIBOR.

The Floor element represents such a transaction and includes the following sub elements and attributes 

 Premium Details the details of the premium to be paid as either a percentage Premium Percentage or a specified amount Premium Amount and the payment date Premium Date .

 Strike Rate the rate that if exceeded will trigger the settlement of a single payment Floorlet within the Floor transaction.

 Writer the recipient of the premium for the option to be exercised this is a reference to a Counterparty element.

 Volatility Spread the spread over the volatility calculated using the volatility surface an additional spread for pricing the cap transaction.

 Rate Reset Calendar the calendar to be used for reference to business holidays for interest rate resets.

 Anchor Date the date to which the payment schedule is anchored i.e. the end date of the first interest period or specific date of first payment could be the start of the last interest period if dates generated in reverse.

 Amortization Details details regarding how the payment cashflow should be amortized including amortization method e.g. single payment at end equal payments over term of stream .

 Compounding Details details regarding how the interest should be compounded including calculation frequency and rate.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

A Fixed Rate Loan Deposit transaction is one in which one party borrows a sum of money from another party at a fixed interest rate. For example a Member borrows from a Provider 1 million U.S. Dollars at a fixed interest rate for one year.

The Fixed Loan Deposit element represents such a transaction and includes the following sub elements and attributes 

 Anchor Date the date to which the payment schedule is anchored i.e. the end date of the first interest period or specific date of first payment could be the start of the last interest period if dates generated in reverse.

 Amortization Details details regarding how the loan payment cashflow should be amortized including amortization method e.g. single payment at end equal payments over term of loan .

 Compounding Details details regarding how the loan interest should be compounded including calculation frequency and rate.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Fixed Loan Deposit element has the following XML definition 

A Floating Rate Loan Deposit transaction is one in which one party borrows a sum of money from another party at a variable interest rate generally based on a floating rate index e.g. London Interbank Offered Rate or LIBOR . For example a Member borrows from a Provider 1 million U.S. Dollars at a variable interest rate for two years.

The Floating Loan Deposit element represents such a transaction and includes the following sub elements and attributes 

 Rate Reset Calendar the calendar to be used for reference to business holidays for interest rate resets.

 Anchor Date the date to which the payment schedule is anchored i.e. the end date of the first interest period or specific date of first payment could be the start of the last interest period if dates generated in reverse.

 Amortization Details details regarding how the loan payment cashflow should be amortized including amortization method e.g. single payment at end equal payments over term of loan .

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Floating Loan Deposit element has the following XML definition 

A Foreign Exchange Option FX Option transaction is one in which one party in exchange for a premium payment acquires from another party the right but not the obligation to buy i.e. exercise a put option or sell i.e. exercise a call option a specified quantity of one currency at a specified price on a specified exercise date or during a specified exercise period. For example a Member pays a premium to a Provider for the right to exercise an option to purchase 1 million Euro for a set price in U.S. Dollars in three months.

The FX Option element represents such a transaction and includes the following sub elements and attributes 

 Premium Details the details of the premium to be paid as either a percentage Premium Percentage or a specified amount Premium Amount and the payment date Premium Date .

 Dealt Amount the specified amount of currency to be converted into the currency to be bought or sold upon exercise of the option.

 Delivery Date the date on which either the cash difference or the underlying contract nominal amount must be exchanged upon exercise of the option.

 Delivery Mode indicator of whether the cash difference Cash or the underlying contract nominal amount Physical must be exchanged upon exercise of the option.

 Physical indicates whether the option will be settled on the basis of delivery of an underlying asset.

 Writer the recipient of the premium for the option to be exercised this is a reference to a Counterparty element.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

A Foreign Exchange Swap FX Swap transaction is one in which two parties exchange two payments Near and Far each in a different currency. The first payment is delivered at the beginning of the transaction period and the second payment is delivered at the end of the transaction period. The payments may be based upon a specified interest rate. For example a Member buys a payment of 3 million Euro from a Provider in exchange for a payment of 1 million U.S. Dollars to be paid six months after the first payment.

The FX Swap element represents such a transaction and includes the following sub elements and attributes 

 Near Leg Value Date the date on which the final payment of the first leg the Near Leg of the swap will be paid.

 Far Leg Value Date the date on which the final payment of the second leg the Far Leg of the swap will be paid.

 Near Leg Settled Amount the amount that will be paid under the Near Leg alternative to Near Leg FXRate.

 Far Leg Settled Amount the amount that will be paid under the Far Leg alternative to Far Leg FXRate.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

A Cross Currency Fixed Fixed Swap is a type of interest rate swap in which two parties exchange periodic payment streams based on fixed interest rates each in a different currency.

The Cross Currency Fixed Fixed Swap element represents such a transaction and includes the following sub elements and attributes 

 Fixed Leg Details the details of the fixed interest payments separate information for each of the two fixed legs.

 Events the various payment and calculation events in the swap transaction including cash payment principal payment interest payment interest calculation compound interest calculation and interest rate reset information.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Cross Currency Fixed Fixed Swap element has the following XML definition 

A Cross Currency Float Float Swap is a type of interest rate swap in which two parties exchange periodic payment streams based on a floating rate index e.g. LIBOR each in a different currency.

The Cross Currency Float Float Swap element represents such a transaction and includes the following sub elements and attributes 

 Float Leg Details the details of the floating interest payments separate information for each of the two fixed legs.

 Events the various payment and calculation events in the swap transaction including cash payment principal payment interest payment interest calculation compound interest calculation and interest rate reset information.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Cross Currency Float Float Swap element has the following XML definition 

A Cross Currency Fixed Float Swap is a type of interest rate swap in which two parties exchange periodic payment streams where one payment stream is based on a fixed interest rate and the other payment stream is based on a floating rate index e.g. LIBOR each in a different currency.

The Cross Currency Fixed Float Swap element represents such a transaction and includes the following sub elements and attributes 

 Events the various payment and calculation events in the swap transaction including cash payment principal payment interest payment interest calculation compound interest calculation and interest rate reset information.

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Cross Currency Fixed Float Swap element has the following XML definition 

A Forward Rate Agreement transaction is one in which one party buys a single floating rate payment in exchange for a single fixed rate payment. The fixed rate payment amount is determined by applying a fixed rate of interest to the notional amount of the transaction while the floating rate payment amount is determined by sampling the value of a specified floating rate option on a specified date and applying the sampled rate to the notional amount. The parties settle the Forward Rate Agreement by netting the effects of the two payments into a single payment made by one or the other of the parties if the floating rate amount due is greater than the fixed rate amount due then the floating rate payer pays the excess to the fixed rate payer conversely if the fixed rate amount due is greater than the floating rate amount due then the fixed rate payer pays the excess to the floating rate payer. Settlement occurs at the beginning of the transaction subject to future discounting specific to the Forward Rate Agreement i.e. payment of difference in fixed and floating rates .

The Forward Rate Agreement element represents such a transaction and includes the following sub elements and attributes 

 Roll Convention the convention to be used for rolling the payment dates in the event the date falls on a holiday.

 Rate Reset Calendar the calendar to be used for determining the dates on which to reset floating interest rates.

 Premium Details the details of the premium to be paid as either a percentage Premium Percentage or a specified amount Premium Amount and the payment date Premium Date .

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Forward Rate Agreement element has the following XML definition 

In addition to the financial transactions represented by the elements described above the present embodiment of this invention supports customized trades and transactions created by Members and or Providers so long as such transactions are permitted by applicable law. Such customized transactions might include hybrid trades where one or more aspects of one type of trade are combined with those of another. For example a party might structure a foreign exchange swaption in which a stream of periodic payments in one currency is exchanged for the right to buy a specified quantity of another currency at a specified price on a specified date.

FinXML enables the representation of customized transactions through the combination of elements that comprise different types of transactions. Using FinXML a party can specify the element fields and values that it wishes to comprise the particular customized transactions. The Customized Trade element represents such a transaction and includes the following sub elements and attributes 

 Field Name a particular component included in the transaction separate information for each component paired with Field Value .

 Field Value the value of a particular component included in the transaction separate information for each component paired with Field Name .

 External ID one or more identifiers assigned by a user to identify a transaction in its internal or back end system optional.

In the present embodiment of this invention the Customized Trade element has the following XML definition 

In the present embodiment of this invention FinXML includes a number of elements that represent details common to one or more of the Trade Type elements . Such elements may also be included in customized trades.

Generic trade details include information relating to notional amounts and interest rate amortization and compounding calculations that are common to different types of trades. The Generic Spec Details element represents such information and includes the following sub elements and attributes 

 Payment Frequency the frequency of interest principal payment e.g. monthly quarterly semi annually .

 Anchor Date the date to which the payment schedule is anchored i.e. the end date of the first interest period or specific date of first payment.

 Date Stub an indicator for a schedule of loan payments in which the payment period differs i.e. is offset from the start of from all other payment periods.

 Amortization Details details regarding how the loan payment cashflow should be amortized including amortization method e.g. single payment at end equal payments over term of loan .

 Compounding Details details regarding how the loan interest should be compounded including calculation frequency and rate.

In the present embodiment of this invention the Generic Spec Details element has the following XML definition 

Fixed rate details include information relating to fixed interest rates. The Fixed Spec Details element represents such information and includes the following sub elements and attributes 

In the present embodiment of this invention the Fixed Spec Details element has the following XML definition 

Floating rate details include information relating to floating interest rates that are based on a floating rate index e.g. LIBOR . The Floating Spec Details element represents such information and includes the following sub elements and attributes 

 Rate Reset Calendar the calendar to be used for reference to business holidays for interest rate resets.

In the present embodiment of this invention the Floating Spec Details element has the following XML definition 

A number of the transactions described above include multiple legs where each leg is a series of payments or cashflows. Such legs can be fixed or floating. 

A fixed leg is a payment stream based on a fixed interest rate. The Fixed Leg Details elements represents information regarding the fixed leg of a trade and includes generic trade details described above in Generic Spec Details element fixed rate details described above in Fixed Spec Details element financial events details described below in Events element and the following additional sub elements and attributes 

 Receiver the recipient of the proceeds of the fixed leg in a trade this is a reference to a Counterparty element.

In the present embodiment of this invention the Fixed Leg Details element has the following XML definition 

A floating leg is a payment stream based on a floating interest rate. The Float Leg Details elements represents information regarding the floating leg of a trade and includes generic trade details described above in Generic Spec Details element floating rate details described above in Float Spec Details element financial event details described below in Events element and the following additional sub elements and attributes 

 Receiver the recipient of the proceeds of the floating leg in a trade this is a reference to a Counterparty element.

In the present embodiment of this invention the Float Leg Details element has the following XML definition 

In the present embodiment of this invention FinXML includes a number of elements that represent details common to certain Trade Type elements including customized trades that relate to optional events during the life cycle of a trade such as premium payment interest payment contingent payment and interest calculation. Events element shown in describes such information and includes the following sub elements Cash Payment Principal Payment Interest Payment Interest Calculation Compound Interest Calculation and Contingent Payment .

Cash Payment element describes information relating to cash payments to be made as a part of certain trades and includes the following sub elements and attributes 

Principal Payment element describes information relating to principal payments to be made as a part of certain trades and includes the following sub elements and attributes 

In the present embodiment of this invention Principal Payment element has the following XML definition 

Interest Payment element describes information relating to interest payments to be made as a part of certain trades and includes the following sub elements and attributes 

In the present embodiment of this invention Interest Payment element has the following XML definition 

Contingent Payment element describes information relating to contingent payments to be made in the settlement of certain trades after the exercise of an option and includes the following sub elements and attributes 

 Settlement Amount the amount to be paid in settlement of the exercise of the option in return for the underlying instrument.

 Exercise Rule the rule governing normal exercise of the option e.g. American the option may be exercised on any day within a given period European the option may only be exercised on the option expiration date .

 Exercise Condition any conditions that must be met to permit exercise of the option e.g. the 3 month LIBOR rate must be greater than 4.5 on the exercise date .

 Payer the party responsible for delivering the option underlying instrument this party will receive the settlement amount in exchange for the option underlying instrument.

 Receiver the recipient of the option underlying instrument this party will pay the settlement amount as the price for exercising the option.

 Option Type the nature of the option e.g. Call an option to buy the underlying instrument at the exercise price Put an option to sell the underlying instrument at the exercise price .

 Delivery Type an indicator describing whether the Payer will physically deliver the option underlying instrument to the Receiver or alternatively that the transaction will be settled for cash where the option writer will upon exercise pay to the option holder the difference between the value of the underlying instrument and the exercise price.

In the present embodiment of this invention Contingent Payment element has the following XML definition 

Interest Calculation element describes information relating to an interest amount calculated for a given period within a particular interest payment and includes the following sub elements and attributes 

 Start Date the start date of the interest period for which the interest calculation is to be performed.

In the present embodiment of this invention Interest Calculation element has the following XML definition 

Compound Interest Calculation element describes information relating to a compound interest amount calculated for a given period within a particular interest payment and includes the following sub elements and attributes 

 Start Date the start date of the interest period for which the compound interest calculation is to be performed.

 End Date the end date of the interest period for which the compound interest calculation is to be performed.

In the present embodiment of this invention Compound Interest Calculation element has the following XML definition 

In the present embodiment of this invention FinXML includes a number of elements that represent details regarding calculations to be performed in certain Trade Type elements including customized trades. These elements relate to compounding amortization and calculation frequency.

The Compounding Details element describes information relating to any compounding calculations that need to be performed in a particular transaction. This typically arises where the actual interest payment frequency is longer than the interest calculation frequency. For example if interest is calculated every three months but paid every 6 months then the interest calculated at the end of the 3 month period would be compounded and paid along with the interest calculated for the fourth through sixth months. The Compounding Details element includes the following sub element 

 Calculation Frequency the frequency at which interest calculations should be performed in a multi period transaction.

In the present embodiment of this invention the Compounding Details element has the following XML definition 

The Amortization Details element describes information relating to any amortization calculations that need to be performed in a particular swap transaction. If the amortization method is defined to be bullet principal will be paid in one lump sum at maturity whereas under equal amortization principal will be paid in equal installments during the life of the swap transaction. The Amortization Details element includes the following sub elements and attributes 

 Amortization Frequency the frequency at which amortization will be performed in a particular transaction e.g. semi annual or annual .

In the present embodiment of this invention the Amortization Details element has the following XML definition 

The Calculation Frequency element describes information relating to the frequency of a particular calculation to be performed. The Calculation Frequency element includes the following sub elements and attributes 

 Convention the particular calculation methodology based on the market convention e.g. IMM FRN Eurodollar or Normal .

 End of Month indicator of whether the particular calculation should be moved to the end of the month.

In the present embodiment of this invention the Calculation Frequency element has the following XML definition 

The Payment Frequency element describes information relating to the frequency of a particular payment to be made. The Payment Frequency element includes the following sub elements and attributes 

 Convention the particular calculation methodology based on the market convention e.g. IMM FRN Eurodollar or Normal .

 Term the term of the interest index used in calculating the particular payment e.g. 3 months 6 months etc. .

In the present embodiment of this invention the Payment Frequency element has the following XML definition 

The Amortization Frequency element describes information relating to the frequency of a particular amortization to be performed. The Amortization Frequency element includes the following sub elements and attributes 

 Convention the particular calculation methodology based on the market convention e.g. IMM FRN Eurodollar or Normal .

 End of Month indicator of whether the particular amortization should be moved to the end of the month.

In the present embodiment of this invention the Payment Frequency element has the following XML definition 

Reference data describes the profile information specific to Members and Providers that will be referenced in any transactions engaged in by such parties. The FinXML syntax represents this profile information with the following elements Organization element Contact Information element Address element Credit Rating element Legal Entity element and Book element .

Organization element as shown in describes the organizational information regarding a Disclosed Party . Organization element includes the following sub elements and attributes 

Contact Information element as shown in describes the information necessary to contact a Disclosed Party during the transaction process. Contact Information element includes the following sub elements and attributes 

In the present embodiment of this invention Contact Information element has the following XML definition 

Address element as shown in describes the registered address information of the Disclosed Party . Address element includes the following sub elements and attributes 

Credit Rating element as shown in describes the details of the credit rating of the Disclosed Party or Undisclosed Party as rated by standard credit rating agencies. Credit Rating element includes the following sub elements and attributes 

 Country the country to which the party is assigned for purposes of the credit rating by the credit rating agency.

 Industry Group the industry group to which the party is assigned for purposes of the credit rating by the credit rating agency.

 Industry the industry to which the party is assigned for purposes of the credit rating by the credit rating agency.

Legal Entity element as shown in describes the details of any legal entities e.g. subsidiaries or affiliate companies associated with an Internal Party as shown in . Legal Entity element includes the following sub elements and attributes 

Book element as shown in describes the details of any internal trading book associated with the transaction by a party. Book element includes the following sub elements and attributes 

Market data describes information obtained from market sources for use in financial transactions. FinXML represents this information with the following elements Floating Interest Rate element and Interest Index element.

The Floating Interest Rate element describes information relating to the floating interest rate that can be used in a transaction. The Floating Interest Rate element includes the following sub elements and attributes 

 Interest Index the details of a particular index used for a floating interest rate including currency Currency term Term and name Index Name .

 Spread the differential plus or minus to be applied to the index rate in order to determine the floating interest rate.

In the present embodiment of this invention the Floating Interest Rate element has the following XML definition 

The Interest Index element describes information relating to the interest index used to calculate the floating interest rate. The Interest Index element includes the following sub elements and attributes 

In the present embodiment of this invention the Interest Index element has the following XML definition 

In the present embodiment of this invention the Connect Processor as shown in provides the means for communicating information related to financial transactions between users i.e. Members and Providers and the CFOWeb System. Connect Processor performs this function by converting FinXML or other XML documents to from financial Java objects using proprietary stylesheets created in XSL known as FinScript as will be described below.

In the present embodiment of this invention both Connect Processor and Connect Messaging Server process messages between users and the CFOWeb System and convert FinXML or other XML documents to from financial Java objects. Whereas Connect Processor performs such conversion between FinXML or other XML documents and the proprietary objects of Members and Providers Connect Messaging Server performs such conversion between FinXML or other XML documents and the proprietary objects of the CFOWeb System. Connect Messaging Server provides centralized within the CFOWeb System messaging and conversion functionality while Connect Processor provides distributed messaging and conversion functionality at Member and Provider client sites. Therefore in the present embodiment of this invention descriptions of the messaging and conversion functionality of Connect Processor are also applicable to Connect Messaging Server .

Members and Providers send requests for price quotes price quotes and other messages via an automated message broker which in turn sends such information through automated connection to a messaging middleware client application that is in communication with Connect Processor . Messaging middleware client application sends the information in the form of XML streams to Connect Processor . Connect Processor converts the XML information into Connect message objects including trade objects as will be described below . Connect Processor processes the message objects and if related to trades sends the message objects to the CFOWeb System including the content provided by the Member or Provider. Alternatively if the message objects do not include information regarding specific financial transactions and relate to non trade functions on CFOWeb System Connect Processor will send the message objects as actions or events to be performed at one of the system servers.

Connect Processor processes messages which may include trade information to Members or Providers by converting them into message objects . In addition Connect Processor processes actions and events occurring at any of the system servers by converting them into message objects . Next Connect Processor converts the message objects into XML documents which may be in the form of FinXML documents . Connect Processor sends the resulting XML documents e.g. a price quote or price quote request to messaging middleware client application . Messaging middleware client application sends the XML documents to the automated message broker of the appropriate Member or Provider through automated connection for conversion into objects. Note that in parallel to the processing and conversion of messages and objects from CFOWeb System Connect Processor routes the appropriate destination and addressing information for the particular Member or Provider that will receive the XML documents . The XML documents which may be in the form of FinXML documents will be converted into objects appropriate for processing by the Member or Provider as described below .

Connect Processor contains one or more Message Handlers a different Message Handler can be constructed to handle each type of message to be received by the Member or Provider. Using payload the appropriate Message Handler will invoke actions on the target Member or Provider system where the action is based on the information contained in payload . The Member Provider system communicates with Message Handler by sending a synchronous response . The Member Provider system sends an asynchronous response to Message Constructor Servlet . Message Constructor Servlet enables the Member Provider system to asynchronously construct messages for the CFOWeb System by sending parameters via transfer protocol e.g. HTTP or TCP IP calls. Message Constructor Servlet will send the asynchronous message to Message Sender Service . Message Sender Service also receives synchronous messages from Message Handler . Message Sender Service in turn forwards the messages to Inbound Queue of CFOWeb System .

In this embodiment each message is expressed in XML in Java Messaging Server JMS format. Each message consists of JMS based middleware and document . Middleware which may be an off the shelf product includes communications protocol e.g. HTTP TCP IP SSL and message administration and logging functionality that enable the reliable transmission of XML documents across networks and between the CFOWeb System and the Connect Processor.

Document which is an XML document includes header and message detail . Header in turn includes message identification and routing information . Message identification includes the message type e.g. Workflow or Control a message identifier and a date time stamp. Routing information identifies the message source and destination. Such information is managed by a routing table within the CFOWeb System that maps source and destination identifiers against participating Members and Providers.

Message detail includes text describing the purpose and detail of the message and may contain the payload which includes FinXML Trade information represented by the FinXML Trade element described above and in that defines the transaction.

Message root tag or CFOWeb Connect root tag identifies the message as a Connect message and includes the following attributes 

 System Name the name of the system that generated the message e.g. CFOWeb Connect for a Member or Provider system or the name of a third party system if applicable.

 Version the version of the Connect message vocabulary may differ for different Member Provider configurations.

 Test identifier of messages as test Y or live N a test message in a live environment will be communicated but not included and acted on in the business workflow.

 Conversation ID a system assigned sequence number that identifies the message as belonging to a particular conversation initiated by one of the communicating parties.

 Sequence ID a sequence number generated separately by each communicating node that is used as a reference by control messages and to provide chronological ordering of messages.

Routing element contains reference routing information about the source and destination of the message. This information includes the system defined identifier of Members and Providers. The routing information is used to derive the middleware addressing scheme e.g. point to point message queue topic of a publish subscribe channel and to identify the user responsible for the conversation. Routing element includes the following sub elements 

 Source the identifier of the source organization this is a reference to a Counterparty element can be anonymous.

 Destination the identifier of the destination organization this is a reference to a Counterparty element can be anonymous.

Workflow Message element contains descriptions of messages that effect state transition and actions in the workflow cycle including financial transactions communications between Members and Providers and interactions with CFOWeb System servers. Workflow Message element contains Note element which is used as an indicator whenever a Member or Provider desires to attach freeform textual information with trade information. In addition each instance of Workflow Message element contains one of the following Workflow Message types 

Each Workflow Message type element represents a different type of Workflow Message which will be described below.

In the present embodiment of this invention Workflow Message element has the following XML definition 

Quote Request Message element describes a message to notify a Provider s system that a Member is requesting a price quote. Quote Request Message element includes the FinXML trade object as its payload as well as information regarding the type of quote requested by the Member e.g. spread . The CFOWeb System may handle an incoming Quote Request Message element in the following ways i use Provider configured automated pricing and send a Quote Response Message containing a computed price or ii pass the Quote Request information to an internal trading environment to alert a Provider that the quote is available to be filled in which case the trade details from the payload could be loaded into a back end spreadsheet or other pricing system to allow a Provider to price the trade manually.

 Expiry Time deadline in 24 hour format specified by Member for submission of quotes in response to Quote Request.

 Leg Ref identifier of particular trade leg for which quote requested if applicable e.g. Leg ID of particular leg or None .

 Payload information describing a particular financial transaction. Payload Type the category of payload e.g. FinXML .

In the present embodiment of this invention Quote Request Message element has the following XML definition 

The following is an example Quote Request Message element in the present embodiment of this invention 

Quote Response Message element describes a message to notify the CFOWeb System that a Provider has submitted a price quote in response to a Quote Request Message from a Member. Quote Response Message element includes the value of the quoted variables and can optionally include a payload of the complete trade which is useful where the Provider may have suggested a modified or alternate structure. The CFOWeb System uses the payload information to update the original quote request with a price quote and refreshes the requesting Member s web browser to display the offered price quote.

 Leg Ref identifier of particular trade leg for which price quote submitted if applicable e.g. Leg ID of particular leg or None .

In the present embodiment of this invention Quote Response Message element has the following XML definition 

The following is an example Quote Response Message element in the present embodiment of this invention 

In the present and other embodiments of this invention Workflow Message element can include other message types to enable communications related to financial transactions.

Quote Indicate Interest Message element describes a message used by the CFOWeb System in to notify the Connect Processor that a Member has indicated interest in a price quote submitted by a Provider in response to the Member s earlier quote request. The Connect Processor can be configured with a Message Handler that will route Quote Indicate Interest Message element to the Provider s internal system as a screen pop up or alert.

Quote Accept Message element describes a message used by the CFOWeb System to notify the Connect Processor that a Member wishes to accept the price quote submitted by a Provider. Quote Accept Message element includes a reference to the quote request and the price accepted by the Member. The system will send the Quote Accept Message only to the Provider whose price was accepted all other Providers who submitted price quotes in response to the quote request will receive a Quote Reject Message described below . The Connect Processor in can be configured with a Message Handler that will route Quote Accept Message element to the Provider s internal system as a screen pop up or alert.

Quote Reject Message element describes a message used by the CFOWeb System to notify a Provider that a Member has rejected the price quote submitted by the Provider. This will occur when a Member expressly rejects a Provider s price quote or accepts another Provider s quote in response to the same quote request thus implicitly rejecting all other price quotes. Quote Reject Message element includes a reference to the quote request. The Connect Processor in can be configured with a Message Handler that will route Quote Reject Message element to the Provider s internal system as a screen pop up or alert.

Withdraw Indication of Interest IOI Message element describes a message used by the CFOWeb System in to notify the Connect Processor that a Member has withdrawn its indication of interest in a price quote submitted by a Provider in response to the Member s earlier quote request. The Connect Processor can be configured with a Message Handler that will route WithdrawIOI Message element to the Provider s internal system as a screen pop up or alert.

Withdraw Quote Request Message element describes a message used by the CFOWeb System to notify the Connect Processor that a Member wishes to withdraw a quote request that was sent previously. All Providers that were sent the original Quote Request Message will receive the Withdraw Quote Request Message as they no longer need to track activity on their price quotes regarding the particular quote request. its indication of interest in a price quote submitted by a Provider in response to the Member s earlier quote request. The Connect Processor in can be configured with a Message Handler that will route Withdraw Quote Request Message element to the Provider s internal system as a screen pop up or alert.

Withdraw Quote Message element describes a message used by the CFOWeb System to indicate that a Provider wishes to withdraw a price quote that was sent previously. The Withdraw Quote Message can be sent from either the CFOWeb System if a Provider withdraws the price quote manually or through the Connect Processor if the withdrawal action is generated by means of a Provider s internal system either manually or automatically . If the Withdraw Quote Message is generated through the Connect Processor a synchronized clock timestamp will be set on the message indicating the expiration time of the price quote.

Disclose Message element describes a message used by the CFOWeb System to disclose to a party the identity of a previously undisclosed Counterparty. Such disclosure will only occur upon notification of the system by the Counterparty to disclose its identity.

Price Request Message element describes a message used by the CFOWeb System for semi automated pricing to notify the Connect Processor that a Member is requesting a price quote for a request from the Member s internal system. Price Request Message element includes the FinXML trade object as its payload as well as information regarding the type of quote requested by the Member e.g. spread . The Connect Processor handles the message with one or more Providers and sends the CFOWeb System a Price Response Message described below containing a price quote.

Price Response Message element describes a message used by the Connect Processor for semi automated pricing to notify the CFOWeb System that a Provider s internal system has calculated a price quote for a quote request and to submitted the price quote to the CFOWeb System. The CFOWeb System uses the information to refresh the requesting Member s web browser to display the offered price quote. The Provider may submit the quote with this pricing information or with information entered manually. In either case the Provider submits the price quote to the Member manually e.g. by clicking a button .

Quote Request Expiry Message element describes a message used by the CFOWeb System to notify the Connect Processor that a Member s quote request has expired. The CFOWeb System generates the Quote Request Expiry Message automatically upon the occurrence of the expiry time for the quote request. All Providers that were sent the original Quote Request Message will receive the Quote Request Expiry Message as they no longer need to track activity on their price quotes regarding the particular quote request. The Connect Processor in can be configured with a Message Handler that will route Quote Request Expiry Message element to the Provider s internal system as a screen pop up or alert.

Quote Expiry Message element describes a message used by the CFOWeb System to notify the Connect Processor that a Provider s price quote has expired. The CFOWeb System generates the Quote Expiry Message automatically upon the occurrence of the expiry time for the price quote.

Withdraw All Quotes Message element describes a message used by the CFOWeb System to notify the Connect Processor that a Provider wishes to withdraw all price quotes. The message can specify criteria for the quotes to be withdrawn.

Control Message element contains descriptions of messages that are sent in response to Workflow Messages to indicate the success or failure of message receipt and processing. While the middleware serves to transmit messages between the CFOWeb System and the Connect Processor the middleware does not guarantee certain system performance parameters including particular delivery time successful translation and processing of the XML content or the successful provision of a price quote. Thus Control Message element provides acknowledgement of message delivery and reports error conditions to the sender of a message.

Control Message element includes a Sequence ID element which is a system assigned sequence number for the particular Workflow Message to which Control Message element applies. In addition each instance of Control Message element contains one of the following Control Message types 

Each Control Message type element represents a different type of Control Message which will be described below.

In the present embodiment of this invention Control Message element has the following XML definition 

Acknowledge Ack Message element is used to acknowledge the successful receipt translation and processing of a Connect message and transaction payload. Ack Message element includes Our Payload Ref element which contains a reference to a Payload element carried by the acknowledged message. Our Payload Ref element includes the following sub elements 

In the present embodiment of this invention Ack Message element including Our Payload Ref element has the following XML definition 

In the present and other embodiments of this invention Ack Message element may include specific acknowledgement messages for verification and completion of a transaction as described below.

Trade Download Response Message element describes a message used by the CFOWeb System to notify a Provider s internal system that both the Provider and a Member have agreed to the terms of a particular price quote and that the specified trade should now be processed. The Connect Processor uses the Trade Download Response Message element to send all relevant trade information to the Provider s internal system for processing. The Trade Download Response Message element includes the trade payload.

Trade Download Acknowledge Message element describes a message used by the CFOWeb System to notify the Connect Processor that all necessary internal systems of the Provider have completed initial processing for a particular trade.

Trade Download Request Message element describes a message used by the Connect Processor when it needs to download executed trades from the CFOWeb System. Typically this occurs when trades did not load properly. The CFOWeb System uses the Trade Download Request Message to send all trades to the Connect Processor so that it may process and feed the trade information to Providers internal systems.

Deal Verify Request Message element describes a message used by the Connect Processor to notify the CFOWeb System that a completed transaction has been verified at the Provider internal system and to request that the CFOWeb System also verify the completed transaction.

Deal Verify Acknowledge Message element describes a message used by the Connect Processor to communicate confirmation to the CFOWeb System that a Deal Verify Request Message has been received.

Deal Verify Confirm Message element describes a message used by the CFOWeb System to communicate confirmation to the Connect Processor that a verification request has been carried out successfully.

Error Message element is used to provide notification to the sender of a message any time application level processing of the XML message content fails including the unsuccessful translation of XML into objects or execution of a pricing algorithm. Error Message element includes the following sub elements 

 ABC Corp. XYZ l t destination Failed to instantiate trade in Connect Cache 001 This is an error control message d. Message Flow

The flow of Workflow Messages back and forth from the CFOWeb System through the Connect Processor to Member and Provider internal systems differs depending on the type of Workflow Message e.g. quote request price quote and the type of processing e.g. automated manual synchronous asynchronous .

The Provider s pricing engine sends a synchronous response back to Price Request Message Handler in the form of a Return Price Message . Price Request Message Handler generates a Price Response Message using the price quote and sends it to Message Sender Service . Price Response Message is a message used by the Connect Processor for semi automated pricing to notify the CFOWeb System that a Provider s internal system has calculated a price quote for a quote request and to submitted the price quote to the CFOWeb System the CFOWeb System uses the information to refresh the requesting Member s web browser to display the offered price quote. Message Sender Service in turn forwards the Price Response Message to Inbound Queue of CFOWeb System for processing.

Dispatcher extracts the payload from Trade Download Response Message and passes the payload as a Trade Object Java object to the Trade Download Response Message Handler . Using the payload in Trade Object Trade Download Response Message Handler executes a Call Deal Capture Function on the target Provider deal capture system in the Provider s internal system. Call Deal Capture Function notifies the Provider s deal capture system to process the completed transaction based on the information contained in Trade Object . The Provider s deal capture system sends an asynchronous response containing message details to Message Constructor Servlet . Message Constructor Servlet constructs a Trade Download Acknowledge Ack Message using message details and sends it to Message Sender Service . Trade Download Ack Message is a message used by the Connect Processor to notify the CFOWeb System that all necessary internal systems of the Provider have completed initial processing for a particular trade. Message Sender Service in turn forwards the Trade Download Ack Message to Inbound Queue of CFOWeb System for processing.

The present invention enables users Members and Providers to conduct financial transactions using the CFOWeb System and Connect Processor via connections to the users internal back end systems. In the present embodiment of this invention the Connect Processor enables the communication of information related to financial transactions between users i.e. Members and Providers and the CFOWeb System by converting FinXML or other XML documents to from proprietary financial Java objects as used on the users internal systems using proprietary stylesheets created in XSL known as FinScript . The Connect Processor as shown in creates a FinXML document that can be sent using a transfer protocol e.g. HTTP or TCP IP to the Connect Messaging Server for conversion to objects that can be processed on the server side. Following processing the Connect Messaging Server converts the objects to a FinXML or other XML document using XSL stylesheets and sends the FinXML or other XML document to the Connect Processor which uses FinScript to create a JavaScript program from the FinXML or other XML document. In turn Java objects are created from the JavaScript program and sent to the other organization e.g. a Provider .

When a user Member or Provider wishes to send information e.g. a quote request or a price quote to the CFOWeb System the Connect Processor must convert the proprietary financial objects used by the user s internal system into FinXML or other XML documents that can be used by the CFOWeb System. illustrates the components of the conversion or encoding process and shows the steps to be executed by the system to perform such conversion in an embodiment of the present invention. Note that these steps could be combined certain steps could be removed and others deleted and or the order of the steps could be modified in various other embodiments of this invention.

When the user wishes to submit information regarding a transaction e.g. a quote request from a Member a price quote from a Provider the user s messaging client sends the financial objects as shown in as represented on the user s internal system to the Connect Processor via an application programming interface API step of . Typically financial objects will be stored on the user s internal system as Java objects which are in the form of object graphs. Such object graphs consist of inter linked nodes representing the elements and attributes of the financial object.

Upon receiving financial objects the Connect Processor will identify the applicable XML object mapping to apply to financial objects step . In some embodiments of this invention XML object mappings may be customized by the user in order to correspond to the form and structure of the user s proprietary financial objects.

Next the Connect Processor invokes a dynamic Document Object Model DOM parser module to parse financial objects and apply XML object mapping to the elements and attributes of financial objects step . DOM is a platform and language neutral interface that will allow programs and scripts to dynamically access and update the content structure and style of documents. DOM provides a standard set of objects for representing HTML and XML documents a standard for how these objects can be combined and a standard interface for accessing and manipulating them. DOM is described in the Document Object Model DOM Level 1 Specification Version 1.0 Oct. 1 1998 World Wide Web Consortium Massachusetts Institute of Technology Institut National de Recherche en Informatique et en Automatique Keio University .

The dynamic DOM parser generates a DOM tree which is a 1 1 mapping to the object graph of financial objects step . Generation of the DOM tree is dynamic and occurs on an as needed basis as finite boundaries transitive closure of the object graph are determined. Thus steps and may be repeated as necessary. Next the Connect Processor obtains the XSL stylesheet to apply to DOM tree step based on the object values contained in DOM tree . The proprietary XSL stylesheet known as FinScript contains rules for navigating i.e. determining boundaries of and converting DOM tree into a FinXML document. In the present embodiment of this invention XSL stylesheets are linked to a single root. In some embodiments of this invention XSL stylesheets may be customized by the user in order to correspond to the form and structure of the user s proprietary financial objects.

Next the Connect Processor invokes a XSLT processor an off the shelf component e.g. International Business Machines Corp. s Lotus XSL product to apply the rules of the XSL stylesheet to DOM tree step . This process results in the generation of a FinXML document step that can be used by the CFOWeb System. The following is an example FinXML document generated by the XSLT processor in the present embodiment of this invention 

Note that the same process described above will be used by the Connect Messaging Server to convert the proprietary financial objects used by the various servers of the CFOWeb System into FinXML or other XML documents that can be sent to the Connect Processor.

When the CFOWeb System is ready to send information regarding a transaction to a user Member or Provider Connect Processor must convert the FinXML or other XML documents into proprietary financial objects that can be used by the user s internal system. illustrates the components of the conversion or decoding process and shows the steps to be executed by the system to perform such conversion in an embodiment of the present invention. Note that these steps could be combined certain steps could be removed and others deleted and or the order of the steps could be modified in various other embodiments of this invention.

When the CFOWeb System wishes to send information regarding a transaction e.g. a quote request from a Member a price quote from a Provider the Connect Messaging Server sends the previously created FinXML or other XML document as shown in to the Connect Processor step of . The following is an example FinXML document created in the present embodiment of this invention 

Upon receiving FinXML or other XML document the Connect Processor will obtain the XSL stylesheet to apply to FinXML document step based on the transaction type identified in FinXML document . There is a different XSL stylesheet for each type of transaction and all options supported by the CFOWeb System. The proprietary XSL stylesheet known as FinScript contains rules for converting FinXML document into a JavaScript program including reusable fragments of JavaScript programming code. In the present embodiment of this invention XSL stylesheets are linked to a single root. In some embodiments of this invention XSL stylesheets may be customized by the user in order to correspond to the form and structure of the user s proprietary financial objects.

 xmlns http www.finxml.org finxml 1.0 someProperties newPackages.java.util.HashMap someProperties.put Packages.com.integral.finance.trade.TradeCrea tionKeys.TRADE DATE trade Packages.com.integral.apps.ui.fxtrade.FXTradeFactory.newFXSpotTrade applicationEnvironment uow null null someProperties trade.setFrontOfficeID tradeID events trade.getFinancialEvents . . . 

Next the Connect Processor invokes a XSLT processor an off the shelf component e.g. International Business Machines Corp. s Lotus XSL product to apply the rules of the XSL stylesheet to FinXML or other XML document step . This process results in the generation of a JavaScript program step that can be executed to generate Java objects. The following is an example JavaScript program generated by the XSLT processor in the present embodiment of this invention 

counterpartyA Packages.com.integral.finance.counterparty.CounterpartyFactory.newLegalEntity . . . someProperties newPackages.java.util.HashMap someProperties.put Packages.com.integral.finance.trade.TradeCreationKeys .TRADE DATE 2000 06 12 trade packages.com.integral.ap ps.ui.fxtrade.FXTradeFactory.newFXSpotTrade applicationEnvironment uow null null someProperties valueDate Packages.com.integral.finance.dateTime.DateTimeFactory.newDate 2002 06 14 trade.setValueDate valueDate . . . trade.setCounterpartyA counterpartyA trade.setCounterpartyB counterpartyB 

Next the Connect Processor invokes a JavaScript interpreter 1240 an off the shelf component e.g. Mozilla.org s Rhino JavaScript interpreter to execute the JavaScript program step . This process results in the generation of financial objects Java objects step that can be used by the user s internal systems. The Connect Processor sends the financial objects to the messaging client application of the user s system via an API step .

Note that the same process described above will be used by the Connect Messaging Server to convert the FinXML or other XML documents created and sent by the Connect Processor into proprietary financial objects to be used by the various servers of the CFOWeb System.

In other embodiments of this invention the Connect Processor enables the communication of information related to financial transactions between users i.e. Members and Providers and the CFOWeb System by converting documents in non XML formats such as binary data streams byte streams other digital information streams or hash tables to from proprietary financial Java objects as used on the users internal systems using the FinScript stylesheets described above. The Connect Processor as shown in can create a non XML format document that can be sent using a transfer protocol e.g. HTTP or TCP IP to the Connect Messaging Server for conversion to objects that can be processed on the server side. Following processing the Connect Messaging Server converts the objects to a non XML format document using XSL stylesheets and sends the document to the Connect Processor which uses FinScript to create a JavaScript program from the document. In turn Java objects are created from the JavaScript program and sent to the other organization e.g. a Provider .

In an embodiment of the present invention the above described Connect Processor can be modified to enable multiple separate portals to communicate with the Connect Processor and in turn each other simultaneously. Such portals can include banks i.e. Providers and corporate entities i.e. Members that desire to engage in financial transactions of the type described herein using the system.

There are several scenarios under which multi portal transactions can occur using the Connect Processor. First a single corporate entity can conduct transactions with one or more banks where the corporate entity and each bank use the same message set e.g. XML based or non XML based message set and protocol. Second one or more corporate entities can conduct transactions with a single bank where the parties to a transaction may use different message sets and protocols the Connect Processor will translate the parties transaction messages into a common message set e.g. FinXML and aggregate them into a single message flow for processing by the bank as well as translate messages from the bank into the message set and protocol applicable to each corporate entity. Third one or more banks can conduct transactions with a single corporate entity where the parties to a transaction may use different message sets and protocols the Connect Processor will translate the parties transaction messages into a common message set e.g. FinXML and aggregate them into a single message flow for communication with the corporate entity as well as translate messages from the corporate entity into the message set and protocol applicable to each bank.

The architecture of the multi portal embodiment of the Connect Processor as modified to enable multi portal transactions is shown in . Multiple external portals portals from banks and corporate entities connect to Connect Processor via public or private networks. Each portal has an associated client clients that receives incoming messages from the portal as well as response messages sent from Connect Processor . Each client is connected to an associated bridge bridges .

Each bridge is a plug in adapter that in turn consists of an incoming receiver adapter and an outgoing sender adapter and performs a certain function. Such plug in adapters may be included with the system Connect Processor or created by a corporate entity or bank for interface with Connect Processor . The bridge serves to convert between the native message format of the associated portal XML based or non XML based and the standard format of Connect Processor e.g. FinXML and tie together the transport protocol e.g. DLL FTP JMS etc. of the associated portal with that of Connect Processor . Each bridge is connected to an associated bus client bus clients that serves to send receive messages to from and communicate with Bus . The bus clients can use filters to control the delivery and receipt of messages by a particular entity. Such filters can be specified in the form of message header properties applied to each message where such properties include information such as system identifier entity name message type transaction type time zone currency type and other profile information provided by the entity.

Bus connects the various bridges services translators message builders and other plug in adapters connected to Connect Processor . Bus determines the appropriate bus client to which each message will be dispatched using a dispatch registry. The dispatch registry is a database that includes for each bank and corporate entity connected to Connect Processor the address of a specific bus client for each type of message that the bank or corporate entity indicated it is willing to receive in its system profile information. Note that the different channels i.e. portals services translators message builder etc. for which Bus enables inter communication may not know about each other. For example corporate entities and banks can communicate through a common set of topics by sending messages to the topic and specifying the topics for which messages should be received. An entity could send a message to the topic without knowing whether any other entities or banks were currently listening to the topic conversely an entity could subscribe to receive messages related to a particular topic without knowing whether any other entities or banks were currently publishing to the topic. Bus determines how to route such topic messages to the appropriate destinations.

In addition to portals other functionality may be connected to Connect Processor such as a database containing information necessary for generating certain response messages for example exchange or interest rate information. Database for example is connected to Connect Processor via Database Client . Database Client receives data from Database as well as data request messages sent from Connect Processor . Database Client is connected to Cache Service a plug in adapter that creates data request messages from FinXML messages received from Connect Processor . Cache Service is connected to Cache Bus Client that serves to send receive messages to from and communicate with Bus .

Message Builder in combination with Message Builder Bridge creates FinXML response messages to messages sent by portals via Connect Processor .

One or more translators serve to transform one application language into another independent of portals and bridges as necessary for exchanging transaction messages. For example a translator might translate XSL stylesheets into XML based or non XML based objects. Translator bus clients serve to send receive messages to from and communicate with Bus .

The message flow of the multi portal embodiment of the Connect Processor as modified to enable multi portal transactions is shown in . In a typical transaction such as a request for a quote submitted by a corporate entity to one or more recipient banks using the system the corporate entity e.g. Portal in submits a quote request for a particular type of transaction e.g. swap spot etc. to the system i.e. Connect Processor . Client receives the incoming message from its associated Portal step in . Bridge converts the message from the native format used by the corporate entity in Portal into a Connect Message i.e. a message in the format used by Connect Processor e.g. FinXML step . Next associated Bus Client sends the Connect Message via Bus to the appropriate destination as determined by Bus step . In this particular example the destination is Message Builder with respect to other messages the destination might be another portal or a service such as Cache Service or a language translator such as Translator .

Message Builder Bus Client receives the Connect Message from Bus and Message Builder in combination with Message Builder Bridge constructs a FinXML response message to the Connect Message step . Message Builder Bus Client sends the response message via Bus to the appropriate portal s for example the portals of one or more banks. In this example Message Builder Bus Client sends the response message via Bus to Bus Client step . Bridge associated with Bus Client converts the response message from FinXML to the native message format utilized by destination Portal step . Finally Bridge sends the response message in the native format to Client step for processing by Portal .

In an embodiment of the present invention the system includes the Auto Dealer processing engine that enables banks to provide instantaneous responses to requests for quotes placed by entities that desire to engage in financial transactions using the system described herein. The Auto Dealer processing engine integrates a bank s internal processing systems and automates one and two way pricing margining and credit checking mechanisms.

The message flow of the Auto Dealer processing engine is shown in . In a typical transaction a corporate entity will submit a request for a quote via the entity s system integrated with Auto Dealer which is received by one or more recipient banks using the system step . The recipient banks will be those banks that set their profile information to allow receipt of a quote request based on the specified type of transaction the specified currency the amount of the request and or the identity of the requesting entity. Upon receipt of the quote request the processing engine will check the requesting entity s profile in order to determine whether the entity is permitted to engage in auto trading and receive auto quotes step . If not manual intervention will be required step whereby the bank i.e. an employee will make the decision to create and send a manual quote to the requesting entity step or decline to send a quote step .

If the requesting entity is permitted to engage in auto trading the processing engine will perform credit verification regarding the entity step in order to determine whether the entity has an established line of credit with a particular bank or whether based on the entity s financial status the bank is willing to provide a credit line to the entity engage in a financial transaction with the entity and offer it a price quote. The credit relationship and amount will be confirmed if a quote acceptance is subsequently received for an issued price quote. The credit amount will be withdrawn in the event that a quote request expires or is withdrawn by the requesting entity. If the credit verification is not successful manual intervention will be required step whereby the bank i.e. an employee will make the decision to create and send a manual quote to the requesting entity step or decline to send a quote step .

If the credit verification of the requesting entity is successful the processing engine will access raw market data step for use in creating a price quote. In an embodiment of this invention this step may be performed by accessing an electronic spreadsheet containing currency pairs spot and forward dates and continually updated currency rates bid and offer for those dates. If because of a technical problem or lack of an updated rate market data related to the quote request cannot be accessed manual intervention will be required step whereby the bank i.e. an employee will make the decision to create and send a manual quote to the requesting entity step or decline to send a quote step .

If the market data access is successful the processing engine will check the trade parameters of the quote request step in order to determine whether the transaction specified in the quote request is executable e.g. whether the specified currency is tradable and whether the specified notional amount is within the bank s acceptable bid offer range. If not manual intervention will be required step whereby the bank i.e. an employee will make the decision to create and send a manual quote to the requesting entity step or decline to send a quote step .

If verification of the trade parameters is successful the processing engine will initiate the calculation of spreads and margins as applicable step which are necessary for the creation of a price quote. Such calculation will incorporate the following factors transaction currency pair trade type trade tenor notional amount and margin level. A bank can define multiple margin types such as sales margin branch margin and volume margin each of which would be applicable in different situations. Margins could also be customized for particular trading entities. Typically each margin type would have two versions a bid side version and an offer side version.

After calculating the margin the processing engine will then prepare the auto quote response containing the price quote step and send the auto quote response to the requesting entity step .

Note that in another embodiment of this invention the credit verification step access of raw market data step and verification of trade parameters step steps are not inter dependent and should all be processed independently regardless of whether any of those steps were not successful. If any of those steps were not successful then the processing engine will route the request to manual intervention step prior to initiating the calculation of spreads and margins step .

The processing engine also enables the bank to create and send multiple price quotes for each quote request received. For example if a price quote expires but the underlying quote request is still valid i.e. not expired or withdrawn the processing engine can be set to automatically issue a new price quote from the bank if the bank set its profile for such automatic quote issuance .

The Auto Dealer processing engine includes user interfaces for the input of transaction parameters. illustrates the Trader Price Maintenance user interface to that enables a bank trader to change at any moment the parameters for a given currency pair and trade type combination including the following tenor bid and offer amount bid and offer currency trader margins bid and offer default expiry time and currency tradable indicator. The trader could also add or remove currency pairs for a particular trade type using the Trader Preferences interface illustrated in .

The processing engine also provides interfaces for the generation of manual price quotes in situations in which certain steps of the auto quote process were not successful e.g. credit verification access of market data trade parameter verification . Such interfaces show quote request details credit verification details and market data details and enable the bank to input and modify the price quote and margins. illustrates such an interface for a Spot transaction similar interfaces exist for other types of transactions.

The present embodiment of this invention includes a web based system that enables users e.g. Members and Providers to interactively communicate and trade financial instruments among one another and to manage their portfolios. Interactive communications supported by the system include establishing credit relationships structuring financial transactions requesting price quotes monitoring and reviewing quote requests issuing price quotes monitoring and reviewing price quotes negotiations between Members and Providers acceptance and confirmation of price quotes reporting portfolio management analysis of financial information and market data and communications among Members Providers and or system administrators including e mail chat and message boards.

When a user e.g. a Member or Provider accesses the web based system the system presents the user with a home page as shown in . This page includes a registration link for new users and member login interface for existing users which requires entry of the user s account ID and password. The home pages also includes market data and news headlines as well as links to the following system functionality each of which will be described below 

The functionality provided by the present embodiment of this invention enables users to conduct interactive and automated financial transactions in capital markets. The types of transactions that may be conducted are described above. The functionality and interactive user interfaces that support the creation and execution of such transactions enable users to engage in pre transaction transaction and post transaction activities. Note that the functionality and interfaces described in this embodiment could be combined with other functionality and interfaces or certain of such functionality and interfaces or portions thereof could be isolated in separate systems in various other embodiments of this invention. The system can be implemented as a stand alone central system or as a distributed system with separate versions of the functionality and interfaces distributed to multiple users platforms or portals. In other embodiments portions of the system functionality and interfaces could be divided into separate systems e.g. a transaction structuring system a price quote system a transaction acceptance system with a communication links that enable the different systems to exchange data. Other embodiments will be apparent to and could be implemented by practitioners skilled in this art.

The present embodiment of this invention enables Members and Providers to interactively establish certain defaults and parameters that will facilitate the on line financial transactions.

As will be described below with respect to the present embodiment this invention provides each user Member or Provider of the system with the ability to customize their interaction with the trading community through the use of automated filters. By selecting user defined and or system defined criteria from an interactive filtering interface a user can set limits and restrictions on i which other users will receive communications such as messages transaction requests and or price quotes from the user via the system and ii which communications such as messages transactions requests and or price quotes the user will receive from other users via the system. Example filtering criteria for limiting recipient users include 

the corporate nationality of a particular user the industry of a particular user SIC code for semiconductor manufacturing 

For example a user could set a filter such that only price quotes from U.S. banks for FX Swap transactions be sent to the user via the system. A financial institution could set a filter such that it would only receive transaction requests for Forward Rate Agreements from companies with a Moody s credit rating of AA .

The Legal Entities interface illustrated by enables a Member to display add or edit the details of any legal entities see Legal Entity element shown in and described above associated with the Member. The Member can search for an existing legal entity using search pull down menu and keyword field . After conducting a search the Member can click on Search button to conduct a new search or click on Clear button to clear the legal entity display. Alternatively the Member can use alphabetic index to search for an existing legal entity. The Member can display all existing legal entities by clicking Show All button .

As shown in for each legal entity the interface displays a short name e.g. PatentCorp name e.g. Test Patent Corporation entity type e.g. Corporation parent i.e. if other than Member and default contact. The Member can remove the displayed legal entity from its list of active entities by clicking Inactivate button .

Upon clicking New button the system will display the Legal Entity interface shown in which enables the Member to create a new legal entity or edit the information regarding an existing legal entity. For each legal entity information that can be inputted on this interface includes the following 

The Legal Entity interface also displays any existing trading book see Book element shown in and described above associated with the Member. As shown in for each trading book the interface displays a short name e.g. Test Book name e.g. Test Trading Book trading book type e.g. DEFAULT and a radio button showing whether the trading book is the default book. The Member can set the displayed trading book as the default book by clicking Make Default button .

Clicking on the displayed short name of the trading book e.g. Test Book will cause the system to display the Book interface shown in which enables the Member to edit the information regarding the trading book. Alternatively clicking New button will enable the Member to create a new trading book on the Book interface shown in . For each trading book information that can be inputted on this interface includes the following 

The Legal Entity interface shown in also displays any existing contacts see Contact Information element shown in and described above associated with a legal entity. As shown in for each existing contact the interface displays a short name name description and radio buttons showing whether the contact is a default contact and or a public contact. The Member can set the displayed contact as a i public ii private and or iii default contact by clicking Make Public button Make Private button and or Make Default button respectively.

Clicking on the displayed short name of contact will cause the system to display the Contact interface shown in which enables the Member to edit the information regarding the contact. Alternatively clicking New button will enable the Member to create a new contact on the Contact interface shown in . For each contact information that can be inputted on this interface includes short name full name mailing address telephone and facsimile numbers e mail address and Web URL address. Clicking Goto Page button will cause the system to access the contact s specified Web URL address. By clicking Update button the Member can save the information inputted on the Contact interface.

The Legal Entity interface shown in also displays and enables modification of any existing credit information see Credit Rating element shown in and described above associated with a legal entity. As shown in for each existing credit rating the interface displays the rating industry e.g. Moody credit rating e.g. Aaa industry group and industry. The interface provides pull down menus for editing of rating agency country credit rating industry group and industry . By clicking Add button the Member can save the modified credit information.

Returning to the Legal Entity interface shown in by clicking Save button the Member can save the information inputted on the Legal Entity interface. Further clicking Back button will cause the system to return to the previous interface visited by the Member i.e. the Legal Entities interface shown in . A similar Back button appears on most interfaces included in the system.

Note that the Page Help button that appears on the Legal Entities interface shown in and all other interactive interfaces leads the user to a comprehensive context dependent interactive system assistance utility.

The Member Trading Preferences interface illustrated by enables a Member to customize on line financial transactions by setting default expiration times for the Member s pricing requests for each type of financial transaction e.g. FX Swap Forward Rate Agreement etc. that the Member will seek to execute using the system. The interface also enables the Member to create filters to specifically include by clicking Add button shown in or exclude particular Providers as recipients of the Member s pricing requests. The interface displays such included Providers field as shown in e.g. PatentBank and excluded Providers field as shown in . By clicking Save button the Member can save the pricing request preference settings.

The My Profile Display interface illustrated by enables a Member to customize on line financial transactions by setting certain defaults related to the display of price quotes received from Providers in response to the Member s pricing requests. The default settings include the following 

filter radio buttons that enable the Member to select the types of price quotes e.g. FX Swap Forward Rate Agreement etc. received from Providers to be displayed

default expiration times for classifying the price quotes received from Providers as Urgent for each type of financial transaction e.g. FX Swap Forward Rate Agreement etc. 

The Trading Documentation interface illustrated by enables a Member to take two preliminary steps necessary to engage in on line financial transactions using the system. One step involves executing a trading agreement with the system administrator. The Member can download the agreement by clicking Download Trading Member Agreement button .

The other step involves the establishment of credit relationships between the Member and each Provider with which the Member may engage in on line financial transactions using the system see step in . The Trading Documentation interface displays any Providers with which the Member has existing credit relationships and who have notified the system of such relationships. If the Member clicks Show All Providers indicator the interface will display all Providers that may engage in financial transactions via the system. Using such list of Providers the Member can notify the system of any existing credit relationships with the Providers by clicking under Existing column next to the name of a Provider and then clicking Submit button the system will communicate with any selected Providers to verify the existence of such relationships. The Member can also request the creation of a credit relationship with any of the Providers by clicking under New column next to the name of a Provider and then clicking Submit button . The system will automatically forward the Member s request to each selected Provider. The Member and each such Provider can then negotiate a credit relationship by communicating via the electronic mail or chat functionality provided by the system.

The Provider Trade Preferences Quote Defaults interface illustrated by enables a Provider to customize on line financial transactions by setting default expiration times for the Provider s price quotes for each type of financial transaction e.g. FX Swap Forward Rate Agreement etc. submitted in response to pricing requests received from Members. The Provider can also add default comments e.g. additional trade requirements to its price quotes. By clicking Save button the Provider can save the price quote preference settings.

Clicking Request Filter button on the Provider Trade Preferences Quote Defaults interface shown in will cause the system to display the Provider Trade Preferences Request Filter interface illustrated by . The Provider Trade Preferences Request Filter interface enables a Provider to customize on line financial transactions by setting filter indicators that allow the Provider to select certain pricing requests submitted by Members of each type of transaction to be displayed. Clicking New button will enable the Provider to create a new filter using the Filter interface shown in . Alternatively clicking Edit button adjacent to a particular transaction type e.g. FX Forward will cause the system to display the Filter interface shown in which enables the Provider to edit the information regarding the filter for the particular transaction type. For each request filter information that can be inputted on the Filter interface shown in includes 

The interface includes Add and Remove buttons to add or delete currencies. By clicking Save button the Provider can save the information inputted on the Filter interface. Alternatively clicking Delete button will cause the displayed filter to be deleted. Clicking Back button will cause the system to display the Provider Trade Preferences Request Filter interface shown in .

Clicking Communications button on the Provider Trade Preferences Quote Defaults interface shown in will cause the system to display the Provider Trade Preferences Communications interface illustrated by . The Provider Trade Preferences Communications interface enables a Provider to set a filter that indicates whether the Provider desires to receive an electronic mail notification from the system each time a Member submits a pricing request for a particular type of transaction. The Provider can specify the electronic mail address to receive such messages for each type of transaction in field . By clicking Save button the Provider can save the information inputted on this interface.

The Standard Text List interface illustrated by enables a Provider to create standardized text such as boilerplate language disclaimers or other comments to attach to all of the Provider s price quotes. The Provider can create one or more versions of text and name and save the text files. The Standard Text List interface will display each of the Provider s standard text files including short name name and the text. By selecting a text file and clicking Inactivate button the Provider can inactivate the text file such that it will not be attached to its price quotes. Clicking New button will enable the Provider to create a new text file using the Standard Text Information interface shown in . Alternatively clicking on the name of a text file will cause the system to display the Standard Text Information interface shown in which enables the Provider to edit the particular standard text file. For each text file the Provider can input short name name and the text information. By clicking Save button the Provider can save the information inputted on the Standard Text Information interface.

The present embodiment of this invention enables Members and Providers to interactively engage in financial transactions in capital markets through a series of interfaces. Using such interfaces Members can structure desired financial transactions and automatically communicate pricing requests for such transactions. Providers can monitor incoming pricing requests from Members and respond to any of the request with structured price quotes. In turn Members can monitor incoming price quotes conduct back and forth negotiations with Providers via the system regarding such price quotes and accept price quotes. Members and Providers can also confirm payment schedules and other settlement details of accepted transactions via the system.

The present embodiment of the invention includes a request structuring interface for each type of financial transaction that a Member may structure and trade using the system as will be described below.

The New Request FX interface illustrated by enables a Member to create a Foreign Exchange Spot FX Spot see Section B.1.b.i. b 1 above for description of FX Spot Trade Type sub element or Foreign Exchange Forward FX Forward see Section B.1.b.i. b 2 above for description of FX Forward Trade Type sub element transaction request to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each FX Spot or FX Forward transaction request includes the following 

Value Date the date on which the traded currencies will be exchanged. For FX Spot transaction Member selects Spot in pull down menu. For FX Forward transaction Member selects forward period e.g. 1 Week 1 Month etc. in pull down menu.

Quote Currency the currency to be acquired or the currency to which the quote will be pegged e.g. USD in .

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking Save button the Member can save the transaction request information inputted on this interface. By clicking Send button the Member can automatically send the transaction request information to Providers.

Clicking Parameters button will cause the system to display the Parameters interface illustrated by . This interface enables the Member to specify parameters related to the transaction request. The parameters include the expiration trigger for the request which may be i a specific date and time or ii a specific duration. In addition the Member can input notes to accompany the transaction request. By clicking Save button the Member can save the transaction request information inputted on this interface. By clicking Send button the Member can automatically send the transaction request information to Providers. Note that the system provides a similar Parameters interface for each type of transaction request described below.

Clicking Providers button on the New Request FX interface shown in will cause the system to display the Providers interface illustrated by . This interface enables the Member to specify the Providers to whom the FX Spot transaction request should be forwarded via the system. The interface enables the Member to select all or particular Providers as recipients from the list of system Providers. For each such Provider the interface displays a short name full name and company symbol as well as a check box that indicates whether the Provider is a selected recipient. The interface also permits the Member to specify the e mail address of a potential Provider to be contacted by the system administrator. By clicking Save button the Member can save the transaction request information inputted on this interface. By clicking Send button the Member can automatically send the associated transaction request information to Providers. Note that the system provides a similar Providers interface for each type of transaction request described below.

Clicking Review button on the New Request FX interface shown in will cause the system to display the Review interface illustrated by . This interface enables the Member to review the details parameters and Provider recipient list for each FX Spot transaction request. If upon review the Member wishes to modify and of that information the Member can click on the appropriate Details Parameters or Providers buttons located on the interface in order to access any of those interfaces and make the modifications. By clicking Send button the Member can automatically send the associated transaction request information to Providers. Note that the system provides a similar Review interface for each type of transaction request described below.

The New Request FX Swap interface illustrated by enables a Member to create a Foreign Exchange Swap FX Swap transaction request see Section B.1.b.i. b 10 above for description of FX Swap Trade Type sub element to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each FX Swap transaction request includes the following 

Reference Spot FX Rate optional the spot rate to be used when calculating the foreign exchange rate for this transaction.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The New Request FX European Option interface illustrated by enables a Member to create a Foreign Exchange Option FX Option transaction request see Section B.1.b.i. b 9 above for description of FX Option Trade Type sub element to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each FX Option transaction request includes the following 

Delivery Date the date on which either the cashflow or underlying trade amount must be exchanged upon exercise of the option.

Notional Amount the amount of currency to be converted into the currency to be bought or sold upon exercise of the option.

Against Amount the settled amount of currency that will be bought or sold upon exercise of the option.

Delivery radio button showing whether to settle i the net cashflow only of the underlying trade Cash or ii the underlying trade Physical upon exercise of the option.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The New Request Swap interface illustrated by enables a Member to create any of the following types of transaction requests to be submitted via the system to Providers 

As shown in the information to be inputted by the Member using the interface for each swap transaction request includes the following 

Radio button showing whether Member will pay to Provider fixed or floating interest interest payments.

Pay Leg Notional Amount and Currency the amount and type of currency of the leg to be paid by Member.

Receive Leg Notional Amount and Currency the amount and type of currency of the leg to be received by Member.

Radio button showing whether Provider will quote i fixed rate for Pay Leg Receive Leg or ii floating rate for Receive Leg Pay Leg.

The combination of fixed floating interest rates and the same or different currencies specified by the Member for the Pay and Receive Legs on this interface will determine the specific type of transaction requested which will in turn cause the system to display one of five different interfaces as described below.

If the Member specifies a Fixed Pay Leg and Float Receive Leg as shown on radio buttons in with the same currency and clicks on Next button the system will display the New Request Fixed Float Interest Rate Swap interface illustrated by FIG. A. This interface enables a Member to create a Fixed Float Interest Rate Swap transaction request see Section B.1.b.i. b 3 above for description of Interest Rate Fixed Float Swap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Fixed Float Interest Rate Swap transaction request includes the following 

First Fixing Rate the interest rate to be used for the first interest rate calculation period for the floating leg optional .

Day Count the day count method to be used for calculating interest specified for each of the i fixed leg and ii floating leg.

Payment Frequency the frequency of interest payment specified for each of the i fixed leg and ii floating leg.

Roll Date the specific day and convention for each period to be used for determining payment of interest when such event occurs on a non business day specified for each of the i fixed leg and ii floating leg.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets for the floating leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i fixed leg and ii floating leg.

Stub an indicator for an irregular schedule of payments specified for each of the i fixed leg and ii floating leg.

Stub Length the irregular payment schedule length specified for each of the i fixed leg and ii floating leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i fixed leg and ii floating leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

Note that if the Member specifies a Float Pay Leg and Fixed Receive Leg using radio buttons in with the same currency and clicks on Next button the system will display the New Request Float Fixed Interest Rate Swap interface. This interface enables a Member to create a Float Fixed Interest Rate Swap transaction request which is structured opposite of the Fixed Float Interest Rate Swap described above.

If the Member specifies a Float Pay Leg and Float Receive Leg as shown on radio buttons in with the same currency and clicks on Next button the system will display the New Request Float Float Interest Rate Swap interface illustrated by . This interface enables a Member to create a Float Float Interest Rate Swap transaction request see Section B.1.b.i. b 4 above for description of Interest Rate Float Float Swap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Float Float Interest Rate Swap transaction request includes the following 

Notional Amount and Currency to be specified for each of the i floating Pay Leg and ii floating Receive Leg.

Floating rate index and basis point spread for each of the i floating Pay Leg and ii floating Receive Leg.

First Fixing Rate the interest rate to be used for the first interest rate calculation period for each of the i floating Pay Leg and ii floating Receive Leg optional .

Day Count the day count method to be used for calculating interest specified for each of the i floating Pay Leg and ii floating Receive Leg.

Payment Frequency the frequency of interest payment specified for each of the i floating Pay Leg and ii floating Receive Leg.

Roll Date the specific day and convention for each period to be used for determining payment of interest when such event occurs on a non business day specified for each of the i floating Pay Leg and ii floating Receive Leg. Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets for each of the i floating Pay Leg and ii floating Receive Leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i floating Pay Leg and ii floating Receive Leg.

Stub an indicator for an irregular schedule of payments specified for each of the i floating Pay Leg and ii floating Receive Leg.

Stub Length the irregular payment schedule length specified for each of the i floating Pay Leg and ii floating Receive Leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i floating Pay Leg and ii floating Receive Leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

If the Member specifies a Fixed Pay Leg and Fixed Receive Leg as shown on radio buttons in with different currencies for the Pay Leg and Receive Leg as shown on radio buttons and clicks on Next button the system will display the New Request Fixed Fixed Cross Currency Swap interface illustrated by . This interface enables a Member to create a Fixed Fixed Cross Currency Swap transaction request see Section B. 1.b.i. b 11 above for description of Cross Currency Fixed Fixed Swap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Fixed Fixed Cross Currency Swap transaction request includes the following 

Start Date the date on which the swap contract will begin and exchange of principal if applicable will occur.

Notional Amount and Currency to be specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Principal Exchange Rate and Currency the exchange rate and currency of the principal exchange if any.

Day Count the day count method to be used for calculating interest specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Payment Frequency the frequency of interest payment specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Roll Date the specific day and convention for each period to be used for determining payment of interest when such event occurs on a non business day specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Stub an indicator for an irregular schedule of payments specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Stub Length the irregular payment schedule length specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i fixed Pay Leg and ii fixed Receive Leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

If the Member specifies a Fixed Pay Leg and Float Receive Leg as shown on radio buttons in with different currencies for the Pay Leg and Receive Leg as shown on radio buttons and clicks on Next button the system will display the New Request Fixed Float Cross Currency Swap interface illustrated by . This interface enables a Member to create a Fixed Float Cross Currency Swap transaction request see Section B.1.b.i. b 13 above for description of Cross Currency Fixed Float Swap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Fixed Float Cross Currency Swap transaction request includes the following 

Start Date the date on which the swap contract will begin and exchange of principal if applicable will occur.

Maturity Date the date on which the swap contract will end. Notional Amount and Currency to be specified for each of the i fixed leg and ii floating leg.

Principal Exchange Rate and Currency the rate and currency of the principal exchange if any. Fixed rate index and basis point spread for the fixed leg or floating rate index and basis point spread for the floating leg.

First Fixing Rate the interest rate to be used for the first interest rate calculation period for the floating leg optional .

Day Count the day count method to be used for calculating interest specified for each of the i fixed leg and ii floating leg.

Payment Frequency the frequency of interest payment specified for each of the i fixed leg and ii floating leg.

Roll Date the specific day and convention for each period to be used for determining payment of interest when such event occurs on a non business day specified for each of the i fixed leg and ii floating leg.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets for the floating leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i fixed leg and ii floating leg.

Stub an indicator for an irregular schedule of payments specified for each of the i fixed leg and ii floating leg.

Stub Length the irregular payment schedule length specified for each of the i fixed leg and ii floating leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i fixed leg and ii floating leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

Note that if the Member specifies a Float Pay Leg and Fixed Receive Leg using radio buttons in with the same currency and clicks on Next button the system will display the New Request Float Fixed Cross Currency Swap interface. This interface enables a Member to create a Float Fixed Cross Currency Swap transaction request which is structured opposite of the Fixed Float Cross Currency Swap described above.

If the Member specifies a Float Pay Leg and Float Receive Leg as shown on radio buttons in with different currencies for the Pay Leg and Receive Leg as shown on radio buttons and clicks on Next button the system will display the New Request Float Float Cross Currency Swap interface illustrated by . This interface enables a Member to create a Float Float Cross Currency Swap transaction request see Section B.1.b.i. b 12 above for description of Cross Currency Float Float Swap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Float Float Cross Currency Swap transaction request includes the following 

Start Date the date on which the swap contract will begin and exchange of principal if applicable will occur.

Notional Amount and Currency to be specified for each of the i floating Pay Leg and ii floating Receive Leg.

Principal Exchange Rate and Currency the exchange rate and currency of the principal exchange if any.

Floating rate index and basis point spread for each of the i floating Pay Leg and ii floating Receive Leg.

First Fixing Rate the interest rate to be used for the first interest rate calculation period for each of the i floating Pay Leg and ii floating Receive Leg optional .

Day Count the day count method to be used for calculating interest specified for each of the i floating Pay Leg and ii floating Receive Leg.

Payment Frequency the frequency of interest principal payment specified for each of the i floating Pay Leg and ii floating Receive Leg.

Roll Date the specific day and convention for each period to be used for determining payment of interest when such event occurs on a non business day specified for each of the i floating Pay Leg and ii floating Receive Leg.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets for each of the i floating Pay Leg and ii floating Receive Leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i floating Pay Leg and ii floating Receive Leg.

Stub an indicator for an irregular schedule of payments specified for each of the i floating Pay Leg and ii floating Receive Leg.

Stub Length the irregular payment schedule length specified for each of the i floating Pay Leg and ii floating Receive Leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i floating Pay Leg and ii floating Receive Leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The New Request Cap Floor interface illustrated by enables a Member to create Cap and Floor transaction requests to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each Cap or Floor transaction request includes the following 

Notional Amount and Currency the amount and type of currency to be used as a basis for calculating the payment stream.

Radio button showing whether Member requests a price quote with i a premium amount in a specified currency or ii a strike percentage in a specified currency.

If the Member specifies the purchase or sale of a Cap as shown on radio buttons in and clicks on Next button the system will display the New Request Cap interface illustrated by . This interface enables a Member to create a Cap transaction request see Section B.1.b.i. b 5 above for description of Cap Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Cap transaction request includes the following 

Notional Amount and Currency the amount and type of currency to be used as a basis for calculating the payment stream.

Roll Date the specific day and convention for each period to be used for determining payment of option payments when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

If the Member specifies the purchase or sale of a Floor as shown on radio buttons in and clicks on Next button the system will display the New Request Floor interface illustrated by . This interface enables a Member to create a Floor transaction request see Section B.1.b.i. b 6 above for description of Floor Trade Type sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Floor transaction request includes the following 

Notional Amount and Currency the amount and type of currency to be used as a basis for calculating the payment stream.

Roll Date the specific day and convention for each period to be used for determining payment of option payments when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The New Request FRA interface illustrated by enables a Member to create a Forward Rate Agreement transaction request to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each Forward Rate Agreement transaction request includes the following 

Term the start and end dates of the trade e.g. 3.times.6 months means that the trade will begin on the first business date three months after the trade date and will end on the first business date six months after the trade date.

Notional Amount and Currency the amount and type of currency to be used as a basis for calculating the payment stream.

Clicking Next button will cause the system to display the New Request Forward Rate Agreement interface illustrated by . This interface enables a Member to provide the details of a Forward Rate Agreement transaction request see Section B.1.b.i. b 14 above for description of Forward Rate Agreement sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Forward Rate Agreement transaction request includes the following 

Term the start and end dates of the trade e.g. 3.times.6 months means that the trade will begin on the first business date three months after the trade date and will end on the first business date six months after the trade date.

Notional Amount and Currency the amount and type of currency to be used as a basis for calculating the payment stream.

Roll Date the specific day and convention for each period to be used for determining payment of Forward Rate Agreement payments when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The New Request Deposit interface illustrated by enables a Member to create a Fixed Rate Deposit transaction request to be submitted via the system to Providers. As shown in the information to be inputted by the Member using the interface for each Fixed Rate Deposit transaction request includes the following 

Clicking Next button will cause the system to display the New Request Fixed Rate Deposit interface illustrated by . This interface enables a Member to provide the details of a Fixed Rate Deposit transaction request see Section B.1.b.i. b 7 above for description of Fixed Rate Deposit sub element to be submitted to Providers via the system. As shown in the information to be inputted by the Member using the interface for each Fixed Rate Deposit transaction request includes the following 

Deposit Amount and Currency the amount and type of currency of the deposit by the Member to a Provider.

Roll Date the specific day and convention for each period to be used for determining payment of deposit payments when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

By clicking the Save button the Member can save the transaction request information inputted on this interface. By clicking the Send button the Member can automatically send the transaction request information to Providers.

The present embodiment of the invention includes a series of interfaces that enable a Member to monitor the status of transactions created by the Member including new transactions requests requests to which one or more Providers submitted responsive price quotes accepted requests and expired requests as will be described below. Such monitors aggregate the requests for the particular Member regardless of the counterparty e.g. Provider to the transaction.

The Request Monitor Current interface illustrated by enables a Member to view an aggregated summary of the Member s i active and ii recently completed transaction requests. As shown in the information displayed for each active i.e. un expired request includes the following 

By clicking ID button Type button or Expires button the display of active requests can be sorted by identification number transaction type or expiration date time respectively.

The information displayed on the interface for each recently completed request includes the following 

a Chat button that can be clicked to communicate with the Provider that submitted the responsive price quote if Provider permits chat communication for particular type of transaction 

Clicking on the identification number for a particular transaction request will cause the system to display the details for that request. This functionality is also available from the other request monitor interfaces described below. For example clicking on the identification number 4314 for the FX Spot transaction request identified as button will cause the system to display the Request Detail FX Spot interface shown in . This interface shows the details of the FX Spot transaction request created by the Member including the following information 

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

If a responsive price quote has already been received the interface will also display the following information 

a Chat button that can be clicked to communicate with the Provider if Provider permits chat communication for particular type of transaction 

The Member can click on the Counterparty name which will cause the system to display profile information regarding the counterparty see described below and the quote which will cause the system to display further details regarding the quote see described below . By clicking Off button the Member can withdraw the transaction request. By clicking History button the Member will cause the system to display a summary of all events related to the transaction request such as modifications to the initial request and price quotes received from different Providers.

As another example clicking on the identification number 4089 for the Swap transaction request identified as button on will cause the system to display the Request Detail Fixed Float Interest Rate Swap interface shown in . This interface shows the details of the Fixed Float Interest Rate Swap transaction request created by the Member including the following information 

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

If a responsive price quote has already been received the interface will also display the following information 

a Chat button that can be clicked to communicate with the Provider if Provider permits chat communication for particular type of transaction 

The system includes similar interfaces displaying detail of transaction requests and price quotes for all other types of transaction requests displayed on the request monitor interfaces. The system will automatically refresh the Request Monitor Current interface and the Request Detail interfaces for each type of transaction request when a new price quote is received or the status of a transaction request changes.

The Request Monitor Active interface illustrated by which can be accessed by clicking Active button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s active transaction requests. As shown in the information displayed for each active i.e. un expired request includes the following 

By clicking the ID button Type button or Expires button the display of active requests can be sorted by identification number transaction type or expiration date time respectively. Clicking Run button will cause the system to run a report that can be selected from pull down menu regarding the displayed active request s . Such reports may include an activity log of events transaction statistics and an audit log regarding the active requests. Such aggregate reports are available for each of the request monitors describe below.

The Request Monitor Active interface as well as the other request monitor interfaces describe below also enables the Member to conduct an automated search of the listed requests which is useful in the event that there are a large number of active requests. Using pull down menu the user can select the attribute on which to search e.g. transaction type description and input the search term in field e.g. FX Spot . Clicking Search button will cause the system to run the search and display the results. Clicking Clear button will cause the system to clear the search criteria in order that new search criteria can be entered. Clicking Show All button will cause the system to display all active requests. Clicking Empty Trash button will cause the system to permanently delete obsolete or draft transaction requests the quantity of such requests is indicated next to Empty Trash button .

The Request Monitor Accepted interface illustrated by which can be accessed by clicking Accepted button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s accepted transaction requests i.e. each transaction request for which the Member has accepted a price quote from a Provider. As shown in the information displayed for each accepted request includes the following 

a Chat button that can be clicked to communicate with the Provider if Provider permits chat communication for particular type of transaction 

The Request Monitor Verified interface illustrated by which can be accessed by clicking Verified button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s verified transaction requests i.e. each transaction request for which the Member has accepted a price quote from a Provider and the Provider has verified the Member s acceptance. As shown in the information displayed for each verified request includes the following 

The Request Monitor Obsolete interface illustrated by which can be accessed by clicking Obsolete button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s obsolete transaction requests i.e. each transaction request that has expired or that the Member has withdrawn. As shown in the information displayed for each obsolete request includes the following 

The Request Monitor Draft interface illustrated by which can be accessed by clicking Draft button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s draft transaction requests i.e. each transaction request that the Member has drafted and saved but not yet submitted to Providers. As shown in the information displayed for each obsolete request includes the following 

The Request Monitor Trash interface illustrated by which can be accessed by clicking Trash button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of the Member s trashed i.e. obsolete and draft transaction requests and permanently delete such requests. As shown in the information displayed for each trashed request includes the following 

By clicking on the selection indicator for a particular request the Member can mark it for restoration. Subsequently clicking the Restore button will restore the selected requests to active status. Clicking the Empty Trash button will permanently delete all trashed requests.

The Request Monitor All interface illustrated by which can be accessed by clicking All button on the Request Monitor Current interface shown in enables a Member to view an aggregated summary of all of the Member s transaction requests including active accepted verified withdrawn and expired requests. As shown in the information displayed for each request includes the following 

The Request Monitor Edit interface illustrated by which can be accessed by clicking Edit button on the Request Monitor Current interface shown in enables a Member to customize the request monitor interfaces. Using pull down menu the Member can specify the number of most recently completed requests to be displayed in the Request Monitor Current interface shown in . By clicking radio button the Member can specify whether the system will i electronically notify the Member when there are changes to a request e.g. expiration or new price quote so that the Member can manually refresh the monitor display or ii automatically refresh the monitor display when there are changes to a request. By clicking indicator the Member can set whether the system will display a countdown meter showing time until expiration of a price quote in the monitor display. For each type of transaction the Member can set Visible indicator which acts as a filter that determines whether the particular type of transaction will be displayed on the Member s monitor. Finally using Urgent Time to Expiry field the Member can set a default time at which the time until expiration countdown meter will change colors e.g. from green to red to indicate urgency. By clicking the Save button the Member can save the pricing request preference settings.

The present embodiment of the invention includes a series of interfaces that enable a Provider to monitor the status of transactions created by Member including new transactions requests requests to which the Provider has submitted responsive price quotes accepted requests verified requests and expired requests as will be described below. Such monitors aggregate the requests for the particular Provider regardless of the counterparty e.g. Member to the transaction.

The Request Monitor Current interface illustrated by enables a Provider to view an aggregated summary of i active transaction requests from Members and ii the Provider s recently completed price quotes. As shown in the information displayed for each active i.e. unexpired request received from Members includes the following 

a Chat button that can be clicked to communicate with the Member that submitted the request if Member permits chat communication for particular type of transaction 

The display of active requests can be sorted by identification number transaction type request expiration date time price quote price quote expiration date time or description by clicking on the respective column header.

Clicking on the identification number for a particular quote will cause the system to display the details for that quote. This functionality is also available on the other request monitor interfaces described below. For example clicking on the identification number 4314 for the FX Spot quote identified as button will cause the system to display the Request Detail FX Spot interface shown in . This interface shows the details of the FX Spot price quote created by the Provider including the following information 

Legal Entity the name of the Provider or the Provider s associated legal entity to which the transaction will be assigned.

Comments regarding the quote which may include standard text defined by the Provider see Standard Text and Standard Text Definition interfaces described above and shown in .

The Provider can click on the Counterparty name which will cause the system to display profile information regarding the counterparty see described below . By clicking History button the Provider will cause the system to display a summary of all events related to the price quote such as modifications to the initial request and price quote.

As another example clicking on the identification number 4089 for the Swap transaction request identified as button on will cause the system to display the Request Detail Fixed Float Interest Rate Swap interface shown in . This interface shows the details of the Fixed Float Interest Rate Swap price quote created by the Provider including the following information 

Amount and currency to be paid by the Member for the fixed Pay Leg Amount and currency to be paid by the Provider for the floating Receive Leg.

Legal Entity the name of the Provider or the Provider s associated legal entity to which the transaction will be assigned.

Comments regarding the quote which may include standard text defined by the Provider see Standard Text and Standard Text Definition interfaces described above and shown in .

As shown in the interface will also display the following information regarding the transaction request 

The Provider can click on the Counterparty name which will cause the system to display profile information regarding the counterparty see described below . By clicking Withdraw All button the Provider can withdraw all of the Provider s active price quotes. By clicking the History button the Provider will cause the system to display a summary of all events related to the price quote such as modifications to the initial request and price quote.

The system will automatically refresh the Request Monitor Current interface when a new transaction request is received or the status of a price quote changes. The interface will also display the status of transaction requests for which the requesting Member accepted the price quote of another Provider. In such event the status of the transaction request will be shown as Dealt Away the accepted price quote will not be displayed.

The Request Monitor New interface illustrated by which can be accessed by clicking New button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the most recent transaction requests received from Members. As shown in the information displayed for each new transaction request includes the following 

a Chat button that can be clicked to communicate with the Member that submitted the request if Member permits chat communication for particular type of transaction 

By clicking the ID button Type button or Expires button the display of active requests can be sorted by identification number transaction type or expiration date time respectively. Clicking Run button will cause the system to run a report that can be selected from the adjacent pull down menu regarding the new request s . Such reports may include an activity log of events transaction statistics and an audit log regarding the active requests. Such aggregate reports are available for each of the request monitors described below.

The Request Monitor New interface as well as the other request monitor interfaces describe below also enables the Provider to conduct an automated search of the listed requests which is useful in the event that there are a large number of new requests. Using pull down menu the user can select the attribute on which to search e.g. transaction type description and input the search term in the adjacent field e.g. FX Spot . Clicking Search button will cause the system to run the search and display the results. Clicking Clear button will cause the system to clear the search criteria in order that new search criteria can be entered. Clicking Show All button will cause the system to display all new requests. Clicking the check indicator adjacent to one or more requests or clicking the Check All button to select all displayed requests and then clicking Delete button will cause the system to delete the selected request s from view. Clicking Empty Trash button will cause the system to permanently delete obsolete or draft price quotes the quantity of such requests is indicated next to Empty Trash button . Clicking Withdraw All button will cause all of the Provider s active price quotes to be withdrawn from the view of Members thereby removing such quotes from potential acceptance by a Member. The functionality described in this paragraph is available on each of the request monitor interfaces described herein.

The Request Monitor Active interface illustrated by which can be accessed by clicking New button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the Provider s active i.e. unexpired price quotes. As shown in the information displayed for each active quote includes the following 

a Chat button that can be clicked to communicate with the Member that submitted the request if Member permits chat communication for particular type of transaction 

The Request Monitor Accepted interface illustrated by which can be accessed by clicking Accepted button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the Provider s accepted price quotes i.e. each quote that has been accepted by a Member. As shown in the information displayed for each accepted quote includes the following 

a Chat button that can be clicked to communicate with the Member if Member permits chat communication for particular type of transaction 

The Request Monitor Verified interface illustrated by which can be accessed by clicking Verified button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the Provider s verified price quotes i.e. each quote accepted by a Member for which the acceptance has been verified by the Provider. As shown in the information displayed for each verified quote includes the following 

The Request Monitor Obsolete interface illustrated by which can be accessed by clicking Obsolete button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the Provider s obsolete price quotes i.e. each quote that has expired or that the Provider has withdrawn. As shown in the information displayed for each obsolete quote includes the following 

The Request Monitor Trash interface illustrated by which can be accessed by clicking Trash button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of the Provider s trashed i.e. obsolete and draft price quotes and permanently delete such quotes. As shown in the information displayed for each trashed quote includes the following 

By clicking on the selection indicator for a particular request the Provider can mark it for restoration. Subsequently clicking the Restore button will restore the selected requests to active status. Clicking the Empty Trash button will permanently delete all trashed requests.

The Request Monitor All interface illustrated by which can be accessed by clicking All button on the Request Monitor Current interface shown in enables a Provider to view an aggregated summary of all of the Provider s price quotes requests including active accepted verified withdrawn and expired requests. As shown in the information displayed for each quote includes the following 

The Request Monitor Change Display interface illustrated by which can be accessed by clicking Edit button on the Request Monitor Current interface shown in enables a Provider to customize the request monitor interfaces. Using pull down menu the Provider can specify the number of most recently completed requests to be displayed in the Request Monitor Current interface shown in . By clicking radio button the Provider can specify whether the system will i electronically notify the Provider when there are changes to a request e.g. expiration or modification so that the Provider can manually refresh the monitor display or ii automatically refresh the monitor display when there are changes to a request depending upon the user s web browser . By clicking the countdown indicator the Provider can set whether the system will display a countdown meter showing time until expiration of a transaction request in the monitor display. For each type of transaction the Provider can set the Visible indicator which acts as a filter that determines whether the particular type of transaction will be displayed on the Provider s monitor. Finally using the Urgent Time to Expiry field the Provider can set a default time at which the time until expiration countdown meter will change colors e.g. from green to red to indicate urgency. By clicking the Save button the Provider can save the pricing request preference settings.

The present embodiment of the invention includes a price quote creation interface that enables a Provider to create a quote in response to each type of financial transaction request structured by a Member using the system. Upon selecting a particular transaction request as described above the Provider can review the details of the transaction request and input a price quote to be submitted to the Member.

For example as shown in described above clicking on the identification number 4314 for the FX Spot quote identified as button in will cause the system to display the Request Detail FX Spot interface shown in . That interface shows the details of the FX Spot transaction request created by the Member and enables the Provider to input the foreign exchange quote rate e.g. 0.920000 in field as well as the following quote details 

Legal Entity the name of the Provider or the Provider s associated legal entity to which the transaction will be assigned.

Comments regarding the quote which may include standard text defined by the Provider see Standard Text and Standard Text Definition interfaces described above and shown in .

As another example clicking on the identification number 4089 for the Swap transaction request identified as button on will cause the system to display the Request Detail Fixed Float Interest Rate Swap interface shown in . That interface shows the details of the Fixed Float Interest Rate Swap transaction request created by the Member and enables the Provider to input the fixed quote rate e.g. 5.950000 in field as well as the quote details described above.

Using the Request Detail interfaces the Provider can also create and submit indicative price quotes. Such quotes cannot be accepted by Members but allow the Provider to send an indication of the market level for the transaction type in order to encourage negotiation or a potential transaction between the Provider and Member. Indicative quotes may also be used where the Member does not yet have a credit relationship with the Provider. The Provider can identify an indicative price quote as such using the comments field of the quote.

Using an embodiment of this invention Members and Providers can engage in the online execution of financial transactions. An example of such a transaction a Foreign Exchange Spot FX Spot transaction is described below with reference to the flowchart set forth in . Note that these steps could be executed using this invention for each of the different types of transactions described herein.

This example presupposes that the Member and Provider have executed the standardized agreements necessary for online trading using the system step in and that they have negotiated a credit line to be assigned to the Member step . As described above these steps can be performed using the Trading Documentation interface shown in which includes credit relationship functionality as well as the various communication mechanisms provided by the system.

The Member must first structure and create the desired transaction request step in . The New Request interface shown in is the starting point for that task as it provides a road map to the various new request interfaces included in the present embodiment of the invention. In this example the Member desires to create a FX Spot transaction so the Member clicks on FX Spot Forward button which causes the system to display the New Request FX interface shown in . On this interface the Member inputs the following details regarding the desired FX Spot transaction 

Value Date for Spot exchange is Sep. 15 2000 field note that date can be set by clicking Set Date button .

Member will buy radio button 1 000 000 field Euro pull down menu against U.S. Dollars pull down menu .

Clicking Parameters button will cause the system to display the Parameters interface for the FX Spot transaction shown in . On this interface the Member provides the parameters of the online transaction request including i expiration date time field or ii time remaining until expiration field and notes comments regarding the request. Clicking Save button will cause the system to save the information regarding the transaction request. Clicking Send button will cause the transaction request details and parameters to be sent to Providers via the system.

Clicking Providers button in will cause the system to display the Providers interface for the FX Spot transaction shown in . On this interface the Member can specify the Providers e.g. PatentBank to whom the online transaction request is to be sent when the Member clicks the Send button.

Clicking Review button in will cause the system to display the Review interface for the FX Spot transaction shown in . On this interface the Member can review the details and parameters of the transaction request before sending it to one or more Providers by clicking Send button . If after review the Member wishes to modify any of the transaction request details or parameters the Member can return to the New Request FX interface or Parameters interface as necessary.

Upon submission of the transaction request to one or more Providers step in the Member can review the transaction request and its status including any price quote information via the Request Detail FX Spot interface shown in and described above.

The next step in the execution of the trade is the receipt and review of the Member s transaction request by one or more Providers step in . Using the system Providers monitor incoming transaction requests using the request monitor interfaces described above. In addition if specified as a preference a Provider can receive automatic notifications e.g. e mail messages from the system upon receipt of a new transaction request. The Request Monitor Current interface shown in and described above displays the new transaction request. In the present example the Member s FX Spot request is displayed with the system assigned identification number 5064 . Clicking on that identification number button will cause the system to display the Request Detail FX Spot interface shown in and described above from which the Provider can create a responsive price quote. Alternatively the Provider may choose to decline the transaction request by clicking Decline button in which will trigger a system notification to the Member that the Provider declined the request. The new FX Spot transaction request will also be displayed on the Provider s i Request Monitor New interface shown in and described above and ii Request Monitor Active interface shown in and described above.

After receiving and reviewing the Member s transaction request if desired the Provider may create and submit a responsive price quote step in using the Request Detail FX Spot interface shown in and describe above. Using this interface the Provider inputs the foreign exchange quote rate 0.920000 in field to be offered to the Member. This step may go through multiple iterations during negotiations between the Provider and the Member with such negotiations occurring via the communication mechanisms provided by the system chat e mail instant messaging or traditional means such as telephone. After submitting its quote the Provider can monitor the status of the quote using the Request Monitor Active interface shown in and described above. The Provider may withdraw the quote at any time while the quote is Active .

The next step in the execution of the trade is the receipt and review of price quotes from one or more Providers by the Member step in . Using the system Members monitor incoming quotes using the request monitor interfaces described above. In addition if specified as a preference a Member can receive automatic notifications e.g. e mail messages from the system upon receipt of a new transaction request. The Request Monitor Current interface shown in and described above displays the new quote. In the present example the Member s FX Spot request and the Provider s quote is displayed with the system assigned identification number 5064 . The display indicates that the member has received one quote in response to its transaction request. Clicking on the request identification number button will cause the system to display the Request Detail FX Spot interface shown in and described above. This interface displays the details of the Member s request as well as the details of the Provider s quote.

After receiving and reviewing the price quote s from one or more Providers unless the Member withdraws its request as described above the Member will select the price quote s of one or more Providers and likely negotiate with the Provider s to obtain a more favorable quote step in . Such negotiations may occur via the communication mechanisms provided by the system chat e mail instant messaging or traditional means such as telephone. For example the Member could click on Chat button shown in to engage in negotiations with the Provider regarding the price quote for that FX Spot transaction. Following such negotiations the Member will accept the quote from one of the Providers step in . The Member can automatically perform this step by clicking Accept button shown in . This will cause the system to display the Acceptance FX Spot interface shown in . This interface displays the details of the accepted quote and transaction including terms and counterparty information.

The Member s action of clicking Accept button shown in will also update the respective request monitors of the Member and the Provider. The Member s Request Monitor Accepted shown in and described above displays the aggregated details of the Member s accepted transaction requests including the FX Spot transaction 5064 of the present example.

The Provider s Request Monitor Current interface shown in and described above will display the aggregated details of the Provider s active price quotes accepted by Members including the FX Spot transaction 5064 of the present example. In addition if specified as a preference a Provider can receive automatic notifications e.g. e mail messages from the system upon receipt of acceptance of a quote by a Member. At this stage and using this interface the Provider could attempt to further communicate or negotiate with the Member e.g. by initiating a chat session by clicking Chat button or verify i.e. confirm the Member s acceptance of the Provider s quote. This verification step step in can be performed by clicking Verify button shown in . Upon verification the system will re categorize the transaction from an Active request to a Recently Completed quote as shown in . In this example the FX Spot transaction 5064 is shown with a status of Verified . The transaction will also be displayed on the Provider s Request Monitor Verified interface shown in and described above. In addition this verification will be displayed on i the Member s Request Monitor Verified interface shown in and described above and ii the Request Monitor Current of other Providers on which the transaction request will be displayed with a status of Dealt Away .

Following acceptance and verification of the transaction and quote the Member and Provider can use the system of this invention to automatically update their proprietary back end systems regarding the transaction step in as described above and to communicate with each other regarding settlement and payment step in . The system also enables the Member and Provider to continue to track and manage the transaction including cashflows and fees as will be described below.

In addition to providing system users i.e. Members and Providers with the ability to engage in online financial transactions the present embodiment of this invention also provides a wealth of other interactive functionality to users as described below.

The present embodiment of the invention includes a series of interfaces that enable Members and Providers to personalize and customize the system in order to increase user efficiency and ease of use and enhance the user s experience executing online financial transactions using the system.

Users can personalize the news content provided by the system as shown for example on the My CFOWeb interface illustrated by . By using the personalization interface shown in a user can select one or more news content modules tools summaries and charts from Available Modules pull down menu and specify the on screen location of such content using the Left Panel Middle Panel and Right Panel fields in conjunction with the Add Remove buttons. Clicking the Update button shown in will cause the system to save the user s selections.

In addition to the filtering feature described above the system provides interfaces that enable users to set their system profiles. Members can specify their identifying and contact information on the Member My Profile interface shown in . Using pull down menus the Member can indicate default reporting currency industry and time zone. Clicking Save button will cause the system to save such profile information.

Similarly Providers can specify their identifying and contact information on the Provider My Profile interface shown in which can be reached by clicking Profile button on the My Profile menu illustrated by . Using pull down menus the Provider can indicate default reporting currency industry and time zone. Clicking Save button will cause the system to save such profile information.

The present embodiment of the invention includes a series of interfaces that enable Members to manage their portfolios of completed transactions. The Trade List interface shown in provides an aggregated summary of each of the Member s completed transactions including the following information for each transaction 

The listing can be ordered by any of the above listed categories of information by clicking on the respective column header. Transaction listings can be deleted by clicking the select indicator adjacent to a listing or clicking Check All button to select all and clicking Delete button . Clicking Run button shown in will cause the system to run a report that can be selected from pull down menu shown in regarding the displayed portfolio of transactions. Such reports may include mark to market summary or detail upcoming events e.g. payments due rate resets foreign exchange shift report interest rate sensitivity report trade ticket or audit report.

Clicking on any of the individual transactions listed in the summary will cause the system to display a detail summary of that particular transaction. In addition the system generates and displays cashflow fee and additional information displays regarding each type of transaction. For example clicking on the identification number 1 shown in for the FX Spot transaction will cause the system to display the FX Spot Details interface shown in . The detail interfaces for each type of transaction will be described below. In describing these interfaces features and or interfaces that are common to more than one type of transaction will only be described once.

The FX Spot Details interface illustrated by displays the details of a particular FX Spot transaction in the Member s transaction portfolio including the following 

Counterparty name . By clicking profile button the Member can view the counterparty s profile information.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking Value button .

Clicking Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking Refresh button .

Clicking Fees button in will cause the system to display the Fees interface illustrated by which shows fees associated with the particular transaction. This interface also enables the Member to add by inputting the information requested in the displayed fields and clicking the Add button or delete by clicking the Delete button payments associated with the transaction.

Clicking Additional Information button in will cause the system to display the Additional Information interface illustrated by which shows user input comments or other information regarding the particular transaction. This interface also enables the Member to add by inputting the information and clicking the Add button or delete by clicking the Delete button additional information. If adding information the Member must input item type value i.e. information and description for each item added.

The FX Forward Details interface illustrated by displays the details of a particular FX Forward transaction in the Member s transaction portfolio including the following 

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

The FX Swap Details interface illustrated by displays the details of a particular FX Swap transaction in the Member s transaction portfolio including the following 

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

The FX European Option Details interface illustrated by displays the details of a particular FX European Option Foreign Exchange Option transaction in the Member s transaction portfolio including the following 

Delivery Date the date on which either the cashflow or underlying trade amount must be exchanged upon exercise of the option.

Principal the amount of currency to be converted into the currency to be bought or sold upon exercise of the option.

Delivery radio button showing whether to settle i the net cashflow only of the underlying trade Cash or ii the underlying trade Physical upon exercise of the option.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

The Fixed Float Interest Rate Swap Details interface illustrated by displays the details of a particular Fixed Float Interest Rate Swap transaction or a Float Fixed Interest Rate Swap in the Member s transaction portfolio. The system includes similar interfaces for the Float Float Interest Rate Swap Fixed Fixed Cross Currency Swap Fixed Float Cross Currency Swap or a Float Fixed Cross Currency Swap and Float Float Cross Currency Swap transactions. The details displayed by the interface include the following 

First Fixing Rate the interest rate to be used for the first interest rate calculation period for the floating Receive Leg optional .

Day Count the day count method to be used for calculating interest specified for each of the i fixed leg and ii floating leg.

Payment Frequency the frequency of interest payment specified for each of the i fixed leg and ii floating leg.

Roll Date the specific convention and day for each period to be used for determination of payment of interest when such event occurs on a non business day specified for each of the i fixed leg and ii floating leg.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets for the floating leg.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations specified for each of the i fixed leg and ii floating leg.

Stub an indicator for an irregular schedule of payments specified for each of the i fixed leg and ii floating leg.

Stub Length the irregular payment schedule length specified for each of the i fixed leg and ii floating leg.

Compounding Frequency interest compounding calculation frequency specified for each of the i fixed leg and ii floating leg.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

Clicking the Rate Resets button in will cause the system to display the Rate Resets interface illustrated by which shows all past and future rate reset events for the particular transaction and enables specification of a Lock and Lock Rate . Any one of these rates can be locked by resetting such rate and clicking the Update button.

The Forward Rate Agreement Details interface illustrated by displays the details of a particular Forward Rate Agreement transaction in the Member s transaction portfolio including the following 

Term the start and end dates of the trade e.g. 3.times.6 months means that the trade will begin on the first business date three months after the trade date and will end on the first business date six months after the trade date.

Notional Amount the amount and type of currency to be used as a basis for calculating the payment stream.

Forward Rate Agreement Rate the Forward Rate Agreement rate that triggers the payments of the Forward Rate Agreement.

Roll Date the specific convention and day for each period to be used for determination of payment of interest when such event occurs on a non business day.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

Clicking the Rate Resets button in will cause the system to display the Rate Resets interface illustrated by which shows all past and future rate reset events for the particular transaction and enables specification of a Lock and Lock Rate . Any one of these rates can be locked by resetting such rate and clicking the Update button.

The Fixed Rate Deposit Details interface illustrated by displays the details of a particular Fixed Rate Deposit transaction in the Member s transaction portfolio including the following 

Rate the interest rate of the deposit. Day Count the day count method to be used for calculating interest.

Roll Date the specific convention and day for each period to be used for determination of payment of interest when such event occurs on a non business day.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button will cause the system to display the Cashflows interface illustrated by which shows future cashflow information payments in or out regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

The Cap Details interface illustrated by displays the details of a particular Cap transaction in the Member s transaction portfolio including the following 

Notional Amount the amount and type of currency to be used as a basis for calculating the payment stream.

Roll Date the specific convention and day for each period to be used for determination of payment of interest when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface in also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button in will cause the system to display the Cashflows interface illustrated by which shows future cashflow information regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

Clicking the Fees button in will cause the system to display the Fees interface illustrated by which shows fees associated with the particular transaction. This interface also enables the Member to add by inputting the information requested in the displayed fields and clicking the Add button or delete by clicking the Remove button payments associated with the transaction.

Clicking the Rate Resets button in will cause the system to display the Rate Resets interface illustrated by which shows all past and future rate reset events for the particular transaction and enables specification of a Lock and Lock Rate . Any one of these rates can be locked by resetting such rate and clicking the Update button.

The Floor Details interface illustrated by displays the details of a particular Floor transaction in the Member s transaction portfolio including the following 

Notional Amount the amount and type of currency to be used as a basis for calculating the payment stream.

Roll Date the specific convention and day for each period to be used for determination of payment of interest when such event occurs on a non business day.

Rate Reset Calendar the location specific e.g. New York London calendar to be used for reference to business holidays for interest rate resets.

Holidays the location specific e.g. New York London business holidays to be used for reference for payment calculations.

Legal Entity the name of the Member or the Member s associated legal entity to which the transaction will be assigned.

The interface in also displays indicative valuation information e.g. net present value regarding the transaction which is the value of the transaction against the latest market data. The valuation can be calculated for the particular date of display by clicking the Value button.

Clicking the Cashflows button in will cause the system to display the Cashflows interface illustrated by which shows future cashflow information regarding the particular transaction. This information can be refreshed by clicking the Refresh button.

Clicking the Fees button in will cause the system to display the Fees interface illustrated by which shows fees associated with the particular transaction. This interface also enables the Member to add by inputting the information requested in the displayed fields and clicking the Add button or delete by clicking the Remove button payments associated with the transaction.

Clicking the Rate Resets button in will cause the system to display the Rate Resets interface illustrated by which shows all past and future rate reset events for the particular transaction and enables specification of a Lock and Lock Rate . Any one of these rates can be locked by resetting such rate and clicking the Update button.

The present embodiment of the invention includes a series of interfaces that provide current market data to system users. Such data is periodically at fixed intervals refreshed by real time market feeds to the system. These interfaces include the following 

 Market Summary interface shown in provides an overview summary of key exchange rates interest rates treasury rates and other indices.

 Foreign Exchange Cash interface shown in provides a summary of international currency exchange rates.

 Exchange traded Instruments interface shown in provides a summary of international exchange traded instrument e.g. bond and short contracts .

The present embodiment of the invention includes a series of interfaces that provide current news and financial information to system users. Such data is continually refreshed. The World Business interface illustrated by displays current world and business news headlines. In addition this interface and other news interfaces include a search function that enables a user to input a term in field and search for that term in the news by clicking the Search button.

The Industry news interface illustrated by displays the current news headlines for the particular industry e.g. Airlines selected by the user in industry list . The World Business news interface illustrated by displays the current international business news headlines.

The Foreign Exchange news interface illustrated by displays the current news headlines relating to international exchange rates and markets. The interface also provides access to market briefs. For example clicking MCM button will cause the system to display foreign exchange market analysis prepared by MCM as shown in .

The Money Markets news interface illustrated by displays the current news headlines relating to international money markets. The interface also provides access to market briefs. For example clicking Briefing.com button will cause the system to display interest rate analysis prepared by Briefing.com as shown in . The Credit Markets news interface illustrated by displays the current news headlines relating to international credit markets and provides access to market briefs. The Equities news interface illustrated by displays the current news headlines relating to international equities markets and provides access to market briefs. Finally the Commodities news interface illustrated by displays the current news headlines relating to international commodities markets and provides access to market briefs.

The present embodiment of the invention includes a series of interfaces that provide relevant financial research content to system users. The Ideas interface illustrated by displays links to content and articles regarding international finance topics. The interface also includes links to Best Practices and Content Providers . Clicking Content Providers button causes the system to display the Content Providers interface illustrated by . This interface includes links to information regarding the providers of system content. For example clicking link will cause the system to display information regarding content provider Deloitte Touche.

The Research interface illustrated by displays a topic index to financial research and analysis briefs prepared by various content providers. The user can link to particular briefs or a listing of all briefs prepared by a content provider. For example clicking BNP Paribas link or will cause the system to display the BNP Paribas Research interface illustrated in . This interface lists various research briefs prepared by BNP Paribas that can be downloaded by the user.

The Providers interface illustrated by provides links to the web sites of certain Providers. These are the same Providers that engage in transactions with Members. For example clicking BNP Paribas link will cause the system to link to BNP Paribas web site.

As described above the present embodiment of the invention enables users i e. Members and Providers to engage in chat communications regarding transaction requests and price quotes. The system supports such chat via chat server in . For example the Member Request Monitor Current interface shown in enables the Member to click on the Chat button to initiate chat with a Provider regarding a particular transaction request. In the present embodiment upon initiation of the chat the system will display a pop up interface that displays the following 

The present embodiment of the invention also enables users i.e. Members and Providers to communicate with each other as well as the system via electronic mail. The system supports secure e mail via e mail server in . An e mail message may include an XML document detailing the description of a transaction request the recipient of such a message can examine the transaction description using a variety of XML tools. Such XML tools may have the capability to create the transaction and provide real time pricing analytics from the e mail message. The system may also send XML messages directly to users back end systems such systems may include XML interpreters that receive and automatically process transaction requests.

The present embodiment of this invention includes a system that enables a corporate entity to request two way pricing from banks using the system i.e. the entity can request a price quote for both the purchase and sale of currency without informing the banks in advance whether the entity will be buying or selling currency. Such two way pricing is available for the various transaction types e.g. FX Spot FX Swap Outright etc. handled by the system as described herein .

The user interface shown in also includes buttons that enable the bank to refresh the bid offer rates from an automatic feed button withdraw a price quote button decline a request for price quote button and send a new or modified price quote to the requesting entity button .

The inventions described herein can be implemented to process transactions involving multiple bank users for example a bank to bank to bank to corporate user transaction. By way of example as shown in corporate user seeks a price quote for a particular currency pair transaction from regional bank and sends Request for Quote . Unknown to corporate user upon receipt of Request for Quote regional bank automatically generates and sends Request for Quote to money centre bank using the same terms and parameters as Request for Quote . Note that regional bank can send Request for Quote to more than one money centre bank in order to receive the best price quote from multiple money centre banks

If money centre bank does not make a currency trading market in the particular currency pair of Request for Quote money centre bank unknown to regional bank automatically generates and sends Request for Quote to local bank using the same terms and parameters as Request for Quote . Note that money centre bank can send Request for Quote to more than one local bank in order to receive the best price quote from multiple local banks

If local bank makes a currency trading market in the particular currency pair of Request for Quote local bank automatically generates and sends Price Quote A to money centre bank which represents the price at which local bank will deal with money centre bank for the requested currency pair transaction. If local bank does not make a currency trading market in the particular currency pair of Request for Quote local bank unknown to money centre bank automatically generates and sends a request for quote to one or more other banks not shown using the same terms and parameters as Request for Quote . This process could be repeated until the system located a bank that made a currency trading market in the particular currency pair of Request for Quote .

Upon receipt of Price Quote A from local bank or if money centre bank makes a currency trading market in the particular currency of Request for Quote money centre bank automatically generates and sends Price Quote B to regional bank which represents the price at which money centre bank will deal with regional bank for the requested currency pair transaction. If money centre bank received Price Quote A from local bank Price Quote B would reflect the application of a spread function to the rate of Price Quote A.

Upon receipt of Price Quote B from money centre bank regional bank automatically generates and sends Price Quote C to corporate user which represents the price at which regional bank will deal with corporate user for the requested currency pair transaction. Price Quote C would reflect the application of a spread function to the rate of Price Quote B.

Note that the number of i levels of banks e.g. regional bank money centre bank local bank ii and banks per level that participate in such a transaction can be greater or lesser than the example described above. Furthermore the flow of a transaction need not follow the path illustrated by but instead may pass through one or more of the bank levels in a different order or direction than shown.

The present embodiment of this invention includes a system that provides customized continuous price quotes specific to a particular customer e.g. corporate user for certain financial products. The banks providing such price quotes compute the quotes based on information regarding the particular customer including for example the customer s transaction history or credit history with a particular bank. The system provides customers with continuously available prices that enable a customer to select and accept a specific best rate buy or sell for a specific financial product and execute a transaction for that product with a particular bank without having to negotiate with the bank regarding the transaction. The system provides the quotes to a particular customer based on the customer s profile criteria for example particular types of financial products for which the customer chooses to receive price quotes and particular banks from which the customer choose to receive such quotes.

Pricing server distinguishes the offers to sell Quotes 1 3 from the offers to buy Quotes 2 4 and processes them separately. In step pricing server determines the best offer to sell by comparing Quote with Quote . Upon determining the best offer to sell Quote in this example as the Euro rate is lower pricing server will perform a credit check on the bank that provided the best offer to sell Bank in order to determine whether the particular customer has a current credit relationship with that bank step and that the daily notional amount of credit between the customer and the bank has not been exhausted. If such a credit relationship exists and is not exhausted pricing server will display the best offer to sell Quote to the customer on an interactive display interface step if not pricing server will return to step in order to determine the next best offer to sell and then perform a credit check on that offer.

Similarly with respect to the offers to buy Quotes 2 in step pricing server determines the best offer to buy by comparing Quote with Quote . Upon determining the best offer to sell Quote in this example as the Euro rate is higher pricing server will perform a credit check on the bank that provided the best offer to buy Bank in order to determine whether the particular customer has a current credit relationship with that bank step . If such a credit relationship exists pricing server will display the best offer to buy Quote to the customer on an interactive display interface step if not pricing server will return to step in order to determine the next best offer to sell and then perform a credit check on that offer.

Once pricing server displays to the customer the respective best offers to buy and or sell the customer can select and execute a purchase and or sale of currency up to the amounts specified by the offering bank s . For example if the customer selected to execute Quote the customer could purchase up to US 6 000 000 from Bank at the rate of 0.8510 Euro. If the customer elected to purchase only US 4 000 000 at that rate the particular offer to sell would continue to be displayed except the amount of currency for sale would be modified by pricing server in order to reflect the customer s purchase i.e. US 2 000 000 instead of US 6 000 000 if the customer elected to purchase the entire amount of currency offered for sale pricing server would remove the offer to sell from the customer s display interface. The best offer to buy would be processed in the same manner.

Pricing server will display each of the best offers to the customer until one of three events occurs 1 the offering bank withdraws the particular offer or it automatically expires 2 the entire amount of currency offered for purchase or sale is exhausted whether in one or multiple transactions or 3 pricing server receives a new offer and determines that it is the best offer and removes the current best offer from that display position. Note that in certain embodiments of this invention the customer could choose to have more than one best offer displayed for each type of transaction e.g. purchase or sale of currency in which case pricing server would perform the best offer determinations and credit checks accordingly.

In an embodiment of the present invention the system includes a method and mechanism for enabling an entity requesting a price quote to define the best price rules used to highlight the price quotes displayed to the entity when quotes are returned from banks in response to a request for price quote. The rules that can be defined using the system include highest bid lowest offer tightest spread of bid offer fastest initial price fastest current price and specified bank.

The entity can define such rules using the Best Price Rules preference user interface as shown in . Using that interface the entity can define the best price criteria e.g. Highest bid and lowest offer Tightest bid offer spread Selected bank and specify the rank for application of each definition by clicking on the appropriate indicator e.g. First Second Third . The system will apply the entity s ranked definitions in order to display the best price as price quotes are returned from banks. In the case of a tie between price quotes under the first definition the system will use the second and third definitions to break the tie and determine the best price. If the price quotes are still tied under all three definitions the system will choose the best price based on alphabetical order of the banks names. Note that in different embodiments of this invention the number of definition levels could be lower or higher the best price criteria could be different and the tie breaking rules could be different.

With respect to the highest bid lowest offer rule the best price is defined as either the highest bid or the lowest offer depending on whether the entity is looking to sell or buy the base currency in the requested currency pair. When the entity is looking to buy the base currency the best price will be the lowest offer quoted by a bank conversely when the entity is looking to sell the base currency the best price will be the highest bid quoted by a bank.

With respect to the tightest bid offer spread rule the best price is defined as the set of price quotes with the narrowest bid offer spread.

With respect to the fastest initial price rule the best price is defined as the first price quote made most quickly in response to the request for quote. As a bank may change or refresh its price while the corporate entity is waiting for other banks to respond the best price definition under this scenario will still take the first price quote made most quickly as the best price even if an equivalent price was actually a subsequent change to a price quote. As the quotes on the screen are listed in the order in which the initial quotes are made the best price will thus be the first line of the price quote for the particular transaction.

With respect to the fastest current price rule the best price is defined as the fastest submitted price quote among all the available price quotes. Once there are updates made to the quotes the amended quotes will be moved to the end of the displayed queue. If this happens to the current best price the next in line quote will then be used as the current best price .

With respect to the specified bank rule the best price is defined as the price quote being submitted by the specified bank identified by the corporate entity on its preference user interface. This selection will not be considered for the particular request if the bank selected on the preference interface is not included on the list of banks to which the request for price quote is being sent.

In addition to the features described herein embodiments of this invention may include further features integrated into the system.

In certain embodiments of this invention as described above i users e.g. Members submit transaction requests that are aggregated and displayed to one or more other users e.g. Providers and ii one or more of the recipient users i.e. Providers submit responsive price quotes that are aggregated and displayed to the requesting user i.e. Member . The participating users negotiate with each other regarding such transaction requests and quotes via the system supported chat instant messaging e mail communications and text included with the requests and quotes or other traditional means such as telephone or Internet wide e mail.

Price improvement occurs when a price quote changes or improves for certain trading partners either publicly or confidentially using automated software routines or manual intervention. Price improvement may occur on the basis of existing relationships between certain users e.g. a particular Member always receives a discount from a Provider transaction type e.g. FX Spot transaction size e.g. volume discount credit ratings of potential partners industry of potential partners or other trading policies or parameters.

In certain embodiments of this invention Providers can execute custom user defined trading policy templates or utilize system defined buying pattern templates or a mix of user defined and system defined templates that will automatically modify price quotes according to the parameters detected. Similarly in certain embodiments Members can execute custom user defined trading policy templates or utilize system defined buying pattern templates or a mix of user defined and system defined templates that will automatically respond to price quotes by modifying them and submitting such modifications to the quoting Providers according to the parameters detected. Automated trading policies or templates can also be implemented to conduct block transactions. Such automated policies may include 

distributing pieces of a transaction among multiple transaction types breaking a transaction into pieces over multiple time increments

In certain embodiments of this invention Providers or other users may push tradable price quotes to an aggregated real time display for review by potential trading partners i.e. Members . The tradable quotes submitted by Providers are at price levels at which the Providers are willing to execute transactions though the prices may be improved or negotiated down. Such quotes may be targeted to and customized for certain trading partners and enable potential trading partners to view transaction price quotes before submitting requests for price quotes. The pushing users may include individual banks and financial institutions as well as consortiums of multiple banks and financial institutions. The aggregated display of tradable quotes which may be in the form of a product matrix including product e.g. FX Spot price or rate currency Provider transaction limits expiration date time may also include a filter to display only the best price for a particular type of financial transaction. The tradable price quotes are determined by sending a market data message through a set of workflow rules which may consider transaction type notional amount date and time and or category and credit rating of the potential trading partners.

Upon review of such price quotes in the aggregated real time display recipient trading partners may i accept a quote as is and execute a transaction ii accept an improved quote and execute a transaction or iii communicate with the pushing user and negotiate the price down. Quote acceptance occurs when a trading partner hits a price at an acceptable level either 1 manually by clicking on the quote in the display and triggering acceptance verification and settlement with the pushing user or 2 automatically via a software routine or robot programmed to accept quotes at a certain level.

Embodiments of this invention can support multi party transactions. In such a transaction a user i.e. Member structures the transaction so that it is divided among more than one other parties i.e. Providers . Each of those other parties will provide a portion of the traded asset in an amount determined by the user s structured transaction. For example a Member may seek an exchange of 1 Million Euro for U.S. Dollars where one Provider will exchange a certain amount of U.S. Dollars for 400 Thousand Euro and the other Provider will exchange a certain amount of U.S. Dollars for 600 Thousand Euro. The system enables the user to accept multiple price quotes for the transaction with one acceptance and it displays such acceptance on the various display monitors in the same way that a single party transaction is displayed. In other embodiments the system enables the user to accept multiple price quotes for the same transaction with multiple acceptances.

Embodiments of this invention include automated alerts whereby the system providers a user with customized notifications or alerts based on the particular user s portfolio trading activity or profile information. Such alerts may be in the form of e mail messages or auto refreshing pop up windows that are displayed while a user is engaged with the system. Alerts may be sent to notify users of events including without limitation a new transaction request or price quote a change in an interest market or foreign exchange rate or equity price an upcoming event relating to the user s portal e.g. payment due date option date or an upcoming economic event.

Embodiments of this invention include functionality that enables Providers such as individual banks and financial institutions to automatically aggregate or net buy and sell orders from requesting users e.g. Members for execution in order to eliminate the step of having such orders transmitted to the Provider s trading desk for execution. For example for a particular foreign exchange transaction a Provider may offer at a particular moment in time a bid i.e. buy price of 34 and an ask i.e. sell price of 36 which produces a spread of 2 36 34 . Typically the Provider will pass that spread on to its trading desk which in order to make a profit will increase the spread by 1 on each side i.e. bid price 33 ask price 37 spread 4. The trading desk will in turn pass the spread on to individual salespersons who in order to make a profit will increase the spread when they offer the foreign exchange transaction to customers. The offers may also vary by customer based on factors that may include creditworthiness relationship with the Provider and industry. Thus in this example a salesperson may offer a bid price of 31 and an ask price of 39 spread 8 to a particular customer but on average will offer a bid price of 32 and an ask price of 38 average spread 6 . The trading desk will pass the spread offer to the salesperson with for a set duration of time e.g. 10 seconds during which the trading desk will honor the offer even though the market prices for the transaction continue to move. The salesperson will accept orders from customers based on the offer and submit each order separately to the trading desk less the salesperson s profit included in the offer spread for execution.

Using the functionality included in embodiments of this invention during the time period e.g. 10 seconds during which the trading desk will honor the offer to the salesperson the system will automatically aggregate the customers orders to buy and sell based on the trading desk offer and transmit the net difference to the trading desk for execution. The opportunity to net the trades will occur where different customers have accepted offsetting offer prices but where the offer duration e.g. 10 seconds for the first accepting customer has not yet expired. This functionality will eliminate overhead salesforce costs in that most orders will be aggregated without requiring separate execution of trades by the trading desk.

The foregoing description of a preferred embodiment of the invention has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Obviously many modifications and variations will be apparent to practitioners skilled in this art. One skilled in the art will readily appreciate that other applications may be substituted for those set forth herein without departing from the spirit and scope of the present invention. Accordingly the invention should only be limited by the claims included below.

