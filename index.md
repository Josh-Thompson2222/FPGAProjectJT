---
layout: home
title: FPGA VGA Driver Project - Josh Thompson
tags: fpga vga verilog
categories: demo
---

Welcome to my FPGA Project, my name is Josh Thompson. In my SoC project, I will adapt and develop an FPGA VGA driver to display graphics on a 
640x480 display

## **Template VGA Design**
### **Project Set-Up**
The set-up for this project was relatively straightforward. Firstly I imported the required files from the moodle page. Testbench was reloacted to the simulation sources where we set it as the top layer. The first simulation I carried out was on the colourCycle design, followed by the colourStripes and finally my own unique design.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/ProjectSummary.png">


### **Template Code**

VGA uses a 15-pin D-subminiature connector arranged in three rows of five pins. It supports RGB analog signals, horizontal sync (HSYNC), and vertical sync (VSYNC). The colours within the colourCycle design were programmed in 4-bit binary code. For example the colour 
Red = R=1111, G=0000, B=0000. 

The first code template I used was the colourCycle design. This design encompasses the full 640x480 pixel screen to display a solid colour which transitions into another colour, if programmed right. In this specific design, the clock frequency was set to change the colour of the display every 
250 milliseconds. I set the clocks prescaler in the clock wizard within the design sources. 


The second template design I carried out was the colourStripes design. I found this template much easier to understand than the colourCycle. The template code that I was given splits the screen into 8 equal columns, all of different colours. The screen is 640 pixels wide, divided by 8 colours. This means that each colour stripe is 80 pixels wide and 480 tall. Firstly each section is divided into it's own column, 1/8th of the total width, then the colour of the column is managed within.

### **Simulation**
This design was simulated using Testbench. Testbench was set as the top layer in our simulation sources ahead of VGATop. When the simulation is run, the Waveform Viewer opens, displaying the signals from your design and testbench. From the waveform viewer, we are able to zoom in on specific time intervals, observe input and output signal transitions and also verify if the output matches expected behavior.
### **Synthesis**

After connecting the Basys3 board to my monitor using a vga cable, I ran implementation and connected to the device within the hardware manager. After the Basys3 board was connected to the monitor, I programmed the board and viewed the following video on the screen. 

### **Demonstration**
I have enclosed a video of my ColourCycle design running. i hav converted this from a .mov file to a .gif so it can run on github pages.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/FPGAScreenshotColCyc.png">

Video of ColourCycle

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/IMG_7630.gif">


Below is a photo of the colourStripes design connected to my monitor during a lab.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/ColourStripesSS.png">

## **My VGA Design Edit**
My idea in this project was to edit the colourStripes file to include both columns and rows. Figuring out how to work with both columns and rows added another dimension to the complexity of my code. Before I learned how to work with rows, I only knew how to arrange columns, so my idea was to design the French flag. This was a simple design as it only took ashort amount of time to calculate the total width of the screen and divide it into three equal sections for the French flag. Once divided evenly, I just had to set the colour of each sector.

My second design edit was more complex as I decided to create the Swedish flag to incorporate both columns and rows. It was fun to work out the size dimensions of the flag and incorporate that into my project to create an accurate visualistion of the flag on my own.
### **Code Adaptation**
To edit the ColourStripes code, I simply removed some existing columns and reshaped the 3 remaining ones to fit the full 640 pixel screen width. I also changed the colours of the remaining columns to the blue white and red of the France flag. Below is a screenshot of the code I edited to get this design.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/ScreenshotFranceFlagFPGA.png">

My second design required a more technical breakdown as I had to determine the size of each of the blue squares on the left-hand side, both above and below the yellow stripes. Secondly I worked out the size of the rectangles, above and below the horizontal yellow line on the right-hand side. From this it was easy to determine the space that was left, which would be occupied by the yellow line. I have attached a photo of my copy that I used to work out the exact dimensions the flag needed to be to fit on the VGA display.  

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/IMG_7698%5B1%5D.jpg">

### **Simulation**
I simulated this design using Testbench. When the simulation is run, the Waveform Viewer opens, displaying the signals from my design and testbench. From the waveform viewer, I can zoom in on specific time intervals, observe input and output signal transitions and also verify if the output matches expected behavior. In the case of simulating the Swedish flag, the output signal did match expected behaviour as predicted. 
### **Synthesis**
I ran synthesis on the design to ensure it was all working correctly and to provide a project summary to ensure it worked before running implementation and programming my board. Vivado reads and parses the verilog code, checking for syntax and logical errors. Synthesis optimizes the design to reduce resource usage and improve performance. After synthesis, Vivado provides an estimate of how many FPGA resources the design will use. 
### **Demonstration**
My first complete design edit was the French flag.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/FrenchFlagPhoto.JPG">

My final design edit was the Swedish flag.

<img src="https://raw.githubusercontent.com/Josh-Thompson2222/FPGAProjectJT/main/docs/assets/images/SwedishFlagPhoto.JPG">

