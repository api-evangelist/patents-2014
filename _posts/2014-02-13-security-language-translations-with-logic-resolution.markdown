---

title: Security language translations with logic resolution
abstract: Security language constructs may be translated into logic language constructs and vice versa. Logic resolution may be effected using, for example, the logic language constructs. In an example implementation, translation of a security language assertion into at least one logic language rule is described. In another example implementation, translation of a proof graph reflecting a logic language into a proof graph reflecting a security language is described. In yet another example implementation, evaluation of a logic language program using a deterministic algorithm is described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09282121&OS=09282121&RS=09282121
owner: Microsoft Technology Licensing, LLC
number: 09282121
owner_city: Redmond
owner_country: US
publication_date: 20140213
---
This application is a continuation of and claims priority to U.S. patent application Ser. No. 11 530 556 filed on Sep. 11 2006 the disclosure of which is incorporated by reference herein.

Computers and other electronic devices are pervasive in the professional and personal lives of people. In professional settings people exchange and share confidential information during project collaborations. In personal settings people engage in electronic commerce and the transmission of private information. In these and many other instances electronic security is deemed to be important.

Electronic security paradigms can keep professional information confidential and personal information private. Electronic security paradigms may involve some level of encryption and or protection against malware such as viruses worms and spyware. Both encryption of information and protection from malware have historically received significant attention especially in the last few years.

However controlling access to information is an equally important aspect of securing the safety of electronic information. This is particularly true for scenarios in which benefits are derived from the sharing and or transferring of electronic information. In such scenarios certain people are to be granted access while others are to be excluded.

Access control has been a common feature of shared computers and application servers since the early time shared systems. There are a number of different approaches that have been used to control access to information. They share a common foundation in combining authentication of the entity requesting access to some resource with a mechanism of authorizing the allowed access. Authentication mechanisms include passwords Kerberos and x.509 certificates. Their purpose is to allow a resource controlling entity to positively identify the requesting entity or information about the entity that it requires.

Authorization examples include access control lists ACLs and policy based mechanisms such as the eXtensible Access Control Markup Language XACML or the PrivilEge and Role Management Infrastructure PERMIS . These mechanisms define what entities may access a given resource such as files in a file system hardware devices database information and so forth. They perform this authorization by providing a mapping between authenticated information about a requestor and the allowed access to a resource.

As computer systems have become more universally connected over large networks such as the Internet these mechanisms have proven to be somewhat limited and inflexible in dealing with evolving access control requirements. Systems of geographically dispersed users and computer resources including those that span multiple administrative domains in particular present a number of challenges that are poorly addressed by currently deployed technology.

Security language constructs may be translated into logic language constructs and vice versa. Logic resolution may be effected using for example the logic language constructs. In an example implementation translation of a security language assertion into at least one logic language rule is described. In another example implementation translation of a proof graph reflecting a logic language into a proof graph reflecting a security language is described. In yet another example implementation evaluation of a logic language program using a deterministic algorithm is described.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter. Moreover other method system scheme apparatus device media procedure API arrangement protocol etc. implementations are described herein.

In a described implementation security scheme can be overlaid and or integrated with one or more devices which can be comprised of hardware software firmware some combination thereof and so forth. As illustrated d devices with d being some integer are interconnected over one or more networks . More specifically device device device . . . device are capable of communicating over network .

Each device may be any device that is capable of implementing at least a part of security scheme . Examples of such devices include but are not limited to computers e.g. a client computer a server computer a personal computer a workstation a desktop a laptop a palm top etc. game machines e.g. a console a portable game device etc. set top boxes televisions consumer electronics e.g. DVD player recorders camcorders digital video recorders DVRs etc. personal digital assistants PDAs mobile phones portable media players some combination thereof and so forth. An example electronic device is described herein below with particular reference to .

Network may be formed from any one or more networks that are linked together and or overlaid on top of each other. Examples of networks include but are not limited to an internet a telephone network an Ethernet a local area network LAN a wide area network WAN a cable network a fibre network a digital subscriber line DSL network a cellular network a Wi Fi network a WiMAX network a virtual private network VPN some combination thereof and so forth. Network may include multiple domains one or more grid networks and so forth. Each of these networks or combination of networks may be operating in accordance with any networking standard.

As illustrated device corresponds to a user that is interacting with it. Device corresponds to a service that is executing on it. Device is associated with a resource . Resource may be part of device or separate from device .

User service and a machine such as any given device form a non exhaustive list of example entities. Entities from time to time may wish to access resource . Security scheme ensures that entities that are properly authenticated and authorized are permitted to access resource while other entities are prevented from accessing resource .

As illustrated device A includes two security related components a security token and an application . Security token includes one or more assertions . Device B includes five security related components an authorization context a resource guard an audit log an authorization engine and a security policy . Security policy includes a trust and authorization policy an authorization query table and an audit policy .

Each device may be configured differently and still be capable of implementing all or a part of security scheme . For example device A may have multiple security tokens and or applications . As another example device B may not include an audit log or an audit policy . Other configurations are also possible.

In a described implementation authority issues security token having assertions to entity . Assertions are described herein below including in the section entitled Security Policy Assertion Language Example Characteristics . Entity is therefore associated with security token . In operation entity wishes to use application to access resource by virtue of security token .

