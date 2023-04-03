// Code your design here
module vending_machine(clk,rst,in,out,change);
  input clk;
  input rst;
  input [1:0]in;//01=5 10=10
  output reg out ;
  output reg [1:0] change ;
  
  parameter s0 = 2'b00;
  parameter s1 = 2'b01;
  parameter s2 = 2'b10;
  
  reg [1:0] cs,ns;
  
  always @(posedge clk)
    begin
      if(rst)
        begin 
          cs=0;
          ns=0;
          change = 0;
        end
      
      else 
        begin
          cs=ns;
          
          case(cs)
            s0: if(in==0)
              begin
                ns=s0;
                out=0;
                change=0;
        	  end
            
            else if(in==2'b01)
              begin
              ns=s1;
               out=0;
                change=0;
              end
            else if(in==2'b10)
              begin
              ns=s2;
               out=0;
                change=0;
              end
            
            s1: if(in==0)
              begin
                ns=s1;
                out=0;
                change=0;
        	  end
            
            else if(in==2'b01)
              begin
              ns=s2;
               out=0;
                change=0;
              end
            else if(in==2'b10)
              begin
                change=2'b00;
              ns=s0;
               out=1;
             //   change=2'b00;
                
              end
            
            
            s2: if(in==0)
              begin
                ns=s2;
                out=0;
                change=0;
        	  end
            
            else if(in==2'b01)
              begin
              ns=s0;
               out=1;
                change=2'b00;
                //rst=1;
              end
            else if(in==2'b10)
              begin
                change=2'b01;
              ns=s0;
               out=1;
                //rst=1;
              end
            
          endcase
         // cs=ns;
                
        end
    end
endmodule
