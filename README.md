# 16-bit-Multiplier
module main(A,B,C,D,W,X,Y,Z,product1,a1,a2,a3,a4);

input [3:0] A; 
input [3:0] B;
input [3:0] C;
input [3:0] D;
input [3:0] W;
input [3:0] X;
input [3:0] Y;
input [3:0] Z;

output [32:0] product1;
output a1,a2,a3,a4;

wire [7:0] P;
wire [7:0] Q;
wire [7:0] R;
wire [7:0] S;

wire [7:0] E;
wire [7:0] F;
wire [7:0] G;
wire [7:0] H;

wire [7:0] I;
wire [7:0] J;
wire [7:0] K;
wire [7:0] L;

wire [7:0] M;
wire [7:0] N;
wire [7:0] O;
wire [7:0] T;

wire [19:0] w_1;
wire [19:0] x_1;
wire [19:0] y_1;
wire [19:0] z_1;

fourbitmul mul1(P,W,A);
fourbitmul mul2(Q,W,B);
fourbitmul mul3(R,W,C);
fourbitmul mul4(S,W,D);
fourbitmul mul5(E,X,A);
fourbitmul mul6(F,X,B);
fourbitmul mul7(G,X,C);
fourbitmul mul8(H,X,D);
fourbitmul mul9(I,Y,A);
fourbitmul mul10(J,Y,B);
fourbitmul mul11(K,Y,C);
fourbitmul mul12(L,Y,D);
fourbitmul mul13(M,Z,A);
fourbitmul mul14(N,Z,B);
fourbitmul mul15(O,Z,C);
fourbitmul mul16(T,Z,D);

bit_twenty part1(P,Q,R,S,w_1,a1);
bit_twenty part2(E,F,G,H,x_1,a2);
bit_twenty part3(I,J,K,L,y_1,a3);
bit_twenty part4(M,N,O,T,z_1,a4);


final final1(w_1,x_1,y_1,z_1,product1);	 

endmodule




module final(w_,x_,y_,z_,product);

inout [19:0] w_;
inout [19:0] x_;
inout [19:0] y_;
inout [19:0] z_;
output [32:0] product;

wire  c1,c2,c3,c4,c5,c6,c7,c8,c9,c10,c11,c12,c13,c14,c15,c16,c17,c18,c19,c20,
          c21,c22,c23,c24,c25,c26,c27,c28,c29,c30,c31,c32;	



wire  u1,u2,u3,u4,u5,u6,u7,u8,u9,u10,u11,u12,u13,u14,u15,u16,u17,u18,u19,u20,
          u21,u22,u23,u24,u25,u26,u27,u28,u29,u30,u31,u32,u33,u34,u35,u36,u37,u38,
          u39,u40,u41,u42,u43,u44,u45,u46,u47,u48,u49,u50,u51,u52,u53,u54,u55,u56,
          u57,u58,u59;

assign product[0]=(w_[0]);
assign product[1]=(w_[1]);
assign product[2]=(w_[2]);
assign product[3]=(w_[3]);
HA HA1 (product[4],u1, w_[4],x_[0]);



FA FA1 (product[5],u2, w_[5],x_[1],u1);
FA FA101 (product[6],u3,u2, w_[6],x_[2]);
FA FA102 (product[7],u4, w_[7],x_[3],u3);
FA FA100(c1,u5,u4,w_[8],x_[4]);
HA HA5 (product[8],u6, c1,y_[0]);
FA FA2(c2,u7,u5,u6,w_[9]);
FA FA3(product[9],u8,c2,x_[5],y_[1]);
FA FA4(c3,u9,u7,u8,w_[10]);
FA FA5(product[10],u10,c3,x_[6],y_[2]);
FA FA6(c4,u11,u9,u10,w_[11]);
FA FA7(product[11],u12,c4,x_[7],y_[3]);
FA FA8(c5,u13,u11,u12,w_[12]);
FA FA9(c6,u14,c5,x_[8],y_[4]);
HA HA6(product[12],u15,c6,z_[0]);
FA FA10(c7,u16,u13,u14,u15);
FA FA11(c8,u17,c7,w_[13],x_[9]);
FA FA12(product[13],u18,c8,y_[5],z_[1]);
FA FA13(c9,u19,u16,u17,u18);
FA FA14(c10,u20,c9,w_[14],x_[10]);
FA FA15(product[14],u21,c10,y_[6],z_[2]);
FA FA16(c11,u22,u19,u20,u21);
FA FA17(c12,u23,c11,w_[15],x_[11]);
FA FA18(product[15],u24,c12,y_[7],z_[3]);
FA FA19(c13,u25,u22,u23,u24);
FA FA20(c14,u26,c13,w_[16],x_[12]);
FA FA21(product[16],u27,c14,y_[8],z_[4]);
FA FA22(c15,u28,u25,u26,u27);
FA FA23(c16,u29,c15,w_[17],x_[13]);
FA FA24(product[17],u30,c16,y_[9],z_[5]);
FA FA25(c17,u31,u28,u29,u30);
FA FA26(c18,u32,c17,w_[18],x_[14]);
FA FA27(product[18],u33,c18,y_[10],z_[6]);
FA FA28(c19,u34,u31,u32,u33);
FA FA29(c20,u35,c19,w_[19],x_[15]);
FA FA30(product[19],u36,c20,y_[11],z_[7]);
FA FA31(c21,u37,u34,u35,u36);
FA FA32(c22,u38,c21,x_[16],y_[12]);
HA HA7(product[20],u39,c22,z_[8]);
FA FA33(c23,u40,u37,u38,u39);
FA FA34(c24,u41,c23,x_[17],y_[13]);
HA HA8(product[21],u42,c24,z_[9]);
FA FA35(c25,u43,u40,u41,u42);
FA FA36(c26,u44,c25,x_[18],y_[14]);
HA HA9(product[22],u45,c26,z_[10]);
FA FA37(c27,u46,u43,u44,u45);
FA FA38(c28,u47,c27,x_[19],y_[15]);
HA HA10(product[23],u48,c28,z_[11]);
FA FA39(c29,u49,u46,u47,u48);
FA FA40(product[24],u50,c29,y_[16],z_[12]);

