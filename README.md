# Single-Pass-Macro-Processor
This project implements a two-pass macro processor in C, designed to process macro definitions and expansions in assembly-like code. Despite the title "Single Pass Macro Processor," the implementation uses a two-pass approach for clarity and functionality, as it separates macro definition processing from macro expansion. The processor reads an input file containing macro definitions and calls, processes them, and generates an expanded output file along with several intermediate files for debugging and verification.
What Does the Code Do?
A macro processor allows programmers to define macros—short names that represent longer sequences of code. When a macro is invoked, the processor expands it into the full code sequence, improving code readability and maintainability. This implementation:
# Pass 1: 
Reads the input file, identifies macro definitions, builds necessary tables (Macro Name Table, Macro Definition Table, and Argument List Array 1), and writes non-macro lines (including macro calls) to an intermediate file.
# Pass 2: 
Reads the intermediate file, expands macro calls using the stored definitions and actual parameters (via Argument List Array 2), and generates the final expanded code.
The code also produces detailed logs and console output to help users understand the processing steps.
# Input and Output
Input
File: input.txt
# Output
Console Output (Output Window)
The following are displayed in the console:
ALA1 (Argument List Array 1): Maps formal parameters (e.g., &a) to positional parameters (e.g., #1) after Pass 1.
IR (Intermediate Representation): Contents of the intermediate file after Pass 1, showing the code with macro calls intact.
ALA2 (Argument List Array 2): Maps positional parameters (e.g., #1) to actual parameters (e.g., 5) after Pass 2.
# Files Generated
The rest of the output is reflected in the following files:
ala_pass1.txt: Contains ALA1 mappings (e.g., &a #1).
mnt.txt: Macro Name Table, listing macro names, parameter counts, and indices to the Macro Definition Table (e.g., ADD 2 1).
mdt.txt: Macro Definition Table, storing macro bodies with positional parameters (e.g., 1 ADD #1 #2).
intermediate.txt: Intermediate Representation (IR) of the code, excluding macro definitions but including macro calls (e.g., START ADD 5 10 END).
ala_pass2.txt: Contains ALA2 mappings (e.g., #1 5).
output.txt: Final expanded code (e.g., START ADD 5 10 END).
log.txt: Detailed log of processing steps for debugging.
# How to Run the Code
Follow these steps to compile and execute the macro processor:
# For turbo C++ compiler 
download the files paste them in bin opne in turbo c hit run!!
# OR 

Save the Code:
Copy the source code into a file of your choice (eg macro_processor.c)

Compile the Code:
Open a terminal and navigate to the directory containing macro_processor.c.
Use a C compiler (e.g., GCC) to compile:
gcc macro_processor.c -o macro_processor
This generates an executable named macro_processor.

Prepare the Input File:
Create a file named input.txt in the same directory.
Add your assembly-like code with macro definitions and calls (see the example above).

Run the Program:
Execute the compiled program:
./macro_processor
On Windows, use:

macro_processor.exe
Files: Open the generated files (ala_pass1.txt, mnt.txt, mdt.txt, intermediate.txt, ala_pass2.txt, output.txt, log.txt) to see the detailed results.
