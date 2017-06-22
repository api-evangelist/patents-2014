---

title: Security testing of web applications with specialized payloads
abstract: In one embodiment, a computer-implemented method for security testing of web applications with specialized payloads includes submitting a test to a web application, where the test includes a payload with a set of constraints. A response is received from the web application. One or more constraints are derived from the response. The set of constraints of the payload are updated with the derived one or more constraints. The payload is synthesized, by a computer processor, for the updated set of constraints. The test having the synthesized payload is iterated with the updated set of constraints.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09436829&OS=09436829&RS=09436829
owner: GLOBALFOUNDRIES INC.
number: 09436829
owner_city: Grand Cayman
owner_country: KY
publication_date: 20140919
---
This application claims priority to Great Britain Patent Application No. 1318119.3 filed 14 Oct. 2013 and all the benefits accruing therefrom under 35 U.S.C. 119 the contents of which in its entirety are herein incorporated by reference.

Embodiments of this disclosure relate to the field of security testing of web applications or services and more particularly to security testing of web applications with specialized payloads.

Security testing is an important area of research and development. The rapid growth of mobile applications web applications and web services creates many opportunities for security attacks thus emphasizing the need for quality testing of such applications.

One of the main challenges in security testing is to synthesize quality payloads which are likely to demonstrate vulnerabilities in the target software system if such vulnerabilities indeed exist.

Current techniques rely on a generic pool of test payloads. These are not specific to the target application. Instead a security expert defines all the payloads in advance and the testing tool is then responsible for choosing which of the predefined payloads to send and in what order.

Advanced products have some limited adaptation capabilities deciding which payloads from the pool to try when testing a given application. In these products the choice of next payload is based on an analysis of why the last payload failed.

The testing tool has limited insight into the workings of server side defenses. This has traditionally led commercial as well as research vulnerability scanners toward heuristic approaches such as testing each input point e.g. Hypertext Transfer Protocol HTTP parameter with a short predefined list of effective test payloads to balance between coverage and performance.

In one embodiment a computer implemented method for security testing of web applications with specialized payloads includes submitting a test to a web application where the test includes a payload with a set of constraints. A response is received from the web application. One or more constraints are derived from the response. The set of constraints of the payload are updated with the derived one or more constraints. The payload is synthesized by a computer processor for the updated set of constraints. The test having the synthesized payload is iterated with the updated set of constraints.

In another embodiment a system includes a memory and one or more processors communicatively coupled to the memory. The one or more processors are configured to submit a test to a web application where the test includes a payload with a set of constraints. The one or more processors are further configured to receive a response from the web application and to derive one or more constraints from the response. The one or more processors are further configured to update the set of constraints of the payload with the derived one or more constraints and to synthesize the payload for the updated set of constraints. The one or more processors are further configured to iterate the test having the synthesized payload with the updated set of constraints.

In yet another embodiment a computer program product for security testing of web applications with specialized payloads includes a computer readable storage medium having program instructions embodied therewith. The program instructions are executable by a processor to cause the processor to perform a method. The method includes submitting a test to a web application where the test includes a payload with a set of constraints. Further according to the method a response is received from the web application. One or more constraints are derived from the response. The set of constraints of the payload are updated with the derived one or more constraints. The payload is synthesized for the updated set of constraints. The test having the synthesized payload is iterated with the updated set of constraints.

Additional features and advantages are realized through the techniques of the present invention. Other embodiments and aspects of the invention are described in detail herein and are considered a part of the claimed invention. For a better understanding of the invention with the advantages and the features refer to the description and to the drawings.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the disclosure. However it will be understood by those skilled in the art that the various embodiments of the disclosure may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the embodiments described.

Method and system are provided for dynamic security testing whereby the testing tool does not require a list of candidate payloads in advance of testing. Instead the payloads are generated on the fly during testing based on a synthesis algorithm that is guided by hints or constraints derived from the ongoing testing session.

The payload is the information sent to a web application at a server for testing. Example payloads may include Extensible Markup Language XML information for web services a uniform resource locator URL for PHP Hypertext Preprocessor scripts Representational State Transfer REST web services etc. The payload may contain parts generated by the described method using specific grammar adapted for the technical context. The grammar of the payload describes the way the items or vocabulary are structured together.

Referring to a testing system environment is illustrated including a data processing system which may be remotely connected to a server which may host a web application . The data processing system and server may be in communication via a network .

The data processing system may include a testing system for testing the security of the web application . Web applications are highly vulnerable to security attacks. The testing system may aim to detect vulnerabilities in the web application .

The testing system may include a payload synthesizer for synthesizing a payload for testing based on constraints derived from the testing session. The payload synthesizer may include a constraint adaptor for updating constraints based on feedback from the testing.

