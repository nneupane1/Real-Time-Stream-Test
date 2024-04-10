import random
import datetime
import matplotlib.pyplot as plt
import matplotlib.animation as animation

# Initialize the values for the plot
num_iterations = 300
timestamps = []
battery_temps = []
battery_charges = []
initial_soc = []
final_soc = []
vehicle_speeds = []  # Added vehicle speeds

# Initialize the start time
start_time = datetime.datetime.now()

# Create the figure and axis with double size
fig, axs = plt.subplots(5, 1, figsize=(10, 10))  # Default size is (5, 4)

# Create line for Battery Temperature
line_temp, = axs[0].plot([], [], 'g-')
axs[0].set_xlim(0, num_iterations)
axs[0].set_ylim(0, 100)
axs[0].set_xlabel('Time (seconds)')
axs[0].set_ylabel('Battery Temperature')
axs[0].set_title('Battery Temperature Over Time')

# Create line for Battery Charge
line_charge, = axs[1].plot([], [], 'r-')
axs[1].set_xlim(0, num_iterations)
axs[1].set_ylim(0, 100)
axs[1].set_xlabel('Time (seconds)')
axs[1].set_ylabel('Battery Charge')
axs[1].set_title('Battery Charge Over Time')

# Create line for Initial SOC
line_initial_soc, = axs[2].plot([], [], 'b-')
axs[2].set_xlim(0, num_iterations)
axs[2].set_ylim(0, 100)
axs[2].set_xlabel('Time (seconds)')
axs[2].set_ylabel('Initial SOC')
axs[2].set_title('Initial SOC Over Time')

# Create line for Final SOC
line_final_soc, = axs[3].plot([], [], 'y-')
axs[3].set_xlim(0, num_iterations)
axs[3].set_ylim(0, 100)
axs[3].set_xlabel('Time (seconds)')
axs[3].set_ylabel('Final SOC')
axs[3].set_title('Final SOC Over Time')

# Create line for Vehicle Speed
line_vehicle_speed, = axs[4].plot([], [], 'c-')  # Added vehicle speed
axs[4].set_xlim(0, num_iterations)
axs[4].set_ylim(0, 100)
axs[4].set_xlabel('Time (seconds)')
axs[4].set_ylabel('Vehicle Speed')
axs[4].set_title('Vehicle Speed Over Time')

# Function to generate the data
def generate_data(i):
    timestamp = (datetime.datetime.now() - start_time).total_seconds()
    battery_temp = random.uniform(0, 100)
    battery_charge = random.uniform(0, 100)
    initial_soc_value = random.uniform(0, 100)
    final_soc_value = initial_soc_value + random.uniform(-10, 10)  # Final SOC is usually close to Initial SOC
    vehicle_speed = random.uniform(0, 100)  # Added vehicle speed
    
    timestamps.append(timestamp)
    battery_temps.append(battery_temp)
    battery_charges.append(battery_charge)
    initial_soc.append(initial_soc_value)
    final_soc.append(final_soc_value)
    vehicle_speeds.append(vehicle_speed)  # Added vehicle speed
    
    # Update the line data
    line_temp.set_xdata(timestamps)
    line_temp.set_ydata(battery_temps)
    
    line_charge.set_xdata(timestamps)
    line_charge.set_ydata(battery_charges)
    
    line_initial_soc.set_xdata(timestamps)
    line_initial_soc.set_ydata(initial_soc)
    
    line_final_soc.set_xdata(timestamps)
    line_final_soc.set_ydata(final_soc)
    
    line_vehicle_speed.set_xdata(timestamps)  # Added vehicle speed
    line_vehicle_speed.set_ydata(vehicle_speeds)  # Added vehicle speed
    
    return line_temp, line_charge, line_initial_soc, line_final_soc, line_vehicle_speed,  # Added vehicle speed

# Create the animation
ani = animation.FuncAnimation(fig, generate_data, frames=range(num_iterations), blit=True)

plt.tight_layout()
plt.show()
