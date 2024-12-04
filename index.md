---
layout: home
title: FPGA VGA Driver Project
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
<img src="">
### **Simulation**
Show how you simulated your own design. Are there any things to note? Demonstrate your understanding. Add a screenshot. Guideline: 1-2 short paragraphs.
### **Synthesis**
Describe the synthesis & implementation outputs for your design, are there any differences to that of the original design? Guideline 1-2 short paragraphs.
### **Demonstration**
If you get your own design working on the Basys3 board, take a picture! Guideline: 1-2 sentences.

## **More Markdown Basics**
This is a paragraph. Add an empty line to start a new paragraph.

Font can be emphasised as *Italic* or **Bold**.

Code can be highlighted by using `backticks`.

Hyperlinks look like this: [GitHub Help](https://help.github.com/).

A bullet list can be rendered as follows:
- vectors
- algorithms
- iterators

Images can be added by uploading them to the repository in a /docs/assets/images folder, and then rendering using HTML via githubusercontent.com as shown in the example below.

<img src="https://raw.githubusercontent.com/melgineer/fpga-vga-verilog/main/docs/assets/images/VGAPrjSrcs.png">
