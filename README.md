# Experiment-6-Integrate-sensors-to-monitor-vehicle-components

## AIM
To develop an embedded IoT-based predictive maintenance system for an electric vehicle by integrating sensors that monitor battery health, motor temperature, and brake wear and analyze the data for maintenance prediction.
 

## PROCEDURE

1.	Simulate Sensor Data 

o	Generate battery health, motor temperature, and brake wear data.

2.	Analyze Trends 

o	Detect if any sensor crosses predefined maintenance thresholds.

3.	Predict Maintenance Needs 

o	If any component shows abnormal behavior, flag it for preventive maintenance.

4.	Visualize Data with Graphs 

o	Plot sensor readings and highlight maintenance limits.

5.	Display Alerts 

o	Output maintenance warnings based on real-time sensor data analysis.

 

## THEORY

1. Predictive Maintenance in EVs

•	Battery degradation over time affects range and efficiency.

•	Motor overheating can lead to failures if not detected early.

•	Brake wear monitoring ensures vehicle safety.

2. IoT and Data Analytics Role

•	Real-time monitoring of EV components using embedded sensors.

•	Threshold-based predictions help prevent breakdowns.

•	Graphs help visualize component performance over time.

## PROGRAM

clear; clc; close all;


%% Simulated Time (100 samples)

time = linspace(0, 10, 100); 


%% Simulated Sensor Data

battery_health = 100 - 2*time + 3*sin(0.5*time);  % Battery health (%)

motor_temp = 40 + 10*sin(time); % Motor temperature (°C)

brake_wear = 5 + 0.3*time + 2*sin(0.3*time); % Brake wear (%)


%% Predict Maintenance Need (Thresholds)

battery_threshold = 60;  % Battery needs maintenance if below 60%

motor_temp_threshold = 70;  % Motor needs check if temp exceeds 70°C

brake_threshold = 15;  % Brake needs check if wear exceeds 15%

maintenance_flag = (battery_health < battery_threshold) | ...

                   (motor_temp > motor_temp_threshold) | ...
                   (brake_wear > brake_threshold);


%% Plot Sensor Data

figure;


subplot(3,1,1);

plot(time, battery_health, 'b', 'LineWidth', 2);

hold on; yline(battery_threshold, 'r--', 'Battery Threshold');

title('Battery Health Over Time');

xlabel('Time (s)');

ylabel('Battery Health (%)');

grid on;


subplot(3,1,2);

plot(time, motor_temp, 'g', 'LineWidth', 2);

hold on; yline(motor_temp_threshold, 'r--', 'Temp Threshold');

title('Motor Temperature Over Time');

xlabel('Time (s)');

ylabel('Temperature (°C)');

grid on;


subplot(3,1,3);

plot(time, brake_wear, 'm', 'LineWidth', 2);

hold on; yline(brake_threshold, 'r--', 'Brake Wear Limit');

title('Brake Wear Over Time');

xlabel('Time (s)');

ylabel('Wear (%)');

grid on;

%% Display Maintenance Predictions

fprintf('Predictive Maintenance Alert:\n');

if any(maintenance_flag)

    disp('⚠️ Maintenance Needed for Vehicle Components! ⚠️');

else

    disp('✅ All systems are operating within safe limits.');

end

## OUTPUT

<img width="1600" height="847" alt="image" src="https://github.com/user-attachments/assets/09f41697-7a9d-468b-b3e6-7f79cada5606" />


<img width="1038" height="221" alt="image" src="https://github.com/user-attachments/assets/f8d05c27-1c6d-4012-be4a-75c8f3127485" />

 
## RESULT

✅ The MATLAB simulation successfully predicts maintenance needs in an electric vehicle.

✅ The system detects potential failures in battery, motor, and brakes.

✅ Graphical analysis provides a clear view of component health.
 



