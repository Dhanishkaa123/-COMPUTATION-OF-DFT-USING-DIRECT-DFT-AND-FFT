
# EXP 2 : COMPUTATION OF DFT USING DIRECT DFT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
DFT program


    clc;
    clear;
    xn=[1 1 1 1 0 0 2 1];
    n1=0:1:length(xn)-1
    subplot(3,1,1)
    plot2d3(n1,xn);
    xlabel('Time n');
    ylabel('Amplitude xn');
    title('Input sequence');
    j=sqrt(-1);
    N=length(xn);
    Xk=zeros(1,N);
    for k=0:N-1
    for n=0:N-1
        Xk(k+1)=Xk(k+1)+xn(n+1)*exp((-j*2*%pi*k*n)/N);
        
    end
    end
     disp(Xk)

    K1 = 0:1:length(Xk)-1;
    magnitude = abs(Xk);

    subplot(3,1,2);
    plot2d3(K1, magnitude);
    xlabel('frequency(Hz)');
    ylabel('magnitude(gain)');
    title('magnitude spectrum');

    angle = atan(imag(Xk)./real(Xk))

    subplot(3,1,3);
    plot2d3(K1, angle);
    xlabel('frequency(Hz)');
    ylabel('Phase');
    title('Phase spectrum');



FFT Program:

    clear;
    clc;
    close;
    xn = [1 2 4 1 2 4 2 1];
    n1 = 0:1:length(xn)-1;

    subplot(2,2,1);
    plot2d3(n1,xn);

    xlabel('Time n');
    ylabel('Amplitude');
    title('Input Sequence');


    Xk = fft(xn);
    K1 = 0:1:length(Xk)-1;
    magnitude = abs(Xk)

    subplot(2,2,2);
    plot2d3(K1, magnitude);

    xlabel('frequency(Hz)');
    ylabel('magnitude(gain)');
    title('magnitude spectrum');

    angle = atan(imag(Xk), real(Xk))

    subplot(2,2,3);
    plot2d3(K1, angle);

    xlabel('frequency(Hz)');
    ylabel('Phase');
    title('Phase spectrum');

    y = ifft(Xk);
    n2 = 0:1:length(y)-1;

    subplot(2,2,4);
    plot2d3(n2, y);

    xlabel('Time n');
    ylabel('Amplitude');
    title('Inverse FFT OF X(K)');

# CALCULATIONS: 


<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/b1ab22c4-89ce-4edf-b484-462fc22a928e" />

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/91e460e2-c929-4ba6-9c54-35b56c8a77c4" />

<img width="1200" height="1600" alt="image" src="https://github.com/user-attachments/assets/02fccedc-5f27-4f4f-882c-fd66335d8f35" />

# SAMPLE OUTPUT: 
DFT:

<img width="1087" height="837" alt="image" src="https://github.com/user-attachments/assets/338adcff-a60c-4cfa-824f-80712e7683cc" />

FFT:

<img width="1078" height="552" alt="image" src="https://github.com/user-attachments/assets/285671ee-2e8e-42e1-9ee8-d7a6ef39237e" />

# RESULT: 
