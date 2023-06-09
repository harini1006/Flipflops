### Ex. No. 5
### Date: 12.5.23
# Implementation of Flipflops using Verilog HDL
## Aim:
To design and implement the following flipflops using Verilog HDL and verify its characteristic table.
1.	SR Flipflop
2.	D Flipflop
3.	JK Flipflop
4.	T Flipflop
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A flip-flop in digital electronics is a circuit with two stable states that can be used to store binary data. The stored data can be changed by applying varying inputs. Flip-flops and latches are fundamental building blocks of digital electronics systems used in computers, communications, and many other types of systems. Both are used as data storage elements.
## SR Flipflop
The SR flip flop is a 1-bit memory bistable device having two inputs, i.e., SET and RESET. The SET input 'S' set the device or produce the output 1, and the RESET input 'R' reset the device or produce the output 0. The SET and RESET inputs are labeled as S and R, respectively.
The SR flip flop stands for "Set-Reset" flip flop. The reset input is used to get back the flip flop to its original state from the current state with an output 'Q'. This output depends on the set and reset conditions, which is either at the logic level "0" or "1".
The NAND gate SR flip flop is a basic flip flop which provides feedback from both of its outputs back to its opposing input. This circuit is used to store the single data bit in the memory circuit. So, the SR flip flop has a total of three inputs, i.e., 'S' and 'R', and current output 'Q'. This output 'Q' is related to the current history or state. The term "flip-flop" relates to the actual operation of the device, as it can be "flipped" to a logic set state or "flopped" back to the opposing logic reset state.

![image](https://github.com/rvinifa/Flipflops/assets/133735746/725727f1-85ef-4b56-8fb5-5fd470d8d207)
 

## D Flipflop
The D flip flop is the most important flip flop from other clocked types. It ensures that at the same time, both the inputs, i.e., S and R, are never equal to 1. The Delay flip-flop is designed using a gated SR flip-flop with an inverter connected between the inputs allowing for a single input D(Data).
This single data input, which is labeled as "D" used in place of the "Set" input and for the complementary "Reset" input, the inverter is used. Thus, the level-sensitive D-type or D flip flop is constructed from a level-sensitive SR flip flop.
So, here S=D and R= ~D(complement of D)
![image](https://github.com/rvinifa/Flipflops/assets/133735746/c9c8383d-6f6d-48c6-b35b-2a2fa28178ed)
 
## JK Flipflop
The JK flip flop is one of the most used flip flops in digital circuits. The JK flip flop is a universal flip flop having two inputs 'J' and 'K'. The JK flip flop work in the same way as the SR flip flop work. The JK flip flop has 'J' and 'K' flip flop instead of 'S' and 'R'. The only difference between JK flip flop and SR flip flop is that when both inputs of SR flip flop is set to 1, the circuit produces the invalid states as outputs, but in case of JK flip flop, there are no invalid states even if both 'J' and 'K' flip flops are set to 1. The JK Flip Flop is a gated SR flip-flop having the addition of a clock input circuitry. The invalid or illegal output condition occurs when both of the inputs are set to 1 and are prevented by the addition of a clock input circuit. So, the JK flip-flop has four possible input combinations, i.e., 1, 0, "no change" and "toggle". 
 ![image](https://github.com/rvinifa/Flipflops/assets/133735746/ad5d7905-7ed9-4ddb-ba91-4e284fc151d6)


## T Flipflop
In T flip flop, "T" defines the term "Toggle". In SR Flip Flop, we provide only a single input called "Toggle" or "Trigger" input to avoid an intermediate state occurrence. Now, this flip-flop work as a Toggle switch. The next output state is changed with the complement of the present state output. This process is known as "Toggling"'. Both the inputs of the "JK Flip Flop" are connected as a single input T.
 ![image](https://github.com/rvinifa/Flipflops/assets/133735746/d8ebd20c-4a91-4496-bd67-2239ab1a0798)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
### SR-Flipflop:
```python
  module exp5a(s,r,clk,q,qbar);
  input s,r,clk;
  output reg q;
  output qbar;
  always@(posedge clk)
  begin
  q=s|((~r)&q);
  end
  assign qbar=~q;
  endmodule
 ```
### D_Flipflop:
```python
   module exp5b(d,clk,q,qbar);
   input d,clk;
   output reg q;
   output qbar;
   always@(posedge clk)
   begin
   q=((~q)&d)|(q&d);
   end
   assign qbar=~q;
   endmodule
   ```
   ### JK Flipflop:
   ``` python
   module exp5c(j,k,clk,q,qbar);
   input j,k,clk;
   output reg q;
   output qbar;
   always@(posedge clk)
   begin
   q=((~q)&j)|(q&(~k));
   end
   assign qbar=~q;
   endmodule
   ```
   ### T Flipflop:
   ```python
      module exp5d(t,clk,q,qbar);
   input t,clk;
   output reg q;
   output qbar;
   always@(posedge clk)
   begin
   q=((~q)&t)|(q&(~t));
   end
   assign qbar=~q;
   endmodule
   ```
## RTL Schematic:
### SR Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/080114f5-c7bc-42de-9cd1-e1815dd3a93a)
### D Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/5250053f-efc7-4749-bd6e-803cc2a368e6)
### JK Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/13bedf63-a0a8-441f-a64a-584d3caaae9f)
### T Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/25468ff8-cadb-440e-aa72-cb7be5d1dc49)

## Timing Diagram:
### SR Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/47b89a56-f05a-4135-8239-0f7f828c2f5d)
### D Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/8d1ca69d-0951-40e6-9177-564bd6e542c2)
### JK Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/2633d9ac-0fcf-4023-bf77-d13a8c8593a5)
### T Flipflop:
![image](https://github.com/harini1006/Flipflops/assets/113497405/0076f29a-7193-4144-837c-e750f94ef1a1)

## Result:
Thus the SR, D, JK and T flipflops are implemented and the characteristic tables are verified.

