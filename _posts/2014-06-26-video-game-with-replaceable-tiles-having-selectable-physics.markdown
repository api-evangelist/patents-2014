---

title: Video game with replaceable tiles having selectable physics
abstract: A computer device has user interface configured to display user actuatable game elements and to detect user input when a user engages with a game element; and a processor configured to receive a detected user input and on detecting a match game condition to control the user interface to remove at least three game elements from the display and to provide on the user interface replacement user actuatable game elements, wherein the manner of providing each replacement game element has a graphical representation governed by a tile associated with each game element, wherein each tile has a selectable physics which controls at least one of (i) the direction in which it moves to replenish a vacancy left by the removed user game elements; and (ii) the speed at which it moves to replenish the vacancy.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09079097&OS=09079097&RS=09079097
owner: KING.COM LTD.
number: 09079097
owner_city: St. Julians
owner_country: MT
publication_date: 20140626
---
This application is a continuation in part of U.S. application Ser. No. 14 183 997 filed Feb. 19 2014 which is a continuation in part of U.S. application Ser. No. 14 029 261 filed Sep. 17 2013 and a continuation in part of U.S. application Ser. No. 14 029 538 filed Sep. 17 2013 and is based on and claims priority to GB Application No. 1302910.3 filed Feb. 19 2013 GB Application No. 1311119.0 filed Jun. 21 2013 GB Application No. 1318416.3 filed Oct. 17 2013 and GB Application No. 1401717.2 filed Jan. 31 2014 the entire content of each of which is fully incorporated herein by reference.

The present invention relates to controlling a user interface responsive to user engagement with displayed elements on the interface of a computer device.

In the field of computer implemented games there are many technical challenges facing the designer of such games when considering how the user interface is to be controlled in the context of computer devices available to play the game.

One technical challenge can involve allowing a game to be fun and compelling even when there is limited display resource available such as when a game is being played on a smartphone tablet or other minicomputer. Another significant challenge is that of user engagement. Engagement involves designing gameplay to be engaging and rewarding to players. This typically requires games to be easily understood at their simplest or introductory levels providing rewarding gameplay with quite simple game mechanics but becoming progressively more challenging so that players are not bored but remain engaged and develop rewarding skills. Effective engagement requires various forms of feedback to reinforce player sense of success and accomplishment.

An existing type of match three game is a so called switcher game. A match three game is a type of casual puzzle game where the player is required to find patterns on a seemingly chaotic board. The player then has to match three or more of the same type of game element on the game board and those matched elements will then disappear. In a switcher game the player switches place onto adjacent game elements on the game board so that one or both of them create a chain of at least three adjacent game elements of the same type. Those matched game elements will then disappear. The game board is then repopulated with game objects.

One such known match three type game is known by the trade name Candy Crush. In that game the game board is repopulated with game elements which are perceived as falling downwards onto the game board from the top edge of the screen from which the game is played.

Aspects of the present invention provide improved methods of controlling a user interface in the context of a computer implemented game of the match three game type. They provide a solution to the technical problem of user engagement with a limited screen resource and or improve user engagement.

One aspect of the present invention provides a computer device having a user interface configured to display user actuatable game elements and to detect user input when a user engages with a game element a processor configured to receive a detected user input and on detecting a match game condition to control the user interface to remove at least three game elements from the display and to provide on the user interface replacement user actuatable game elements wherein the manner of providing each replacement game element has a graphical representation governed by a tile associated with each game element wherein each tile has a selectable physics which controls at least one of i the direction in which it moves to replenish a vacancy left by the removed user game elements and ii the speed at which it moves to replenish the vacancy.

In one embodiment of the game the processor is configured to select the physics for each tile based on user input at the user interface.

The user input can be a deliberately generated user input to alter the physics of tiles which would then govern how game elements are replaced. Alternatively the user input can form part of the game play as discussed more fully in the following.

In the following described embodiments the physics of the tile which is adjusted as the direction in which a replacement tiles moves. However the speed at which a tile moves can also be adjusted either by deliberate user input or by player involvement in the game. Thus a tile can be replenished at various speeds depending on how a player has played the game. This is the game element could arrive extremely quickly or could arrive more slowly associated with visual animations of its arrival.

The processor may be configured to select physics for each tile based on the location on the display at which the at least three game elements are removed. That is part of the displayed game board is replenished with game elements according to one physics and another part would be replenished with game elements of another physics.

The computer device can comprise a graphics controller which is connected to receive information for the processor defining the graphical representation and to supply the graphical representation to the user interface in the form of a video sequence based on the physics of the tile. For example the game element can be perceived as falling downwards or moving upwards.

The user interface can be configured to display each tile with a visual indication of its selected physics such as colour.

The user interface can be configured to display a separator between tiles of a first physics and tiles of a second physics. In this case the displayed part of the game board may be shown in two colours representing two different physics. In the described embodiment the tiles of the first physics move in a direction replenish a vacancy downwards from an upper portion of the screen and tiles of the second physics move in the direction to replenish a vacancy upwards from a lower portion of the screen. The lower part of the screen is purple referred to herein as lemonade . It could be termed water or soda or any fluid name. More generically any highlighting nomenclature could be utilised. In the lemonade the tiles move upwards. The selectable physics controls a direction in any orientation of the Cartesian or polar axes for replenishment of tiles from an outer portion of a game board to an inner portion of a game board. In one game mechanic the user interface is configured to display a balloon game element which alters the physics of a set of displayed tiles when a match game condition of game elements associated with the balloon element is detected. The balloon element does not need to take the form of a balloon any container type icon would be suitable such as a bottle. The balloon bursts and causes more game elements to have the lemonade physics. Game elements are associated with the balloon element by virtue of having a matching colour with the balloon element. If a match for example of red game elements is detected a red balloon will burst increasing the level of the lemonade the separator will rise one or more rows up the displayed parts of the game board. The tiles are arranged in rows and columns in one version of the game. The separator extends laterally across the game board between two rows of lines.

In a grid type arrangement the set of tiles whose physics is altered by the balloon game element is a row of tiles. Any other kind of set could be chosen e.g. three rows top to bottom one column etc.

To visually demonstrate different physics to a user the user interface can be controlled by the processor to sequentially apply a visual effect to sets of tiles thereby indicating physics of the tiles. The visual effect can be a highlighting or shimmer effect wherein game elements are temporarily enlarged and or brightened.

In a grid arrangement the visual effect is sequentially applied to adjacent rows. To distinguish different game physics the visual effect is applied in a first direction in a set of rows above the separator and not in a set of rows below the separator.

In one version of the game the number of replacement game elements is the same as the number of game elements in the match condition. However the number could be different the location of a spawner can be set to replenish vacancies according to selected tile physics.

In a particularly distinctive optional feature a game board of the game elements is generated by the processor but only a portion of the game board is displayed to a user with subsequent portions of the game board being displayed as a result of a scrolling action displayed on the user interface.

Another aspect of the invention provides user interface responsive to user engagement with displayed game elements on the interface the method comprising the following steps implemented by a processor of a computer device detecting a match game condition of at least three game elements responsive to user input generating replacement game elements to be displayed each game element associated with a tile selecting a physics for each tile controlling a graphical representation on the user interface of replacing the game element based on the selected tile physics wherein the tile physics controls at least one of i the direction in which it moves to replenish the vacancy left by the removed game elements and ii the speed at which it moves to replenish the vacancy.

In a grid type arrangement the user interface displays a game board of game elements in rows and wherein there is a visual indication of the tile physics associated with each tile in a row. All tiles in the same row have the same physics. Where a separator is displayed on the user interface between adjacent rows of differing tile physics the location of the separator on the game board can be adjusted by user input which causes the balloon elements to be actuated thereby increasing the number of tiles below the separator.

In one game mechanic a game character is displayed on a tile having a first kind of physics and movement of that character over the game board is affected by the tile physics of the set of tiles surrounding the game character. For example the character moves up in the lemonade as game elements above him are removed. A target row is identified on the display for example with visual targets such as rubber rings and one game objective is to cause the game character to move up to the target row.

Where the full game board is not displayed on the user interface a portion of the game board is displayed on the user interface the displayed portion varying as a result of a scrolling action to display different portions of the game board on the display.

When a first portion of the game board is displayed on the display the target row is not visible to a player and wherein when a second portion of the game board is displayed on the display as a result of said scrolling action the target row comes into view of the player.

Another aspect of the invention provides a computer device having a user interface configured to generate a game board having game elements for display for engagement by a user and a processor configured to control the user interface responsive to user engagement with the game element to remove from the display game elements on detection of a match game condition and to provide replacement game elements on the display wherein a portion of the game board is displayed including the replacement game elements said portion being controlled to change by a scrolling action whereby enabling portion of the game board is newly displayed and a previously displayed portion of the game board is removed from the display.

Another aspect provides a method of controlling a user interface in a computer device to show a portion of a match three game board and to scroll the game board to show different portions responsive to user input at the user interface to detect and activate matched game elements.

Another embodiment provides a computer device having a user interface configured to display user game elements and to detect user input when a user engages with a game element and a processor configured to receive a detected user input and on detecting a game condition to control the user interface to provide a graphical representation of one or more game elements wherein movement of one or more game elements is controlled by a selectable physics which controls the direction in which it moves.

Another embodiment provides a computer implemented method of controlling a user interface responsive to user engagement with displayed game elements on the interface the method comprising the following steps implemented by a processor of a computer device 

controlling a graphical representation on the user interface of one or more game elements wherein movement of one or more game elements is controlled by said selectable physics which controls the direction in which it moves.

The terms user and player are used interchangeably throughout this document and no specific meaning is intended using one or the other unless the context suggests otherwise.

In the following description of various implementations of the invention reference is made to the accompanying drawings which form a part thereof and in which is shown by way of illustration various implementations in which the invention may be utilized. It is to be understood that other implementations may be utilized and structural and functional modifications may be made without departing from the scope of the present invention.

In the known version of the match 3 switcher game the aim of the game is to swap game elements in the shape of candies with each other to make moves on the game board. To gain points the player has to make moves that create matches of at least three of the same candy. In doing so the player gains points and the matched candies are removed. As a result new candies fall into place from the top of the game board in order to fill any spaces created. Assume in that game element is moved one place to the right to form a three line match with game elements and . Turning now to this has the effect of game board elements and disappearing creating a visual effect animation on the screen to indicate the disappearance such as a minimal explosion effect denoted in . The two game elements which were directly above game elements will now fall downwards into the spaces created by the removal of game elements and . Thus game element will end up at the location of tile and game element will end up at the location of tile . In addition three new tiles with game elements are created and fall downwards into the game board to fill the remaining three spaces above tile . The game elements on the newly created tiles which fall downwards into the game board are generated at random. The user then has a new game board on which to play a subsequent move. is a flow chart illustrating a process implemented by software in a processor for executing the basic game mechanic just discussed. At step S the input made by a player on the screen is analysed. At step S the game rules are applied to see whether or not at least a three element match has been created. If it has not at step S the screen indicates an illegal move to a user and the player must try again. If a match has been detected at step S an appropriate visual effect is generated for the display to denote the match and the disappearance of the game elements which have been matched. At step S new game elements are generated for the display these game elements falling downwards to fill up the display from the top. The so called physics of the tile on generation of a new game board after each move is always the same in the existing version of the game called Candy Crush. That is tiles drop down from above the game board at a set speed.

