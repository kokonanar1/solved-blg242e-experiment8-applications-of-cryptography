Download Link: https://assignmentchef.com/product/solved-blg242e-experiment8-applications-of-cryptography
<br>
Secure communication is one of the essential needs of today. People need security and privacy in their communications. Cryptography provides many techniques and methods for secure communication. Although cryptography was utilized especially in the military field in the past, it is possible to come across its applications in almost all technological devices today.

In this experiment, three important cryptography applications in the history of cryptography will be implemented as digital designs. First, the implementation of Caesar Cipher, named after the Roman Republic general and dictator Julius Caesar, will be implemented. Caesar Cipher was one of the first examples of cryptography in history. Julius Caesar used this encryption technique to communicate with his generals during the war [1].

The second technique will be the implementation of the Vigen`ere Cipher used by the Confederate Army. Unlike the Caesar Cipher, the Vigen`ere Cipher encrypts messages using a key. Both parties, the sender and the receiver, must have the same key for conducting the communication [2].

Finally, the implementation of the Enigma machine used by the German Army in the World War 2 and a sample communication environment will be realized. The Enigma machine was used to encrypt and decrypt secret messages. According to experts, the defeat of the German Army was accelerated by 2 years thanks to the work of the Ultra group, which deciphered the Enigma and other encryption machines [3].

<strong>You can use any operator/code block in this experiment. You must simulate all parts and modules.</strong>

<h2>2 Part 1: Helper Modules</h2>

In this part you will design 4 helper modules. Detailed information is given below.

<ul>

 <li><strong>CharDecoder Module: </strong>Transform A-Z chars to binary decoded version.</li>

</ul>

Ex: ‘A’ → h0000001, ‘Z’ → h2000000, ‘T’ → h0080000

<ul>

 <li><strong>char (8-bit input)</strong>: ASCII code of the character.</li>

 <li><strong>decodedChar (26-bit output)</strong>: Decoded output of the character.</li>

</ul>

<ul>

 <li><strong>CharEncoder Module: </strong>Transform binary decoded version of the char to ASCII code for A-Z char.</li>

</ul>

Ex: h0000020 → ‘F’, h0000400 → ‘K’, h0020000 → ‘R’

<ul>

 <li><strong>decodedChar (26-bit input)</strong>: Decoded input of the character.</li>

 <li><strong>char (8-bit output)</strong>: ASCII code of the character.</li>

</ul>

<ul>

 <li><strong>CircularRightShift Module: </strong>Right Shift Module with shift count.

  <ul>

   <li><strong>data (26-bit input)</strong>: Input data.</li>

   <li><strong>shiftAmount (5-bit input)</strong>: Shift amount.</li>

   <li><strong>out (26-bit output)</strong>: Data shifted to the right ‘shiftAmount’ times.</li>

  </ul></li>

 <li><strong>CircularLeftShift Module: </strong>Left Shift Module with shift count.

  <ul>

   <li><strong>data (26-bit input)</strong>: Input Data.</li>

   <li><strong>shiftAmount (5-bit input)</strong>: Shift amount.</li>

   <li><strong>out (26-bit output)</strong>: Data shifted to the left ‘shiftAmount’ times.</li>

  </ul></li>

</ul>

<h2>3 Part 2: Caesar Cipher</h2>

In this part, you are required to implement Caesar Cipher Encryption and Decryption modules. Then you’ll create a Caesar Module to show encrypted and decrypted messages. Figure 1 shows the encryption technique of Caesar Cipher when the shift count is 3.

Example inputs and outputs of the encryption module are ‘A’ → ‘D’, ‘F’ → ‘I’, and ‘X’ → ‘A’. For the decryption module, ‘E’ → ‘B’, ‘H’ → ‘E’, ‘J’ → ‘G’, etc. Required modules and their information are given below.

<ul>

 <li><strong>CaesarEncryption Module: </strong>Encrypt the char using Caesar Cipher technique.

  <ul>

   <li><strong>plainChar (8-bit input)</strong>: ASCII code of the input character.</li>

   <li><strong>shiftCount (5-bit input)</strong>: Shift amount of the cipher.</li>

   <li><strong>chipherChar (8-bit output)</strong>: The character which is encrypted using Caesar Cipher with shiftCount.</li>

  </ul></li>

</ul>

Figure 1: Caesar Encryption

