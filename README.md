# 6T-SRAM-IN-CMOS
Abstract
 -------------------------------------------------------------------------
 
SRAM is a memory component and is used in 
various VLSI chips due to its unique capability to 
retain data. This memory cell has become a subject 
of research to meet the demands for future 
communication systems. In this paper a 6T SRAM 
cell is designed by using Verilog and esim software.
Static random-access memory (SRAM) is a static 
memory cell which is widely used in various 
electronic systems. It is faster and consumes less 
power as compared to other memory cells [1-2]. It 
does not require refreshing periodically. Because of 
this, SRAM is the most popular memory cell among 
VLSI designers. 




Reference Circuit Diagram
---------------------------------------------------------------------
![image](https://user-images.githubusercontent.com/101354062/158364247-131f79c3-8cd6-452a-b0c6-9023794ec87f.png)

![image](https://user-images.githubusercontent.com/101354062/158364085-28ad134a-8627-4fb1-bb85-ab008aa8ed63.png)


Reference Waveform
------------------------------------------------------------------
![image](https://user-images.githubusercontent.com/101354062/158364425-f9aaade6-445a-4190-95ba-6b24ffff3c9d.png)


Circuit Detail
-------------------------------------------------------

Hence continuous evolution is going on for better 
performance of SRAM cells. Due to this, different 
types of 
SRAM cells are available in the literature like 6T 
SRAM cell, 7T SRAM cell, 8T SRAM cell, 9T 
SRAM cell 
etc. Most common SRAM cells used in digital 
system is the 6T SRAM cell. This cell can store 1-
bit of data. The 
bit remains in the cell as long as power is supplied.
A conventional 6T SRAM cell consists of two 
inverters which are connected back-to-back. Fig. 1 
shows the basic structure of a 6T SRAM memory 
cell [1]. The data which must be stored is latched in 
these two inverters. The process of storing a data is 
known as Write operation and the process of 
recovering the data is known as Read operation. 
Write operation is used for uploading the contents in 
a SRAM cell while Read operation is used for 
fetching the contents. The read operation is done 
with the help of sense circuits which sense BL and 
BLB data line before discharging it completely Basically, SRAM performs three operations 
which are Hold, Read and Write operations. ... 
Whenever the two access pass transistors of the 
word line (WL) are in OFF state, then the bit line 
and bit line bar (BL & BLB) are also in OFF 
condition, hence the memory cell is in hold state .


Truth Table
----------------------------------
![image](https://user-images.githubusercontent.com/101354062/158365932-7a96e43c-7907-4e71-9bcc-83d7d8e6c639.png)


Software Used
-------------------------------
eSim
It is an Open Source EDA developed by FOSSEE, IIT Bombay. It is used for electronic circuit simulation. It is made by the combination of two software namely NgSpice and KiCAD.
For more details refer:
https://esim.fossee.in/home

NgSpice
It is an Open Source Software for Spice Simulations. For more details refer:
http://ngspice.sourceforge.net/docs.html

Makerchip
It is an Online Web Browser IDE for Verilog/System-verilog/TL-Verilog Simulation. Refer
https://www.makerchip.com/
Verilator
It is a tool which converts Verilog code to C++ objects. Refer: https://www.veripool.org/verilator/

Circuit Diagram in eSim
----------------------------------------------
The following is the schematic in eSim:
![image](https://user-images.githubusercontent.com/101354062/158366274-4f06a4b0-62f2-40d7-b017-0b1f4d4819d1.png)

Verilog Code
---------------------------------------------

![image](https://user-images.githubusercontent.com/101354062/158366616-6c8a5f43-8a24-44ed-a732-89cec941ad56.png)

Makerchip
------------------------------

     \TLV_version 1d: tl-x.org

     \SV

    /* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

    //Your Verilog/System Verilog Code Starts Here:

    module ixorxnor(output yXOR,output yXNOR, input a,input b);
  
      assign yXOR = a ^ b;
  
     assign yXNOR = ~(a ^ b);
  
      endmodule 

    //Top Module Code Starts here:

    	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed,     output logic failed);
		logic  yXOR;//output
    
		logic  yXNOR;//output
    
		logic  a;//input
    
		logic  b;//input
    
    //The $random() can be replaced if user wants to assign values'

      always @(posedge clk) 
      
         begin
         
         a = $random();
         
		   b = $random();
       
            end
            
		ixorxnor ixorxnor(.yXOR(yXOR), .yXNOR(yXNOR), .a(a), .b(b));
    \TLV

    //Add \TLV here if desired                                     
    \SV

    endmodule

----------------------------------------------------

Makerchip Plots
----------------------
![WhatsApp Image 2022-03-15 at 5 17 54 PM](https://user-images.githubusercontent.com/101354062/158371953-3b802ab7-c277-455e-8b04-8d5686617a5b.jpeg)


Netlists
----------------------
![image](https://user-images.githubusercontent.com/101354062/158372297-7463928e-5ff2-4efc-9f46-7b6512d34f4d.png)

Ngspice Plots
-----------------
![Screenshot from 2022-03-10 22-49-37](https://user-images.githubusercontent.com/101354062/158373519-b7ccc7fc-2393-496c-95f2-5b9bbc8b6550.png)

![Screenshot from 2022-03-10 22-49-31](https://user-images.githubusercontent.com/101354062/158373570-ff25b4ea-0468-4d3a-8ff4-cc52fd8482a6.png)

![Screenshot from 2022-03-10 22-49-25](https://user-images.githubusercontent.com/101354062/158373608-a5909f37-4625-4c04-b1c0-b9c36122895f.png)

![Screenshot from 2022-03-10 22-49-15](https://user-images.githubusercontent.com/101354062/158373638-0e1537aa-1e5d-4350-97de-e13b9ce04b78.png)

![Screenshot from 2022-03-10 22-49-04](https://user-images.githubusercontent.com/101354062/158373675-68e1eccb-c8cb-4a63-a1a5-ac0cfbf203f6.png)

GAW Plot
-------------------------------
![Screenshot from 2022-03-10 22-31-06](https://user-images.githubusercontent.com/101354062/158373871-18933be6-7650-468d-821c-713c3c367c21.png)


    
Python Plots
-------------------------------------

![Screenshot from 2022-03-10 22-07-14](https://user-images.githubusercontent.com/101354062/158374776-62382329-1728-4094-a728-4b527b4fd536.png)

![Screenshot from 2022-03-10 22-07-27](https://user-images.githubusercontent.com/101354062/158374780-ed14def6-e245-46db-9926-b45bc2fa080e.png)
![Screenshot from 2022-03-10 22-07-37](https://user-images.githubusercontent.com/101354062/158374792-94961427-4388-4353-a404-c9438116d1b7.png)


![Screenshot from 2022-03-10 22-07-46](https://user-images.githubusercontent.com/101354062/158374806-0a83bc73-2392-412a-91ea-4ad00a1a7ff6.png)


Steps to run this project
-----------------------------
1.Open a new terminal.

2.Clone this project using the following command:
  git clone https://github.com/AnkitKumar01github/6T-SRAM-IN-CMOS.git
  
3.  Change directory:
   cd eSim_project_files/6T-SRAM-IN-CMOS
   
4. Run ngspice:
    ngspice 6T-SRAM-IN-CMOS.cir.out
    
5. To run the project in eSim:
    Run eSim,
    Load the project,
    Open eeSchema

References
------------------------------------
1.Rohit Kumar Sah1 , Inamul Hussain 2 , Manish Kumar3 1,2,3 Department of ECE, North-eastern Regional Institute of Science & Technology, Nirjuli, India, https://www.iosrjournals.org/iosr-jvlsi/papers/vol5-issue2/Version-1/C05212022.pdf