Resource guard receives requests to access resource and effectively manages the authentication and authorization process with the other security related components of device B . Trust and authorization policy as its name implies includes policies directed to trusting entities and authorizing actions within security environment . Trust and authorization policy may include for example security policy assertions not explicitly shown in . Authorization query table maps requested actions such as access requests to an appropriate authorization query. Audit policy delineates audit responsibilities and audit tasks related to implementing security scheme in security environment .

Authorization context collects assertions from security token which is are used to authenticate the requesting entity and security policy assertions from trust and authorization policy . These collected assertions in authorization context form an assertion context. Hence authorization context may include other information in addition to the various assertions.

The assertion context from authorization context and an authorization query from authorization query table are provided to authorization engine . Using the assertion context and the authorization query authorization engine makes an authorization decision. Resource guard responds to the access request based on the authorization decision. Audit log contains audit information such as for example identification of the requested resource and or the algorithmic evaluation logic performed by authorization engine .

In a described implementation entity authenticates itself to resource guard with a token security token . Resource guard forwards the token assertions to authorization context . These token assertions are assertions of of security token . Security policy provides the authorization query table to resource guard . The authorization query table derives from authorization query table module . The authorization query table sent to resource guard may be confined to the portion or portions directly related to the current access request.

Policy assertions are extracted from trust and authorization policy by security policy . The policy assertions may include both trust related assertions and authorization related assertions. Security policy forwards the policy assertions to authorization context . Authorization context combines the token assertions and the policy assertions into an assertion context. The assertion context is provided from authorization context to authorization engine as indicated by the encircled A .

An authorization query is ascertained from the authorization query table. Resource guard provides the authorization query auth. query to authorization engine . Authorization engine uses the authorization query and the assertion context in an evaluation algorithm to produce an authorization decision. The authorization decision auth. dcn. is returned to resource guard . Whether entity is granted access to resource by resource guard is dependent on the authorization decision. If the authorization decision is affirmative then access is granted. If on the other hand the authorization decision issued by authorization engine is negative then resource guard does not grant entity access to resource .

The authorization process can also be audited using semantics that are complementary to the authorization process. The auditing may entail monitoring of the authorization process and or the storage of any intermediate and or final products of e.g. the evaluation algorithm logically performed by authorization engine . To that end security policy provides to authorization engine an audit policy from audit policy . At least when auditing is requested an audit record having audit information may be forwarded from authorization engine to audit log . Alternatively audit information may be routed to audit log via resource guard for example as part of the authorization decision or separately.

Generally a device may represent any computer or processing capable device such as a client or server device a workstation or other general computer device a PDA a mobile phone a gaming platform an entertainment device one of the devices listed above with reference to some combination thereof and so forth. As illustrated device includes one or more input output I O interfaces at least one processor and one or more media . Media include processor executable instructions .

In a described implementation of device I O interfaces may include i a network interface for communicating across network ii a display device interface for displaying information on a display screen iii one or more man machine interfaces and so forth. Examples of i network interfaces include a network card a modem one or more ports and so forth. Examples of ii display device interfaces include a graphics driver a graphics card a hardware or software driver for a screen or monitor and so forth. Printing device interfaces may similarly be included as part of I O interfaces . Examples of iii man machine interfaces include those that communicate by wire or wirelessly to man machine interface devices e.g. a keyboard a remote a mouse or other graphical pointing device etc. .

Generally processor is capable of executing performing and or otherwise effectuating processor executable instructions such as processor executable instructions . Media is comprised of one or more processor accessible media. In other words media may include processor executable instructions that are executable by processor to effectuate the performance of functions by device .

Thus realizations for security related implementations may be described in the general context of processor executable instructions. Generally processor executable instructions include routines programs applications coding modules protocols objects components metadata and definitions thereof data structures application programming interfaces APIs schema etc. that perform and or enable particular tasks and or implement particular abstract data types. Processor executable instructions may be located in separate storage media executed by different processors and or propagated over or extant on various transmission media.

Processor s may be implemented using any applicable processing capable technology. Media may be any available media that is included as part of and or accessible by device . It includes volatile and non volatile media removable and non removable media and storage and transmission media e.g. wireless or wired communication channels . For example media may include an array of disks flash memory optical media for longer term mass storage of processor executable instructions random access memory RAM for shorter term storing of instructions that are currently being executed link s on network for transmitting communications e.g. security related data and so forth.

As specifically illustrated media comprises at least processor executable instructions . Generally processor executable instructions when executed by processor enable device to perform the various functions described herein including those actions that are illustrated in the various flow diagrams. By way of example only processor executable instructions may include a security token at least one of its assertions an authorization context module a resource guard an audit log an authorization engine a security policy e.g. a trust and authorization policy an authorization query table and or an audit policy etc. some combination thereof and so forth. Although not explicitly shown in processor executable instructions may also include an application and or a resource .

This section describes example characteristics of an implementation of a security policy assertion language SecPAL . The SecPAL implementation of this section is described in a relatively informal manner and by way of example only. It has an ability to address a wide spectrum of security policy and security token obligations involved in creating an end to end solution. These security policy and security token obligations include by way of example but not limitation describing explicit trust relationships expressing security token issuance policies providing security tokens containing identities attributes capabilities and or delegation policies expressing resource authorization and delegation policies and so forth.

In a described implementation SecPAL is a declarative logic based language for expressing security in a flexible and tractable manner. It can be comprehensive and it can provide a uniform mechanism for expressing trust relationships authorization policies delegation policies identity and attribute assertions capability assertions revocations audit requirements and so forth. This uniformity provides tangible benefits in terms of making the security scheme understandable and analyzable. The uniform mechanism also improves security assurance by allowing one to avoid or at least significantly curtail the need for semantic translation and reconciliation between disparate security technologies.