<ul>

 <li><strong>CaesarDecryption Module: </strong>Decrypt the encrypted char using Caesar Cipher technique.

  <ul>

   <li><strong>chipherChar (8-bit input)</strong>: Encrypted char input.</li>

   <li><strong>shiftCount (5-bit input)</strong>: Shift amount of the cipher.</li>

   <li><strong>decryptedChar (8-bit output)</strong>: The character which is decrypted using Caesar Cipher with shiftCount.</li>

  </ul></li>

 <li><strong>CaesarEnvironment Module: </strong>Encryption and decryption processes of a plain char. Figure 2 shows the block scheme of the CaesarEnvironment Module.

  <ul>

   <li><strong>plainChar (8-bit input)</strong>: ASCII code of the input character.</li>

   <li><strong>shiftCount (5-bit input)</strong>: Shift amount of the cipher.</li>

   <li><strong>chipherChar (8-bit output)</strong>: The character which is encrypted using Caesar Cipher with shiftCount.</li>

   <li><strong>decryptedChar (8-bit output)</strong>: The character which is decrypted using Caesar Cipher with shiftCount.</li>

  </ul></li>

</ul>

<strong>Hint: </strong>You can use helper modules for encryption and decryption operations.

Figure 2: Caesar Encryption and Decryption Process

<h2>4 Part 3: Vigen`ere Cipher</h2>

In this part, you are requested to implement the Vigen`ere Cipher Encryption and Decryption modules. Then, you will create a Vigen`ere Module to show encrypted and decrypted messages. Vigen`ere Cipher uses the same key message for encryption and decryption processes. Equation 1 and Equation 2 show encryption and decryption calculations of the Vigen`ere Cipher, respectively. Table 1 shows an example for the encryption and decryption calculations of the Vigen`ere Cipher whose key message is ”KADIROZLEM” and the plain text is ”ISTANBULTECHNICAL”.

<em>C<sub>i </sub></em>= (<em>P<sub>i </sub></em>+ <em>K<sub>i</sub></em>) <em>mod </em>26                                                                     (1)

where <em>C<sub>i </sub></em>is the cipher char, <em>P<sub>i </sub></em>is the plain char, and <em>K<sub>i </sub></em>is the key char.

<em>D<sub>i </sub></em>= (<em>C<sub>i </sub></em>−<em>K<sub>i</sub></em>) <em>mod </em>26                                                                     (2)

where <em>D<sub>i </sub></em>is the decrypted char, <em>C<sub>i </sub></em>is the cipher char, and <em>K<sub>i </sub></em>is the key char.

