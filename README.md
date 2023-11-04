# Booth's Multiplication Algorithm 

Here Booth's multiplication algorithm is implemented using the tool iverilog. It is a multiplication algorithm that multiplies two signed binary numbers in 2's complement notation. Here we use the notation of a, m and Q which stands for accumulator, multiplicand and multiplier respectively. Let x represent the number of bits in Q. Booth's multiplication algorithm works as follows :  
- Fill all the bits with zeroes for accumulator. 
- In first step Q-1 is zero.
- Determine the LSB of Q and Q-1. 
  - If they are 01, find the value of a=a+m and perform arithmetic shift by 1 bit.
  - If they are 10, find the value of a=a-m and perform arithmetic shift by 1 bit.
  - If they are 00 or 11, perform arithmetic shift by 1 bit.
- Repeat the previous step for x times. 

# Compile and Run 

- iverilog -o "filename" lib.v booth_mul.v booth_mul_tb.v 
- vvp "filename"
- gtkwave booth_mul.vcd