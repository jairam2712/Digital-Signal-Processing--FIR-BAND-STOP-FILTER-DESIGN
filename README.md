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
clear;
close all;

% Given parameters
M = 21;
n = 0:M-1;
alpha = (M-1)/2;

w1 = pi/4;        % Lower cutoff
w2 = 7*pi/9;      % Upper cutoff

% Ideal Band-Stop impulse response (no if-else using sinc)
hd = sinc(n - alpha) ...
     - (w2/pi)*sinc((w2/pi)*(n - alpha)) ...
     + (w1/pi)*sinc((w1/pi)*(n - alpha));

% Bartlett window
w = bartlett(M)';

% Final FIR filter
h = hd .* w;

% Frequency response
[H, W] = freqz(h, 1, 1024);



% Magnitude response
figure;
plot(W/pi, abs(H));
title('Magnitude Response');
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('|H(e^{j\omega})|');
grid on;
```
## OUTPUT:
![WhatsApp Image 2026-04-09 at 11 14 32 PM](https://github.com/user-attachments/assets/9048e6b8-c1d8-4259-b7c0-7b3cecfb046a)

## RESULT:
![WhatsApp Image 2026-04-09 at 11 12 44 PM](https://github.com/user-attachments/assets/1b54de5e-bd4c-4a13-bc87-41e8388f0a53)
