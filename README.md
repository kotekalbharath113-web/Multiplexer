module mux_8(Y,S,I,A);
input[7:0]I;
selector lines[3:0]S;
wires[7:1]w;
output Y;
mux_2 n1(w[2], S[0], 1'b1, 1'b0);
mux_2 n2(w[3], S[0], w[1], 1'b1);
mux_2 n3(w[4], S[0], 1'b0, 1'b1);
mux_2 n4(w[5], S[0], 1'b0, A);
mux_2 n5(w[6], S[1], w[2], w[3]);
mux_2 n6(w[7], S[1], w[4], w[5]);
mux_2 n7(w[], S[2], w[6], w[7]);
endmodule
