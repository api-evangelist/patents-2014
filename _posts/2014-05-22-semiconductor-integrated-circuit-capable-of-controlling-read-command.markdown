---

title: Semiconductor integrated circuit capable of controlling read command
abstract: The semiconductor integrated circuit includes a command decoder, a shift register unit and a command address latch unit. The command decoder is responsive to an external command defining write and read modes and configured to provide a write command or a read command according to the external command using a rising or falling clock. The shift register unit is configured to shift an external address and the write command by a write latency in response to the write command. The column address latch unit is configured to latch and provide the external address as a column address in the read mode, and to latch a write address, which is provided from the shift register unit, and provide the write address as the column address in the write mode.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09281035&OS=09281035&RS=09281035
owner: SK HYNIX INC.
number: 09281035
owner_city: Gyeonggi-do
owner_country: KR
publication_date: 20140522
---
The present application claims priority under 35 U.S.C. 119 a to Korean application number 10 2008 0130991 filed on Dec. 22 2008 in the Korean Patent Office which is incorporated by reference in its entirety as if set forth in full.

Embodiments described herein relate generally to a semiconductor integrated circuit and more particularly to a semiconductor integrated circuit capable of controlling a read command.

Typically a semiconductor integrated circuit operates by synchronizing a command signal and an address with the rising edge of a clock. The trend towards an increase in data bandwidth has a tradeoff in that the number of pins required by the semiconductor integrated circuit is increased. Since a reduced number of pins can be considered beneficial techniques for achieving such results have been considered.

For example the use of a multiplexing scheme for the pins has been considered. In this scheme multi addressing can be performed relative to one address pin using rising and falling edges of a clock. For example the address pin is used as a first address at the rising edge of the clock and if the address pin is synchronized with the falling edge of the clock the address pin can be used as a tenth address. In this way the requisite number of pins can be partially reduced.

However a semiconductor integrated circuit typically starts a read or write operation at a subsequent rising edge occurring after multi addressing is performed twice after an external read or write command is applied to the semiconductor integrated circuit. Thus an address access time tAA may be increased in a scheme for reducing the number of requisite pins.

Embodiments of the present invention include a semiconductor integrated circuit capable of improving an address access time tAA .

According to one embodiment a semiconductor integrated circuit includes a command decoder configured to provide a write or read command using a rising or falling clock in response to an external command that defines write and read modes a shift register unit configured to shift an external address and the write command by a write latency in response to the write command and a column address latch unit configured to latch the external address as a column address in the read mode and latch a write address which is provided from the shift register unit to provide the write address as the column address in the write mode.

According to another embodiment a semiconductor integrated circuit which performs multiplexing using rising and falling clocks through one address pin includes a command decoder configured to provide a first write command and a read command by synchronizing the first write command and the read command with the rising and falling clocks in response to an external command a shift register unit configured to shift an external address and the write command by a write latency in response to the write command thereby providing a write address and a second write command a burst command controller configured to provide a burst read write command which indicates an additional write or read operation and a burst address which corresponds to the burst read write command in response to the first write command the read command and a burst length if a predetermined burst length is exceeded and a column address latch unit configured to latch the external address as a column address in the read mode provide the write address as the column address by latching the write address in the write mode and latch the burst address as the column address in response to the burst read write command.

According to further another embodiment a semiconductor integrated circuit includes a command decoder configured to provide a write command and a read command a read write command controller configured to provide a write read clock in synchronization with a first edge of a clock in response to the write read command and provide the write read clock in synchronization with a second edge of the clock in response to the read command and a column address latch unit configured to latch the external address as a column address in response to the read command and provide the column address by latching the write address which is provided from a shift register unit in response to the write read command.

According to still another embodiment a semiconductor integrated circuit includes a command decoder configured to provide a read command in synchronization with a first edge of a clock a read write command controller configured to provide a read clock in synchronization with a second edge of the clock in response to the read command and a column address latch unit configured to latch an external address in response to the read command and provide a column address in synchronization with the second edge of the clock.

These and other features aspects and embodiments are described below in the section entitled Detailed Description. 

Referring to in an embodiment of the present invention the semiconductor integrated circuit includes first and second pad sections and each having a plurality of pads a memory area A having a plurality of banks and a peripheral circuit area B formed at a periphery of the memory area A .

External signals are applied to the semiconductor integrated circuit through the pads of the first and second pad sections and and internal signals of the semiconductor integrated circuit are transmitted to the outside through the pads.