In an improved version of the game described herein the physics of each individual tile can be altered based on the game play of a user or based on an instruction from the game software. Both the speed at which the tile can move and the direction in which it can move can be governed by play of the game. illustrates a game board of one embodiment of the present invention. The game board has two sections which are divided by a dividing line . In the upper section the game mechanic is as just described with respect to . If a match is made the game elements are removed and replacement tiles with associated game elements fall down from the top of the screen into the new game board. However if game elements are matched and thus removed from an area below the dividing line then game elements arrive to create a new game board from below the screen in the direction of arrow in . Thus the physics of the tile below the dividing line is such that there is an upward movement to complete the display rather than a downward movement in the upper section. The physics of the tile is governed by the location of the tile vis vis the dividing line . This dividing line is visible to a player as a result of having tiles above the dividing line of one colour and tiles below the dividing line of another colour. The tiles below the dividing line form a continual background which is referred to in the game as lemonade . This is just a denotation of a continuous colour formed by the tiles below the dividing line . Game elements cannot fall into the lemonade from above the dividing line. The dividing line represents a barrier to game elements moving further either upwards or downwards.

Players can control the location of the dividing line with respect to the displayed area of the game board. That is they can move the dividing line upwards on the screen in accordance with a particular game mechanic involving the bursting of balloon shaped game elements. illustrates this game mechanic. A balloon has arrived on the game board and is thus available for bursting. In order to burst the balloon a match of game board elements of the same colour as the balloon needs to be formed. In this case an L shaped match of red elements is shown as having been made on the left hand corner of the display at . This match has been shown with a visual effect on the screen and these game elements will thus disappear. This is shown in where the balloon has now burst the game elements of the match have disappeared and the level of the lemonade has now risen. Thus the dividing line is now in a new location one row above its earlier location in . The movement is denoted by arrow in . In this way a player can influence the number of tiles which have an altered physics in this case the number of tiles which have a physics to cause them to replenish the game board moving upwardly from below the screen as opposed to downwardly from above the screen see

In an alternative embodiment shown in and game elements move in from the side to replace matched game elements. shows five game elements moving from the left hand side as new replacement elements.

As mentioned activity at the user interface can alter tile physics. The data structure is responsible for managing how replacement tiles are delivered to the user interface. Each tile has a tile ID . The tile ID can define the location on the user interface where the tile is to be replenished that is governed by the vacancy which has been released by gameplay. This allows the rendering engine to generate that tile at an appropriate location on the user interface display . Each tile ID is associated with tile data which defines how the tile is to be displayed that is what game element it has associated with it and whether it has any blockers in addition to or instead of a game element or any foreground or background. Different alternatives for blockers foreground and background are discussed later.

In addition to tile data the tile physics is also stored in association with a tile identifier. The tile physics can be modified for a particular tile based on activity at the user interface . Thus after each gameplay the tile identifier which defines the location at which the tile is to be replenished can have different tile physics associated with it as modified by activity at the user interface . The modified tile physics is stored in the data structure so that at the next gameplay the appropriate tile physics is utilised to replenish that particular tile when the vacancy arises.

As the level of the lemonade moves by virtue of activity at the user interface the tile physics associated with all tiles which are affected by the movement of the level are altered in the data structure .

In the embodiments described above the physics of the tiles are predetermined by the game software in dependence on the location of the tile on the screen in particular as to whether or not it is in the lemonade . However players can use boosters and or sidekicks to alter the physics of tiles in a more general way. For example a sidekick can be provided which when enabled changes the physics of some or all of the tiles. The tiles of whom the physics is changed can be preselected or determined by a user or the result of game play.

In the embodiments described above altering the physics of a tile can change the speed or direction with which the game element can fill vacancies left by matched game elements. In an alternative embodiment the physics of a tile could affect how game elements bounce off one another.

One game objective will now be discussed with reference to . illustrates across the screen a row of rubber rings . There is also illustrated a teddy bear . The requirement to complete this level is to release the teddy bear from its bubble. This can be achieved by raising the level of the lemonade to the row which contains the rubber ring . The reverse gravity effect of the game tiles in the lemonade enables the player to bring the bear up to the rubber rings. That is if the bear was formerly below game elements a match of those game elements would cause them to disappear and the bear would thus move upwardly towards the rubber rings. In it is shown in the row immediately below the rubber rings. In it is shown in capture by the rubber rings and thus being released from its bubble. The transition between and has been achieved by swapping game element with element . shows the gameboard immediately after the player has provided the input to produce this swap. The game element is moving to occupy the position above the level where a row of three green elements will be formed. One of the green elements of this row is a balloon the matching of which will lead to a rise in the level . shows the gameboard after the level rise has occurred. The bear has risen up the gameboard to encounter the rubber rings and be removed from the gameboard. A record of the removal of the bear is made at bear icon on the left hand side of the screen . This icon denotes that there may be more than one bear available to a player on any particular game board.

The game software is programmed to visually indicate to a player the physics of the tile by a shimmering or Mexican wave effect. Highlight could involve briefly enlarging or brightening game elements in the row. That is the rows of the tiles above the dividing line are each highlighted in sequence so as to illustrate that game elements fall downwardly to the dividing line. Conversely rows of game elements below the dividing line are briefly highlighted in a reverse sequence indicating that game elements arrive upwardly below the dividing line. Alternatively no highlighting can take place in the lemonade.

Another aspect of the present invention pertains to the manner in which the game elements are displayed as a game board. In the known version of the three match game known as Candy Crush the game board has a fixed size in 8 5 elements and is replenished to the fixed size by game elements falling downwardly. The fixed size does not need to be 8 5 or indeed a matrix but in the known game it is a fixed size. According to an embodiment of the present invention there is instead a scrolling version of the screen illustrated in and . Note that in there are two rows R1 and R2 illustrated at the bottom of the display and note that the dividing line occurs six rows above the bottom of the display. Above the dividing line there are three visible rows. Consider now where the screen has scrolled upwardly so that a user can now not see two R1 and can only see the upper half of row R2 at the bottom of the screen. However an additional row R3 has now appeared at the top of the screen and half of a further row R4 with the rubber rings has also appeared at the top of the screen. This allows a user to see how progress is being made of the lemonade to bring the teddy bear character up to engagement with the rubber ring . The effect of this is that the game board appears to move downwards relative to the background once the lemonade appears to be over halfway up the visible game board allowing a player to see the level of rubber rings which they must reach and which was not in immediate view when the player started the game.

One aim of the scrolling is to follow the bear character as though he is being followed by a camera. This improves user engagement and interest in following the fate of the character as it moves towards the target. Other modes of moving the camera are available. It is possible to move in any direction in the two dimensional screen and to control the camera to centre on any particular tile based on a predetermined condition. For example a condition could have the following components same state goal met user input booster. In some embodiments user input can thus determine which character or tile to centre the camera view of the screen.

In the known version of Candy Crush Saga some levels have special game elements known as jelly blocks . As will be described later jelly blocks are placed on game tiles underneath game elements. A jelly block can be removed by performing a match on the tile on which it is located. shows a gameboard having jelly blocks placed over it. On the gameboard there are tiles with jellies and tiles without .

One novel game objective that may be presented to the player may be to collect all of these jelly bears by removing all of the jelly blocks covering them. shows the gameboard after all of the jelly blocks that were covering the jelly bear have been removed. Consequently the jelly bear is no longer present on the gameboard and the value of the counter has increased by one. To successfully complete the level the player must remove all of the jelly bears from the gameboard. There is therefore no need for all of the jelly blocks to be removed as in previous implementations of the game but only those that cover the jelly bears.

The concept of booster is described later. illustrate a novel booster in the form of colouring candy. The colouring candy looks like a sweet inside a bubble as illustrated for example at in . In the sweet is an orange sweet. Swapping a colouring candy with one of its adjacent neighbours will cause all occurrences of that neighbour to change into the colour of the colouring candy. For example swapping the orange colouring candy with a purple candy such as will cause all instances of the purple candy all denoted in to change into orange candies as illustrated at in .

According to another embodiment of the invention a new dynamic is introduced when a colour bomb is swapped with a wrapped candy. This has the effect of destroying all the candy on that level. See for example where a colour bomb is denoted and a wrapped candy adjacent it . illustrates the effect of swapping the colour bomb with the wrapped candy . also illustrates the numerical scores that result from the destruction of the candies.

People skilled in the art will understand that other devices than the exemplary ones listed can be also be used without departing from the spirit and scope of the invention.

The techniques described in this patent can be deployed in many different gameplay architectures. For example a computer game can be implemented as a computer program that is stored and runs entirely locally on the processor of a PC games console tablet or mobile telephone or other computing device. The game can be implemented solely as a computer program that is stored and runs entirely on one of many processors in a remote server and data streams or updates are supplied to the client device e.g. tablet smartphone etc. to enable the client to render and display graphics and sounds this web services approach is increasingly common.

Another approach is a hybrid one in which back end servers handle some elements of the gameplay and for instance a Java game applet is provided to client devices and it is the locally running Java applet that generates the graphics sounds user interaction for gameplay on the player s client device. Some data may be fed back to the back end servers to enable scoring interaction with other players and cross platform synchronisation. Generally the techniques described in this specification are not specific to any one game architecture but can be deployed on any suitable game architecture.

The game can be implemented allowing a user to interact with it in different ways depending on the capabilities of the device which the user is accessing the game with. A user can interact with the game through using a touch screen where the user can select and or move elements on the game board with a finger or for instance with a stylus. The game can also be played with a pointing device such as a mouse or other interaction devices such as a keyboard.

Mobile devices may have a touch screen interface where the player can interact with the game using a finger or a pointing device such as a stylus. Some mobile devices have hard keys that complement the touch screen interface. Such hard keys may be in the form of a button or in the form of a joystick type of interaction.

Over the course of players playing the game data will be produced. This data can for instance be related to a player s game performance or to game information related to a social network to which the game is connected. It is possible to gather this data store it and make use of it for instance to improve the game. One example is by using a database to store the amount of times players try and fail a level on average. This data can then be reviewed and if the players seem to fail a substantial amount of times before completing a level the difficulty can be adjusted accordingly. The difficulty can be adjusted through changing a score target for the level increasing the available time or moves or giving the player for instance a booster to enhance the gameplay.