A SecPAL implementation may include any of the following example features 1 SecPAL can be relatively easy to understand. It may use a definitional syntax that allows its assertions to be read as English language sentences. Also its grammar may be restricted such that it requires users to understand only a few subject verb object e.g. subject verb phrase constructs with cleanly defined semantics. Finally the algorithm for evaluating the deducible facts based on a collection of assertions may rely on a small number of relatively simple rules.

 2 SecPAL can leverage industry standard infrastructure in its implementation to ease its adoption and integration into existing systems. For example an extensible markup language XML syntax may be used that is a straightforward mapping from the formal model. This enables use of standard parsers and syntactic correctness validation tools. It also allows use of the W3C XML Digital Signature and Encryption standards for integrity proof of origin and confidentiality.

 3 SecPAL may enable distributed policy management by supporting distributed policy authoring and composition. This allows flexible adaptation to different operational models governing where policies or portions of policies are authored based on assigned administrative duties. Use of standard approaches to digitally signing and encrypting policy objects allow for their secure distribution. 4 SecPAL enables an efficient and safe evaluation. Simple syntactic checks on the inputs are sufficient to ensure evaluations will terminate and produce correct answers.

 5 SecPAL can provide a complete solution for access control requirements supporting required policies authorization decisions auditing and a public key infrastructure PKI for identity management. In contrast most other approaches only manage to focus on and address one subset of the spectrum of security issues. 6 SecPAL may be sufficiently expressive for a number of purposes including but not limited to handling the security issues for Grid environments and other types of distributed systems. Extensibility is enabled in ways that maintain the language semantics and evaluation properties while allowing adaptation to the needs of specific systems.

As illustrated at the top row of assertion format an example assertion at a broad level includes a principal portion a says portion and a claim portion . Textually the broad level of assertion format may be represented by principal says claim.

At the next row of assertion format claim portion is separated into example constituent parts. Hence an example claim portion includes a fact portion an if portion n conditional factportions . . . n and a c portion . The subscript n represents some integer value. As indicated by legend c portion represents a constraint portion. Although only a single constraint is illustrated c portion may actually represent multiple constraints e.g. c . . . c . The set of conditional fact portions . . . n and constraints . . . m on the right hand side of if portion may be termed the antecedent.

Textually claim portion may be represented by fact if fact . . . fact c. Hence the overall assertion format may be represented textually as follows principal says fact if fact . . . fact c. However an assertion may be as simple as principal says fact. In this abbreviated three part version of an assertion the conditional portion that starts with if portion and extends to c portion is omitted.

Each fact portion may also be further subdivided into its constituent parts. Example constituent parts are an e portion and a verb phrase portion . As indicated by legend e portion represents an expression portion. Textually a fact portion may be represented by e verbphrase.

Each e or expression portion may take on one of two example options. These two example expression options are a constant and a variable . Principals may fall under constants and or variables .

Each verb phrase portion may also take on one of three example options. These three example verb phrase options are a predicate portion followed by one or more eportions . . . n a can assert portion followed by a fact portion and an alias portion followed by an expression portion . Textually these three verb phrase options may be represented by predicate e. . . e can assert fact and alias e respectively. The integer n may take different values for facts . . . n and expressions . . . n .

Generally SecPAL statements are in the form of assertions made by a security principal. Security principals are typically identified by cryptographic keys so that they can be authenticated across system boundaries. In their simplest form an assertion states that the principal believes a fact is valid e.g. as represented by a claim that includes a fact portion . They may also state a fact is valid if one or more other facts are valid and some set of conditions are satisfied e.g. as represented by a claim that extends from a fact portion to an if portion to conditional fact portions . . . n to a c portion . There may also be conditional facts . . . n without any constraints and or constraints without any conditional facts . . . n .

In a described implementation facts are statements about a principal. Four example types of fact statements are described here in this section. First a fact can state that a principal has the right to exercise an action s on a resource with an action verb . Example action verbs include but are not limited to call send read list execute write modify append delete install own and so forth. Resources may be identified by universal resource indicators URIs or any other approach.

Second a fact can express the binding between a principal identifier and one or more attribute s using the possess verb. Example attributes include but are not limited to email name common name group name role title account name domain name server service DNS name internet protocol IP address device name application name organization name service name account identification identifier ID and so forth. An example third type of fact is that two principal identifiers can be defined to represent the same principal using the alias verb.

 Qualifiers or fact qualifiers may be included as part of any of the above three fact types. Qualifiers enable an assertor to indicate environmental parameters e.g. time principal location etc. that it believes should hold if the fact is to be considered valid. Such statements may be cleanly separated between the assertor and a relying party s validity checks based on these qualifier values.

An example fourth type of fact is defined by the can assert verb. This can assert verb provides a flexible and powerful mechanism for expressing trust relationships and delegations. For example it allows one principal A to state its willingness to believe certain types of facts asserted by a second principal B . For instance given the assertions A says B can assert fact0 and B says fact0 it can be concluded that A believes fact0 to be valid and therefore it can be deduced that A says fact0 .

Such trust and delegation assertions may be i unbounded and transitive to permit downstream delegation or ii bounded to preclude downstream delegation. Although qualifiers can be applied to can assert type facts omitting support for qualifiers to these can assert type facts can significantly simplify the semantics and evaluation safety properties of a given security scheme.

