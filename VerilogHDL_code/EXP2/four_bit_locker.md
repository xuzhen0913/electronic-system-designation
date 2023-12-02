```
module four_bit_locker(D,EN,CS,Q);
   input EN,CS;
	input [3:0]D;
	output [3:0]Q;
	reg [3:0]Q;
	
	always@(EN or CS or D)begin
		if(CS==1'b0)
		   if(EN==1'b1)Q<=D;
	end
endmodule
```
