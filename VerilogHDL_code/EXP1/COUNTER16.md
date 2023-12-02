```Verilog
module COUNTER16(CLK,RST,DOUT);

   input CLK,RST;
   output [3:0]DOUT;
   reg[3:0]d;
   assign DOUT=d;
   always@(posedge CLK or negedge RST)begin
      if(!RST)d<=4'b0000;
      else d <= d+1;
   end

endmodule

```
