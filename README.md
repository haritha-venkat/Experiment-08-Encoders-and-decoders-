# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
Step 1: Create module encoder and decoder.

Step 2: Get inputs and outputs for encoders and decoders.

Step 3: Perform "or" operation for encoder and "and" logic for decoders.

Step 4: Perform RTL LOGIC and get waveform.

Step-5: End the module.





### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: harithashree.v
RegisterNumber:  212222230046
*/
## ENCODER:
```python
module encoder(x,y,z,d0,d1,d2,d3,d4,d5,d6,d7);
output x,y,z;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(x,d4,d5,d6,d7);
or(y,d2,d3,d6,d7);
or(z,d1,d3,d5,d7);
endmodule
```
## DE-CODER:
```python
module deco(x,y,z,d0,d1,d2,d3,d4,d5,d6,d7);
input x,y,z;
output d0,d1,d2,d3,d4,d5,d6,d7;
wire xbar,ybar,zbar;
not (xb0ar,x);
not (ybar,y);
not (zbar,z);
and (d0,xbar,ybar,zbar);
and (d1,ybar,ybar,z);
and (d2,zbar,y,zbar);
and (d3,xbar,y,z);
and (d4,x,ybar,zbar);
and (d5,x,ybar,z);
and (d6,x,y,zbar);
and (d7,x,y,z);
endmodule
```

### RTL LOGIC  

## ENCODER:
![Screenshot 2023-06-09 204348](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/7a1863d3-e8d4-4142-83dc-97d8fcfdeb1a)

## DE-CODER:

![Screenshot 2023-06-09 204424](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/2db50a7e-0e34-4ff6-b96b-32007ffa30c2)







### TIMING DIGRAMS  

## ENCODER:

![Screenshot 2023-06-09 204452](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/49d7d2e7-ff72-4d38-b7dc-3c7b04c17a88)

## DE-CODER:

![Screenshot 2023-06-09 204523](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/47eb7b30-4bdb-4475-9df1-d3b2b32b1f17)




### TRUTH TABLE 

## ENCODER:

![Screenshot 2023-06-09 204601](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/69170de3-1efa-450c-8208-b802f7adaa64)

## DE-CODER:

![Screenshot 2023-06-09 204628](https://github.com/haritha-venkat/Experiment-08-Encoders-and-decoders-/assets/121285701/96c26f0a-dadb-4140-a5f2-3ebd8b6902a4)

### RESULTS :
Thus the program to desing encoder and decoder is done.


