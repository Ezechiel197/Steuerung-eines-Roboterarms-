ABB Industrial Robot: THM Logo Drawer
This repository contains a RAPID module designed for an ABB industrial robot (e.g., IRB 120) to draw the official logo of the Technische Hochschule Mittelhessen (THM). 
The program is highly dynamic, allowing for user-defined scaling, color selection, and integrated binary encoding of department numbers.

Key Features
Dynamic Scaling: Users can input a custom size x for the logo grid (up to 20mm). All coordinates are calculated relative to this value.

Department Binary Encoding: A unique feature that prompts for a Department Number (Fachbereich) and renders it as a binary matrix within the logo using filled/hollow squares.

Automated Tool Handling: The robot automatically picks up the requested pen from a rack and returns it safely after the drawing process.

Multi-Color Support: Supports four different pens (Black, Blue, Green, Red) with pre-defined pickup targets.

Hatch Filling: Includes a custom algorithm to "fill" squares using a zig-zag hatching pattern for visual clarity.

Technical Specifications
Tool Center Points (TCP)
The project utilizes specific TCP definitions found in the CalibData module:

Front_TCP: Used for the gripping process and approaching the pen rack.

Pen_TCP: The primary drawing tool, calibrated to the tip of the pen (300mm length).

Coordinate Logic
The drawing uses the Offs() (Offset) function extensively. 
This ensures that the entire logo is drawn relative to a single BoardCenter point, making the system easy to recalibrate if the paper is moved.

How to Use
Setup: Ensure the pen rack is positioned according to the robtarget constants (Black_Pen_Target, etc.).

Calibration: Define the BoardCenter WorkObject on your drawing surface.

Execution: Run the main() procedure.

User Input: * Enter the grid size in mm (e.g., 10).

Enter the Department Number (e.g., 06 for ME).

Select the pen color (0–3).

Safety: The robot will move at v1000 for air moves and slow down to v30 for precise drawing contact.

<img width="734" height="683" alt="image" src="https://github.com/user-attachments/assets/ed8a304e-eac1-4753-97f5-d46e18be1c19" />