The number and arrangement of the banks of the memory area A may vary depending on the configuration and or degree of integration of the semiconductor integrated circuit.

In an embodiment the peripheral circuit area B includes the command controller . The command controller controls the memory area A . In an embodiment the command controller provides a write command in synchronization with a rising clock and a read command in synchronization with a falling clock. Hereinafter the command controller will be described in detail with reference to the accompanying drawings.

Referring to in an embodiment the command controller includes a command decoder a shift register unit a column address latch unit and a burst command controller .

The command decoder provides a first write command EWT and a read command RD which correspond to a rising clock RCLK or a falling clock FCLK in response to an external command CMD and a chip select signal CSB . For example if the external command CMD is received and defines a write mode the command decoder provides the first write command EWT synchronized with the rising clock RCLK . If the external command CMD is received and defines a read mode the command decoder provides the read command RD synchronized to the falling clock FCLK . Thus as described above according to an embodiment of the present invention the read command RD and the first write command EWT can be provided in synchronization with each edge of a clock the rising and falling edges corresponding to the rising clock and the falling clock according to the external command CMD . In more detail the rising clock RCLK denotes a clock generated in synchronization with the rising edge of the clock. Further the falling clock FCLK denotes a clock generated in synchronization with the falling edge of the clock. Since generating rising and falling clocks from a clock signal is generally known in the art a detailed description about the generation scheme thereof will be omitted.

In an embodiment the shift register unit includes a column address shift register and a command shift register .

The column address shift register provides a write address WT ADD which is delayed by a write latency WL in response to an external address ADD the first write command EWT the rising clock RCLK and the write latency WL .

Further the command shift register is configured to provide a second write command WT which is delayed by the write latency WL in response to the first write command EWT the rising clock RCLK and the write latency WL .

In other words the semiconductor integrated circuit starts a write operation with an internal write command which satisfies a predetermined time requirement necessary for an actual write operation in response to the first write command EWT which represents the write mode. Thus the shift register unit synchronizes the external address ADD and the first write command EWT with the rising clock RCLK and delays by the write latency WL thereby providing the write command WT and the write address WT ADD which are necessary for the actual write operation.

In an embodiment the burst command controller includes a column command generator a read write command controller a burst command generator and a burst address counter .

The column command generator provides a write read command WTRDB in response to the first write command EWT the read command RD and a reset signal RESET . Thus it is possible to determine whether the signal corresponds to the read command RD or the first write command EWT based on a level e.g. a logic level of the write read command WTRDB .

The read write command controller provides a write read clock WTRD CLK and a burst signal BURST in response to the second write command WT the read command RD the rising clock RCLK the falling clock FCLK the reset signal REST and burst length BL . The read write command controller is configured to provide the rising clock RCLK as the write read clock WTRD CLK in response to the second write command WT or provide the falling clock FCLK as the write read clock WTRD CLK in response to the read command RD . Further the read write command controller can be configured to provide the burst signal BURST in response to the burst length BL provided from an MRS mode register set . For example the burst length BL may be set as 4 8 or 16. For the purpose of illustration the burst length BL is set to 4.

In an embodiment the burst command generator provides a burst read write command BURST WTRD in response to the write read command WTRDB the write read clock WTRD CLK and the burst signal BURST . That is either a read mode or a write mode is performed and the selection of read mode write mode is based on the level e.g. voltage level of the write read command WTRDB . When the base burst length BL is set to 4 as described above the burst signal BURST is generated once. If the burst length BL is 8 the burst signal BURST is generated twice. If the burst length BL is 16 the burst signal BURST is generated four times. Thus if the burst length BL is 16 the read command RD or the write command WT must be provided once and an additional read command must be provided three times. In this regard a command including additional read information corresponds to the burst read write command BURST WTRD . The relationship between the second write command WT and the burst read write command BURST WTRD can be explained in the same manner as described above. However it should be understood that the above description is for explaining but not limited to a read or write operation when the burst length BL is set to 4.

In an embodiment the burst address counter is configured to provide a burst address BURST ADD in response to the read command RD the second write command WT the burst read write command BURST WTRD the burst length BL and a column address YADD . In detail when providing the burst address BURST ADD in response to the burst read write command BURST WTRD the burst address counter counts from and increments the column address YADD which is latched in response to the read command RD or the second write command WT to the burst length BL and then provides the burst address BURST ADD .

