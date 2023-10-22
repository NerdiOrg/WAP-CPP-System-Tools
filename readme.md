# WAP C++ System Tools

Learning how to access directories, return file & folder lists, read files, save files, run sub-programs, use C++ headers, etc.

Command Line Menu: 

1. Save file to C://wap.md
2. Read C://wap.md file
3. System Users
     1. View User Folders
     2. Get Current Username
     3. Get Current User Directory Path
4. Pictures
     1. List all files in user Pictures folder.
     2. Delete all files in user Pictures folder, recursively.
5. Confusing Filenames
     1. All Desktop Files
     2. All Desktop Files, Subfolders (Recursive)

## Compile the Resource Script

Run the following command from project root dir to compile the resource script into a COFF object file:

windres config/sysAccess.rc -O coff -o config/sysAccess.res

*NOTE: This is not needed if you are using the Packager.exe for a version distribution (this command is ran automatically from Packager)



# Compile the program:

g++ -std=c++17 main.cpp lib/FolderScanner/main.cpp lib/Random/main.cpp lib/SystemUser/main.cpp config/sysAccess.res -o dist/alpha-0.0.4/pkg/run.exe

The version of gcc must be 8+ to use filesystem dependencies. I am using 'gcc.exe (x86_64-posix-seh-rev0, Built by MinGW-Builds project) 13.2.0' at this time.

*NOTE: This is not needed if you are using the Packager.exe for a version distribution (this command is ran automatically from Packager). If you don't use start.exe, you must run pkg/run.exe as Administrator to use full features.



## Create a starter executable:

This only needs to be done once. This will automatically request admin permissions for the run.exe, to support all operations.

g++ starter.cpp -o dist/alpha-0.0.1/start.exe

*NOTE: This is not needed if you are using the Packager.exe for a version distribution (this command is ran automatically from Packager)



## Compile the Packager:

This is only here for an example of a C++ executable that allows distributions of WAP C++ System Tools to be easily packaged into a new version. It is not needed if you are using manual commands above.

g++ dev/Packager/packager.cpp -o dev/Packager/Packager.exe

*NOTE: This is not needed if you are compiling manually. Simply open dev/Packager/Packager.exe and follow command prompt instructions to create a new compiled version in /dist/ folder.



# Notes

Run start.exe from distribution folders in /dist/, or compile from source manually with commands above, or using dev/Packager/Packager.exe. Source is provided for both starter & packager programs alongside main source for WAP C++ System Tools.