In a described implementation concrete facts can be stated or policy expressions may be written using variables. The variables are typed and may either be unrestricted e.g. allowed to match any concrete value of the correct type or restricted e.g. required to match a subset of concrete values based on a specified pattern .

Security authorization decisions are based on an evaluation algorithm e.g. that may be conducted at authorization engine of an authorization query against a collection of assertions e.g. an assertion context from applicable security policies e.g. a security policy and security tokens e.g. one or more security tokens . Authorization queries are logical expressions which may become quite complex that combine facts and or conditions. These logical expressions may include for example AND OR and or NOT logical operations on facts either with or without attendant conditions and or constraints.

This approach to authorization queries provides a flexible mechanism for defining what must be known and valid before a given action is authorized. Query templates e.g. from authorization query table form a part of the overall security scheme and allow the appropriate authorization query to be declaratively stated for different types of access requests and other operations actions.

Security is critical in modern computing systems. Security may be facilitated with an efficient high assurance and flexible mechanism for determining authorized access. This is achievable using a policy based approach. In such systems policy can change to reflect current needs without having to change the underlying code for making and enforcing access decisions.

Existing approaches fail to fully meet these needs especially in complex distributed computing environments. Simple rule based policies such as ACLs are very efficient but not sufficiently flexible. More complex rule based policy systems such as XACML offer more flexibility in return for a less efficient evaluation. Furthermore such rule based policy systems still have functional limitations e.g. the lack of delegation support .

Conventional logic based policy models generally offer the best functionality but they are not without other problems. Some of these models do not offer adequate evaluation safety properties. In other words a given authorization decision algorithm can not be guaranteed to terminate. Some are highly inefficient. Still others are theoretically sound but they are not considered practical to implement in commercial systems.

What is needed is a logic based security policy language that is both practical to implement and highly flexible and that has the requisite evaluation safety properties that ensure efficient evaluation as well as guaranteed termination. Described implementations of an example security policy language provide improvements in these areas.

In the sections that follow an example security language is described. In many locations the description is precise inasmuch as it provides a security language model that is supportable by a relatively rigorous logical foundation. The example described implementations that include a rigorous logical foundation are provided to ensure that the theoretical underpinnings are understood. However any given real world implementations of a security language may not include any particular much less all of the aspects of the rigorous logical descriptions. Thus the invention of the instant application is to be defined by the claims and not by any particular detailed implementations that are described herein.

Multiple example implementations for the expressions of a security language are provided herein. The implementations are designed such that the resulting security policies can be resolved logically in an efficient and certain manner.

Assertion syntax authorization query syntax and language semantics each contribute to the formation and governance of example security language . Security scheme also includes assertion syntax safety checks and authorization query safety checks . Assertion syntax safety checks and authorization query safety checks may be integrated into security language to help ensure authorization query tractability.

In section 2 below example syntax and semantics for assertions of the security language are described. In section 3 example syntax and semantics for authorization queries are described. In section 4 safety principles for the assertions and authorization queries are described. These safety properties when properly applied can guarantee that an authorization query evaluation will terminate and can ensure that the evaluation will proceed efficiently.

A core syntax for an example security language is described here. Additional syntax for a security language may provide for the grouping of assertions for example to delegate a series of rights in a single assertion however additions such as these can be reduced to the core syntax. An example implementation of the security language may also enforce a typing discipline for constants functions and variables but such typing enforcement is omitted here to concentrate on the core syntax.

where the facts range over predicates that state properties on principals for example that someone has the right to read a file. In an example implementation assertions may be similar to Horn clauses with the difference that 1 they are qualified by some principal A who issues and vouches for the asserted claim 2 facts can be nested using the keyword can assert by means of which delegation rights are specified and 3 variables in the assertion are constrained by c a first order formula that can express e.g. temporal inequality tree structure regular expression constraints and so forth.

In a described implementation variables only range over strings and integers but not predicates facts claims or assertions. A phrase of syntax is ground when it contains no variables. The set PredicateNames may not contain can assert can assert and alias. Functions and predicates have a fixed arity. A predicate is a verb phrase with holes for its object parameters. If it has multiple words these holes may appear at any fixed position within it e.g. has access from till .

In the remainder of the text we use A B C and D as meta variables for constants usually for denoting principals. We use a vector notation to denote a possibly empty list or tuple of items e.g. we may write f right arrow over e for f e . . . e .

Facts can be nested as can be seen from the syntax definition above. Nested facts are of the form ecan assert. . . ecan assertfact for some n 1 where fact is flat as defined next.

Two definitions are presented below. The first defines a flat fact and the second defines parts of an assertion.

For example the fact Alice says Bob can read f is flat but Alice says Charlie can assertBob can read f is not flat.

Definition 2.2. Let A says fact if fact . . . fact c be an assertion. Then A is its issuer the fact are its conditional facts and c is its constraint. The fact may be considered the assertion s primary fact or asserted fact.

Constraints range over any constraint domain that extends the example basic constraint domain shown below. Basic constraints include integer inequalities e.g. for expressing temporal constraints tree order constraints e.g. for directories and regular expressions e.g. for ad hoc filtering . Examples of basic constraints are set forth below 

Additional constraints can be added without affecting decidability or significantly affecting tractability. However it is preferred that the validity of ground constraints can be checked in polynomial time to maintain a desired level of tractability.