There can be certain performance indicators used to measure the success of the game. These indicators can for instance relate to player retention the virality of the game and the revenue of the game.

A person skilled in the art will realise that the different approaches to implementing the game is not exhaustive what is described herein are certain preferred embodiments. It is possible to implement the way in a number of variations without departing from the spirit or scope of the invention.

The terms user and player are used interchangeably throughout this document and no specific meaning is intended using one or the other unless the context suggests otherwise.

The following description describes additional game components of match 3 switcher games. The person skilled in the art will understand that there are many other ways the present ideas can be implemented and the description is not limited to only one implementation. The following features can be used in combination with any of the aforesaid novel game components.

Game board The area where the matching and swapping of elements occur Note that the entire game board is not visible to a player but can be scrolled to change the player view.

Standard game elements These are the six basic candies used for making switches and colour matches on the game board. Compared to special game elements the standard game elements have no extra properties or behaviour they are only used to make colour combinations or to create new special game elements.

Ingredients Game elements that are included in levels where one of the goals to complete the level is to bring down ingredient elements to the bottom of the game board.

Jelly block A game element that is placed underneath other game elements and need one or two matches on top of them to disappear.

Special game elements All elements that appear on the game board and which have specific behaviours and properties.

Moves Score Level In this game mode you have a limited number of switches before running out of moves. If you have not reached the score required to earn at least 1 Star then you will fail the level.

Jelly Level In this game mode the game board behind the candy is covered in jelly. Remove the jelly by matching candy on top of the jelly. If you fail to remove all jelly before running out of moves then you will fail the level.

Ingredients Level In this game mode ingredients will appear on the game board. Collect these ingredients by bringing them to their delivery point. On the side of the board you will see a recipe of how many ingredients you need to collect. If you do not bring down all the ingredients before running out of moves then you will fail the level.

Time Limited Level In this game mode there is a time limit. If you have not reached the score required to earn at least 1 Star when the time runs out then you will fail the level.

Candy Order level In this game mode you are tasked with collecting a number of candies. This is done by removing the wanted candies. If you have not collected all the wanted candies before running out of moves then you will fail the level.

Booster Something that enhances the gameplay and that supports assists or increases power or effectiveness.

Blocker Special game elements that are unswappable need 1 or more matches next to them to disappear and are in the way for falling candies.

Candy Crush Saga by the games developer King is a game belonging to the match 3 category of games. This means that the core basic of the game is to match three or more game elements sharing the same colour with each other. In Candy Crush Saga these game elements are implemented as candies. and shows one implementation of the first level in Candy Crush Saga where candies have to be matched to complete the level.

To play game elements in the shape of candies are swapped with each other to make moves on a game board. To gain points the player has to make moves that create matches of at least three of the same candy. In doing so the player gains points and the matched candies are removed. As a result new candies populate the game board in order to fill any empty spaces created. The game board is populated depending on the physics of a tile associated with each game element. For all candies that are removed on the game board points are always shown in the same colour as the candy that was removed for example three red candies will show red points green candies green points and so on. If a blocker element would be removed then the points shown would be in the same colour as the candies from the match that removed it.

Only swapping moves that will create at least one combination of at least three game elements of the same type are allowed.

A typical game mode of Candy Crush Saga provides the player with a limited number of moves to reach the level target.

The game board is a scrolling game board. The display displays a grid of square tiles each with a game element showing a portion of the level being played see .

To add more diversity and make Candy Crush Saga a more dynamic game players have to fulfil different criteria in order to complete different levels these are referred to as goals. Each level always has one or more goals that have to be fulfilled in order to complete that level.

One of Candy Crush Saga s most common goals is to collect a certain amount of points before running out of moves. The points are collected through making matching combinations on the game board. The smarter combinations made the more points.

Candy Crush Saga also has timed levels. The goal that needs to be fulfilled on these levels is to collect a certain amount of points before time runs out. The smarter combinations made the more points.

Some levels are referred to as Ingredients levels. The Ingredients levels have two goals which need to be fulfilled in order to complete the level 

One of the most frequent set of goals in Candy Crush Saga is the one used for levels that contain Jelly blocks. Jelly blocks are game elements that are found underneath other game elements and need one or two matches on top of them to disappear See description elsewhere . The goals that need to be fulfilled on levels with Jelly blocks are 

Another type of level Candy Crush Saga has introduced to their variety of game modes is a so called Order level. Order levels have two goals 

In this game mode players are required to collect an even amount of two colours of candies to complete the level. The level goal can be indicated with a scale where the two different types of candies to be collected are placed on either side. When the count is unbalanced one side of a scale starts tipping the bigger the difference the faster it tips. If one end touches bottom level has failed. Score is given to the player based on the number of moves it takes to collect the required amount of the two colours.

The goal of this game mode is to light up all squares cells on the game board. In some implementations the requirement to light up a cell is to combine a candy that is in that cell. In other implementations the player has to combine multiple candies in the same cell before it lights up.

In this game mode players are required to combine candies in cells adjacent to blockers in order to dig down in the level. When digging the player can uncover objects that are covered initially.

All of the game modes described herein can also be used in any combination with one another. For instance the requirement to complete one level could be to remove all jelly as well as bringing down ingredients.

If the player tries to make a move with two candies in such a way that no candy will be matched with at least two more of its own colour then the move will not be allowed and the player will have to try to find another move.

If no moves are possible on the game board then all the candies are reshuffled so that there will always be at least one possible move available. If the player can t see or find a move to make then the game helps the player by giving a hint. The hint is displayed after a few seconds of inactivity and is shown by brightening and magnifying the candies of a possible move in a flashing animation.

Not only the match of 3 candies is allowed but matches of more candies can also be done see for the different possible match patterns. Matches with more than 3 candies give more points and is something the player should try and aim for. Different acceptable matches are 

As can be noticed from the list of possible matches no diagonal matches are accepted. Diagonal matches and or swaps can be allowed in some implementations of the game.

Matches made of four or more candies not only give more points but also reward the player with special game elements. The special game elements received from combos have various positive properties and can be used to gain more points and to easier pass a level. The elements received from different matches are 

If a match is made with more than 6 candies then it is likely that the combo is a shape merged from 4 in a row 5 in a row L shape and T shape. If so there is a hierarchy of what kind of special element is received 

Special game elements received from matches can be combined with each other for various positive effects affecting the game board. Striped candies Wrapped candies and Colour bombs can all be matched with each other. To trigger these combos they do not need to be matched by game elements of the same colour but can simply be swapped with each other for an instant trigger.

Special game elements can either be received from special combos or from an automatic placement on the game board.

A Striped candy is given by matching four candies of the same colour in a horizontal or vertical line.

The Striped candies have the same shape and colour as the standard game elements except for that they have white vertical or horizontal lines on them. The colour and the shape of the striped candy will be the same as the candies which were being matched to create it.

If the match of four candies is done in a horizontal line then a candy with vertical lines will be given. If a match of four candies is done in a vertical line then a candy with horizontal lines will be given.

Striped candies remove a whole row or column depending on if it was made from a vertical or horizontal combo. The white lines on the candy indicate whether it will remove a row or a column. To trigger a Striped candy it needs to be matched with two more candies of the same colour.

Striped candies removes all candies in a row or column also if the game board is divided up in two or more areas that are not connected. The player can this way remove candies from areas that otherwise would be hard or impossible to find combinations in. The impact of different game board designs are described elsewhere in this document.

When a Striped candy is being triggered an animation shoots out of the Striped candy following the row or column which it is removing. The animation looks something like the candy being stretched out and turned into lines that shoot out together with a sparkle effect. For all candies that are being removed the points given for each candy will be shown in the same colour as the candy being removed.

The Wrapped candies have the same shape and colour as standard game elements but with a wrapping around them. The colour and the shape of the Wrapped candy will be the same as the candies which were being matched to create it.

The Wrapped candy is triggered by matching it with two more candies of the same colour. The result of the trigger are two explosions removing candies in a 3 3 square around the Wrapped candy. The first explosion occurs instantly when the Wrapped candy is being triggered the second explosion occurs after all candies from the first explosion have been removed and replaced with new candies. If the Wrapped candy is at the edge of the game board an explosion will happen but there is no effect from the part of the explosion area that is outside of the game board. When swapped with a colour bomb all candy in the level is destroyed.

When a Wrapped candy detonates an animation with sparkling effect and light circles is shown with the Wrapped candy in the centre of the animation.

To trigger the Colour bomb it can be swapped with any candy no match 3 is necessary. When the Colour bomb is triggered it removes all candies of the same colour as the candy that was used to trigger it.

When the Colour bomb is being used. Blue coloured lightning bolts shoots out from the colour bomb to all candies that are going to be removed.

Mystery Candies are placed randomly on the game board and do not need a special combination to appear.

The Mystery candies have an oval flattened shape which is slightly tilted and with a question mark painted onto it. The Mystery candy comes in the 6 standard candy colours.

To use the mystery candy it needs to be included in a standard match 3 with candies of the same colour as the Mystery candy. The Mystery candy will then turn into a random game element which could have either positive or negative impact for the player. It could for example turn into a Striped candy or a Colour bomb or it could turn into something less fortunate for example a spreading chocolate block see description elsewhere or a bomb that counts down and explodes to make the player game over.

Lucky candies are inserted on the game board automatically when having selected a pre game booster which specifically adds Lucky candies to the candy mix on the game board.

The Lucky candy looks like a flattened sphere with a white tick mark painted on top of it. The candy comes in all the 6 standard candy colours.

To use the Lucky candy it need to be matched with two more candies of the same colour. The Lucky candy will then turn into a random positive game element.

When the Lucky candy is being matched it looks like it is unwrapped and behind the wrap it reveals the new game element.

Fishes are placed on the game board by selecting a pre game booster that specifically does so. They can also be created by creating a match of 4 candies in a 2 2 block.

The fish is used by matching it with two more candies of the same colour. Doing so will cause the fish to swims towards a random element on the gameboard and remove it. If there are Jelly blocks or other blockers then the game will prioritize to remove those before removing a candy that stands on an empty square.

This fish is given when combining a Fish with a Striped candy. The Striped candy and the Fish do not need to be of the same colour. Furthermore the Polka fish will be triggered instantly and cannot be saved for later use.

The Polka fish looks like a standard candy Fish but with the same kind of stripes as the Striped candy.

The Polka fish turns a random candy into a vertical or horizontal striped candy which in turn is instantly triggered and creates a line blast effect.

In one implementation as with the standard candy Fish and the Wrapped Fish the created Polka fish swims out of view and returns with two more Polka fishes of the same colour which then swims to the position of the candies that are to be turned into triggered line blast elements. Having reached their destination the Polka fishes disappear.

