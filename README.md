# Exp-6-Synchornous-counters - up counter and down counter 
## AIM: 
To implement 4 bit up and down counters and validate  functionality.
## HARDWARE REQUIRED:  –
PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:
Quartus prime
## THEORY: 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
## Procedure:
1. Open a new project using Quartus II.
2. Declare the inputs and outputs inside module projname().
3. Set the reset value using register.
4. Use commands like begin and end to stimulate the counter.
5. For Up counter increment the count and for Down counter decrement the count.
6. End the verilog programming.


## PROGRAM: 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: Gunaseelan G
RegisterNumber:  212221240031

i) UP COUNTER
module UC(input clk,input reset,output[0:3]counter);  
reg[0:3]counter_up;  
always@(posedge clk or posedge reset)  
begin  
if (reset)  
counter_up<=4'd0;  
else   
counter_up<=counter_up+4'd1;  
end  
assign counter=counter_up;  
endmodule 

ii) DOWN COUNTER
module DC(input clk,input reset,output[0:3]counter);  
reg[0:3]counter_down;  
always@(posedge clk or posedge reset)  
begin  
if (reset)  
counter_down<=4'd0;  
else   
counter_down<=counter_down-4'd1;  
end  
assign counter=counter_down;  
endmodule   
```


## RTL LOGIC UP COUNTER AND DOWN COUNTER: 
### UP COUNTER:
![image](https://user-images.githubusercontent.com/94233985/201402213-18f90b3c-a113-4eb7-81d4-429295100a8a.png)
### DOWN COUNTER:

![image](https://user-images.githubusercontent.com/94233985/201402255-c92a0f35-b121-46c0-9466-598bf7c938ea.png)


## TIMING DIGRAMS FOR COUNTER:
### UP COUNTER:
with reset=0
![image](https://user-images.githubusercontent.com/94233985/201402491-7c0d8780-d9f9-45d2-84af-01a0235b8313.png)
with reset=1
![image](https://user-images.githubusercontent.com/94233985/201402553-cb0ebd3e-93ab-429f-b857-21af61a6be93.png)


### DOWN COUNTER:
with reset=0
![image](https://user-images.githubusercontent.com/94233985/201402391-5c238916-ac33-4a21-b5d3-8b1ac46b78fa.png)
with reset=1
![image](https://user-images.githubusercontent.com/94233985/201402417-46a3e008-7392-45dc-a728-c97cad2907be.png)




## TRUTH TABLE:
### UP COUNTER:
![image](https://user-images.githubusercontent.com/94233985/201402689-a6736ae6-a3f0-47b6-8c10-7d5d52472fe3.png)

### DOWN COUNTER:
![image](https://user-images.githubusercontent.com/94233985/201402455-03ff97b5-d25a-4747-9f3b-827f860d79ad.png)


## RESULTS:
Hence the Four bit Up counter and Down counter is implemented successfully and its functionality is validated.