We use a sugared notation for constraints that can be derived from the basic ones e.g. False e eor cor c. In assertions we usually omit the True constraint and also omit the if when the assertion has no conditional facts.

We now give a formal definition of the language semantics . We first define the denotation of a ground expression. The denotation of a constant A is just A so A A. The denotation of a function right arrow over e is defined if right arrow over e is ground and is also a constant but may depend on the system state as well as right arrow over e . For example CurrentTime presumably returns a different constant when called at different times. However we assume that a single authorization query evaluation is atomic with respect to system state. That is even though an expression may be evaluated multiple times its denotation is the same during a single evaluation.

For a given constraint c we write c iff it is valid. The following defines validity within the basic constraint domain.

In the rest of this document we refer to a substitution as a function mapping variables to constants and variables. Substitutions are extended to constraints predicates facts claims assertions etc. in the natural way and are usually written in postfix notation. We write Vars X for the set of variables occurring in a phrase of syntax X

In a described implementation the security language includes three deduction rules. We now present these three deduction rules to capture the semantics of the language. Each rule has a set of premises and a single consequence of the form AC D A says fact where Vars fact and D 0 . Intuitively the deduction relation holds if the consequence can be derived from the assertion context AC. If the derivation flag D 0 the Derivation Rule can assert is not used in the derivation.

Delegation semantics rule with a can assert verb implementation for the general delegation directive verb is as follows 

Rule cond allows the deduction of matching assertions in AC with all free variables substituted by constants. In a described strict logical implementation the conditional facts must be deducible and the substitution must also make the constraint s valid. The delegation flag D is propagated to all conditional facts.

In other words given an assertion context AC a delegation flag D a principal A and a substitution we can derive AC D A says fact if all of the following hold 

Rule can assert deduces an assertion made by A by combining a can assert assertion made by A and a matching assertion made by B. In a described strict logical implementation this rule applies when the delegation flag is . The matching assertion made by B must be proved with the delegation flag D obtained from A s can assert assertion.

In other words given an assertion context AC a principal A and a fact fact we can derive AC A says fact if there is a principal B and a delegation flag D such that both of the following hold 

In other words given an assertion context AC a delegation flag D principals A B and C and a verb phrase verbphrase we can derive AC D A says B verbphrase if both of the following hold 

The following propositions state basic properties of the deduction relation they are established by induction on the rules above.

Authorization requests are decided by querying an assertion context containing local as well as imported assertions . In a described implementation of a logic language an authorization query may include a collection of atomic queries of the form A says fact and constraints c combined by logical connectives including negation. An example authorization query syntax is as follows 

The resulting query language is more expressive than in other logic based languages where only atomic queries are considered. For example separation of duties threshold and denying policies can be expressed by composing atomic queries with negation and constraints. In a described implementation negation is not allowed within the assertion language as coupling negation with a recursive language results in semantic ambiguities and often to higher computational complexity or even undecidability. By restricting the use of negation to the level of authorization queries rather than adding these features to the assertion language itself we effectively separate it from recursion thereby circumventing the problems usually associated with negation.

The semantics of queries is defined by the relation AC q. In the following let be the empty substitution. Note that negated queries and constraints are grounded and that conjunctions are not commutative as the second query may be instantiated by the outcome of the first query.

Given a query q and an authorization context AC an authorization algorithm should return the set of all substitutions such that AC q. If the query is ground the answer set will be either empty meaning no or be a singleton set containing the empty substitution meaning yes . If the query contains variables then the substitutions in the answer set are all the variable assignments that make the query true.

In the following section section 4 safety conditions for ensuring that this set of variable assignments is finite and meaningful are described. Section 9 below gives an algorithm for evaluating authorization queries.

Conceptually authorization queries are part of the local policy and may be kept separate from imperative code. In a described implementation of a security language authorization queries belonging to a local assertion context are kept in a single place termed the authorization query table. The table provides an interface to authorization queries by mapping parameterized method names to queries. Upon a request the resource guard calls a method instead of issuing a query directly that gets mapped by the table to an authorization query which is then used to query the assertion context.

The resulting answer set either an empty set if the request should be denied or a variable assignment for id is returned to the resource guard who can then enforce the policy in accordance with the authorization decision.

In an example implementation of the security language the authorization algorithm is required to terminate and return a complete set of answers with respect to the described semantics no matter what the inputs are. Without further restrictions this cannot be guaranteed as the constraint domain is not constraint compact. Thus in a described implementation relatively simple purely syntactic restrictions are enforced on assertions and queries.

Definition 4.1. Assertion safety check of FIG. Let A says fact if fact . . . fact c be an assertion. A variable x Vars fact is safe iff x Vars fact . . . Vars fact .

The safety condition guarantees that the evaluation of the logic language translation as described below in section 8 terminates in all cases and is complete. Furthermore the safety condition enables a simple handling of constraints within the evaluation algorithm of section 8 as long as the query is flat all variables of a constraint are fully instantiated when conditional predicates are processed so constraints do not need to be propagated and there is no need to implement complex constraint solving algorithms.

We now define a safety condition on authorization queries that guarantees that the set of substitutions is finite given that the assertions of the assertion context is safe. Furthermore the condition ensures that subqueries of the form not q or c will be ground at evaluation time assuming a left to right evaluation rule with propagation for conjunctions as is defined in section 9.

We first define a deduction relation with judgments of the form Iq O where q is a query and I O are sets of variables. Intuitively the set I represents the variables that are grounded by the context of the query and O represents the variables that are grounded by the query.