These candies are placed automatically on the game board. They could also be a resulting candy when having used a mystery candy.

Like a standard candy but with a soft glow around it and an animation of a rainbow passing by over the surface of the candy.

This is a game element that is automatically placed on a fixed position on an edge of one of the cells in the game board. The teleporter will typically be placed on the game board in pairs where one of the teleporters act as an entry point for candies falling on the game board across the cell edge where the teleporter sits. The candy will then be introduced on the game board where the exit point teleporter sits. So if a candy is normally falling one way from the top of the game board to the bottom of the game board the teleporter can move a candy up the game board again or to another area of the game board.

The teleporter does not fall down or take space on the area where switching is done and it is never included in any colour combinations.

Jelly blocks are introduced early in the game and a typical goal to complete a level is to remove all Jelly blocks on the game board. Alternatively the goal to complete a level may be to uncover larger game objects that are positioned behind several jelly blocks as seen in .

The Jelly blocks are placed behind candies and are stuck into place. They cannot be swapped and they do not fall down if candies below them are being removed.

To remove a Jelly block a match has to be made on top of it. Sometimes Jelly blocks consist of two layers and then they need two matches on top of them to be removed.

This is a visible game mechanic. In one implementation it can indicate where liquorice bombs and ingredients are set to appear.

Special game elements can be combined with each other through a simple switch. Doing so creates powerful effects that help the player earn more points and to easier pass a level.

Combining two Striped candies will trigger two simultaneous line blasts where one row and one column is removed in a cross shaped way see . It does not matter if the Striped candies combined are horizontal or vertical. The column and row blasts will be initiated from the position which the moved striped candy has been moved to.

Swapping any two Wrapped candies with each other will create a double explosion as with a standard Wrapped candy the difference being that the area of effect will be much larger and remove everything in a 6 5 square area or a 5 6 square area depending on if the Wrapped candies are placed next to each other horizontally or vertically.

Combining any Striped candy with any Wrapped candy will trigger 3 horizontal and 3 vertical line blast effects. The result is three adjacent rows being removed and thereafter three adjacent columns being removed.

Combining these two will first remove all of the candies on the gameboard. See for example where a colour bomb is denoted and a wrapped candy adjacent it . illustrates the effect of swapping the colour bomb with the wrapped candy .

The combination of these two special candies will turn all candies of the same colour as the Striped candy into randomly vertical or horizontal Striped candies which are then instantly triggered and fills the game board with line blasts.

Combining two Colour bombs will remove all game elements on the game board except if a game element is a multi layered blocker see description elsewhere . If a game element has more than one layer then one of those layers will be removed.

Combing two fish causes three fish to swim out from the position of the combination to three random locations on the gameboard. The fishes remove the game elements at the three position that they swim to.

First all candies which the game board has the most of will be removed. After those candies have been removed the Coconut wheel will roll over the board and every candy it rolls over will turn into stripes.

With this combination the Coconut wheel will roll over the board and turn all candies it rolls over into Striped candies that instantly triggers.

With this combination the Coconut wheel turns all candies that it rolls over into Wrapped candies which are then instantly triggered and explodes.

The game implements several different kinds of so called Blockers. Blockers are negative game elements that are in the way for the player when wanting to make matches on different areas of the game board. The game described herein has a new game objective associated with a Chocolate blocker.

The Chocolate blocker not only blocks a space on the game board but also multiplies to block even larger areas of the game board. If a colour combination is made next to a Chocolate blocker then no Chocolate block will multiply and that Chocolate block will be removed. However if a colour match is made and is not next to a chocolate block then one of the Chocolate blocks on the game board will multiply and another space on the game board will be filled with a Chocolate blocker. The space that receives a new Chocolate block will always be adjacent to an existing Chocolate block however which Chocolate block on the game board it will come from is seemingly random. If all Chocolate blocks on the game board have been removed then no new Chocolate blocks will appear. Chocolate blockers cannot be swapped and change places but are stuck where they are. Chocolate blockers can only multiply to a cell on the game board that is occupied with a candy.

Part of the game board is presented to the player while playing levels in Candy Crush Saga. The term game board signifies the area that contains candies and other elements such as ingredients jelly and frosting not the surrounding landscape such as the score meter and the heart showing the amount of lives left. The entire game board is not visible to a player instead the CPU can control the user interface to scroll the service board to a player.

There are audio controls on the user interface used for the music and sound effects. The amount of moves the player has left to complete the level is shown. The current score of the player expressed in absolute points is presented so that the player may follow the gameplay. The star meter showing an indication of how much points the player has in relation to the pre defined goals required for achieving a certain amount of stars. The game board is populated with regular candies in regular cells and or tiles. The number of lives the player has left is shown. Both the current level of the game and a symbol indicating what the goal of the level is are shown in relation to the game board. The physics of a tile governs where new candies enter onto the board when existing ones are removed. For part of the game board upper part in new candies are generated from the top and fall downwards as shown by the arrows and for the lower part in candies are generated from the bottom and move into place upwards.

The entire game board is not visible to a player instead it can scroll upwards or downwards depending how the game progresses as described earlier.

In the most basic version this feature serves the purpose of letting players know their performance while playing the game by showing which level of score they have accomplished. The level of score is determined by the amount of points gathered and compared against predefined levels that will earn the player one two or three stars. Stars are a representation of how well a player is performing on a level. Achieving at least one star is required to pass a level. Achieving more than one stars indicates that a player is performing better than the minimum required and is a factor that helps drive engagement by making players feel more skilled. The amount of points required to achieve one two or three stars is pre defined and typically does not change for any level. However in some implementations it is possible to have a variable score required for different amounts of stars for instance one that is correlated with the average scores of all players playing the game.

In some implementations there are indications of the performance of other players displayed during the play of a level. This information is often based on data from previously completed levels but it can also be related to levels that have been attempted and failed by other players. Performance information can for instance be derived from a social network connected to the game or from databases more directly related to the game. In some implementations players can see the score of other players in real time thus increasing the competitive element of the game. The other players whose performance will be displayed is sometimes chosen by the player sometimes automatically derived from a social network of the player and other times it can be based on other elements such as the performance of all players of the game.

In some implementations the player can see indications of the previous high score achieved on a level while playing it. It is also possible that no indication of the player s own previous score is shown.

In some implementations the indications of the performance of other players are shown in relation to the score meter. It can be both absolute and relative indications. The indications can be in the form of pictures associated with the players. When the player passes the score of another player or the previous best score the player has achieved a message can be shown to encourage the player and denote the accomplishment.

It should be understood that the invention is not limited to using stored scores to show the performance of other players. In one implementation players can see the scores of other players currently playing the same level while they are playing it making it so that the indications of other players scores can be moving in real time during the play of a game.

The score comparisons presented to the player can be given in percentages points and when applicable other indicators for instance time played or number of attempts on a level.

The look of a level as well as the overall look of the virtual landscape can change as the player performs better. For instance after achieving one star during the play of a level the digits shown when scoring points can turn into a different colour. The lookout of the virtual landscape can become warmer and more colourful as more stars are gained. The look of the game can change according to other variables as well such as the in game view changing depending on how many moves are left in order to convey a sense of urgency.

The Star Meter also has other important functions. One is that the score of friends from a social network is shown on the meter if there is data available. This increases competition and incentivises players to replay levels in order to beat the score of friends.

Another function is that the amount of stars achieved on each level is shown next to the levels on the map view. This gives players an overview of their overall performance in the game. Also in order to complete a level the player needs to reach the amount of points needed to achieve at least one star.

Upon finishing a level Candy Crush Saga may display the words Sugar Crush accompanied by audio saying the words. In one embodiment the first thing that happens after this display is that all special candies trigger one after another removing other game elements and gaining points. Secondly the special game elements such as wrapped candies stripped candies etc may be placed on the gameboard in random position and instantly triggered removing further game elements and gaining points. The number of game elements placed on the board may be equal to the number of moves that remain to the player upon completion of the level.

In some game modes players are awarded for their remaining moves by a number of candy fish spawning. The fish are proportional to the amount of remaining moves left. The fish come from outside the game board and randomly seek out candies which are removed upon impact. Players receive bonus score for when each fish hits a candy.

In levels where the player has a limited amount of time there are certain candies that are marked with a 5 symbol meaning that they give an additional 5 seconds if popped. If any of these candies remain when the time runs out they transform into wrapped candies that subsequently trigger.

Before starting a level players have to select which level to play from the map view. The exception to this is the very first time Candy Crush Saga is played when level one starts immediately. When selecting a level the player is shown information about the level such as the amount of points needed the available boosters that can be used the goal of the level and also the high scores of friends who have previously played that level.

A difference between playing a level for the first time and playing a previously completed level is that the previous best score of the player is displayed together with the amount of stars achieved. Also the text that is telling the player what the target goal is in terms of points is changed depending on how many stars the players has achieved before. Having the game set up in this way increases replayability by making players focus on always improving but not necessarily too much at a time. If the first goal presented was the one correlating to three stars players could feel inadequate if they get less points than that even if the level was completed.

The player can choose boosters that will in some way affect the game play before starting a level. Boosters are unlocked and gained as the player progresses throughout the game but it is also possible to purchase more boosters.

When completing a level the player is presented with a screen that shows the amount of points gained the amount of stars achieved and the previous high scores of friends.

After the post level screen has been closed the player may be presented with yet another screen related to the performance of the just completed level.

Both the Post level screen and the screen that shows when a friend has been beaten present the player with an option to share this information. The sharing part is done on a social network to which the game is connected. By sharing information such as which friends the player has beaten competition is encouraged and the viralisation of the game is increased due to people not playing the game also being able to see such messages.

It is possible to help friends by sending lives from this screen as well. This can be done with a click on an icon with a heart and letter on it next to the friends names. The tick marks indicate that the player has already sent lives to those friends. The player may only send lives to any one friend once within a certain period of time for instance once per day.

When failing to complete a level a screen similar to the one shown when completing a level is displayed. The difference is that the screen when failing a level has a broken heart on it together with information stating why the level was failed. Failing a level can happen due to a number of reasons such as not reaching the minimum score for one star failing to accomplish the goal or by a bomb exploding. The player is informed of the reason for why he has failed the level. Understanding why you have failed a level increases the likelihood that he player will try to play the level again to reach that target for the level. If wanting to play the same level again there is an option to do so. In one implementation the option to replay the failed level is presented with a large and visually significant button.

Games created using the techniques described herein can be played locally on a player s computer or handheld device. The game can also be played over the Internet where the whole game or portions are downloaded and executed on the local machine or run on a remote computer or server. The user s progress in the game and results can be stored locally and compared to the user and other players on the local computer. The progress and results can in an alternative embodiment be synchronised with other players either directly or through a server or social network or gaming platform.