The testing system may include a test starting point component for determining a starting probe or payload. A test submitting component may submit the test to the web application and receive the test response. A response analysis component may analyze the response and determine the outcome of the test.

The testing system may include a constraint feedback component for updating the constraint adaptor based on the response to the previous test. An outcome component may be provided to report the outcome of the testing to a user.

Referring to an exemplary system for implementing aspects of the invention includes a data processing system suitable for storing or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements may include local memory employed during actual execution of the program code bulk storage and cache memories that provide temporary storage of at least some program code to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also include a primary storage means such as a magnetic hard disk drive and secondary storage means such as a magnetic disc drive and an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices may be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter which may include a GPU.

At the beginning of the method in a first iteration there are no specific constraints to synthesize the first payload. Therefore a payload is created at block based on existing grammar using various techniques adapted for the technical context. In some embodiments this first generation may be done randomly using tokens from a vocabulary that respects the grammar. For example token number X from the vocabulary may be selected and then other tokens are added as required using the rules defined by the grammar so that the result is a payload that starts with token X and respects the grammar.

A payload vocabulary V is initially input at block initialized with an empty or starting set of constraints C. A starting point may be selected at block which may be an arbitrary probe or payload.

The payload may then be submitted at block to the subject application. A response may be received and analyzed for the payload sent at block .

It may be determined at block if the analysis is successful. If so then the process may exit the testing loop at block .

If the analysis is not successful constraints may be derived at block from the test failure and these may be added at block to the set of constraints C. A new payload over V may be synthesized at block where the payload is compatible with the updated set of constraints C.

An input is made at block of payload grammar P and an input point PT. The payload grammar P is encoded at block as propositional formula F. A payload test TST is obtained at block as a SAT model of F. A SAT model is a satisfying or unsatisfying solution which takes the set of constraints dynamically generated and applies them to the grammar to determine if it is possible to generate a new payload that respects the grammar and also respects the existing constraints.

If there is no possible model at block it is UN SAT which means that there are no more solutions for this problem and the process exits at block as no vulnerability is found.

For example in some embodiments if previous tests have proven that some tokens are well handled by the application i.e. tokens X Y and Z then as a result the constraints payload should not contain token X payload should not contain token Y etc. may be added and the SAT solver may attempt to generate the new payload based on these constraints. If this is not possible the result is UN SAT and there are no more solutions and therefore no vulnerability is found.

It may be determined at block if the response is valid. For example this may be determined by testing that the answers from the server do not contain the previously injected tokens. If the test succeeded for example in the case that the server side allows the return to the end user some injected tokens then the process exits at block with a detected vulnerability with the payload test.

If the test failed payload constraints CNS may be derived at block from the response. A new propositional formula F is proposed at block equal to the previous F conjoined with the constraints. The new propositional formula F is input into step to obtain a payload test as a SAT model of the new F and the method iterates.

To cast this algorithm into a concrete example setting consider security testing of web applications for example for cross site scripting XSS vulnerabilities. XSS is ranked as one of the top web vulnerabilities. XSS enables attackers to inject client side scripts into web pages viewed by other users. An XSS vulnerability permits an attacker to bypass access controls such as the same origin policy which can lead to significant security risks. Such risks commonly include transmitting private data like cookies to the attacker or redirecting the victim to web content controlled by the attacker.

In this example embodiment the vocabulary for synthesis of new payloads consists of XSS tokens such as script alert JavaScript etc. Constraints learned during testing may be about the tokens within the payload that undergo sanitization for example if the response replaces script by an empty string .

In some embodiments synthesis of new payloads can be achieved with a standard satisfiability solver where the learned sanitization related constraints and structural constraints over payloads are encoded in propositional form.

More specifically consider the common case of a PHP Hypertext Preprocessor PHP page and cross site scripting vulnerabilities. By design such attacks consist of attempts to inject code i.e. user provided scripts to the remote server using vulnerabilities e.g. permeability to such injection due to a lack of sanitizer .

Vulnerabilities that may also be detected arise when the server side allows the return to the end user of some tokens that belong to the XSS grammar whereas the server side could have sanitized all the tokens.

The context for XSS vulnerabilities is to check that there are no capabilities for an external source to craft the server answer with code that would be executed on the client side. This kind of code injection could change the behavior of the HTML page. For example such a code injection may introduce redirection to incorrect URLSs change behavior of specific buttons alter display of information etc. To avoid this the server side could sanitize all the inputs in order to deleted all the possible code injection attempts.

An example implementation is described of a PHP script that will ask for parameters and will return the result of the input in terms of a form that compiles the previous parameters.

That is the structure on the client side of the call i.e. the payload executed against the server may be 

For this example it is assumed also that the server side code is protected by a sanitizer intended to prevent this code injection. The structure of this sanitizer may be 