The following deduction relationships provide syntactic checks of on authorization queries based on inference rules. If the top is proved then the bottom may be considered proved as well.

Definition 4.2. Authorization query safety of FIG. An authorization query q is safe iff there exists a set of variables O such that q O.

Checking safety can be done by recursively traversing all subqueries and thereby constructing the set O which is always uniquely determined by the query and I .

Examples of safe and unsafe queries are provided in the table below In the following examples and or are left associative.

In a described implementation at block the safety of the assertions of the assertion context are checked. For example definition 4.1 may be applied to each assertion of an assertion context AC. Accordingly at block it is verified that the initial variables of an assertion are safe. For example part 1 of definition 4.1 may be applied. For instance the initial variables are the variables of fact if fact is flat or the variables of the expression e if fact is not flat .

At block it is verified that any constraint variables are also present somewhere else in the assertion. For example part 2 of definition 4.1 may be applied. At block it is verified that the conditional facts are flat. For example part 3 of definition 4.1 may be applied.

At block the safety of the authorization query is checked. For example definition 4.2 may be applied to the authorization query. At block depending on the syntax of the authorization query one or more of the safe inference rules is applied to the authorization query to confirm compliance and ensure the query s safety. Example inference rules are assertion conjunction disjunction negation and constraint.

If the assertion context fails its check at block or the authorization query fails its check at block then the evaluation algorithm may be aborted to avoid attempting to evaluate an assertion context and or authorization query that will not terminate or that will not be completed. After the safety has been checked successfully at blocks and then at block the authorization query may be evaluated in conjunction with the assertion context.

In a described implementation of the security language expiration dates can be expressed as ordinary verb phrase parameters 

An acceptor can then use the date to enforce its own time based constraints on the validity of the assertion 

Assertions may have to be revoked before their scheduled expiration date. If the revocation is necessitated due to the compromise of an explicitly trusted issuer s cryptographic key then revocation is done by informing the relying party that the key should no longer be trusted. The relying party then removes the policy expressing the explicit trust in that key. But it is far more common that an issuer needs to revoke an assertion it has made in the past. This could be due to compromise of the cryptographic key associated with the principal whom the assertion is about some change in the principal s relationships e.g. change in employment or malicious behavior on the part of the principal. For instance the assertion in the example above has to be revoked if Alice drops out of her university.

We assume that every assertion M is associated with an identifier e.g. a serial number ID. Revocation and delegation of revocation can then be expressed in a described implementation by revocation assertions with the verb phrase revokes ID. For example the revocation assertion

Definition 5.1. revocation assertion An assertion is a revocation assertion if it is safe and of the form

Given an assertion context AC and a set of revocation assertions ACwhere AC AC we remove all assertions revoked by ACin AC before an authorization query is evaluated. The filtered assertion context is defined by

The condition that AC and ACare disjoint means that revocation assertions cannot be revoked at least not within a described implementation of the security language . Allowing revocation assertions to be revoked by each other causes the same problems and semantic ambiguities as negated body predicates in logic programming. Although these problems could be formally overcome for example by only allowing stratifiable revocation sets or by computing the well founded model these approaches are not simple enough to encourage their use in commercial systems.

An example implementation of a security language as described herein above provides a mechanism for expressing security policies in a highly human understandable form. Moreover the security language can be checked for safety. However security policies also need to be evaluated to make authorization decisions.

To that end existing logic languages can be leveraged. There are existing logic languages that have been developed over time and are thoroughly tested. There are also helpful tools that may be used with these logic languages. An example applicable logic language is Datalog and specifically constrained Datalog. However other logic languages may alternatively be utilized.

Techniques and mechanisms are described herein to enable such existing logic languages to be used with a security language. The security language may be translated into a logic language as described in section 7. Section 8 describes an evaluation algorithm with tabling that is performed in the logic language. The evaluation algorithm can produce a proof graph in the logic language. In section 9 a technique is described for translating the proof graph reflecting the logic language into a proof graph reflecting the security language. Hence the authorization process including the evaluation algorithm may be analyzed in terms of the security language.

Example assertion semantics for a described security language is defined by the three deduction rules of section 2. This semantics is more comprehensible and intuitive than one defined in terms of a translation into some form of formal logic which has been proposed. Nevertheless it is useful to be able to efficiently translate security language assertion contexts into equivalent logic language programs. We can then leverage known complexity results e.g. polynomial data complexity and use the translated logic language program for query evaluation which is described in section 8.

We now describe an algorithm for translating a safe assertion context into an equivalent logic language program. By way of example only the safe assertion context is translated into a constrained Datalog program. In the following we treat expressions of the form esaysfact as Datalog predicates where k is either a variable or 0 or . This can be seen as a sugared notation for a predicate where the predicate name is the string concatenation of all infix operators says can assert alias revokes and predicate names occurring in the expression including subscripts for can assert. The arguments of the predicate are the collected expressions between these infix operators. For example the expression

In a described implementation at block a security language assertion with an asserted fact and zero or more conditional facts is extracted from an assertion context. At block it is determined whether the asserted fact is flat. If so then at block the assertion is translated into a logic language rule having a primary fact and zero or more side conditions. For example part 1 of Algorithm 7.1 may be performed. The primary fact corresponds to the asserted fact and the side conditions correspond to the conditional facts. These differing terms are used for the sake of clarity to textually differentiate parts of the logic language program from parts of the security language assertion context.