Table 1: Example Calculation of Vigen`ere Cipher

<table width="573">

 <tbody>

  <tr>

   <td width="30"><em>i</em></td>

   <td width="96"><strong>Plain Char</strong></td>

   <td width="88"><strong>Key Char</strong></td>

   <td width="30"><em>P<sub>i</sub></em></td>

   <td width="33"><em>K<sub>i</sub></em></td>

   <td width="31"><em>C<sub>i</sub></em></td>

   <td width="108"><strong>Cipher Char</strong></td>

   <td width="32"><em>D<sub>i</sub></em></td>

   <td width="125"><strong>Decryted Char</strong></td>

  </tr>

  <tr>

   <td width="30">0</td>

   <td width="96">I</td>

   <td width="88">K</td>

   <td width="30">8</td>

   <td width="33">10</td>

   <td width="31">18</td>

   <td width="108">S</td>

   <td width="32">8</td>

   <td width="125">I</td>

  </tr>

  <tr>

   <td width="30">1</td>

   <td width="96">S</td>

   <td width="88">A</td>

   <td width="30">18</td>

   <td width="33">0</td>

   <td width="31">18</td>

   <td width="108">S</td>

   <td width="32">18</td>

   <td width="125">S</td>

  </tr>

  <tr>

   <td width="30">2</td>

   <td width="96">T</td>

   <td width="88">D</td>

   <td width="30">19</td>

   <td width="33">3</td>

   <td width="31">22</td>

   <td width="108">W</td>

   <td width="32">19</td>

   <td width="125">T</td>

  </tr>

  <tr>

   <td width="30">3</td>

   <td width="96">A</td>

   <td width="88">I</td>

   <td width="30">0</td>

   <td width="33">8</td>

   <td width="31">8</td>

   <td width="108">I</td>

   <td width="32">0</td>

   <td width="125">A</td>

  </tr>

  <tr>

   <td width="30">4</td>

   <td width="96">N</td>

   <td width="88">R</td>

   <td width="30">13</td>

   <td width="33">17</td>

   <td width="31">4</td>

   <td width="108">E</td>

   <td width="32">13</td>

   <td width="125">N</td>

  </tr>

  <tr>

   <td width="30">5</td>

   <td width="96">B</td>

   <td width="88">O</td>

   <td width="30">1</td>

   <td width="33">14</td>

   <td width="31">15</td>

   <td width="108">P</td>

   <td width="32">1</td>

   <td width="125">B</td>

  </tr>

  <tr>

   <td width="30">6</td>

   <td width="96">U</td>

   <td width="88">Z</td>

   <td width="30">20</td>

   <td width="33">25</td>

   <td width="31">19</td>

   <td width="108">T</td>

   <td width="32">20</td>

   <td width="125">U</td>

  </tr>

  <tr>

   <td width="30">7</td>

   <td width="96">L</td>

   <td width="88">L</td>

   <td width="30">11</td>

   <td width="33">11</td>

   <td width="31">22</td>

   <td width="108">W</td>

   <td width="32">11</td>

   <td width="125">L</td>

  </tr>

  <tr>

   <td width="30">8</td>

   <td width="96">T</td>

   <td width="88">E</td>

   <td width="30">19</td>

   <td width="33">4</td>

   <td width="31">23</td>

   <td width="108">X</td>

   <td width="32">19</td>

   <td width="125">T</td>

  </tr>

  <tr>

   <td width="30">9</td>

   <td width="96">E</td>

   <td width="88">M</td>

   <td width="30">4</td>

   <td width="33">12</td>

   <td width="31">16</td>

   <td width="108">Q</td>

   <td width="32">4</td>

   <td width="125">E</td>

  </tr>

  <tr>

   <td width="30">10</td>

   <td width="96">C</td>

   <td width="88">K</td>

   <td width="30">2</td>

   <td width="33">10</td>

   <td width="31">12</td>

   <td width="108">M</td>

   <td width="32">2</td>

   <td width="125">C</td>

  </tr>

  <tr>

   <td width="30">11</td>

   <td width="96">H</td>

   <td width="88">A</td>

   <td width="30">7</td>

   <td width="33">0</td>

   <td width="31">7</td>

   <td width="108">H</td>

   <td width="32">7</td>

   <td width="125">H</td>

  </tr>

  <tr>

   <td width="30">12</td>

   <td width="96">N</td>

   <td width="88">D</td>

   <td width="30">13</td>

   <td width="33">3</td>

   <td width="31">16</td>

   <td width="108">Q</td>

   <td width="32">13</td>

   <td width="125">N</td>

  </tr>

  <tr>

   <td width="30">13</td>

   <td width="96">I</td>

   <td width="88">I</td>

   <td width="30">8</td>

   <td width="33">8</td>

   <td width="31">16</td>

   <td width="108">Q</td>

   <td width="32">8</td>

   <td width="125">I</td>

  </tr>

  <tr>

   <td width="30">14</td>

   <td width="96">C</td>

   <td width="88">R</td>

   <td width="30">2</td>

   <td width="33">17</td>

   <td width="31">19</td>

   <td width="108">T</td>

   <td width="32">2</td>

   <td width="125">C</td>

  </tr>

  <tr>

   <td width="30">…</td>

   <td width="96">…</td>

   <td width="88">…</td>

   <td width="30">…</td>

   <td width="33">…</td>

   <td width="31">…</td>

   <td width="108">…</td>

   <td width="32">…</td>

   <td width="125">…</td>

  </tr>

 </tbody>

</table>

Required modules and their information are given below for Vigen`ere Cipher.

