# EXP 6 : SIMULATION OF MULTIRATE DSP WITHOUT FUNCTION 

## AIM: 

To perform and verify multirate DSP without function using SCILAB.

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM : 
```
clear;
clc;
close;

// Time index
n = 0 : %pi/50 : 2*%pi;

// Original signal
x = sin(%pi * n);

// Input downsampling & upsampling factors
M = input("Enter the downsampling factor M: ");
L = input("Enter the upsampling factor L: ");

// -------------------- DOWN SAMPLING --------------------
downsampling_x = x(1:M:length(x));

disp(x, "Input signal x(n) = ");
disp(downsampling_x, "Downsampled Signal = ");

figure(1);
subplot(2,1,1);
plot2d3(1:length(x), x);
xtitle("Original Signal");

subplot(2,1,2);
plot2d3(1:length(downsampling_x), downsampling_x);
xtitle("Downsampled Signal (Factor M)");


// -------------------- UPSAMPLING --------------------
upsampling_x = zeros(1, L * length(x));  // allocate memory

for i = 1:length(x)
    upsampling_x(L*(i-1) + 1) = x(i);
end

disp(upsampling_x, "Upsampled Signal = ");

figure(2);
subplot(2,1,1);
plot2d3(1:length(x), x);
xtitle("Original Signal");

subplot(2,1,2);
plot2d3(1:length(upsampling_x), upsampling_x);
xtitle("Upsampled Signal (Factor L)");
```

## OUTPUT: 
<img width="400" height="116" alt="image" src="https://github.com/user-attachments/assets/e956401e-b1c9-48eb-a259-285f72e8570d" />
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/2c6b1d33-cb61-4a56-89dd-da9a41fd54dd" />
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/4f186dbb-0bcc-4347-b474-d805bb92f10c" />





## RESULT: 
Thus the decimation process by a factor M and interpolation process by a factor L using 
SCILAB was implemented. 
