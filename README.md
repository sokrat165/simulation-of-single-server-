Data Organization:
A pandas DataFrame named simulation_Table is created to store information about each customer, including:
interarrival_time: The original list.
arrival_time: The time each customer arrives in the system.
server_time: The original list showing service time per customer.
time_service_begins: The time when service starts for each customer.
time_service_end: The time when service ends for each customer.
waiting_time: How long each customer waits before service begins.
time_customer_in_systeam: How long each customer spends in the system (including waiting and service time).
ideal_time: Ideal time (when the server is idle) between customers.
Arrival Time Calculation:
A new column arrival_time is added to the DataFrame.
It calculates the cumulative sum of interarrival times to determine the arrival time of each customer relative to the start of the simulation.
Simulation Loop:
The code iterates through each row (customer) in the DataFrame.
For the first customer:
Service end time is simply the service time since there's no waiting.
For subsequent customers:
The code checks if the previous customer's service ends before or after the current customer's arrival.
Based on the comparison, it calculates the service start and end times for the current customer.
Waiting time for each customer is calculated (service start time minus arrival time).
Time spent in the system for each customer is calculated (service end time minus arrival time).
Ideal time (server idle time) between customers is calculated, considering gaps between service completions and the next customer's arrival.
Output:
The code prints the final state of the simulation_Table DataFrame. This DataFrame can be used to analyze performance metrics like average waiting time or server utilization.
