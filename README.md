# Digital-Signal-Processing--FIR-BAND-STOP-FILTER-DESIGN
## AIM:
To generate design of Band Stop FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Stop filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 
```
clc;            
clear all;      
close all;      

Wc1 = input('Enter the value of Wc1 = ');  
Wc2 = input('Enter the value of Wc2 = ');  
N   = input('Enter the value of N = ');   

alpha = (N-1)/2;  
eps = 0.001;  

% Band Pass Filter Coefficient
n = 0:1:N-1;  

hd = (sin(Wc2*(n - alpha + eps)) - sin(Wc1*(n - alpha + eps))) ...
     ./ (pi*(n - alpha + eps));

% Hanning (Hann) Window Sequence
wh = 0.5 - 0.5*cos(2*pi*n/(N-1));

% Final impulse response
hn = hd .* wh;  

% Frequency response
w = 0:0.01:pi;  
h = freqz(hn, 1, w);  

% Plot
plot(w/pi, abs(h), 'b');
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Band Pass Filter using Hanning Window');
grid on;
```

## OUTPUT:

<img width="1918" height="1040" alt="image" src="https://github.com/user-attachments/assets/dba4c514-c327-4a80-a35f-0271be2859ff" />


## RESULT:

<img width="1600" height="633" alt="image" src="https://github.com/user-attachments/assets/6307fedb-9a47-4e5a-8dde-da10fd911bb6" />

