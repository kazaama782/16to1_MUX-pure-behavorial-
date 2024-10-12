# 16to1_MUX-pure-behavorial




`timescale 1ns / 1ps


module MUX16to1(out, in, sel);
  input [15:0] in;    
  input [3:0] sel;    
  output out;         
  
  assign out = in[sel];

endmodule



Testbench :-

`timescale 1ns / 1ps


module muxtest;
reg [15:0]A;
reg [3:0]S;
wire F;
MUX16to1 uut(.out(F),.in(A),.sel(S));
initial
begin

$monitor($time,"F=%h,A=%h,S=%h",F,A,S);
#5 A=16'h3f0a; S=4'h0;
#5 S=4'h2;
#5 S=4'h6;
#5 $finish;
end
endmodule
