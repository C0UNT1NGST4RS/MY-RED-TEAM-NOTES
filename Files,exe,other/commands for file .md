The archive contains quite a few DLL's as well as an executable file called UserInfo.exe .
Checking the file type of UserInfo.exe shows that it is a .Net executable. As we are using a Linux system
we have two ways to proceed. Decompiling the executable to see what it does or using Wine to attempt to
run it.   

ILSpy


In order to decompile the .Net executable we can use Avalonia ILspy, which is a cross-platform version of
ILSpy that works on Linux. First let's download it from the releases page.


smb: \> get UserInfo.exe.zip
getting file \UserInfo.exe.zip of size 277499 as UserInfo.exe.zip (511.3 KiloBytes/sec)
(average 511.3 KiloBytes/sec)


unzip UserInfo.exe.zip

file UserInfo.exe
UserInfo.exe: PE32 executable (console) Intel 80386 Mono/.Net assembly, for MS Windows

Then we will have to extract the contents using unzip .
The archive will extract a second archive, which we must again unzip .
Finally we must navigate to the artifacts/linux-arm64 folder and run the ILSpy executable.
Let's now load the UserInfo executable in order to decompile it. Click on File , select Open , find the
target binary in the file browser and select it.

wget https://github.com/icsharpcode/AvaloniaILSpy/releases/download/v7.2-
rc/Linux.x64.Release.zip
unzip Linux.x64.Release.zip
Archive: Linux.x64.Release.zip
inflating: ILSpy-linux-x64-Release.zip

unzip ILSpy-linux-x64-Release.zip

cd artifacts/linux-arm64

sudo ./ILSpy