If on the other hand the asserted fact is not determined at block to be flat then the security assertion is translated by blocks and . If the fact is not flat then the assertion is a delegation assertion with at least one delegation directive verb e.g. can assert can say etc. .

At block a logic language rule having a primary fact and zero or more side conditions is added e.g. to a growing logic language program . For example part 2 a of Algorithm 7.1 may be performed. At block for each delegation directive verb of the asserted fact of the security language assertion a logic language rule having an unbounded delegation depth and a fresh variable representing the delegatee is added. More specifically the fresh variable represents the principal to whom rights are being delegated. For example part 2 b of Algorithm 7.1 may be performed.

At block for each logic language rule having an asserted fact with an expression that has been created at block or another logic language rule having an alias capability and a fresh variable representing the object of the alias is added to the logic language program. For example part 3 of Algorithm 7.1 may be performed. At block a logic language program segment corresponding to the input assertion of the security language assertion context is thereby produced. The actions of flow diagram are repeated for each assertion in a given assertion context.

Definition 7.2. Consequence operator The immediate consequence operator Tis a function between sets of ground predicates and is defined as 

Theorem 7.3. Soundness and completeness Let P be the Datalog translation of the assertion context AC. A saysfact T iff AC D A says fact.

In the section above we show how a set of safe security language assertions can be translated into an equivalent at least partially safe constrained Datalog program. In the context of deductive databases the bottom up approach is most often used for Datalog evaluation. There the program s model or its least fixed point which is finite due to safety is computed once and for all. This has the advantage that it is a complete terminating procedure and query evaluation is fast once the fixed point has been constructed.

However bottom up evaluation is not as suitable for a described implementation of the security language because the assertion context is not constant. In fact it may be completely different between different requests. Computing the model for every request is not efficient as it results in the evaluation of irrelevant goals. Furthermore the queries we are interested in are usually fully or partially instantiated thus a top down goal directed approach seems more appropriate.

The most widely known top down evaluation algorithm is SLD resolution as is used in Prolog. Unfortunately SLD resolution can run into infinite loops even for safe Datalog programs if some of the predicates have recursive definitions. The problem remains even if instead of a depth first a breadth first search strategy is employed the looping occurs because the SLD search tree is infinite Tabling or memoing is an approach to guarantee termination by incorporating some bottom up techniques into a top down resolution strategy. The basic idea is to prune infinite search trees by keeping a table of encountered subgoals and their answers and to compute a subgoal only if it is not already in the table.

We describe here a deterministic algorithm based on tabling and apply it to security language assertions that have been translated into a logic language program. Two global tables are kept during the evaluation process.

The first table Ans table maps predicates to sets of ground predicates. If a subgoal P uninstantiated or partially or fully instantiated is computed P is added to the domain of Ans and at any point in time Ans P returns the set of answers to P these are ground instances of P that have been found so far. At the end of the evaluation process Ans will contain the complete answers to all encountered subgoals including the root goal.

The second table is Wait table . It maps predicates P to subgoals of the form P P right arrow over P c S and a predicate P. The subgoal can be interpreted as follows P is the top level predicate of the proof tree Pis the predicate to be solved next right arrow over P is the list of predicates that have to be solved after P c is a constraint on the predicate variables and S is an instance of P that keeps track of the instantiations found so far by being continuously narrowed down.

A number of terms and concepts that relate to the evaluation algorithm are defined and or explained below.

Definition 8.2. Let P and Q be two predicates. A substitution is a unifier of P and Q iff P Q . A substitution is a most general unifier of P and Q iff it is more general than any other unifier of P and Q.

Definition 8.3. A variable renaming for a predicate P is a substitution such that defines a permutation on the set of variables occurring in P.

If two predicates P and Q are unifiable they also have a most general unifier that is unique up to variable renaming We denote it by Mgu P Q . Finding the most general unifier is relatively simple but there are more intricate algorithms that run in linear time.

Definition 8.4. Let P and Q be two predicates. Then P is an instance of Q iff P Q for some substitution . We also say that P is subsumed by Q and write P Q

Proposition 8.5. P Q iff there exists a most general unifier of P and Q and is a variable renaming of P.

The following pseudocode provides an example of an evaluation algorithm. It is explained further below.

To find the answers to a predicate P with respect to a set of rules and with initially empty Ans and Wait tables i.e. Dom Ans Dom Wait call the routine QUERY P .

Q module spawns a new proof tree by calling R C P . After the call Ans P will be populated with the correct and complete answers.

R C module resolves each rule in against Fresh P by calling RESOLVE. The function Fresh P renames all variables in P to fresh ones that do not occur anywhere in .

R module takes as parameters a subgoal of the form P P right arrow over P c S and a predicate P . The Simplify function in Rmay perform any kind of equivalence preserving simplifications on a constraint e.g. False c False . At the very least it should simplify ground constraints to true or false. It is safe to over approximate the satisfiability check on line 1 i.e. false should only be returned if c really is unsatisfiable but true may be returned even in the case if c is unsatisfiable as long as Simplify c is not fully instantiated. A simple implementation of the approximate satisfiability check could thus return true whenever the simplified constraint is not yet fully instantiated.

If the unification and the satisfiability check succeed there are two subcases. Either the list right arrow over P is empty in which case we know that S is an answer to P and moreover it is a ground answer due to safety. P Ais then called to further process the answer. Otherwise we employ a left to right evaluation strategy by picking the first predicate in the list as the next one to be solved and call P Swith the substitution pushed into all the parameters but the first. The first parameter P remains unchanged since it is used for keeping track of what the original goal was. The preliminary solution S is narrowed down to S .