<ul>

 <li><strong>VigenereEncryption Module: </strong>Encrypt the char using Vigen`ere Cipher technique.

  <ul>

   <li><strong>plainChar (8-bit input)</strong>: ASCII code of the input character.</li>

   <li><strong>keyInput (80-bit input)</strong>: Key message of the cipher (10 characters).</li>

   <li><strong>load (1-bit input)</strong>: Load the keyInput to key register at the rising edge of the load signal.</li>

   <li><strong>clock (1-bit input)</strong>: Shift key register only one character at the rising edge of the clock signal (when load = 0).</li>

   <li><strong>chipherChar (8-bit output)</strong>: The character which is encrypted using Vigen`ere Cipher.</li>

  </ul></li>

 <li><strong>VigenereDecryption Module: </strong>Decrypt the encrypted char using Vigen`ere Cipher technique.

  <ul>

   <li><strong>chipherChar (8-bit input)</strong>: Encrypted char input.</li>

   <li><strong>keyInput (80-bit input)</strong>: Key message of the cipher (10 characters).</li>

   <li><strong>load (1-bit input)</strong>: Load the keyInput to key register at the rising edge of the load signal.</li>

   <li><strong>clock (1-bit input)</strong>: Shift key register only one character at the rising edge of the clock signal (when load = 0).</li>

   <li><strong>decryptedChar (8-bit output)</strong>: The character which is decrypted using Vigen`ere Cipher.</li>

  </ul></li>

 <li><strong>VigenereEnvironment Module: </strong>Encryption and decryption processes of the plain char. Figure 3 shows the block scheme of the VigenereEnvironment Module.

  <ul>

   <li><strong>plainChar (8-bit input)</strong>: ASCII code of the input character.</li>

   <li><strong>keyInput (80-bit input)</strong>: Key message of the cipher.</li>

   <li><strong>load (1-bit input)</strong>: Load signal of modules.</li>

   <li><strong>clock (1-bit input)</strong>: Clock signal of modules.</li>

   <li><strong>chipherChar (8-bit output)</strong>: The character which is encrypted using Vigen`ere Cipher.</li>

   <li><strong>decryptedChar (8-bit output)</strong>: The character which is decrypted using Vigen`ere Cipher.</li>

  </ul></li>

</ul>

