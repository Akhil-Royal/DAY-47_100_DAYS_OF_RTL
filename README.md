# DAY-47_100_DAYS_OF_RTL
//FACTORIAL CALCULATION

module FactorialCalculator (
    input [3:0] n,
    output reg [31:0] factorial
);
    integer i;
    always @(*) begin
        factorial = 1;
        for (i = 1; i <= n; i = i + 1) begin
            factorial = factorial * i;
        end
    end
endmodule

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

// Testbench for Factorial Calculator
module FactorialCalculator_tb;
    reg [3:0] n;
    wire [31:0] factorial;
    
    FactorialCalculator uut (
        .n(n),
        .factorial(factorial)
    );
    
    initial begin
        $monitor("n = %d, Factorial = %d", n, factorial);
        
        // Test Cases
        n = 0; #10;
        n = 1; #10;
        n = 3; #10;
        n = 5; #10;
        n = 7; #10;
        
        $finish;
    end
endmodule