In an embodiment the column address latch unit is configured to provide the column address YADD in response to the second write command WT the read command RD the burst read write command BURST WTRD the write address WT ADD the external address ADD and the burst address BURST ADD . In detail the column address latch unit provides the write address WT ADD to the memory area A as the column address YADD in response to the second write command WT provides the external address ADD to the memory area A as the column address YADD in response to the read command RD and provide the burst address BURST ADD to the memory area A as the column address YADD in response to the burst read write command BURST WTRD . According to one embodiment in the case of the read command RD the column address YADD is provided in synchronization with the falling clock FCLK . Further a read related operation of the burst read write command BURST WTRD can also be provided in synchronization with the falling clock FCLK .

Referring to the command decoder according to an embodiment includes first and second NAND gates ND and ND and first and second inverters IV and IV.

The first NAND gate ND is connected in series to the first inverter IV and performs a NAND logical operation on the rising clock RCLK and the external command CMD .

The second NAND gate ND is connected in series to the second inverter IV and performs a NAND logical operation on the falling clock FCLK and the external command CMD .

If the external command CMD is a write mode command the command decoder provides the first write command EWT synchronized with the rising clock RCLK . If the external command CMD is a read mode command the command decoder provides the read command RD synchronized with the falling clock FCLK . In an embodiment the command decoder can divide edges of the synchronization clock into falling and rising edges according to the read command RD and the first write command EWT .

Referring to the command shift register of the shift register unit includes a plurality of transmitters for the purpose of illustration first to fourth transmitters T to T and a first latency activation unit .

In an embodiment each of the first to fourth transmitters T to T includes a transfer gate TR and a latch unit L.

The first transmitter T transmits the first write command EWT in synchronization with a rising edge of the rising clock RCLK . The transfer gate TR is turned on when the level of the rising clock RCLK is a high level. The latch unit L latches the signal output by the transfer gate TR.

The second transmitter T is configured to transmit the signal from the first transmitter T in synchronization with a falling edge of the rising clock RCLK . As shown in the configuration of the transfer gate TR is such that the transfer gate is turned on when the rising clock RCLK is a low level. The latch unit L latches the signal output by the transfer gate TR. The third and fourth transmitters T and T operate in a manner similar to that of the first and second transmitters T and T.

Accordingly the first to fourth transmitters T to T are alternately turned on off in response to the rising clock RCLK . Thus a signal transmission time after turn on of the first and third transmitters T and T or the second and fourth transmitters T and T is delayed by one clock period corresponding to each pair of a turned on and turned off transmitter of the transmitters T to T.

In an embodiment the first latency activation unit is configured to provide output signals of the first to fourth transmitters T to T as the second write command WT in response to the write latency WL of the semiconductor integrated circuit. The first latency activation unit includes pass gates PASS and inverters INV and INV which receive the write latency WL respectively.

The operation of the first latency activation unit will now be described. If the write latency WL is 1 the first write latency WL is at an activated level for example in the activated level is a high level. Thus the pass gate PASS which receives the first activated write latency WL is turned on so that the output signal of the second transmitter T can be provided as the second write command WT . That is time transmission time is delayed by one clock period through the first and second transmitters T and T or the third and fourth transmitters T and T and therefore when the configuration of is used an address signal delayed by one clock period can be provided when the write latency WL is 1.

In an embodiment the column address shift register includes first to fourth transmitters T to T a write command receiver and a second latency activation unit .

Since the configuration and operation principle of the column address shift register is substantially identical to that of the command shift register a detailed description thereof will be omitted in order to avoid redundancy. Briefly the column address shift register receives the external address ADD in order to provide the write address WT ADD by delaying the external address ADD by the write latency WL . In order to operate in response to the first write command EWT the column address shift register further includes the write command receiver .

In an embodiment the write command receiver includes an inverter INVi and a transfer gate TR to transmit the external address ADD in response to an activated level of the first write command EWT .

Referring to in an embodiment the column command generator includes a first PMOS transistor P first and second NMOS transistors N and N and a latch unit L.

The first PMOS transistor P includes a gate terminal which receives an inverted first write command EWT obtained by passing the first write command EWT through a first inverter INV a source terminal which receives a supply voltage VDD and a drain terminal connected to node a .

In an embodiment the first NMOS transistor N includes a gate terminal which receives the read command RD a source terminal connected to a ground voltage VSS and a drain terminal connected to node a .