Three platforms in particular are changing the way people expect games to be played. These three platforms are growing at the same time and provide new input possibilities. To date games have not absorbed all the new input possibilities.

The first platform is Facebook. The skilled person will understand that where Facebook is referred to in this document other social network platforms may be used. A Facebook game may be a social game a game you play with your friends. It is rare or unthinkable to launch a game i.e. to play for the first time on Facebook that is a paid game because people playing games on Facebook expect not to pay to access a game. A Facebook game may be played on the internet after logging in to Facebook whether automatically or manually such as from a personal computer.

The second platform is smartphones. Use of smartphones is not always continuous. You may use a smartphone for 5 minutes on a bus and then for 20 minutes on a connecting train for example. The use can have many starts and stops not like someone working at an office desk or at a home desk in a conventional way. A smartphone can be on an iOS platform or on an Android platform for example.

The third platform is tablets. A tablet can function as a mobile device and as a non mobile device. The tablet can be a substitute for a personal computer. A user may want a seamless experience between using the game on a personal computer and on a tablet and on another mobile device. A tablet can be on an iOS platform or on an Android platform for example.

A game which works on a plurality of such as all three of the above platforms or more may provide a connected fully synchronized seamless experience. Hence multi platform games are important. Key criteria for multi platform games are they are free they are social stop start use is possible and seamless experience is provided. Such games may be played anywhere e.g. in a mobile environment or in a non mobile environment. Such games may also be played online or offline.

The game must be fun when used in a stop start way and when used for even just short intervals. In an example a game consists of parts or levels each of which runs for about 3 minutes e.g. between 1 and 5 minutes. In an example a game is structured in levels so that if successful in a game level such as by scoring a minimum score a user can progress from that level to the next level. In an example a game has about 200 levels.

A game can be optimized post launch. For example if it is clear that too many users are failing to progress past a particular level the minimum score to pass the level can be lowered. An optimized game may be provided as an application update from an application store. In an alternative a game may be optimized by a server sending a revised data file of scores required to pass each game level to a mobile device when a game state of a user is being synchronized with the server wherein the application running on the device replaces the previous file of scores stored on the device required to pass each level with the revised file of scores required to pass each level.

The progress of a player is also synchronised across devices for instance between a handheld device and a computer. This is described in further detail in Appendix A. The player can play on one platform have the progress saved and then continue playing seamlessly on another platform. It is also possible for the player to play on offline devices and having the game synchronise when a connection is available.

In some implementations players can be rewarded for playing the game on multiple platforms. For instance players active on a computer based platform could get a bonus for also installing the game on a handheld device.

Players can also be rewarded for playing multiple games that are related for instance games from the same developer. When choosing to play a new game the player can receive bonuses in another game. This can be triggered by using a link from one game to the other or by games sharing information between one another so that it automatically detects a player that is playing more than one game and subsequently rewards them.

It is also possible that games can have elements in common that enables certain objects for instance boosters to be usable in multiple games. These games can be located on the same or on different servers. In some implementations a booster bought in Candy Crush Saga can be used in another game that shares certain features with it.

A first server for instance one hosting a social network with a first data store storing data relating to the state of a game. The first server is configured to communicate with a first plurality of devices such as mobile phones or personal computers through a first application programming interface where the first plurality of devices is related to a first computing platform.

A second server for instance one hosting a game platform with a second data store storing data relating to the state of the game. The second server is configured to communicate with a second plurality of devices such as mobile phones or personal computers through a second application programming interface where the second plurality of devices is related to a second computing platform.

A third server with a third data store configured to communicate with the first and the second server. The three servers are configured to synchronise the three data stores in such a way that when synchronized the first second and third data store all relate to a synchronised game state.

It is possible for implementations of the game to vary depending on the location of the player. For instance the language can be adapted and translated into different languages. It can also be so that updates of the game are incorporated at different times in different locations in order to avoid interference with the times of the day that players are as most active.

If trying to access the game online as opposed to starting a local version that is saved on the device while updates are being made the player can be met by a message saying that the game cannot be accessed right at that moment. Such a message could be displayed instead of the game as a placeholder for when the game is taken offline for instance so that the game can be updated with new features and software.

The game can be implemented so that a player progresses through multiple levels of changing and typically increasing difficulty. The user interface can present a virtual map layout of a game environment displayed on the computing device used by the game player. As the player travels through the levels in the game his progress is represented as a journey along a path in the virtual map. Representing progress in this manner provides an additional layer of engagement for players and also opportunities for viralisation and monetisation.

The virtual map consists of stages with varying number of levels. The user travels between levels and completes the levels one by one along a path by playing the associated game. When the player reaches the goal of a level the next level is unlocked and the player can play that level in the game. The number of stages and levels can vary depending on the implementation. The levels can be numbered consecutively throughout the game or they can be numbered within a stage it is also understood that other ways of identifying the stages and levels can be implemented. New stages to the virtual map can be added by the game designers at any time so a game may be launched with say 20 levels and after a number of weeks there may be fifty or sixty levels present.

One way of unlocking new stages is to complete the last level on the latest stage. The user is sometimes faced with challenges to unlock the next stage in the virtual map.

In one implementation traveling from one stage to another once all the levels have been completed on that stage requires the help of for instance three friends. The player can ask friends for help by sending an in game message within the game environment or for instance through a social network that the game is connected to. The friends can already be playing the game and do not have to be new players but they can be friends not already on the same social network.

The player can also pay to get instant access to the locked stage. The player can use a combination of help from friend and payment to unlock the new stage. The cost for unlocking can in some implementations be lowered as a fraction of the total number of friends needed when help from some but not all needed friends have been received.

The request for help is sent to the friend who then has the option to accept to help. The request for help can in some implementations be sent using the social network to which the game is connected an alternative implementation is to send the request to someone external to the game via email text message instant message for instance who has to join the game to respond to the help request. This is one of the viralisation techniques implemented in this game.

In addition to the virtual map layout there can also be other levels or stages that are not part of the progress along the path in the virtual map. Such stages or levels can be present in the game associated with the virtual map at all times or can be unlocked when the user reaches a certain in game achievement. This in game achievement can for instance be completing a specific level reaching a predetermined high score for instance collecting a specific number of stars when completing a level highly skilled gameplay can win the user three stars or paying virtual currency to unlock the stage or level.

The map layout can be used in games connected to or linked with a social network. It is common that the users on such networks have avatars with for instance a photo of the user and or the user s name. Such avatars can for instance also be a sign or a figure. It is understood that there are different implementations of showing where the user currently is on the map. This can for instance be the latest level the user completed the level with the highest score or the last completed level along the traversed path.

The user can in some embodiments be given the option to select which users should be shown on the virtual map. The users to choose from can be friends on a social network or the user can get suggestions to show friends which meet a certain criteria for instance friends which the player has interacted with the most in the past or friends living in the same geographic area as the player. The user can get the option to choose from other people not being friends on the social network but that meet other certain criteria.

The user can play any of the unlocked levels on the map so the user can go back and replay already completed levels to get a better score or beat friends high scores.

The player is in some implementations of the game rewarded for good gameplay of a level for instance reaching a target score. In some implementations the user has to reach a certain number of points to complete a level reaching this target score can be represented with a symbol such as a star. In one implementation a star is lit when the user reaches a certain number of points in a level. The user can earn more than one star on each level and the levels are re playable to get a higher score.

The player s total number of stars collected in the game can in some embodiments unlock features. The unlocked features can for instance be power ups in game currency or bonus levels.

The symbol representing how well the user has played on each level can be displayed alongside the level on the map.

If the game is connected to a social network or the user has connected with other players in the game the levels will present a leaderboard showing who among the user s connections has the highest score. There can in some embodiments be a notification shown on the map if the user that has the highest score among the friends connected to the game.

The landscape of the virtual map will typically have animated sequences which give a feeling of the map being alive and dynamic. For example trees on the map can sway in the wind animals can move around and the player progressing from one level to another can be accompanied by an animation of a player associated character moving on the map.

In some implementations it is possible for the player to interact with objects on the map in such a way that animations are triggered. For instance clicking on a bird can make it fly into the air and hovering over water can make waves appear.

It is also possible to have any combination of a map that is static but reacts to player input a static map that does not react to player input a dynamic map that reacts to player input and a dynamic map that does not react to player input.

The game can also be implemented to be played with a limited time or limited number of moves or both over a consecutive set of levels. The score can be collected over the several levels to give the player a score for all the levels completed.

The player can in some implementations play the game in head to head tournaments against one or several other players. The player with the highest collective score over the number of levels will be the winner in the tournament. In some implementations the tournaments are played with real time comparisons of players scores in other implementations the scores of players are compared after finishing a level.

The game can also be played in tournaments with jackpots where the player plays the same level where the same types of game elements are used.

The game can have schemes for giving rewards and bonuses to players. One reason for giving out rewards is to increase player engagement and to some extent to help with monetisation. Players can for instance be rewarded for playing multiple days in a row something that awards persistence and dedication. In other implementations there is a daily bonus available that is gained by every player playing the game online during that day or to players passing a certain secret location during that day. By giving players samples of existing boosters they are given a free preview of purchasable items that potentially can lead to sales in the long run which helps monetise the game.

The virtual landscape of Candy Crush Saga is presented to the player in between levels. This is also referred to as the map view and the virtual map within this document. The player travels along a virtual path as more levels are completed in the game which gives the feel of moving forward.

The looks of the map view is in the style of a physical foldable game board such as one commonly used for board games. However since Candy Crush Saga is not a physical board game but a virtual one the board is much larger than what can be displayed in a single screen. The player can at any time while in the map view look at all available levels and also scroll through the entirety of the map board. Having such a style gives a strong feeling of actually progressing forward in the game as more levels become unlocked.

When navigating on a map in a game it is sometimes difficult to find desired spot or area of the map if the map is for example too large. As mentioned earlier the levels of the game may be grouped together into stages . In one embodiment a list of the different stages of the game may be present in an expandable tab. By clicking on one of the stages in this list the screen jumps to the location of this stage on the main map thereby allowing the player to rapidly navigate the main map. In this document we refer to the expandable tab and the mini map as the navigator.

If the player does not need to use the navigator then it is unnecessary for it to take up precious screen space. Therefore in one implementation the navigator is only in full view when the player needs it the rest of the time it is hidden with only a small part of it showing. Clicking on this small part will expand the navigator and let the player use it. Clicking on the same part again will once more hide the navigator. In one implementation when the navigator is hidden a small tab is placed at the bottom right edge of the screen which will in turn expand the navigator when clicked on.

In one implementation if the player for example wants to jump to the furthest reached location on the map then there is a home button which will take the player there directly. Pressing the home button will not only take the player to the current location but will also hide the navigator giving the player a full view. With the home button the player can always find their active location in the blink of an eye.

