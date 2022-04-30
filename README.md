
===================================================================================================================================================
Custom 8bit CPU Instruction set
NOTE: Operations are executed at EVERY EDGE of the clock cycle (i.e. at both positive and negative edge of the clock cycle) 
===================================================================================================================================================
Abbreviations used in the document:

  inst - Instruction
  op1 - Operand 1
  op2 - Operand 2
  reg - Register
  addr - Address
  NOP - No Operation
===================================================================================================================================================
Instructions and their Execution:

NOTE: Every step in shown in Instruction Execution is an edge of the clock cycle



  a) Store data in register
	Instruction Mnemonic:- 1
     	
	Instruction Format:
     		inst   op1(reg addr)   op2(data)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module
		ii) Fetch operand2(data) and store it in specified register of 8byte memory module
		iii) NOP
		iv) NOP
		v) Free the CPU


  b) Copy data from one register to another register of 8byte memory module
	Instruction Mnemonic:- 2
     	
	Instruction Format:
     		inst   op1(reg addr)   op2(reg addr)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module
		ii) Put the data of 8byte memory module on data bus of 8bit output register
		iii) Fetch operand2(address of the register) and store it in address register of 8byte memory module
		iv) Put the data of 8bit Output register on data bus of 8byte memory module
		v) Free the CPU


  c) Perform addition on data from specified two registers of 8byte memory module
	Instruction Mnemonic:- 3
     	
	Instruction Format:
     		inst   op1(reg addr)   op2(reg addr)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module
		ii) Store the output of 8byte memory module in register1 of ALU via 8bit output register
		iii) Fetch operand2(address of the register) and store it in address register of 8byte memory module
		iv) Store the output of 8byte memory module in register2 of ALU via 8bit output register
		v) Store the Output of ALU in Accumulator, Free the CPU


  d) Perform subtraction on data from specified two registers of 8byte memory module
	Instruction Mnemonic:- 4
     	
	Instruction Format:
     		inst   op1(reg addr)   op2(reg addr)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module, 
		ii) Store the output of 8byte memory module in register1 of ALU via 8bit output register
		iii) Fetch operand2(address of the register) and store it in address register of 8byte memory module, 
		iv) Store the output of 8byte memory module in register2 of ALU via 8bit output register
		v) Signal ALU to compute 2's Complement of data in register2, Store the Output of ALU in Accumulator, Free the CPU



  e) Copy data from Accumulator to a register of 8byte memory module
	Instruction Mnemonic:- 5
     	
	Instruction Format:
     		inst   op1(reg addr)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module
		ii) Put the data of Accumulator on the data bus of 8byte memory module
		iii) NOP
		iv) NOP
		v) Free the CPU


  f) Put data of a register of 8byte memory module on Output Data BUS
	Instruction Mnemonic:- 6
     	
	Instruction Format:
     		inst   op1(reg addr)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in address register of 8byte memory module
		ii)store the output of 8byte memory module in an 8bit output register
		iii) Put data of output register on Output Data BUS
		iv) NOP
		v) Free the CPU


  g) Put data of a Accumulator on Output Data BUS
	Instruction Mnemonic:- 7
     	
	Instruction Format:
     		inst
     	
	Instruction Execution:
     		i) Put data of Accumulator on Output Data BUS
		ii) Free the CPU


  h) Keep CPU busy from some (Clock cycles)/2
	Instruction Mnemonic:- 8
     	
	Instruction Format:
     		inst   op1(data)
     	
	Instruction Execution:
     		i) Fetch operand1(address of the register) and store it in register of 8bit Programmable counter
		ii) NOP
		iii) NOP
		iv) NOP
                  .
                  .
                  .
                  .
                  .
                  .
                  .
		Free the CPU after the counting is done


-------------x-------------x-------------x-------------x-------------x-------------x-------------x-------------x-------------x-------------x-------------x
