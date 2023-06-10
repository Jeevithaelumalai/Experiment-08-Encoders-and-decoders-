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

1.create module encoder and decoder.

2.Get inputs and outputs for encoders and decoders.

3.perform or operation for encoder and and logic for decoders.

4.perform RTL LOGIC and get waveform



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: JEEVITHA E
RegisterNumber:  212222230054
*/
```
i]Encoder

module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule

ii]Decoder

module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule

```



### RTL LOGIC  

# ENCODER:
![image](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/695b17dd-a11d-49c2-93b0-cc29dda51a4b)



### TIMING DIGRAMS  
# DECODER:
![image](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/aacb3c13-dd4c-42ce-ab5c-c513cc80d5df)





### TRUTH TABLE :
# ENCODER:

![image](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/c5cfb607-1b9b-4885-bf57-ce63767cbc2f)
# DECODER:

![image](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/d7c61d5e-09fa-4b5e-9d3b-de0b3ffd3545)


## TRUTH TABLE
# Encoder
![Screenshot 2023-06-10 111959-removebg-preview](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/ab369ccb-d076-4868-a1e3-d1bc08ead0ee)
# Decoder:

![244666606-d81de2a8-5be5-4a75-aae1-8925b1c27379](https://github.com/Jeevithaelumalai/Experiment-08-Encoders-and-decoders-/assets/118708245/fbc0cb9c-5ede-4d18-a620-6d2b6965aea3)



### RESULTS :
Thus the program to desing encoder and decoder is done.
