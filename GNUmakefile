# Lets plain `make` work from PowerShell / cmd on Windows: run recipes in Git's sh
# and use the MSYS2 UCRT64 gcc. GNU make reads this before makefile.
ifeq ($(OS),Windows_NT)
SHELL := C:/Program Files/Git/usr/bin/sh.exe
export PATH := C:\msys64\ucrt64\bin;C:\Program Files\Git\usr\bin;$(PATH)
endif

include makefile
