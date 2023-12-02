```
module count(CLK6D,cose);
   input CLK6D;
	output [2:0] cose;
	reg [2:0] cose;
	
	always@(posedge CLK6D)begin
	   if(cose==3'b111)cose<=3'b000;
		else cose=cose+3'b001;
	end
endmodule
```