FA FA111(c30,u51,u49,u50,y_[17]);
HA HA41(product[25],u52,c30,z_[13]);
FA FA121(c31,u53,u51,u52,y_[18]);
HA HA42(product[26],u54,c31,z_[14]);
FA FA131(c32,u55,u53,u54,y_[19]);
HA HA43(product[27],u56,c32,z_[15]);

FA FA44(product[28],u57,u55,u56,z_[16]);
HA HA14(product[29],u58,u57,z_[17]);
HA HA15(product[30],u59,u58,z_[18]);
HA HA16(product[31],product[32],u59,z_[19]);

endmodule

module bit_twenty(P,Q,R,S,w_,u76);

input [7:0] P;
input [7:0] Q;
input [7:0] R;
input [7:0] S;

output u76;
output [19:0] w_;

wire  u61,u62,u63,u64,u65,u66,u67,u68,u69,u70,u71,u72,u73,u74,u75;

assign w_[0]=P[0];
assign w_[1]=P[1];
assign w_[2]=P[2];
assign w_[3]=P[3];

HA HA18(w_[4],u61,P[4],Q[0]);
FA FA46 (w_[5],u62,u61,P[5],Q[1]);
FA FA47 (w_[6],u63,u62,P[6],Q[2]);
FA FA48 (w_[7],u64,u63,P[7],Q[3]);
FA FA49 (w_[8],u65,u64,Q[4],R[0]);
FA FA50 (w_[9],u66,u65,Q[5],R[1]);
FA FA51 (w_[10],u67,u66,Q[6],R[2]);
FA FA52 (w_[11],u68,u67,Q[7],R[3]);
FA FA53 (w_[12],u69,u68,R[4],S[0]);
FA FA54 (w_[13],u70,u69,R[5],S[1]);
FA FA55 (w_[14],u71,u70,R[6],S[2]);
FA FA56 (w_[15],u72,u71,R[7],S[3]);
HA HA19 (w_[16],u73,u72,S[4]);
HA HA20 (w_[17],u74,u73,S[5]);
HA HA21 (w_[18],u75,u74,S[6]);
HA HA22 (w_[19],u76,u75,S[7]);

endmodule 



module fourbitmul(answer,one,two);

input [3:0] one;
input [3:0] two;

output [7:0] answer;

wire x1,x2,x3,x4,x5,x6,x7,x8,x9,x10,x11,x12,x13,x14,x15,x16,x17;    

assign answer[0]= (one[0]&two[0]);             
HA HA23(answer[1],  x1,  (one[1] & two[0]),  (one[0] & two[1]));
FA FA57(x2,  x3,  (one[2] & two[0]),  (one[1] & two[1]),  x1);
HA HA24(answer[2],  x4,  x2,  (one[0] & two[2]));
FA FA58(x5,  x6,  (one[3] & two[0]),  x4,  x3);
FA FA59(x7,  x8,  (one[2] & two[1]),  (one[1] & two[2]),  x5);
HA HA25(answer[3],  x9,  x7,  (one[0] & two[3]));
FA FA60(x10,  x11,  x6,  x8,  x9);
FA FA61(x12,  x13,  x10,  (one[3] & two[1]),  (one[2] & two[2]));
HA HA26(answer[4],  x14,  x12,  (one[1] & two[3]));
FA FA62(x15,  x16,  x11,  x13,  x14);
FA FA63(answer[5],  x17,  x15,  (one[3] & two[2]),  (one[2] & two[3]));
FA FA64(answer[6],  answer[7],  x16,  (one[3] & two[3]),  x17); 

endmodule

module HA(sout,cout,a,b);

output sout,cout;

input a,b;

assign sout = a^b;
assign cout = (a&b);

endmodule


module FA(sout,cout,a,b,cin);

output sout,cout;

input a,b,cin;

assign sout =(a^b^cin);
assign cout = ((a&b)|(a&cin)|(b&cin));

endmodule
