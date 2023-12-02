```verilog
module SIXFD(clk,clk6d);
        input clk;
	output clk6d;
	reg clk6d,clk6d1,clk6d2;
	reg [499:0] cnt1,cnt2,cnt;
	
	always@(posedge clk)begin
	if(cnt1==10'd499)begin cnt1<=10'd000;clk6d1=~clk6d1;end
	else cnt1<=cnt1+10'd001;
	end
	
	always@(posedge clk6d1)begin
	if(cnt2==10'd499)begin cnt2<=10'd000;clk6d2=~clk6d2;end
	else cnt2<=cnt2+10'd001;
	end
	
	always@(posedge clk6d2)begin
	if(cnt==10'd009)begin cnt<=10'd000;clk6d=~clk6d;end
	else cnt<=cnt+10'd001;
	end
	
endmodule
```


