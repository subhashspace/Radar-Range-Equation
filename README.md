# Radar-Range-Equation

### Aim:

To calculate the maximum range of a radar system using the Radar Range equation and verify through Python Programming.

---

### Theory:

The Radar Range Equation is a fundamental formula used in radar system design to determine the maximum range at which a radar can detect a target. It is given by:

$$R_{max} = \left(\frac{P_t G \sigma A_e}{(4 \pi)^2 S_min} \right)^{\frac{1}{4}}$$

---

### Procedure:

1. Set Up the Python Enviroment:Ensure that Pytho is installed on your system. You can use Anaconda for managing Python packages and environments, or any other Python IDE of your choice.
2. Import Necessary Libraries: Import the math library in Python.
3. Define the Radar Range Equation Function: Create a function to calculate the maximum range using the Radar Range Equation.
4. Input Parameters for the Radar System: Define the input parameters such as transmitted power, transmitter gain, receiver gain, radar frequency, radar cross section and minimum detectable power.
5. Calculate the Maximum Range: Use the function to calculate the maximum range of the radar.
6. Execute the program: Run the Python script to calculate and display the maximum range of the radar.

---

### Program:

```sci
G = 40;
eta = 0.5;
Ae = 1;

Smin = 1e-10;

Ppeak= 2000:100:10000; 

Rmax_values = zeros(1, length(Ppeak));

for i = 1:length(Ppeak)
    Rmax_values(i) = ((Ppeak(i) * G * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

clf;
subplot(3,1,1);
plot(Ppeak, Rmax_values,'b');
xlabel('P_{peak}');
ylabel('R_{max}');

clear "G" "Rmax_values" "Ppeak";
Ppeak = 5000;
G = 10:5:100;
Rmax_values = zeros(1, length(G));

for i = 1:length(G)
    Rmax_values(i) = ((Ppeak * G(i) * eta * Ae) / (16 * %pi^2 * Smin))^(1/4);
end

subplot(3,1,2);
plot(G, Rmax_values,'r');
xlabel("G");
ylabel("R_{max}");

clear "G" "Rmax_values" "Smin";
G = 40;
Smin_values = logspace(-12, -8, 50);
Rmax_values = zeros(1, length(Smin_values));

for i = 1:length(Smin_values)
    Rmax_values(i) = ((Ppeak * G * eta * Ae) / (16 * %pi^2 * Smin_values(i)))^(1/4);
end

subplot(3,1,3);
plot(Smin_values, Rmax_values,'g');
xlabel("S_{min}");
ylabel("R_{max}");
```

---

### Output Waveform:

<img width="1536" height="800" alt="image" src="https://github.com/user-attachments/assets/5e62b980-a4e7-4bda-bf49-27824e761b6a" />


---

### Manual Calculation:

asdfghj

---

### Result:

Thus, the value of maximum range of a radar of a radar system calculated using the Radar Equation is successfully verified using Scilab programming.
