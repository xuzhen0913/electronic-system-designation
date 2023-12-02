```verilog
module SEQ_GENERATE_INCLUDE(CLK,RESET,SEQ_IN);//序列产生器，有效
    input CLK,RESET;
    output SEQ_IN;
    reg SEQ_IN;
    reg [3:0]current_st,next_st;
    parameter S0=4'b0000,S1=4'b0001,S2=4'b0010,S3=4'b0011,S4=4'b0100,S5=4'b0101,S6=4'b0110,S7=4'b0111,S8=4'b1000,S9=4'b1001;

    always@(posedge CLK or negedge RESET)begin
       if(!RESET)current_st<=S0;
        else current_st<=next_st;
    end

    always@(current_st)begin
       case(current_st)
           S0: next_st<=S1;
            S1: next_st<=S2;
            S2: next_st<=S3;
            S3: next_st<=S4;
            S4: next_st<=S5;
            S5: next_st<=S6;
            S6: next_st<=S7;
            S7: next_st<=S8;
            S8: next_st<=S9;
            S9: next_st<=S0;
            default: next_st<=S0;
        endcase
    end

    always@(current_st)begin
       case(current_st)
            S0: SEQ_IN<=1'b1;
            S1: SEQ_IN<=1'b1;
            S2: SEQ_IN<=1'b1;
            S3: SEQ_IN<=1'b0;
            S4: SEQ_IN<=1'b1;
            S5: SEQ_IN<=1'b0;
            S6: SEQ_IN<=1'b0;
            S7: SEQ_IN<=1'b1;
            S8: SEQ_IN<=1'b1;
            S9: SEQ_IN<=1'b0;
            default: SEQ_IN<=1'b0;
        endcase
    end

endmodule
```