In an embodiment the second NMOS transistor N includes a gate terminal which receives the reset signal RESET a source terminal connected to the ground voltage VSS and a drain terminal connected to node a . The activated reset signal RESET is applied to the gate terminal of the second NMOS transistor N in order that node a can be initialized.

In an embodiment the latch unit L includes second and third inverters INV and INV which are connected to each other in a latch type configuration.

When the first write command EWT is activated i.e. enabled so as to be a high level and applied to the column command generator the first PMOS transistor P is turned on since the high level signal is inverted by the first inverter INV and applied to the gate terminal of the first PMOS transistor and node a is therefore at a high level. In this case the signal of node a is latched by the latch unit L and provided to a fourth inverter INV and therefore a high level write read command is output by the column command generator.

When the read command RD is activated i.e. enabled so as to be a high level and applied to the column command generator the first NMOS transistor N is turned on since the high level signal is applied to the gate terminal of the NMOS transistor N and node a therefore at a low level. In this case the signal of node a is latched by the latch unit L and provided to the fourth inverter INV and therefore a low level write read command is output by the column command generator.

Accordingly in the just described embodiment in which the respective first write command and read command are activated at a high level the high level of the write read command WTRDB represents activation of the first write command EWT and the low level of the write read command WTRDB represents activation of the read command RD . Thus the write mode can be distinguished from the read mode based on the level of the write read command WTRDB .

Referring to in an embodiment the read write command controller includes a clock selector and a burst signal generator .

The clock selector selects either the rising clock RCLK or the falling clock FCLK in response to the write read command WTRDB in order to provide the write read clock.

Referring to in an embodiment the clock selector includes a rising clock selection unit and a falling clock selection unit

In an embodiment the rising clock selection unit includes first and second PMOS transistors P and P and first and second NMOS transistors N and N which are connected in series. The rising clock selection unit is a clocked inverter which is responsive to the write read command WTRDB and provides the rising clock RCLK to node d when the write read command WTRDB is at the high level i.e. high logic level .

In an embodiment the falling clock selection unit includes third and fourth PMOS transistors P and P and third and fourth NMOS transistors N and N which are connected in series. The falling clock selection unit is a clocked inverter which is also responsive to the write read command WTRDB . The falling clock selection unit provides the falling clock FCLK to node d when the write read command WTRDB is at the low level i.e. low logic level .

In detail in the case in which the device is in the write mode the clock selector provides the rising clock RCLK as the write read clock WTRD CLK as the level of the write read command WTRDB represents the activation of the first write command EWT . In the case in which the device is in the read mode the clock selector provides the falling clock FCLK as the write read clock WTRD CLK as the level of the write read command WTRDB represents activation of the read command. Accordingly in the just described embodiment each edge i.e. rising and falling edge of the clock can be used to represent the write command or the read command i.e. the write and read commands can be provided in synchronization with rising and falling edges of the clock and the edges of the clock can be used for actual write and read operations.

Referring to in an embodiment the burst signal generator includes a first PMOS transistor P first and second NMOS transistors N and N a plurality of latch units and transfer gates T each corresponding to a latch unit.

The operation principle of the burst signal generator is similar to that of the column address shift register described above with reference to therefore the burst signal generator will be described briefly.

When the second write command WT is activated the burst signal generator generates the burst signal BURST activated and delayed by the burst length BL . Further when the read command RD is activated the burst signal generator generates the burst signal BURST activated and delayed by the burst length BL . The burst signal generator can be initialized by the reset signal RESET .

Further the burst signal generator generates the burst signal BURST delayed by the burst length BL in synchronization with the write read clock WTRD CLK in response to the second activated write command WT . Similar to this the burst signal generator generates the burst signal BURST delayed by the burst length BL in synchronization with the write read clock WTRD CLK in response to the activated read command RD . As described above when the second write command WT is activated the write read clock WTRD CLK corresponds to the rising clock RCLK . Further when the read command RD is activated the write read clock WTRD CLK corresponds to the falling clock FCLK . In the semiconductor integrated circuit according to an embodiment the burst length BL is set to 4 as an initial value. However as described above the burst length BL is not limited to this initial value.

For example if the burst length BL is 4 the burst signal BURST which is divided by 4 clock periods is activated by the burst signal generator in response to the second write command WT or the read command RD . If the burst length BL is 8 a counter pulse can be generated twice by the divide by 4 circuit so that the burst signal BURST activated after being delayed by the 4 clock periods can be activated twice. As described above when the burst length BL exceeds 4 an internal read write command signal is required to additionally provide the read or write command.

