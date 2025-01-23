# Hardware-Accelerated Obstacle Detection for Autonomous Vehicles

## Overview
This project focuses on developing a **Hardware-Accelerated Obstacle Detection System** for autonomous vehicles using the **Zynq 7000 FPGA development board**. The goal was to implement the **Sobel Edge Detection Algorithm** to accelerate image processing and achieve real-time obstacle detection. By leveraging FPGA-based acceleration, we achieved significant performance improvements compared to software-only solutions.

## Project Objectives
- Implement the **Sobel Edge Detection Algorithm** for real-time image processing.
- Profile the software implementation to identify performance bottlenecks.
- Develop a **custom hardware IP block** to accelerate critical computations.
- Integrate the hardware accelerator with the Zynq processing system via AXI interfaces.
- Compare the performance of hardware-accelerated implementation against software-only execution.

## System Architecture

The project follows a **hardware-software co-design** approach:

1. **Software-Only Implementation (Baseline):**
   - Implemented the Sobel algorithm using Vivado HLS.
   - Profiling performed to analyze execution times and identify performance-critical sections.

2. **Hardware Acceleration:**
   - A custom IP block was created for Sobel filtering using Vivado HLS.
   - Optimization techniques such as **loop unrolling, pipelining, and parallel processing** were applied.
   - The custom IP was integrated with the processing system (PS) via **AXI interfaces**.

3. **Integration & Testing:**
   - The system was tested with real-time video input.
   - Performance evaluation was conducted to compare software-only vs. hardware-accelerated implementations.

## Implementation Steps

1. **Software Profiling:**
   - Implemented Sobel filtering in software.
   - Profiled performance using Vivado HLS to determine bottlenecks.

2. **Hardware IP Design:**
   - Developed a custom IP block to offload edge detection computations to the FPGA.
   - Optimized the IP using HLS directives for efficient execution.

3. **PS-PL Communication:**
   - Configured AXI4 interfaces for seamless communication between the ARM processor and FPGA fabric.

4. **Testing and Optimization:**
   - Verified functional correctness using test images.
   - Measured frame processing time and resource utilization.

## Tools and Technologies Used
- **Hardware:** Zynq 7000 FPGA Development Board
- **Software:** Xilinx Vivado 2016.3, Vivado HLS
- **Programming Languages:** C/C++ (for HLS), Python (for testing)
- **Interfaces:** AXI4-Lite (control), AXI4-Stream (data transfer)

## Performance Results
- The hardware-accelerated design achieved **significant speedup** compared to the software-only implementation.
- Frame processing times were reduced, enabling real-time processing suitable for autonomous vehicle applications.
- Optimized resource utilization within FPGA fabric to achieve a balance between power efficiency and performance.

## Challenges Faced
- **AXI Interface Configuration:** Ensuring efficient data transfer between PS and PL.
- **Timing Optimization:** Achieving real-time constraints while maintaining accuracy.
- **Debugging Hardware IP:** Verifying correctness and performance under varying conditions.

## Future Improvements
- Integrating a **machine learning (ML) model** to classify detected obstacles.
- Implementing additional hardware accelerators for improved feature extraction.
- Optimizing power consumption for energy-efficient operation in embedded environments.

## How to Run the Project

1. Clone the repository and set up the Vivado environment.
2. Load the HLS project in Vivado HLS and synthesize the Sobel IP.
3. Import the generated IP into Vivado and connect it via AXI interfaces.
4. Generate the bitstream and program the Zynq board.
5. Run the provided C code on the ARM processor to initiate processing.

## Contributors
- Aizah Ahmed
- Hassan Ahmad
- Tyler Belluomini

## License
This project is licensed under the MIT License. Feel free to use and modify for educational purposes.

## Contact
For questions or contributions, please contact azhahd13@outlook.com , hassanahmad.eng@gmail.com , tbelluom@uoguelph.ca 