Figure 3: Vigen`ere Encryption and Decryption Process

<h2>5 Part 4: Enigma Machine</h2>

In this part, you are request to implement the Enigma machine. The Enigma machine can both encrypt and decrypt a message. For secure communication, receiver and transmitter must have Enigma machines which are configured and initiated identically. The rotors in the Enigma machine rotate every time a new input character is given and this rotation changes the configuration of the machine entirely. This way, a character is decrypted differently every time it is given as an input. Figure 4 shows an example character generation. Plugboard, Rotor1, Rotor2, and Rotor3 get 26-bit inputs and change the orders of the bits for output.

Figure 4: Enigma Machine Character Generation

Rotors rotate according to the clock signal. Rotor1 (fast rotor) rotates one bit at each clock cycle, Rotor2 (normal rotor) rotates one bit for every 26 clock cycles, and Rotor3 (slow rotor) rotates one bit for every 676 clock cycles. Figure 5 shows an example for rotation operations. Green area shows the inner connection for changing order of the connections. You must use circular shift modules for rotation operations. Circular Right Modules will be used for input connections (forward and backward inputs) and Circular Left Modules will be used for output connections (forward and backward outputs). You must use position counter for the shifting operation (0-25). Also, each rotor can be set to a specific starting position between 0-25 at the rising edge of the load signal. Rotor rotates at the rising edge of the clock signal. Rotor1 and Rotor2 have clock outputs for next rotor module. Clock outputs generate a clock signal in 26 clock signal. In other words, Output Clock signal frequency is (1/26) * Input Clock Signal Frequency.

Rotate 0-bit                        Rotate 1-bit                          Rotate 2-bit                           Rotate 3-bit

00                                                            00                                            00                                             00

11                                                            11                                            11                                             11

22                                                            22                                            22                                             22

33                                                            33                                            33                                             33

44                                                            44                                            44                                             44

55                                                            55                                            55                                             55

66                                                            66                                            66                                             66

77                                                            77                                            77                                             77

Figure 5: Example Enigma Rotor Rotate Operations

The Enigma machine has 8-bit char input/output, therefore you should use the char decoder/encoder for plugboard connection. After creating the Enigma machine, you will create EnigmaCommunication module which conducts a full encryption/decryption process with 2 Enigma machines. Figure 6 shows the block scheme of the Enigma Communication module.

Figure 6: Enigma Communication Module Block Scheme

Detailed information for the Enigma machine’s modules is given below.

<ul>

 <li><strong>PlugBoard Module: Provide connection between CharDecoder, CharEncoder and Rotor1. </strong><strong>Table 2 </strong>shows the connection of input and output bits. charInput bits are connected to forwardOutput bits and backwardInput bits are connected to charOutput bits.</li>

</ul>

Example: backwardInput[6]=charOutput[3], forwardOutput[19]=charInput[15]…

<ul>

 <li><strong>charInput (26-bit input)</strong>: Forward direction input of the character.</li>

 <li><strong>backwardInput (26-bit input)</strong>: Backward direction input of the character.</li>

 <li><strong>forwardOutput (26-bit output)</strong>: Forward direction output of the character.</li>

 <li><strong>backwardOutput (26-bit output)</strong>: Backward direction output of the character.</li>

 <li><strong>Rotor1 Module: Provide connection between Plugboard and Rotor2. </strong><strong>Table 3 </strong>shows the inner connection of input and output bits. You also need circular shift modules to generate rotating steps of the rotor. forwardInput bits are connected to forwardOutput bits and backwardInput bits are connectedd to backwardOutput bits.

  <ul>

   <li><strong>forwardInput (26-bit input)</strong>: Forward direction input of the character.</li>

   <li><strong>backwardInput (26-bit input)</strong>: Backward direction input of the character.</li>

   <li><strong>startPosition (5-bit input)</strong>: It is used to determine the starting position of the rotor. It will be loaded to position counter at the positive edge of the load signal.</li>

   <li><strong>load (1-bit input)</strong>: It is used to load the starting position data.</li>

   <li><strong>clockIn (1-bit input)</strong>: Increase the position counter at the rising edge of the clockIn signal (when load=0).</li>

   <li><strong>clockOut (1-bit input)</strong>: Provide clock signal for Rotor2. 26 clockIn signals generate 1 clockOut signal.</li>

   <li><strong>forwardOutput (26-bit output)</strong>: Forward direction output of the character.</li>

   <li><strong>backwardOutput (26-bit output)</strong>: Backward direction output of the character.</li>

  </ul></li>

 <li><strong>Rotor2 Module: Provide connection between Rotor1 and Rotor3. </strong><strong>Table 4 </strong>shows the inner connection of input and output bits. You also need circular shift modules to generate rotating steps of the rotor. forwardInput bits are connected to forwardOutput bits and backwardInput bits are connected to backwardOutput bits.

  <ul>

   <li><strong>forwardInput (26-bit input)</strong>: Forward direction input of the character.</li>

   <li><strong>backwardInput (26-bit input)</strong>: Backward direction input of the character.</li>

   <li><strong>startPosition (5-bit input)</strong>: It is used to determine the starting position of the rotor. It will be loaded to position counter at the positive edge of the load signal.</li>

   <li><strong>load (1-bit input)</strong>: It is used to load the starting position data.</li>

   <li><strong>clockIn (1-bit input)</strong>: Increase the position counter at the rising edge of the clockIn signal (when load=0).</li>

   <li><strong>clockOut (1-bit input)</strong>: Provide clock signal for Rotor3. 26 clockIn signals generate 1 clockOut signal.</li>

   <li><strong>forwardOutput (26-bit output)</strong>: Forward direction output of the character.</li>

   <li><strong>backwardOutput (26-bit output)</strong>: Backward direction output of the character.</li>

  </ul></li>

 <li><strong>Rotor3 Module: Provide connection between Rotor2 and Reflector. </strong><strong>Table 5 </strong>shows the inner connection of input and output bits. You also need circular shift modules to generate rotating steps of the rotor. forwardInput bits are connected to forwardOutput bits and backwardInput bits are connected to backwardOutput bits.

  <ul>

   <li><strong>forwardInput (26-bit input)</strong>: Forward direction input of the character.</li>

   <li><strong>backwardInput (26-bit input)</strong>: Backward direction input of the character.</li>

   <li><strong>startPosition (5-bit input)</strong>: It is used to determine the starting position of the rotor. It will be loaded to position counter at the positive edge of the load signal.</li>

   <li><strong>load (1-bit input)</strong>: It is used to load the starting position data.</li>

   <li><strong>clockIn (1-bit input)</strong>: Increase the position counter at the rising edge of the clockIn signal (when load=0).</li>

   <li><strong>forwardOutput (26-bit output)</strong>: Forward direction output of the character.</li>

   <li><strong>backwardOutput (26-bit output)</strong>: Backward direction output of the character.</li>

  </ul></li>

 <li><strong>Reflector Module: Turn the forward direction of the character to the backward direction. </strong><strong>Table 6 </strong>shows the connection of input and output bits. Reflector module connects to the Rotor3.

  <ul>

   <li><strong>inputConnection (26-bit input)</strong>: Forward direction input of the character.</li>

   <li><strong>outputConnection (26-bit output)</strong>: Backward direction output of the character.</li>

  </ul></li>

 <li><strong>EnigmaMachine Module: Encrypt and decrypt the characters.</strong>

  <ul>

   <li><strong>char (8-bit input)</strong>: Connect to the charDecoder. Output of the decoder is connected to the plugboard charInput.</li>

   <li><strong>startPosition1 (5-bit input)</strong>: StartPosition information for Rotor1.</li>

   <li><strong>startPosition2 (5-bit input)</strong>: StartPosition information for Rotor2.</li>

   <li><strong>startPosition3 (5-bit input)</strong>: StartPosition information for Rotor3.</li>

   <li><strong>load (1-bit input)</strong>: Provides load signal to load start position data to rotors. It is directly connected to the rotors’ load input.</li>

   <li><strong>clock (1-bit input)</strong>: Provides clock signal to Rotor1. Other clocks signal for Rotor2 and Rotor3 generated inside of the Rotor1 and Rotor2.</li>

   <li><strong>outChar (8-bit output)</strong>: Output of the Enigma machine. This data comes from char encoder (connected to charOutput of plugBoard).</li>

  </ul></li>

 <li><strong>EnigmaCommunication Module: Generates the communication environment between two Enigma machines. Block scheme of the environment is shown in </strong><strong>Figure 6.</strong>

  <ul>

   <li><strong>plainChar (8-bit input)</strong>: The character to be transferred securely.</li>

   <li><strong>startPosition1 (5-bit input)</strong>: StartPosition information for Rotor1.</li>

   <li><strong>startPosition2 (5-bit input)</strong>: StartPosition information for Rotor2.</li>

   <li><strong>startPosition3 (5-bit input)</strong>: StartPosition information for Rotor3.</li>

   <li><strong>load (1-bit input)</strong>: Provides load signal to rotors.</li>

   <li><strong>clock (1-bit input)</strong>: Provides clock signal to Rotor1.</li>

   <li><strong>chipherChar (8-bit output)</strong>: Encrypted character which the is output of the first Enigma machine, it will be the input of the second Enigma machine.</li>

   <li><strong>decryptedChar (8-bit output)</strong>: Decrypted character which is the output of the second Enigma machine.</li>

  </ul></li>

</ul>

Table 2: Plugboard Bit Connections

<table width="453">

 <tbody>

  <tr>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="101"><strong>charInput</strong></td>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="101"><strong>charInput</strong></td>

  </tr>

  <tr>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="101"><strong>charOutput</strong></td>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="101"><strong>charOutput</strong></td>

  </tr>

  <tr>

   <td width="126">0</td>

   <td width="101">4</td>

   <td width="126">13</td>

   <td width="101">22</td>

  </tr>

  <tr>

   <td width="126">1</td>

   <td width="101">10</td>

   <td width="126">14</td>

   <td width="101">24</td>

  </tr>

  <tr>

   <td width="126">2</td>

   <td width="101">12</td>

   <td width="126">15</td>

   <td width="101">7</td>

  </tr>

  <tr>

   <td width="126">3</td>

   <td width="101">5</td>

   <td width="126">16</td>

   <td width="101">23</td>

  </tr>

  <tr>

   <td width="126">4</td>

   <td width="101">11</td>

   <td width="126">17</td>

   <td width="101">20</td>

  </tr>

  <tr>

   <td width="126">5</td>

   <td width="101">6</td>

   <td width="126">18</td>

   <td width="101">18</td>

  </tr>

  <tr>

   <td width="126">6</td>

   <td width="101">3</td>

   <td width="126">19</td>

   <td width="101">15</td>

  </tr>

  <tr>

   <td width="126">7</td>

   <td width="101">16</td>

   <td width="126">20</td>

   <td width="101">0</td>

  </tr>

  <tr>

   <td width="126">8</td>

   <td width="101">21</td>

   <td width="126">21</td>

   <td width="101">8</td>

  </tr>

  <tr>

   <td width="126">9</td>

   <td width="101">25</td>

   <td width="126">22</td>

   <td width="101">1</td>

  </tr>

  <tr>

   <td width="126">10</td>

   <td width="101">13</td>

   <td width="126">23</td>

   <td width="101">17</td>

  </tr>

  <tr>

   <td width="126">11</td>

   <td width="101">19</td>

   <td width="126">24</td>

   <td width="101">2</td>

  </tr>

  <tr>

   <td width="126">12</td>

   <td width="101">14</td>

   <td width="126">25</td>

   <td width="101">9</td>

  </tr>

 </tbody>

</table>

Table 3: Rotor1 Bit Connections

<table width="529">

 <tbody>

  <tr>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

  </tr>

  <tr>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

  </tr>

  <tr>

   <td width="126">0</td>

   <td width="139">7</td>

   <td width="126">13</td>

   <td width="139">3</td>

  </tr>

  <tr>

   <td width="126">1</td>

   <td width="139">12</td>

   <td width="126">14</td>

   <td width="139">14</td>

  </tr>

  <tr>

   <td width="126">2</td>

   <td width="139">21</td>

   <td width="126">15</td>

   <td width="139">13</td>

  </tr>

  <tr>

   <td width="126">3</td>

   <td width="139">17</td>

   <td width="126">16</td>

   <td width="139">11</td>

  </tr>

  <tr>

   <td width="126">4</td>

   <td width="139">0</td>

   <td width="126">17</td>

   <td width="139">8</td>

  </tr>

  <tr>

   <td width="126">5</td>

   <td width="139">2</td>

   <td width="126">18</td>

   <td width="139">4</td>

  </tr>

  <tr>

   <td width="126">6</td>

   <td width="139">22</td>

   <td width="126">19</td>

   <td width="139">10</td>

  </tr>

  <tr>

   <td width="126">7</td>

   <td width="139">20</td>

   <td width="126">20</td>

   <td width="139">6</td>

  </tr>

  <tr>

   <td width="126">8</td>

   <td width="139">23</td>

   <td width="126">21</td>

   <td width="139">5</td>

  </tr>

  <tr>

   <td width="126">9</td>

   <td width="139">18</td>

   <td width="126">22</td>

   <td width="139">19</td>

  </tr>

  <tr>

   <td width="126">10</td>

   <td width="139">9</td>

   <td width="126">23</td>

   <td width="139">16</td>

  </tr>

  <tr>

   <td width="126">11</td>

   <td width="139">25</td>

   <td width="126">24</td>

   <td width="139">24</td>

  </tr>

  <tr>

   <td width="126">12</td>

   <td width="139">15</td>

   <td width="126">25</td>

   <td width="139">1</td>

  </tr>

 </tbody>

</table>

Table 4: Rotor2 Bit Connections

<table width="529">

 <tbody>

  <tr>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

  </tr>

  <tr>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

  </tr>

  <tr>

   <td width="126">0</td>

   <td width="139">19</td>

   <td width="126">13</td>

   <td width="139">9</td>

  </tr>

  <tr>

   <td width="126">1</td>

   <td width="139">4</td>

   <td width="126">14</td>

   <td width="139">14</td>

  </tr>

  <tr>

   <td width="126">2</td>

   <td width="139">7</td>

   <td width="126">15</td>

   <td width="139">22</td>

  </tr>

  <tr>

   <td width="126">3</td>

   <td width="139">6</td>

   <td width="126">16</td>

   <td width="139">24</td>

  </tr>

  <tr>

   <td width="126">4</td>

   <td width="139">12</td>

   <td width="126">17</td>

   <td width="139">18</td>

  </tr>

  <tr>

   <td width="126">5</td>

   <td width="139">17</td>

   <td width="126">18</td>

   <td width="139">15</td>

  </tr>

  <tr>

   <td width="126">6</td>

   <td width="139">8</td>

   <td width="126">19</td>

   <td width="139">13</td>

  </tr>

  <tr>

   <td width="126">7</td>

   <td width="139">5</td>

   <td width="126">20</td>

   <td width="139">3</td>

  </tr>

  <tr>

   <td width="126">8</td>

   <td width="139">2</td>

   <td width="126">21</td>

   <td width="139">10</td>

  </tr>

  <tr>

   <td width="126">9</td>

   <td width="139">0</td>

   <td width="126">22</td>

   <td width="139">21</td>

  </tr>

  <tr>

   <td width="126">10</td>

   <td width="139">1</td>

   <td width="126">23</td>

   <td width="139">16</td>

  </tr>

  <tr>

   <td width="126">11</td>

   <td width="139">20</td>

   <td width="126">24</td>

   <td width="139">11</td>

  </tr>

  <tr>

   <td width="126">12</td>

   <td width="139">25</td>

   <td width="126">25</td>

   <td width="139">23</td>

  </tr>

 </tbody>

</table>

Table 5: Rotor3 Bit Connections

<table width="529">

 <tbody>

  <tr>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

   <td width="126"><strong>forwardOutput</strong></td>

   <td width="139"><strong>forwardInput</strong></td>

  </tr>

  <tr>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

   <td width="126"><strong>backwardInput</strong></td>

   <td width="139"><strong>backwardOutput</strong></td>

  </tr>

  <tr>

   <td width="126">0</td>

   <td width="139">19</td>

   <td width="126">13</td>

   <td width="139">13</td>

  </tr>

  <tr>

   <td width="126">1</td>

   <td width="139">0</td>

   <td width="126">14</td>

   <td width="139">25</td>

  </tr>

  <tr>

   <td width="126">2</td>

   <td width="139">6</td>

   <td width="126">15</td>

   <td width="139">7</td>

  </tr>

  <tr>

   <td width="126">3</td>

   <td width="139">1</td>

   <td width="126">16</td>

   <td width="139">24</td>

  </tr>

  <tr>

   <td width="126">4</td>

   <td width="139">15</td>

   <td width="126">17</td>

   <td width="139">8</td>

  </tr>

  <tr>

   <td width="126">5</td>

   <td width="139">2</td>

   <td width="126">18</td>

   <td width="139">23</td>

  </tr>

  <tr>

   <td width="126">6</td>

   <td width="139">18</td>

   <td width="126">19</td>

   <td width="139">9</td>

  </tr>

  <tr>

   <td width="126">7</td>

   <td width="139">3</td>

   <td width="126">20</td>

   <td width="139">22</td>

  </tr>

  <tr>

   <td width="126">8</td>

   <td width="139">16</td>

   <td width="126">21</td>

   <td width="139">11</td>

  </tr>

  <tr>

   <td width="126">9</td>

   <td width="139">4</td>

   <td width="126">22</td>

   <td width="139">17</td>

  </tr>

  <tr>

   <td width="126">10</td>

   <td width="139">20</td>

   <td width="126">23</td>

   <td width="139">10</td>

  </tr>

  <tr>

   <td width="126">11</td>

   <td width="139">5</td>

   <td width="126">24</td>

   <td width="139">14</td>

  </tr>

  <tr>

   <td width="126">12</td>

   <td width="139">21</td>

   <td width="126">25</td>

   <td width="139">12</td>

  </tr>

 </tbody>

</table>

Table 6: Reflector Bit Connections

<table width="572">

 <tbody>

  <tr>

   <td width="148"><strong>outputConnection</strong></td>

   <td width="138"><strong>inputConnection</strong></td>

   <td width="148"><strong>outputConnection</strong></td>

   <td width="138"><strong>inputConnection</strong></td>

  </tr>

  <tr>

   <td width="148">0</td>

   <td width="138">24</td>

   <td width="148">13</td>

   <td width="138">10</td>

  </tr>

  <tr>

   <td width="148">1</td>

   <td width="138">17</td>

   <td width="148">14</td>

   <td width="138">12</td>

  </tr>

  <tr>

   <td width="148">2</td>

   <td width="138">20</td>

   <td width="148">15</td>

   <td width="138">8</td>

  </tr>

  <tr>

   <td width="148">3</td>

   <td width="138">7</td>

   <td width="148">16</td>

   <td width="138">4</td>

  </tr>

  <tr>

   <td width="148">4</td>

   <td width="138">16</td>

   <td width="148">17</td>

   <td width="138">1</td>

  </tr>

  <tr>

   <td width="148">5</td>

   <td width="138">18</td>

   <td width="148">18</td>

   <td width="138">5</td>

  </tr>

  <tr>

   <td width="148">6</td>

   <td width="138">11</td>

   <td width="148">19</td>

   <td width="138">25</td>

  </tr>

  <tr>

   <td width="148">7</td>

   <td width="138">3</td>

   <td width="148">20</td>

   <td width="138">2</td>

  </tr>

  <tr>

   <td width="148">8</td>

   <td width="138">15</td>

   <td width="148">21</td>

   <td width="138">22</td>

  </tr>

  <tr>

   <td width="148">9</td>

   <td width="138">23</td>

   <td width="148">22</td>

   <td width="138">21</td>

  </tr>

  <tr>

   <td width="148">10</td>

   <td width="138">13</td>

   <td width="148">23</td>

   <td width="138">9</td>

  </tr>

  <tr>

   <td width="148">11</td>

   <td width="138">6</td>

   <td width="148">24</td>

   <td width="138">0</td>

  </tr>

  <tr>

   <td width="148">12</td>

   <td width="138">14</td>

   <td width="148">25</td>

   <td width="138">19</td>

  </tr>

 </tbody>

</table>