# Project

### Brainstorming Problem Statements & Applications

gesture recognition via sEMG and replication on a prosthetic (would need a C# software developer to interperet the output of the design and simulate the control signals on a prosthetic virtually)

ECG analysis (arrhythmia detection) - low cost ECG product alternative (potential applications to another proposed DTE project with increasing access to high quality ECGs)

fECG - fetal ECG signals are more difficult and the filtering would be far more complex to incorporate (Adapative Noise Cancellation) to filter out the often stronger maternal ECG signal

Electrical Impedance Tomography (EIT)
- non-invasive imaging (often lungs/thorax)
- precise signal generation (Direct Digital Synths/CORDIC)
- and simultaneous DAQ while driving these signals
- END product would be real-time video capture of patient's internals while breathing, etc
  - really need to explore this one it is super cool and if we could also render the output on a graphical interface this would be nuts - peripherals and sensors are the biggest holdup on this one i believe

High-Performance Phonocardiography
    -- recording sound of heartbeat while filtering lung noises and ambient noise - again the sensors and contacts are a big part of this but being able to extract patient heartbeat (also ideally as a low-cost alternative to existing tech) would be super cool
    

[sEMG cheap sensor](https://www.amazon.com/AD8232-Module-Measurement-Monitoring-Sensor/dp/B0GDXF4JGZ/ref=sr_1_2?channelId=500&clpRedir=Y&dib=eyJ2IjoiMSJ9.B7Jnuc9P10CrhQcb2EAU0HBfAPzHfhPTLgn0bTE50m0M27yiduv2BV80Fe0Btp1cDb4Ln6RK2Sx2riZ_8FsxqXFq8fqYThjnQVtVXhrOZ_u3iyUqj80XbOgfhCpWKY6E3dMasGmoEyNj5uG2RZbpGgLrUt-hnq80aAVKJOHSpCh1vjQwiOJUYSH82i7yXG4LyKus8AhkEcye3HRlf2UVtJMBmLJ61Nda7I0mnPek114.yNkM7BJtzypy6Bi-fBRa7wSP9ShqfKMAZygwPqy8kB0&dib_tag=se&keywords=emg+sensor&plpRedirect=mhFallback&qid=1790705725&sr=8-2)

### Features List

sEMG sensors --> ADC / Instrumentation Amplifier --> FPGA filtering, rectification, feature extraction --> ML classification --> communication of information to a visual interface via HDMI? could also implement a software backend connection

focus on accelerating inference time on biosignals from a standard ML CPU workflow or microcontroller to FPGA-based system

### Development Environment
* Verilator linter, all code written in systemverilog, CI/CD github pipeline to run basic sanity check verification on each commit/push
* use ECE servers (vivado) to synthesize and compile designs
* Questa and Jasper and/or VC formal licenses can be used on remote server for verification as well
* any pure software will be developed within the same project under a different directory
* machine learning logic can be run on the arm cortex on chip/ networking/control logic while the high-speed acquisition system can be done through the fpga

### Available Technologies
* raspberry PI, Zedboard development board with Zynq SoC module and unified memory, ethernet, GPIO, AV connection, hdmi/vga video connections