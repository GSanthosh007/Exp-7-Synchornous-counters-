# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

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
### Procedure
![Screenshot 2024-01-02 133231](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/e67865be-5375-4cfe-a230-b7e7a269684b)

### PROGRAM 
/*Program for flipflops and verify its truth table in quartus using Verilog programming.

Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: SANTHOSH G
RegisterNumber: 212223240152 
*/
## UP COUNTER

![Screenshot 2024-01-02 134031](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/a9a7f2da-2760-420b-803d-91f09d3a5f7f)


## DOWN COUNTER
module dc(clk,A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
A[2]=(((~A[0])&(~A[1]))^A[2]);
A[1]=(~A[0])^A[1];
A[0]=1^A[0];
end
endmodule
## RTL LOGIC UP COUNTER AND DOWN COUNTER
## UP COUNTER
![Screenshot 2024-01-02 134257](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/250d17c7-3172-4132-a72a-8fc5bb26bb7f)

## DOWN COUNTER
![Screenshot 2024-01-02 134338](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/877c7ad1-48c4-42b6-b6d1-f3d998e57028)

### TIMING DIGRAMS FOR COUNTER  
## UP COUNTER

![Screenshot 2024-01-02 134423](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/cdadee65-8c68-485c-9fd8-deb87f7cf95f)

## DOWN COUNTER
![Screenshot 2024-01-02 134519](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/2abe31a5-34dd-495c-9d8e-d7307a532b15)



### TRUTH TABLE 
## UP COUNTER
![Screenshot 2024-01-02 134540](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/66c5b368-32eb-4488-8790-c866b251eef0)

## DOWN COUNTER
![Screenshot 2024-01-02 134636](https://github.com/GSanthosh007/Exp-7-Synchornous-counters-/assets/147527586/03834811-13b7-4bd4-82bc-93c49d24da66)




### RESULTS 