Another implementation may be to offer the player filtering and multiple choices of where to jump on the map. There could for example be an icon which when pressed lets the player choose exactly which level to jump to. There could also be an alternative to receive a list of levels the player can jump to which satisfy certain criteria for example all levels with limited moves and ingredients in them. The filter could offer many kinds of choices.

The overall theme of Candy Crush Saga lends a special atmosphere to the game. Everything is candy themed with bright and warm colours used in all animations and pictures. The words used for encouragement throughout the game such as sweet and delicious serve as an example of the candy theme.

As the player progresses in the game new areas episodes are unlocked. Each episode has a related story and often a mini theme that is present in at least some levels in the area. Also the same background picture is used in all levels in the same area. When reaching a new are the background image will change. Each episode also has a specific colour which is used in the virtual landscape view to show the different episodes.

The episodes all have different names each with a candy theme to it for example Candy Town Candy Factory Lemonade Lake Chocolate Mountains Lollipop Forrest and so on.

Within each episode there is a set of levels. The division of levels between the episodes is not entirely linear. The first two episodes consist of ten levels each while episodes three and onward each consists of 15 levels each. This makes it easier for the player to advance in the beginning something that can be important for player retention and engagement.

In the virtual landscape the player follows a virtual path as the game progresses. After completing a level the next one becomes unlocked and the player travels there on the virtual map. There is an indicator showing which level the player is currently on in one implementation the indicator is in the form of an orange arrow bouncing up and down.

The virtual landscape is divided into areas each area representing a different episode of the game. The episodes are also coloured differently with one colour being used consistently throughout one episode area. The end of an episode is marked by a special kind of obstacle that can only be passed with the help of three friends or through a purchase. When passing these kinds of obstacles there is a celebratory animation accompanying the passage to signal that the player has progressed into a new episode of the game.

In the virtual landscape levels that have not yet been reached by the player are shown in a different way than levels already accessible. There is also a difference between unreached levels in an unlocked area and unreached levels in areas not yet unlocked. As can be seen in areas that have not yet been reached are greyed out. This furthers the experience of giving players a sense of accomplishment when reaching a new area since it is reflected by the virtual landscape actually changing slightly.

As already mentioned there are special obstacles that hinder the player from reaching new areas in the game. These obstacles are collaboration blocks which means that the player needs to receive help from friends in order to pass. Help from friends can be requested through a social network and the new area will not be unlocked until three friends accept to help. This is a way to increase viralisation as well as player engagement. By helping each other players get a sense of collaboration as well as it being a competitive element to remind the player how far friends have come.

It is possible to circumvent the need of having friends to help pass into the next area by instead paying for it. The amount that has to be paid can be reduced by having some friends help even if the required amount of help for passing without paying is not reached. For example if one friends help the player has to pay more than if no friends help if two friends help a lesser amount has to be paid than if one friends help and if three friends help the player does not need to pay at all.

When reaching a collaboration block which is at the end of each episode in the game except for the first two the player is prompted to select which friends to send requests to. The friends need to have Candy Crush Saga installed in order to be able to provide help but it is possible to send requests to friends who do not yet

To travel from one stage to another once all the levels have been completed on that stage requires the help of three friends. These friends can already be playing the game and do not have to be new players. However instant access can also be bought using a virtual currency. Friends can be asked for help either by clicking the Ask friends for help button or by the sign to the right of the buttons. Once the stage has been unlocked with the help of the three friends all the levels within that stage are unlocked too.

The user can choose to request help from only selected friends or to send a request to multiple friends. There can be a limit to how many friends the player can send the request to and also a limit in time before the user can send a reminder or similar request.

The request for help is sent to the friend who then has the option to accept to help or to decline to help. The request can in one implementation be sent using the social network to which the game is connected an alternative implementation is to send the request to someone external to the game via email text message instant message for instance who has to join the game to respond to the help request. This is one of the viralisation techniques implemented in this game.

The inventions may be implemented with ways of getting past a collaboration block other than asking friends for help and paying for it which are the most common ways of passing a collaboration block. This can be done through to use of Mystery Quests which gives the player the option of completing one or several challenges to unlock the block. Such challenge can for instance be to play one or several past levels with modified goals in order to pass the collaboration block for instance three levels one for each of the locks.

These challenges are typically in the form of replaying a previously completed level but with a new goal to reach for instance a target high score. In a typical implementation the score requirement is higher than it is for playing the level regularly and also no other goals need to be fulfilled. For example if the player gets to replay a level with jelly with a new target high score the player would not need to remove the amount of jellies specified as long as the target score was reached.

In a typical implementation this option to pass a collaboration block in the game is available in three cases if the player is not connected to the Internet if the player has not connected the game to a social network or if the player is not connected to either a social network or to the Internet. If the player is not connected to either a social network or the Internet then the other options available for passing the block such as sending requests to friends cannot be used. However it is possible to have this option available to users connected to both a social network and to the Internet as well.

It is possible to combine the ways of passing a collaboration block. For instance completing one Mystery Quest could make it so that the player only has to request help from two friends once a connection to a social network has been established or that the player does not need to pay as much for purchasing a way through the collaboration block.

In some implementations Mystery Quests are not tied to specific collaboration blocks. For example if the player reaches a collaboration block and completes a Mystery Quest then connects to a social network and receives help from three friends the player will only have to complete two Mystery Quests the next time that option is chosen to pass a collaboration block. If the player then only completes one more mission and then goes on to receive help from friends or purchase a way through the third time a Mystery Quest is chosen as a way to pass a collaboration block the player only needs to complete one level.

If the player chooses to play the mystery quest to pass the collaboration block the player will be taken to a screen showing three symbols representing challenges to be completed as well as specifications regarding which level is to be played and what score is required to pass the first challenge. In a typical implementation the game randomly chooses a previously completed level and increases the score required to pass it. In other implementations the Mystery Quest levels can be new levels that the player has not completed before.

If the player chooses to continue with the quest another screen is presented allowing the player to choose boosters. This screen is very similar to a regular pre level screen with the difference that instead of the level number it says Mystery Quest instead of three stars it shows a special padlock indicating that it is a Mystery Quest and a special symbol in front of the target score to further indicate that it is a Mystery Quest and not a regular level.

If the player chooses to play the Mystery Quest level the game proceeds to the game board screen and the player can start playing. If the player fails to achieve the target score a pop up shows why the player failed. In some implementations using levels previously completed as Mystery Quests the regular goals for completing the level are listed as a reason for failure as well as failing the target score. However even though this is shown as a reason for failing the level the player will in a typical implementation complete the Mystery Quest as long as the target score is achieved even if the other goals of the level are not. In other implementations the player can be required to achieve both the target score and other goals for the Mystery Quest to be completed.

However if the player manages to achieve the target score on a Mystery Quest the level will be completed. Completing a Mystery Quest level will take the player to a post level screen similar to a regular post level screen but with the same differences as the pre level screen. After this there will typically be an animation to signal that the player has completed the level such as the padlock going from being locked to being unlocked. There can be other ways to show a post level screen after the animation of unlocking the padlock has been shown.

After completing a Mystery Quest and pressing Done on the post level screen the player is typically taken back to the main Mystery Quest screen. This screen will then show the player the overall progress with the Mystery Quest which in a typical implementation consists of three levels.

In some implementations the player needs to wait 24 hours between completing each of the three levels of the Mystery Quest. In other implementations the wait time could be less or none at all. It is also possible to use other criteria for accessing the next Mystery Quest such as getting more stars on previously completed levels.

Typically the player will use a life for each failed attempt of clearing a Mystery Quest level just as is the case with regular level. It is also possible that the Mystery Quest levels do not affect the player s life total or that it uses up another kind of resource as such as boosters.

It is possible for Mystery Quests to be used for other reasons than to pass a collaboration block. For instance there can be bonus levels within the game that can only be accessed through completing Mystery Quests. In some implementations Mystery Quests can be a way for players to earn boosters in the game without having to purchase them. It is also possible that Mystery Quests are only available at certain times such as between 9 PM and 10 PM each day or on specific days.

For players who are not connected to friends through a social network or players who are connected but only have very small social networks an alternative way is to connect them to other players if they want and find proxies for the social experiences that existing networks provide.

It is important to allow players who otherwise would be stuck at a collaboration block or other social interaction tools to also be able to progress in the game. This is important to minimize the churn and to allow the game to be a fun experience for a larger portion of the players.

One such implementation is to drive installs of the game using new channels SMS E Mail Twitter etc. This will boost DAU create engagement by creating social connections and communication channels with those connections. It may also increase revenue by keeping players in the game.

This alternative approach may be used for interaction for instance when a player reaches a collaboration block or runs out of lives. The game prompts player to ask for help from other players based on some user derived player characteristics such as location player game experience. The player gets a prompt to get help with a generated but editable alias and they send the message. If the player s Push Notification PN settings are set to off include the requirement to turn PN on. The client registers the player request user ID with the server. Server generates a response granting the user request on a random basis from 5 to 55 minutes from request. And sends a PN to player. After the player has completed a single loop request PN request grant. They become capable of receiving help requests when they launch the game.

When a standalone player a player with no or only a few friends connected to the game or to a social network reaches a blocker in the game this alternative approach gives them a way to extend their game play by asking for help. Players will be able to select where they ask for help from through SMS Email Twitter etc.

Upon Completion of the loop they will receive the requested help allowing them to continue in the game.

This approach can be used for collaboration blocks that the player can request lives request other help in the game. It can also be implemented so that the player can send invitations to the game and if the recipient will join the game then the inviting player may get a reward.

The player that receives the request for help can click on the link on for instance his mobile device or computer.

The recipient will be taken to the link destination where the client device is detected and it is identified whether the player has already installed the game on the device. This can for instance be done using a so called URI scheme as described below. If the recipient does not have the game already installed he is taken to the appropriate webpage or application store to download or activate the game. This can for instance be the Apple or android app stores or to the Facebook app page. There are different options available to implement this functionality and the identification of the device can be done on the specific device or on the server.

When a player has run out of lives or is stuck at a collaboration block he or she can send a request for help via SMS. The SMS consists of a short message describing what help is wanted and a link. The message and link can be sent to one or more receivers. The link contains info on who sent the request what the request was for and a timestamp. When the receiver clicks the link the required help is sent. Link usage is kept track of in the database so a link cannot be reused by the same user. If the player does not get help within a certain time span he or she gets help from themselves looks like someone helped them . This is only to reward the behaviour of asking for things and its use is limited.

The data is then encoded in Base64 is replaced by   and is replaced by empty string. The link is a normal http link. Nothing is stored server side until the receiver clicks the link.

Push notifications are used to close the loop and are also limited per 24 h period. In some implementations they are not needed for the help to get sent.

