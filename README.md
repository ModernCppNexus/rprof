<img src="https://www.rudji.com/images/lib/rprof.png"/>

[![License](https://img.shields.io/badge/license-BSD--2%20clause-blue.svg)](https://github.com/RudjiGames/rprof/blob/master/LICENSE)

About
======

**rprof** is a scope based CPU profiling library with [ImGui](https://github.com/ocornut/imgui) visulization and browser profile inspector. The core concept is a time threshold, which can be used to easily catch functions or entire frames that exceed certain time value. By doing this, optimization can focus initially on frames and functions that are only occasionally slow and iteratively progress towards more consistent performance.

Profiler always runs when used, but will display only those frames that exceed given threshold. Default value of 0 means to display every frame. Level value refers to hierachical scope depth where value of 0 represents an entire frame.

![In game screenshot](https://github.com/RudjiGames/rprof/blob/master/img/rprof_vis.jpg) 

Source Code
======

You can get the latest source code by cloning it from github:

      git clone https://github.com/RudjiGames/rprof.git 

Dependencies
======

There are no dependencies besides the [build](https://github.com/RudjiGames/build) system scripts, which are optional.  
It is recommended to use the [build](https://github.com/RudjiGames/build) system scripts to easily generate projects for numerous platforms:

	git clone https://github.com/RudjiGames/build.git

Build
======

GENie script can generate Microsoft Visual Studio solution or makefiles for a GCC based compiler or cross compiler. Generating a MSVC
solution, for example, is done using the following command:

      genie vs2022

The generated solution will be located in the following folder:
   .build/projects/vs2022

Generating makefiles for a GCC based toolchain is done in a similar way, for
example:

      OSX   :   genie --gcc=oxc gmake
      PS4   :   genie --gcc=ps4 gmake

Generated makefiles will be located in the following folder:

      .build/projects/gmake/$(GCC_TOOLCHAIN)

All of the generated solutions/makefiles provide a Debug, Release and Retail configurations,
in both 32bit and 64bit versions. Some platforms support only one word size, for 
example OSX works with 64 bit builds only.

To build a GCC based library use the following command lines:

      Debug, 32bit   :  make -R config=debug32
      Release, 64bit :  make -R config=release64

Browser inspector
======

Captured frame profiles can be saved to binary files for offline inspection.
The browser based inspector is built using Emscripten. Makefile is included for convenience.
Browser inspector is based on [ImGui](https://github.com/ocornut/imgui) and is interacive provinding zooming and panning as well as statistical overview of the frame.  

Viewer is browser based in order to be able to use it as a part of QA pipeline during development process.  

[**Live demo**](https://rudji.com/rprof/rprof.html?path=https://rudji.com/rprof/&file=capture.rprofm)

![Inspector screenshot](https://github.com/milostosic/rprof/blob/master/img/rprof_browser.gif) 

Author
======

The author of **rprof** is Milos Tosic  
[ <img src="https://github.com/RudjiGames/.github/blob/main/images/twitter.png">](https://twitter.com/milostosic)[ <img src="https://github.com/RudjiGames/.github/blob/main/images/mail.png">](mailto:milostosic77@gmail.com) 


License (BSD 2-clause)
======

<a href="http://opensource.org/licenses/BSD-2-Clause" target="_blank">
<img align="right" src="https://opensource.org/wp-content/uploads/2022/10/osi-badge-dark.svg" width="100" height="137">
</a>

	Copyright (c) 2023 by Milos Tosic. All rights reserved.
	
	https://github.com/RudjiGames/rprof
	
	Redistribution and use in source and binary forms, with or without
	modification, are permitted provided that the following conditions are met:
	
	   1. Redistributions of source code must retain the above copyright notice,
	      this list of conditions and the following disclaimer.
	
	   2. Redistributions in binary form must reproduce the above copyright
	      notice, this list of conditions and the following disclaimer in the
	      documentation and/or other materials provided with the distribution.
	
	THIS SOFTWARE IS PROVIDED BY COPYRIGHT HOLDER ``AS IS'' AND ANY EXPRESS OR
	IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
	MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
	EVENT SHALL COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT,
	INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
	(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
	LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
	ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
	(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF
	THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 
