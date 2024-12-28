# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

/* write all the steps invloved */

**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: RegisterNumber:
*/module sr_flipflop (
    input wire S,      
    input wire R,      
    input wire clk,    
    input wire rst,    
    output reg Q,      
    output wire Qn     
);
    
    assign Qn = ~Q;  
    
    always @(posedge clk or posedge rst) begin
        if (rst) 
            Q <= 0;  
        else begin
            case ({S, R})
                2'b00: Q <= Q;        
                2'b01: Q <= 0;        
                2'b10: Q <= 1;        
                2'b11: Q <= Q;        
                default: Q <= Q;      
            endcase
        end
    end

endmodule


**RTL LOGIC FOR FLIPFLOPS**
![Screenshot 2024-12-28 103225](https://github.com/user-attachments/assets/1b59fa46-a98c-442f-b8d6-e3aef39c7ca1)

**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot 2024-12-28 103258](https://github.com/user-attachments/assets/0b4f62ee-0f40-44c1-81c1-0195a64e0528)

**RESULTS**
To implement  SR flipflop using verilog and validating their functionality using their functional tables