Players can choose to be notified of certain events in a game. The notifications may be both pushed as well as only available once a player logs into the game. Notifications can be sent on both stationary computers and mobile devices depending on the player s platform of choice. It is also possible to have notifications that stretch across multiple platforms for instance they can pop up on both Facebook and on a mobile device at the same time.

 Push technology and subsequently push notifications describes communications in which transaction requests are initiated by a publisher or central server as opposed to pull technology in which the receiver or client initiates a transaction requests. Typically the player can configure in which way push notifications should be received from a range of available options such as 

Banners Notifications are shown at the top of the screen and automatically disappear after a set period of time typically a few seconds unless the player interacts with them. Banner notifications can state information regarding the notification or it can simply state which game the notification is coming from. It is in a typical implementation possible to interact with banner notifications for instance by clicking on them. Typically clicking on a banner notification will bring the player into the game.

Alerts Notifications require interaction from a player before disappearing typically they appear in the middle of the screen.

In a typical implementation the player can choose which events to be notified about. In some implementations the player can be choose to be notified when a new Mystery Quest is available or when the player has full lives. In other implementations the player can choose to be notified regarding a variety of different events such as the following 

In a typical implementation the player can choose to interact with notifications in various ways for example 

In some implementations where notifications are pushed the player will only get the first notifications pushed subsequent ones will not be seen until the player chooses to acknowledge the first one. This is because players should not feel irritated or overwhelmed by notifications.

Notifications can also be implemented so that they synchronise across platforms. For instance if a player has been notified about an occurrence it can be sent to both a mobile device and the Facebook platform but after acknowledging the notification on one platform it also disappears from other platforms. Notifications can be sent in various ways for instance 

In order to give players a better overview of their progress and overall performance in the game Candy Crush Saga shows the amount of stars achieved on a level adjacent to the level node. When hovering over a level node the stars are instead displayed adjacent to the thumbnail.

Games created using the invention described herein can be connected to or linked with a social network such as Facebook or Google or a games platform with different players who can interact and see each other s progress. It is common that the users on such networks have avatars with for instance a photo of the user and or the user s name. Such avatars can for instance also be a sign or a figure.

The social network can be located on a server that is different from the server on which the game is located the game and the social network can also be located on the same server. In some implementations there is a direct live connection between the social network and the game platform that continuously synchronise them in other implementations the two platforms synchronise at certain intervals such as when the player logs into the game. The players progress when having played in offline mode for instance completed levels and score for instance if the player is travelling in a tunnel can be synchronized when the player is connected to the internet.

The user and his friends avatars can be displayed in the game or in relation to different levels in the game to show the player s progress. The avatars can also be shown in relation to indicators of the player s skill level or high score. In some implementations the avatars can be derived from a social network to which the game is connected in other implementations they can be derived from a database related to the game. It is possible for the avatars related to users to change depending on the overall progress or performance in the game. For instance an avatar can become larger or more visually advanced as the player plays the game for a longer time.

The user can connect with other users of the social network either as friends on the social network or as friends within the game environment. The player can interact with other players he is connected to on the social network or who are playing the same game.

The game can be implemented to synchronize game state information and or retrieve and connect to the social graph information and user profile of the player on a social network. It can also be connected to a proprietary network related to the game or the game developer.

The game can also be implemented so that it is connected to a plurality of social networks. The user can be given the option to select what information that can be derived and shared with which social network.

One example of how the game can be connected to a social network is the Facebook s Open Graph API allows websites and applications to draw and share information about more objects than simply people including photos events and pages and their relationships between each other. This expands the social graph concept to more than just relationships between individuals and instead applies it to virtual non human objects between individuals as well. A game can typically share in game events such as that a level has been completed that a player has passed a friend in the game or beaten a friend s high score on a level. The game can also post events such as that a player has purchased objects in the game or received objects from other players of the game.

When showing the pre level screen players are presented with the highscores of friends. This gives an opportunity to know beforehand what to aim for and is something that increases the competitive element in the game. The information about friends scores is derived from a social network connected to which the game is connected. It is important for further increasing the engagement and of players and to some extent viralisation since players are constantly being reminded about the performance of others which can incentivise players to try harder.

In some implementations each area in the game can have a Candy King meaning the player within a network of players that has the best performance on the levels in that area.

Another feature in the game that increases the competitive element is that friends progress on the virtual map is shown. Even if the player has not unlocked or reached the areas in which friends are playing their progress can still be shown by means of a picture associated with the player being displayed next to the level they are currently at.

It is also possible to invite new players to play the game. These can be invited through the game platform or through a social network to which the game is connected. In some implementations the game suggests which players to invite. This suggestion can for instance be based on if the players have played other games from the same developer if they are active on a social network or if they seem to like other games in the same genre. It is also possible for the suggestions to be based from data related to a social network such as how often they interact with other players or how often they log in to the social network.

One aspect that increases the competitive element of the game is that messages can be sent to friends for instance related to beating their scores or passing them in terms of overall level progression. In some implementations the game prompts the player to send a message to signal that a friend has been beaten. This message can be edited by the player or it can be a pre defined version suggested by the game.

The messages can be generated on a server hosting the game or on a server hosting a social network to which the game is connected. Information used in the message can for instance be derived from one of the databases to which the game is connected or from databases related to networks to which the game is connected.

One aspect of Candy Crush Saga that increases the viralisation and engagement of players is the ability to send gifts to other players which help them in the game. It is possible to give certain gifts for free such as one extra life. The option to send free lives is available for instance through the pre level screen and the post level screen. When starting the game the player is presented with a list of friends to send lives to.

After this screen the player is presented with new messages. Gifts sent from other players are displayed under messages and certain free gifts such as lives can easily be reciprocated.

In some implementations the game prompts players to send lives to other players that have run out of lives. When a player completes a level after receiving help from a friend a thank you message can be sent to that friend either automatically or manually. This message can contain an item of value. In some implementations the player helping another player can get other benefits such as special symbols or marks being displayed next to their names. Recognition is another benefit that can be awarded to players who help others.

In the mobile version of the game the player is presented with messages when logging in. Messages that are presented can be related to the player receiving lives and friends requesting lives. After receiving a life from a friend the player is asked to send a life back. If choosing to send a life back in response the friend who originally sent it will not get a request to send back yet another life. So this chain of events has two steps if a player starts out by sending a life without request step is sending a life and step is the recipient sending a life back in response. If a player starts with requesting a life the chain of events has three steps step is requesting a life step is receiving a life step is sending a life back in response.

It is also possible to buy gifts in the Yeti shop and send these to friends. Such gifts are in the form of boosters that can be used either during a level or before a level.

Sending extra moves to a player that is stuck on a level for a certain number of days failed attempts.

Another way of helping friends is to send extra moves. This is not something that is possible to do to all players at all times but instead certain criteria must be fulfilled. The criteria are related to how long a player has been stuck on the same level. When selecting the icon Play with Friends a list of friends is presented. Some of these friends will have been stuck on a level for an extended period of time and the player then has an option to help these players by sending three extra moves free of charge. These moves are different from the booster giving five extra moves not only because the amount of extra moves is lower but also because the booster is only usable and available on a specific level. This is a way of facilitating the harder levels of the game by receiving help from friends.

The game can also prompt the player to send extra moves to friends that have been stuck on the same level for an extended period of time. In some implementations this period of time is two days. In other implementations the criteria for a player being stuck is related to the amount of times they have tried and failed a level. The prompting is for instance done when a player logs onto the game. This increases engagement by helping players when the game is particularly difficult and also adds a sense of collaboration and community among players. When a player has received extra moves this is indicated by a ribbon enveloping the node of the level in which the moves can be used.

In some implementations the player can receive help from multiple friends. Help from multiple friends can be used at the same time or subsequently. When a player completes a level after receiving help from a friend a thank you message can be sent to that friend. This message can have different implementations such as the ones described in the passage above about a thank you message related to sending lives.

Candy Crush Saga has a storyline that runs through the game. The main character is a little girl that goes around helping and defeating various creatures. At the start of the game as well as at the start of every new episode there are animated sequences. These sequences tell the story of how the girl goes around the world of Candy Crush Saga and how she overcomes obstacles that are presented to her.

In some implementations an area will start off as being slightly dirty with a sad atmosphere to become colourful and full of love and warmth as the player progresses through the levels. Areas become even more happy and colourful as the player earns more stars even on previously completed levels.

The player may in some implementations select subgroups of all available friends or filter the friends to only show the friends that also are playing the game.

The friend selection may appear when the player is to send requests to other player or ask for help. Exemplary implementations may include 

By way of example one implementation where the player can select to filter the friends may be based on a certain criteria such as the level of interaction the friends have had in the past or the skill level or progress in the games. These different criteria are illustrated with a pre filtering in three tabs in a pop up window in the game. This popup window can be automatically initiated by the game or requested by the player through for instance pressing a button in the game.

The list of friends may be populated from friends of the player that are also active in the game or only from friends on a social network. In one implementation the default mode is that no friends have been selected. Clicking on a friend s picture or name will select that friend and a tick mar may appear to indicate that it has been selected.

Listed friends may be prioritised in the way they are shown in the list to the player. One such criteria in which the order of the listed friends show may be if they have paid for something in the game. Within that group players may be higher ranked if they have spent more money or if they have spent more money within a specific time period. Another criteria may be that the listed friends have been active in the game within a certain time period or with a certain activity level. Another criteria may be that the listed friends are ranked based on how many total game invites they have received to date highest first.

If the user has no friends playing the game this tab may be renamed Friends playing other games and the same prioritisation may be applied to these game network players.

If the user has no friends at all playing games according to the filtering criteria then the tab may not appear.

The friends listed in the different tabs may be prioritised further. The following refers to the tabs all friends and remind friends but the person skilled in the art will understand that this may in some implementations also be applied to other filtered groups.

1. Paying players within the game company s network in order of CLV customer life time value highest CLV first then in order of the invites received to date for the current game highest first 

2. Non paying players within the game company s network in order of CLV if CLV is x highest CLV first then in order of invites received to date in the current game highest first 

3. Non users of the game company s network in order of invites received to date in the current game highest first 

Ideally this list should be easy to reorganise. E.g. in month 1 the focus might be on virality so we would prioritise the game network s players known to be viral but in month 2 we might want to focus on monetisation so we would want to prioritise the game network s players who spend a lot.

Prompting invitees may be stopped at some point so that they are not being spammed. For instance invitees who have received 10 invites should no longer appear in the list.

Friend selector pop ups may be customized according to two factors 1 the user who sees them and 2 the current priorities of the game environment where it has been implemented.

For example the game team wants to push monetization so in the Send moves pop up the user s friends are arranged according to their spend and so only friends with the highest spend appear in the pop up.

The standard implementation for showing popups is to show all friends. Reasons for customizing the popups can be several 