An aim of the described method within this XSS technical context will be to double check that the sanitizer in place on the server side does not offer permeability to a cross site scripting attack. The described method adapted to the XSS context may thus define an XSS payload grammar with test payloads start with a default payload validate whether the result is correct or not according to the existence of the attack into the server answer update as required the SAT encoding so that a new payload is created and then loop over the previous statements.

In a first iteration begin with the SAT formula true which lets whichever payload is wanted to be sent. Send some arbitrary payload for example 

The above may be represented as a constraint over the grammar stating that the payload may not contain the token onmouseover.

In a second iteration search for a payload that models the updated SAT formula. One such payload may be 

Thus update the SAT formula to contain the additional constraint that the token script is not contained in the payload.

In a third iteration search for a production of the grammar that models the updated SAT formula containing two constraints which leads to payload 

In the specific embodiment referred to in the example the learned constraints are over the tokens having a payload i.e. grammar tokens in the grammar representation . Other options exist including more advanced types of constraints. As an example regular constraints i.e. ones that can be expressed as a regular language over the entire payload may be used. This is useful in cases where the server side defenses are implemented as a regex match. The described method and system need not commit to any particular style of constraints but give only examples of possible constraint representations.

As for the actual encoding following the propositional variables that are being introduced are explained. For the simple example of token based constraints assume that there are n tokens t 1 . . . t n such that each payload is a sequence over this set of tokens. Starting with the basic SAT setting which abstracts away the payload s being a sequence and treats it as a set of tokens each propositional variable corresponds to a single token. Thus v 1t1 . . . v nt n. The formula is essentially the conjunction of token based constraints e.g. v 1 v 3 v 5 which means that the payload need not contain tokens v 1 v 3 and v 5.

A more sophisticated encoding may also account for the fact that the payload is a sequence and thus may define a unique propositional variable per each token offset pair where for instance v 3 1 means token v 3 at offset 1 within the payload. This is useful if server side defenses are likely to block a token at a certain position but not in other positions. There are known real world sanitization examples of this nature.

An additional point is about encoding the grammar itself. Following it is explained how this is done by means of an example. Assume for simplicity that the grammar contains only three tokens t 1 t 2 t 3 and two productions t1 t2 and t 1 t3 . Then generate the following initial formula v 1 v 2 v 1 v 3 . Now turn to the SAT solver for the first payload and get back v 1 1 v 2 1 which corresponds to payload t 1 t2 . Assume now that the constraint t 2 is learned. Then the updated formula is v 1 v 2 v 1 v 3 v 2. Turn to the SAT solver again and this time it directs to t 1 t 3 .

It would be understood that this form of encoding may put the grammar productions rather than the grammar itself into the form of a propositional formula. For a standard grammar of security payloads it may also be possible to encode the grammar directly into a propositional formula by distinguishing via propositional variables different occurrences of non terminal tokens. While both options are viable the former option may be simpler than the latter alternative of encoding the grammar directly.

An advantage of the described method is that the synthesized payloads may be specialized per the behavior of the application under consideration.

The developers of the testing algorithm are relieved of the burden of building and later maintaining and updating a comprehensive database of payloads in support of the tool which is a tedious and non trivial task that requires high expertise.

Users of the algorithm do not need to worry about updates and maintenance issues. Also the threat of poor coverage by the algorithm because the payloads are not up to date may be lifted.

According to an embodiment of this disclosure there is provided a method for security testing of web applications with specialized payloads. The method may include submitting a test to a web application where the test includes a payload with a set of constraints. One or more constraints are derived from a received response to the test. The set of constraints may be updated with the derived constraints. The payload may then be synthesized for the updated set of constraints. The test having the synthesized payload may be iterated with the updated set of constraints.

The method may further include creating a payload including defined grammar describing the way items in the payload are structured together. In one embodiment before a first iteration of the test a payload may be generated using random items that respect the grammar. The test may have a first payload with an empty set of constraints.

The method may further include applying the set of constraints to the grammar to determine whether it is possible to generate a new payload that respects the grammar and respects the existing constraints. The application may use a satisfying or unsatisfying solution solver.

In one embodiment the payload grammar may be encoded as a propositional formula. The one or more constraints may be token based constraints. Alternatively the one or more constraints may be regular language constraints over the entire payload.

In one example embodiment the test may be a test for cross site scripting and the payload may include constraints in the form of tokens which should be sanitized by a server hosting the web application under test.

The payload may be a sequence and may define a unique propositional variable for each token offset pair.

The payload may further include encoding grammar into a propositional formula by distinguishing different occurrences of non terminal tokens.

Another embodiment may be a system for performing a method having the above features or a computer program product executable by a computer processor to implement such a method.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.

