# TFLIPFLOP
AIM:

To implement T flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

T Flip-Flop

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

<img width="707" height="442" alt="Screenshot 2025-12-14 200828" src="https://github.com/user-attachments/assets/e0293b53-c62f-4142-b310-ba38adffd4c3" />

This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

<img width="575" height="414" alt="Screenshot 2025-12-14 200840" src="https://github.com/user-attachments/assets/15186ca4-60ab-46e5-9acf-392c7fddedea" />

From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

PROGRAM:
```
module T_FLIP_FLOP(
    input  wire clk, rst, T,
    output reg Q 	  
);

  initial begin
     Q<=1'b0;
	 end
  
  
	 always @(posedge clk or posedge rst) begin
	
        if (rst)
            Q <= 1'b0;       // Reset
        else if (T)
            Q <= ~Q;         // Toggle if T=1
        else
            Q <= Q;          // Hold if T=0
    end
endmodule
```
RTL LOGIC FOR T_FLIPFLOP:[gate.pdf](https://github.com/user-attachments/files/24150910/gate.pdf)





WAVEFORM:[wave.pdf](https://github.com/user-attachments/files/24150912/wave.pdf)




NAME: DEEPAKKUMAR S

REF NO: 25016457

RESULTS

Hence, T flipflop using verilog and validating their functionality using their functional tables is implemented succesfully