These may also be combined e.g. if the game team wants to reactive lapsed spenders they might want the send moves pop up to display each user s friends in order of spend but to display only users who have been inactive for 10 days.

There are many possible approaches. Customisation could be approached on a game specific basis using only information relating to a single game e.g. the game could customise pop ups using only the game s data This information is stored in the game s own database. But customisation may be much more powerful if it used data from across the games company network using data from all games. That information is typically stored in a database.

Customisation on a game specific basis the server creates the user rankings based their past behaviour in the game and that determines which users the server sends to the client. The client would simply display the users selected.

Customisation on a game company network basis we create user rankings based on information taken from a database covering all their activity within the game company network. The rankings would be stored in a system would be updated at least on a daily basis and would be available to all games using that framework. An individual game s servers would pull the rankings out of the system and determine which users to send to the client. The client would simply display the users selected.

Candy Crush Saga has both music and other audio effects that are important for the overall feel of the game. All sounds and music have the same warm feeling to them as the colours and animations.

Audio effects are always played as soon as something is happening in the game whether it is due to an input from the player or if it s some kind of automated event. For example an automated event could be when the user starts the game and a pop up appear suggesting that the player should send gifts to friends. When this pop up appear there is a discrete swishing sound to make the player aware that something happened. Another automated event could be before starting a level and a message screen shows up saying what needs to be done to pass the level before it automatically disappears again.

For all objects that can be interacted with in the game there is always either a visual notification a sound or both to let the player know that something in the interface can be interacted with. For example in one implementation there is a shop icon that highlights starts swinging and lets off a short sound when the mouse is hovered over it.

The sounds played to give indication of interactable objects are always non disturbing sounds that the player does not even think about are there unless someone points it out to him.

Sounds and effects are not only there to indicate when an interaction is possible. They are also present when something is being or has been interacted with for example a click on a button would make a certain sound and sometimes change the appearance on some of the buttons available. In one implementation a play button looks like a wrapped candy and when pressed the wrapper on the button becomes wrinkled.

Clicking on a candy when playing a level would also give a visual notification. In one implementation the candy would be highlighted and so the player will know what candy has been chosen. In another implementation a frame would appear around the chosen candy.

When making different kinds of switches there are also different kinds of sounds and animations connected to these. There is one sound if the player tries to make an invalid move another sound for a match of three yet another sound for a match of four and so on. When candies are removed there is a small animation of stars in the emptied space. This adds to the visual feeling of the game.

The game encourages players to make good moves and the sounds made when generating special candies are triumphant sounding and can give players a feeling of satisfaction.

Triggering special candies also have their unique sounds and visual effects. Animations with lines and stars are shown to emphasize how good it is to use these in the game and how much it helps the player.

If getting a cascade of matches falling one after the other then there is yet another sound together with a message shown on the screen saying either Delicious Divine Sweet and Tasty depending on how many matches were made with only one move. Together with these visual messages there is a voice saying them out loud in order to compliment and motivate the player and as a result adding more feeling to the game. The same thing happens when completing a level there is a voice and a message saying Sugar crush in order to make the player feel like a good player.

Music is constantly played while displaying the virtual landscape as well as when showing the game board. There can in some implementations be different music playing in a level compared to when viewing the virtual landscape.

Candy Crush Saga has implemented a background music that creates a state of mind of the player that is desirable to optimize engagement virality and monetization.

Weird and jarring descending passages in an unusual mode creates a slightly unpleasant and jittery feeling after the contrasting happy swinging jolly music of the game play subconsciously makes the player speed up and get onto the next gameplay screen where normal tonality and harmony resume 

The system and method described herein can be implemented together with a game in which players can see their own and also their social network friends game level position on a virtual path or other virtual world and in which game state information is fully synchronised across different platforms such as iOS desktop and Android via Facebook or other online social network so that a player can seamlessly stop and re start playing the game on any of those different platforms.

Some implementations of the game allows for the game to be synchronised between different devices or platforms.

The game can for instance be played in an offline mode on a handheld device using locally stored information on the handheld device. The device can store all or some of the levels that are available for the player to play in the game. Some of the features in the game can be locally run on the device and dependent on the local machine. This can for instance be that if the game is implemented to regenerate lives after a certain period of time then the time can be locally decided based on the clock on the device. In some implementations the central game server clock can override the local clock when the local device has been synchronised with the server.

A game can be implemented so that the player knows if it has synchronised the available data with the central server or servers. This can for instance be through a coloured symbol or a check mark that indicates that the information is up to date.

The game can also indicate if it has been able to establish a connection with the central server for synchronisation or if for instance the network connection is down. That the device is offline can for instance be illustrated with a greyed out icon.

The game can be implemented to synchronize game state information and or retrieve and connect to the social graph information and user profile of the player on a social network such as Facebook or Google .

The game can also be implemented so that it is connected to a plurality of social networks. The user can be given the option to select what information that can be derived and shared with which social network.

One example of how the game can be connected to a social network is the Facebook s Open Graph API allows websites and applications to draw and share information about more objects than simply people including photos events and pages and their relationships between each other. This expands the social graph concept to more than just relationships between individuals and instead applies it to virtual non human objects between individuals as well. A game can typically share in game events such as that a level has been completed that a player has passed a friend in the game or beaten a friend s high score on a level. The game can also post event such as that a player has purchased objects in the game or received objects from other players of the game.

There are six different game elements candies . They can be combined in series of 3 4 or 5 in a line either row or a column in a 2 2 square or in combinations in the shape of a T or L form.

The game elements have certain sizes all similar but not identical making it possible to have a specific maximum number of rows and columns with candies.

The game board is dark semi transparent and placed on top of a background picture which is tied to the story of the game.

In the game board each element has a square space that is delimited by light horizontal lines and darker vertical lines. The lines do not cover the full square but leave a gap in all the corners.

New special game elements are introduced throughout the game to increase the difficulty. For example a layer which has to be removed by matching a candy covered by the layer Jelly or an impassable block that has to be removed by matching candies next to it a number of times Frosting .

Most levels have two separate goals one involving certain actions remove jelly get fruits to the bottom and another related to score. This makes for a more challenging game.

The player is awarded points for each combination of at least 3 candies enabling high score comparisons with other players as well as a challenge to beat oneself.

The amount of points gained by a combination is shown upon completing a combination in the same colour as the candies used in the combination.

The score given for different combinations is not linear but formed in a way to encourage longer combinations and a more thought out approach of playing the game.

Give Bonus Points in the Form of Certain Schemes to Player when Finishing a Level Sooner than Necessary

When a player finishes with moves left bonus points are awarded. These bonus points may be awarded by i triggering any remaining special elements on the gameboard and ii randomly placing special game elements on the board and then triggering them.

There is a booster that removes three columns by turning three candies into striped candies. This booster is in the form of a coconut wheel.

By making certain combinations of candies special game elements will be produced. These are formed by making combinations of 4 candies in a row or column striped candy candies in a 2 2 grid fish 5 candies in a row or column colour bomb L or T shapes of 5 candies bomb candy .

A colour bomb candy will be produced by combining 5 candies in a row or column. This item will either remove all candies of a certain colour if combined with a regular candy or it will remove all elements on the gameboard if combined with a bomb candy or it will transform all candies of the same colour into striped candies that subsequently trigger if combined with a striped candy .

By combining 5 or 6 candies into a L shape or a T shape a bomb candy will be produced. This removes elements in a rectangle shape with a three candy diameter.

It is possible to combine striped candies when doing so one column and one row of candies will be removed.

It is possible to combine a striped candy with a bomb candy when doing so three columns and three rows of candies will be removed originating from the spot where the combination was made.

It is possible to combine two bomb candies with each other. When doing so a rectangle shape with a diameter of 5 candies will be removed by each combined bomb candy.

When combining a striped candy with a bomb candy a special visual animation is triggered in the form of a giant candy moving first horizontally in both directions from the point of origin then vertically.

When combining a colour bomb with a striped candy all other candies of that colour will also be transformed into striped game elements that automatically trigger.

The player progresses through the levels of the game which is visually represented on a map. This gives the player a more tangible way of seeing progress than if levels were just represented by a number.

The highest level reached by a player is indicated by the corresponding node being highlighted orange. This makes it easy for the player to find the current level and also facilitates the visualization of how far he has progressed.

All available levels in Candy Crush can be viewed in the map even though they haven t been unlocked. However a padlock symbol is shown to represent that a level is yet to be unlocked and that it currently cannot be played.

At the start of Candy Crush the player is greeted by an encouraging message Your adventure starts today Click here to play level 2 

Candy Crush offers a tutorial in the beginning of the game to introduce the player to new concepts. Basic concepts possible combinations and the different game modes are explained among other things.

Different game modes makes for a more diverse game. Candy Crush offers at least seven different game modes Score Jelly Ingredients Orders Time Jelly Bear and Lemonade.

There are game elements in Candy Crush that have to be removed before objects can pass through the space they occupy. These are in the form of frosting blocks and require candies to be matched next to them a certain amount of times before they disappear.

When selecting a level from the map view information about the level is displayed together with an array of boosters that can be purchased and or activated for that level. Information include previous scores of friends and specific instructions for the current level.

The previous high score of friends can be seen before playing a level while playing a level and after a level has been played provided that friends have played the level before . This increases competition and gives a sense of community at the same time.

The player can select boosters before playing a level as well as during the play of a level. The boosters which can be used in the two situations differ. This facilitates and adds more depth to the game.

After finishing a level the player will get feedback to how his score relates to that of friends playing the game. An option is given to share results with friends possibly accompanied by a message saying something along the lines of I beat your score .

The player is provided real time feedback in relation to the score during play of a level. This is done by a meter being filled the meter having three different levels represented by one two and three stars respectively.

In the map view the player can see results of previously completed levels in the form of how many stars were attained in those levels. This makes for an easy overview of the overall performance in the game.

The player starts with 5 lives that are used up when failing to complete a level. These lives are then replenished with one life every 30 minutes.

Candy Crush very quickly recognizes when there are no possible moves left. When that occurs the candies on the game board are re shuffled. When re shuffling there will be no combinations automatically triggering i.e. 3 or more candies are not placed adjacent to each other.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path in which the game is fully sync d across different platforms such as iOS desktop and Android via Facebook and in which the gameplay for each level can be enhanced through the use of an acquired item.

A match 3 switcher game in which players can see their own and their social network friends game level position on a virtual path and in which the game board contains switchable elements that can be matched with other switchable elements and switchable elements that cannot be matched with other switchable elements on the game board where one of the goals for completing a level is to interact with the game board in such a way that a predefined number of non matchable switchable elements are placed in any of a plurality of predefined areas on the game board.

A match 3 game in which the player has to satisfy a plurality of criteria within a limited number of moves to complete the level the criteria include at least one of the following 