Although not shown in the drawings similar to the command decoder shown in in an embodiment the burst command generator provides the burst read write command BURST WTRD by a NAND logical operation performed on the burst signal BURST the write read clock WTRD CLK and the write read command WTRDB . Thus the burst command generator provides an additional write or read command synchronized with the write read clock WTRD CLK whenever the burst signal BURST is activated.

Further when an additional internal command is required according to the write read command WTRDB and the burst length BL the burst address counter in can count the column address YADD latched in response to the second write command WT or the read command RD while increasing the column address YADD thereby providing the burst address BURST ADD . In detail if the burst length BL exceeds 4 the burst address counter receives the column address YADD latched in response to the second write command WT or the read command RD and counts the column address YADD while increasing the column address YADD . At this time an address increment mode may include an interleaving mode or a sequential mode according to the configuration or characteristics of the circuit.

According to an embodiment the burst read write command BURST WTRD is provided in synchronization with either the rising or falling edge of the clock according to which of the read or write modes the device is in. However the scope of the disclosure is not limited thereto. That is the burst read write command BURST WTRD or burst address BURST ADD scheme may be omitted according to the configuration or characteristics of the semiconductor integrated circuit.

Referring to in an embodiment the column address latch unit includes first to third address latch units and and a latch section .

In an embodiment the first address latch unit provides the external address ADD as the column address YADD in response to the read command RD .

The first address latch unit shown in is a clocked inverter that is responsive to the read command RD and includes first and second PMOS transistors P and P and first and second NMOS transistors N and N which are connected in series.

The second address latch unit shown in provides the write address WT ADD as the column address YADD in response to the second write command WT .

The second address latch unit is a clocked inverter that is responsive to the second write command WT and includes third and fourth PMOS transistors P and P and third and fourth NMOS transistors N and N which are connected in series.

The third address latch unit shown in provides the burst address BURST ADD as the column address YADD in response to the burst read write command BURST WTRD .

The third address latch unit is a clocked inverter that is responsive to the burst read write command BURST WTRD and includes fifth and sixth PMOS transistors P and P and fifth and sixth NMOS transistors N and N which are connected in series.

In an embodiment the first to third address latch units share an output node e connected to the input of the latch section . The latch section is configured to provide the column address YADD by inverting and latching the signal of node e .

The operation of the column address latch unit will now be described. When the read command RD is activated the first PMOS transistor P and the second NMOS transistor N are turned on so the address ADD is provided to node e . When the second write command WT is activated the third PMOS transistor P and the fourth NMOS transistor N are turned on so the write address WT ADD is provided to node e . Similarly when the burst read write command BURST WTRD is activated the fifth PMOS transistor P and the sixth NMOS transistor N are turned on so the burst address BURST ADD is provided to node e .

As described above according to the commands the column address latch unit can selectively provide an address to which delay is applied an external address and an address that is further counted in addition to the basic burst length BL .

Referring to the external command CMD is provided in synchronization with the rising edge of a clock CLK . Further the external address ADD is provided and is addressed to the rising and falling edges of the clock CLK with which the external command CMD is synchronized.

According to the related art the read command RD is provided in synchronization with the rising edge of the clock CLK after the addressing has been performed relative to the address ADD addressed to the falling edge of the clock CLK see dotted lines circle around a .

However according to an embodiment of the present invention when the address ADD is addressed to the falling edge of the clock CLK the read command RD can operate in synchronization with the falling edge of the clock CLK see solid lines circle around b . Thus the tAA can be earlier by a predetermined time t e.g. about tCK.

That is when addressing is performed using the rising and falling edges the write command is a synchronous command which must follow predefined timing regulations such as write latency. However in the read mode a non synchronous command path exists until a predetermined cell is accessed after the read command is activated. Thus the read command RD is provided in synchronization with the falling clock FCLK at which the address is received other than the rising clock RCLK such that the tAA is earlier by the tCK whereby the tAA provided to the memory area A see can be improved.

Accordingly in the embodiments of the present invention described above the read command can be provided using the falling edge of the clock or the falling clock so that the speed of the read operation can be improved.

While certain embodiments have been described above it will be understood that the embodiments described are by way of example only. Accordingly the systems and methods described herein should not be limited based on the described embodiments. Rather the systems and methods described herein should only be limited in light of the claims that follow when taken in conjunction with the above description and accompanying drawings.