P A module takes an answer to P and updates Ans table . Wait table contains all the suspended subgoals that are waiting for this answer. Each suspended subgoal is resumed by calling Rtogether with the newly found answer.

P S module takes as argument a subgoal with Pas the next predicate to solve and checks if there already is an existing subgoal P in Ans table that subsumes it. If there is P S existing answers can be reused by calling R there is no need to start a new proof tree for P. Additionally a copy of the subgoal is added to the Wait entry for P that any future answers to P will be used as well. Only if no entry in Ans table subsumes Pa new proof tree is spawned by a call to R C. Prior to that an entry for Pcontaining the subgoal is created in Wait table .

Definition 8.6. P is defined as the return value of the call Q P in the context of a set of equality free rules and initially empty Ans and Wait tables if the call terminates. Otherwise P is undefined.

Theorem 8.8. soundness and completeness Let P be a partially safe query. P is equal to the set of all ground instances of P that are in T .

When testing and troubleshooting security policies it may be useful to be able to see a justification of an authorization decision. This can be a visual and or textual representation of the corresponding proof graph constructed according to the semantics rule system in section 2 above. The proof graph produced during an evaluation may also be archived for auditing purposes.

Leaf nodes of logic language proof graph are represented by rectangular nodes and . Non leaf nodes are represented by circular nodes and . The circles are nodes that prove side conditions e.g. body predicates . The rectangular leaf nodes of logic language proof graph are rules translated from assertions from the original assertion context. The other nodes are derived statements which are taken from the answers table e.g. Ans table if the deterministic tabling algorithm described above is employed in the evaluation.

Logic language proof graph is separated into example fragments . Specifically three fragments are shown but a proof graph may be separated into any number of fragments . Each fragment forms part of a structure of the overall proof graph. Consequently each fragment includes node s and directed edge s .

In order for analysis troubleshooting and or auditing etc. to be performed by someone familiar with the security language logic language proof graph may be translated into a corresponding security language proof graph not separately shown in whole . To effect the translation a pattern matching process is performed. A logic language fragment is matched to a corresponding security language fragment.

In a described implementation the sample security language fragments that may be used in the pattern matching process are each respectively associated with a semantics rule from the security language. Example fragment correspondences between logic language fragments and security language fragments are described below with reference to B A B A and B.

In a described specific example implementation the algorithm presented above with reference to can be modified to construct a Datalog proof graph during query evaluation. A proof graph is a directed acyclic graph. For each answer to a query there is a root node in the graph. Every non leaf node is a ground Datalog predicate of the form A saysfact and has as child nodes the Datalog rule the instantiated conditional facts and the instantiated constraint. Leaf nodes are either Datalog rules in AC or ground constraints that are valid. Examples are shown as the left panels of A and A. 

If during an execution of the Algorithm 7.1 from above each generated Datalog rule is labeled with the algorithm step at which it was generated i.e. 1 2 a 2 b or 3 the Datalog proof graph contains sufficient information to be converted into a corresponding security logic proof graph.

In a described implementation at block a first proof graph that reflects a logic language during a logical evaluation is produced. For example a logic language proof graph may be produced during a logical evaluation. The logical evaluation is effected on a logical language program that is derived from a security language assertion context via a translation.

At block a fragment of the first proof graph is identified. For example a fragment of logic language proof graph may be identified.

At block the fragment of the first proof graph reflecting a logic language is translated into a corresponding fragment of a second proof graph reflecting a security language. For example fragment of logic language proof graph that reflects a logical language e.g. Datalog etc. is translated into a corresponding fragment of a second proof graph that reflects a security language e.g. a policy assertion security language . For instance a logic language pattern of the fragment of the first proof graph may be matched to a corresponding security language pattern selected from multiple possible security language patterns. These security language patterns may for example be associated with semantics rules of the security language.

At block the identification of a fragment and the translation thereof is repeated for each fragment of the first proof graph. For example as indicated by next fragment arrow another fragment of logic language proof graph may be identified and translated into a corresponding fragment of a security language proof graph.

At block the second proof graph reflecting the security language is output once the logic language proof graph has been traversed and translated. The second proof graph includes fragments corresponding to respective fragments of the first proof graph. This second proof graph reflecting the security language can also be archived and or audited.

Based on the algorithm from the previous section we can now describe how to evaluate complex authorization queries as defined in section 3. In the following let AC be an assertion context and its Datalog translation and let c be the empty substitution. We define the function AuthAnson authorization queries as follows.

Theorem 9.1. Finiteness soundness and completeness of authorization query evaluation For all safe assertion contexts AC and safe authorization queries q 

The devices actions aspects features functions procedures modules data structures protocols components etc. of are illustrated in diagrams that are divided into multiple blocks. However the order interconnections interrelationships layout etc. in which are described and or shown are not intended to be construed as a limitation and any number of the blocks can be modified combined rearranged augmented omitted etc. in any manner to implement one or more systems methods devices procedures media apparatuses APIs protocols arrangements etc. for security language translations with logic resolution.

Although systems media devices methods procedures apparatuses mechanisms schemes approaches processes arrangements and other implementations have been described in language specific to structural logical algorithmic and functional features and or diagrams it is to be understood that the invention defined in the appended claims is not necessarily limited to the specific features or acts described above. Rather the specific features and acts described above are disclosed as example forms of implementing the claims.

