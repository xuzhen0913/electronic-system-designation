```verilog
module row_CHS(SW_R3,SW_R2,SW_R1,SW_R0,row_chose);
//编码器，编码行选信号
   input SW_R3,SW_R2,SW_R1,SW_R0;
	output [2:0]row_chose;
	reg [2:0]row_chose;
	
	always@(SW_R3 or SW_R2 or SW_R1 or SW_R0)begin
	   case({SW_R3,SW_R2,SW_R1,SW_R0})
			4'b1111: begin row_chose<=3'b100;end
			4'b1110: begin row_chose<=3'b000;end
			4'b1101: begin row_chose<=3'b001;end
			4'b1011: begin row_chose<=3'b010;end
			4'b0111: begin row_chose<=3'b011;end
		endcase
	end
endmodule
```
