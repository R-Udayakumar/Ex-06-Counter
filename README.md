### Ex. No. 6
#### Date: 19.5.23
# Implementation of 4 bit synchronous counters using Verilog HDL
## Aim:
To design and implement the following synchronous counters using Verilog HDL.
1.	UP counter
2.	DOWN counter
## Components Required:
1.	Laptop with Quartus software and modelsim software.
## Theory:
A Synchronous counter is the counter in which the clock input with all the flip-flops uses the same source and produces the output at the same time.
## UP Counter
### State table
![image](https://github.com/rvinifa/Counter/assets/133735746/ede78598-89fd-4aeb-9d82-329e45d05f2a)


### K-map Simplification
![image](https://github.com/rvinifa/Counter/assets/133735746/21554263-611b-44a2-8f78-7b2220ef5a05)
   
   
### Logic Diagram
![image](https://github.com/rvinifa/Counter/assets/133735746/2ab715d3-f6d5-4cf6-8fda-8fa666518c0b)



## DOWN Counter
### State Table
 ![image](https://github.com/rvinifa/Counter/assets/133735746/5be9585c-11aa-47c3-beaf-0dca916750f2)

### K-map simplification
 ![image](https://github.com/rvinifa/Counter/assets/133735746/dde7bc60-3a4f-4fb7-811d-f420cb74bdef)

### Logic Diagram
 ![image](https://github.com/rvinifa/Counter/assets/133735746/64e2d7b7-1646-4ca7-bc6c-c7c10881223c)

## Procedure:
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations, generate the timing diagram.


## Program:
### 1.UP counter:
```
module upcounter(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@(posedge clk)
begin
q4=(q1&q2&q3)^q4;
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end
endmodule
```

### 2.DOWN counter:
```
module downcounter(clk,q1,q2,q3,q4);
input clk;
output reg q1,q2,q3,q4;
always@(posedge clk)
begin
q4=((~q3)&(~q2)&(~q1))^q4;
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
```

## RTL Schematic:
### UP Counter:
![image](https://github.com/R-Udayakumar/Ex-06-Counter/assets/118708024/0fd4b8a3-7c22-4298-8a3a-d7f92099e12d)

### DOWN Counter:
![image](https://github.com/R-Udayakumar/Ex-06-Counter/assets/118708024/2f86daa9-f7bf-4173-8960-1314bc929664)


## Timing Diagram:
### UP Counter:
![image](https://github.com/R-Udayakumar/Ex-06-Counter/assets/118708024/80ecc0d3-f403-41fa-bdaf-1acff8b6d551)

### DOWN Counter:
![image](https://github.com/R-Udayakumar/Ex-06-Counter/assets/118708024/6f247385-2685-48ab-a178-81092233fc46)


## Result:
Thus the Synchronous UP and DOWN counters using T flipflops are implemented and the state tables are verified.
