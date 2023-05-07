Download Link: https://assignmentchef.com/product/solved-mips-hw3-single-cycle-cpu-simple-edition
<br>
Utilizing the ALU in Lab2 to implement a simple single cycle CPU. CPU is the most important unit in computer system. Reading the document carefully and do the Lab, you will have elementary knowledge of CPU.

<h1>2. Demands</h1>

<ol>

 <li>Please use iverilog</li>

 <li>“Simple_Single_CPU.v”, “Adder.v”, “ALU.v”, “ALU_Ctrl.v”, “Decoder.v”,</li>

</ol>

“Instr_Memory.v”, “Mux2to1.v”, “Mux3to1.v”, “Program_Counter.v”, “Reg_File.v”, “Shifter.v”, “Sign_Extend.v”, “Zero_Filled.v”, and “TestBench.v” are supplied. Please use these modules to accomplish the design of your CPU and don’t change the file name.




Instruction set: the following instructions have to running in your designed CPU (80pts.)

<table width="621">

 <tbody>

  <tr>

   <td width="108"><strong>Instruction </strong></td>

   <td width="107"><strong>Example </strong></td>

   <td width="114"><strong>Meaning </strong></td>

   <td width="108"><strong>Op field </strong></td>

   <td width="71"><strong>Shamt </strong></td>

   <td width="114"><strong>Function field </strong></td>

  </tr>

  <tr>

   <td width="108"><strong>ADD </strong></td>

   <td width="107">add r1,r2,r3</td>

   <td width="114">r1=r2+r3</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b010011</td>

  </tr>

  <tr>

   <td width="108"><strong>SUB </strong></td>

   <td width="107">sub r1,r2,r3</td>

   <td width="114">r1=r2-r3</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b010001</td>

  </tr>

  <tr>

   <td width="108"><strong>AND </strong></td>

   <td width="107">and r1,r2,r3</td>

   <td width="114">r1=r2&amp;r3</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b010100</td>

  </tr>

  <tr>

   <td width="108"><strong>OR </strong></td>

   <td width="107">or r1,r2,r3</td>

   <td width="114">r1=r2|r3</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b010110</td>

  </tr>

  <tr>

   <td width="108"><strong>NOR </strong></td>

   <td width="107">nor r1,r2,r3</td>

   <td width="114">r1=~(r2|r3)</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b010101</td>

  </tr>

  <tr>

   <td width="108"><strong>SLT </strong></td>

   <td width="107">slt r1,r2,r3</td>

   <td width="114">if(r2&lt;r3) r1=1 else r1=0</td>

   <td width="108">6’b000000</td>

   <td width="71">X</td>

   <td width="114">6’b110000 </td>

  </tr>

  <tr>

   <td width="108"><strong>SLL </strong></td>

   <td width="107">sll rd,rt,5</td>

   <td width="114">rd=rt&lt;&lt;5</td>

   <td width="108">6’b000000</td>

   <td width="71">5</td>

   <td width="114">6’b000000</td>

  </tr>

  <tr>

   <td width="108"><strong>SRL </strong></td>

   <td width="107">srl rd,rt,5</td>

   <td width="114">rd=rt&gt;&gt;5</td>

   <td width="108">6’b000000</td>

   <td width="71">5</td>

   <td width="114">6’b000010</td>

  </tr>

  <tr>

   <td width="108"><strong>ADDI </strong></td>

   <td width="107">addi r1,r2,10</td>

   <td width="114">r1=r2+10</td>

   <td width="108">6’b001000</td>

   <td width="71">X</td>

   <td width="114">X</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<h1>Shifter</h1>

The block diagram of the shifter to be implemented is shown:

Shift.v contains the following inputs and outputs:

<ul>

 <li>sftSrc: A 32-bit input data, is the source data of the shifter.</li>

 <li>leftRight: A 1-bit input control signal. When it is set to 1, the shifter perform logical left shift; else, does logical right shift.</li>

 <li>shamt: A 5-bit input data, represents the number of bit positions to be shifted.</li>

 <li>result: A 32-bit output data, which represents the shifting result of the shifter.</li>

</ul>

<h1>SRL Rd, Rt, shamt (Rs is ignored for SRL)</h1>

Shift register Rt right by the distance indicated by immediate shamt







<h1>4. Bonus</h1>

Implement SLLV (Shift left logical variable) and SRLV (Shift right logical variable) instructions. You can add new module or control signal in this advanced design.

<table width="612">

 <tbody>

  <tr>

   <td width="108"><strong>Instruction </strong></td>

   <td width="107"><strong>Example </strong></td>

   <td width="114"><strong>Meaning </strong></td>

   <td width="108"><strong>Op field </strong></td>

   <td width="61"><strong>Shamt </strong></td>

   <td width="114"><strong>Function field </strong></td>

  </tr>

  <tr>

   <td width="108"><strong>SLLV </strong></td>

   <td width="107">sllv rd,rt,rs</td>

   <td width="114">rd=rt&lt;&lt;rs</td>

   <td width="108">6’b000000</td>

   <td width="61">5</td>

   <td width="114">6’b000110</td>

  </tr>

  <tr>

   <td width="108"><strong>SRLV </strong></td>

   <td width="107">srlv rd,rt,rs</td>

   <td width="114">rd=rt&gt;&gt;rs</td>

   <td width="108">6’b000000</td>

   <td width="61">5</td>

   <td width="114">6’b000100</td>

  </tr>

 </tbody>

</table>




<h1>SRLV Rd, Rt, Rs</h1>

Shift register Rt right by the distance indicated by the register Rs







<h1>5. Test Bench</h1>

In Lab3, three test data (binary code), stored in “CO_P3_test_data1.txt” ~

“CO_P3_test_data3.txt”, are provided. The default test data is the first one. If you would like to use second test data, modify line 75 in the file “TestBench.v” as follows: $readmemb(“CO_P3_test_data1.txt”, cpu.IM.Instr_Mem);

<strong> </strong>

The Assembly codes of the test data are given as follows:

<table width="649">

 <tbody>

  <tr>

   <td width="216">CO_P3_test_data1.txt</td>

   <td width="216">CO_P3_test_data2.txt</td>

   <td width="216">CO_P3_test_data3.txt</td>

  </tr>

  <tr>

   <td width="216">addi r1 r0 10   #r1 = 10 addi r2 r0 4    #r2 = 4 slt r3 r1 r2     #r3 = 0 add r4 r1 r2    #r4 =14  sub r5 r1 r2    #r5 = 6 nor r5 r5 r0    #r5 = -7</td>

   <td width="216">addi r6 r0 3    #r6 = 3 addi r7 r0 14   #r7 = 14 and r8 r6 r7    #r8 = 2 or r9 r6 r7     #r9 = 15 sll r10 r9 3    #r10 = 120</td>

   <td width="216">addi r1 r0 -5   #r1 = -5 addi r2 r0 5    #r2 = 5 slt r3 r1 r2     #r3 = 1 slt r4 r2 r1     #r5 = 0 add r5 r1 r2    #r5 = 0 sub r6 r1 r2    #r6 = -10</td>

  </tr>

 </tbody>

</table>




After the simulation of TestBench, you will get the file “CO_P3_result.txt”. You can verify the result. If your design passes the test data, the following words would show in the Transcript windows.


