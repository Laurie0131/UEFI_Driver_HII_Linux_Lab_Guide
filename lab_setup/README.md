<!--- @file
 README.md file for Lab_setup

Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

Redistribution and use in source (original document form) and 'compiled'
forms (converted to PDF, epub, HTML and other formats) with or without
modification, are permitted provided that the following conditions are met:

1) Redistributions of source code (original document form) must retain the
above copyright notice, this list of conditions and the following
disclaimer as the first lines of this file unmodified.

2) Redistributions in compiled form (transformed to other DTDs, converted to
PDF, epub, HTML and other formats) must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
EVENT SHALL TIANOCORE PROJECT BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

-->
# Lab Setup Linux for Ubuntu 16.04 {#lab-setup}


1.  Download the [UEFI Training Materials](https://github.com/Laurie0131/Lab_Material_FW) .zip (accept any security notifications) 
2. **Click** “Open”  and Extract the file to HOME which will take a few minutes <br>
Note:  It is highly important that you unzip the file correctly to this location because all the file locations in this training guide follow that format.
```

  Lab_Material_FW-master/FW/ Edk2 – Open source tianocore.org EDK II 
  Lab_Material_FW-master/FW/ Edk2Linux – BaseTools for Linux
  Lab_Material_FW-master/FW/ DriverWizard – Install python script
  Lab_Material_FW-master/FW/ LabSampleCode  - Solutions for Labs
  Lab_Material_FW-master/FW/ Documentation - .chm files and examples

```

3.  **Install** the Ubuntu Linux tools:

```
bash$ sudo apt-get install build-essential uuid-dev iasl git 
bash$ sudo apt-get install gcc-5 nasm 
bash$ sudo apt-get install qemu
```
4. ** Create **a directory “src”<br>
   `bash$ mkdir ~src` <br>
5. From the `~FW` folder, copy and paste folder “`~FW/edk2`” to `~src`
6. **Rename** or **mv** the directory “`~src/edk2/BaseTools`” to something else <br>
  `bash$ cd ~src/edk2` <br>
  `bash$ mv BaseTools BaseToolsX`<br>
7. **Extract** the file `~FW/edk2Linux/BaseTools.tar.gz`  to  `~src/edk2`<br>
  `bash$ cd ~src/edk2` <br>
8. Make the BaseTools and setup the environment <br>
   `bash$ make –C BaseTools` <br>
   `bash$ . edksetup.sh` <br>
9. **Edit **the file Conf/target.txt<br>
   `bash$ gedit Conf/target.txt`
![](/media/gedit_target.txt.JPG)
10. **Save** and Exit target.txt
11. To build OvmfPkg **Type** <br>
 `bash$ build`







### Invoke QEMU to run UEFI Shell {#invoke-qemu-to-run-uefi-shell}

**_Note_**_: You’ll need to repeat this step each time you exit the Visual Studio Command Prompt window. It is recommended that you keep your command prompt open during the training Labs._

1. **Open** Visual Studio Command Prompt 
2. **Type** `$ CD c:\fw\edk2` and then **Press** “Enter” 

3. **Type** `$ Edksetup` and then Press “Enter” 

Note: If you see “!!! WARNING !!!...”, don’t be alarmed.  The "No CYGWIN..." can be ignored at this time, **BUT** make sure "NASM" is found and the `NASM_PREFIX `is set to `C:\nasm\`


### Configuring Build Tools {#configuring-build-tools}

**_Note_**_: You only need to edit Target.txt and/or Tools_Def.txt once after the first_ **edksetup** _command after downloading the Training materials .zip file._

1. **Open** Notepad or other text editor that supports UNICODE 
2.  **Open** C:/fw/edk2/Conf/Target.txt 
3. Use the 
[Microsoft Windows and Visual Studio Matrix ](../microsoft_windows_and_visual_studio_matrix/README.md) and then update `TOOL_CHAIN_TAG` to match your version of Visual Studio
4. **Modify** **TOOL_CHAIN_TAG** to match your version of Visual Studio.

**Example:**<br>
for Windows 10 64 bit OS and Visual Studio 2013 modify the following in Target.txt<br>
From:<br>
**TOOL_CHAIN_TAG = MYTOOLS**
<br>
to:<br>
**TOOL_CHAIN_TAG = VS2013x86**
<br>
OPTIONAL: Update the `MAX_CONCURRENT_THREAD_NUMBER ` By the number of processors on your laptop + 1.  Example: most have Intel® Dual Core with Hyper threading which means `2 procs + 2 HT + 1 = 5`.
![](/media/image114.png)
5. **Save** and **close** the text file C:/fw/edk2/conf/target.txt

### End of Lab Setup for Windows