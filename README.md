# BBD
This is a C# program made to test algorithms for sequencing DNA.
It was written some time ago (in 2015 I guess) when I was doing my masters.


Michał Komorowski
01/06/2016

-------------------------------------------------- --------
-------------------------------------------------- --------
Biological and Medical Databases - an alignment program
-------------------------------------------------- --------
-------------------------------------------------- --------

Source code: * .cs files in the "KodZrodlowy" folder and subfolders.


I. Starting the program and setting the console window
-------------------------------------------------- -
1. Starting the program
In the "PlikUruchomieniowy/Debug" folder there is Alignment.exe file that
should be run.

2. Suggested console format:
Where content is displayed, it is displayed incorrectly
open the "Properties" window of the console, then RMC on the window and the "Properties" from the menu
pop.
- In the "Font" tab, choose the size = 6 x 8.
- In the tab "Arrangement" set the screen buffer for min. 1500 (recommended).
- Set the screen buffer height on any value (the larger the more results
you can now browse)
- Match the window size to your favorite preferences

II. Working with the program
---------------------
After starting the program, you should take care of it 
choosing appropriate NUMBERS. In case of wrong program selection, you will be asked again.

1. Selecting the program mode
- Single alignment (compares two sequences that exist in a single file)
- Database-target (compares all sequences in the file with the current sequence
from this item from the list of sequences to compare)

2. Choosing the type of alignment
- global (Needleman-Wunsch algorithm for comparisons)
- local (Smith-Waterman algorithm for comparison)

3*. Choosing the similarity threshold
The program will display only those comparisons that max score >= the similarity threshold 
* - when the algorithm for local alignment was chosen

4. Selection of the scoring type
- Standard (default)
penalties / rewards for: compatibility of a pair of aminoacids, incompatibility of a pair of aminoacids,
inserting a break in the sequence)
- Substitution Matrix (value of penalties / rewards when comparing
specific pairs of aminoacids in substitution matrix chosen later by the user)

5*. Selection of the standard value of the score
- compliance (value of the penalty / award when receiving two identical aminoacids)
- non-compliance (value of the penalty / reward when comparing two different aminoacids)
- break (penalty / reward value for inserting spaces in one of the sequences)
* - If you choose standard type of scoring
WARNING! Some unusual score values may make program unstable.

6*. Selecting the type of substitution matrix
You can choose one of three different substitution matrices:
- PAM250
- BLOSUM50
- BLOSUM62
* - if the scoring with substitution matrix was chosen

7*. Providing a file with two sequences
Enter the filename (not full path) containing two sequences.
The program ignores the case.
* - if the "Single alignment" program mode is selected

8*. Providing a file with the sequences database
Enter the filename (not full path) containing list of sequences (from database like PUBMED)
The program ignores the case.
* - if the "Database-target" program mode is selected

9*. Providing file with sequences to be compared with sequence database
Enter the filename (not full path) containing any number of sequences.
The program ignores the case.
* - if the "Database-target" program mode is selected

10. Displaying the alignment matrix
User can decide to show alignment matrices after each step of the algorithm

11. ENTER
- No (Nie) (the program will print all the alignments at once, without waiting)
- Yes (Tak) (the program will print single-person alignments, waiting for ENTER key,
before going to the next alignment)


III. The types of files and their placement in the folder folder
-------------------------------------------------- ---------
Folder with files: PlikUruchomieniowy / Debug / Files /

1. Substitutions matrix
For correct use of substitution matrix place three files in the aforementioned folder:
- PAM250.txt
- BLOSUM50.txt
- BLOSUM62.txt
The content of the files must be analogous to those of the files provided
in program (# - start the comment line; other lines are treated as matrix rows).
In the absence of files, the program at the stage of configuration will inform the user about the error
and will ask to choose a different type of matrix.

2. A file with two sequences (single alignment mode)
Any .fasta or .txt format file. 
Every sequence should be preceded with line with ">" symbol meaning information line (e.g. >unknownPROTEIN ).
Other lines are treated as sequence lines.
The file should contain two sequences.

3. A file with sequence databases (database-target mode)
Any .fasta or .txt format file. 
Every sequence should be preceded with line with ">" symbol meaning information line (e.g. >unknownPROTEIN ).
Other lines are treated as sequence lines.
The file should contain any number of sequences.

4. File with sequences to be compared with sequence database
Any .fasta or .txt format file. 
Every sequence should be preceded with line with ">" symbol meaning information line (e.g. >unknownPROTEIN ).
Other lines are treated as sequence lines.
The file should contain two sequences.

