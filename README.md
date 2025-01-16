module ALU (
    input [7:0] A,      // 8-bit input A
    input [7:0] B,      // 8-bit input B
    input [2:0] Op,     // 3-bit operation selector
    output reg [7:0] Result, // 8-bit output result
    output Zero         // Zero flag
);

    always @(*) begin
        case (Op)
            3'b000: Result = A + B;    // Addition
            3'b001: Result = A - B;    // Subtraction
            3'b010: Result = A & B;    // AND
            3'b011: Result = A | B;    // OR
            3'b100: Result = ~A;       // NOT
            default: Result = 8'b0;    // Default to zero
        endcase
    end

    assign Zero = (Result == 8'b0) ? 1'b1 : 1'b0;

endmodule# ARITHMETIC-LOGIC-UNIT-ALU-
