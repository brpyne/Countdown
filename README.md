#Countdown

### Notes

* Installed PhoneGap
* Installed NodeJS
* Installed JDK
* Installed Android SDK
* Installed Apache Ants
* Update Environment Variables
	
Path += %ANT_HOME%\bin\ant.bat;%ANT_HOME%\bin;
			%JAVA_HOME%\bin\java.exe;
			%ANDROID_HOME%\platform-tools;
			%ANDROID_HOME%\tools;

* Launch the Android SDK Manager

	Tools > AVD Manager
	Add First Device
	
		Device Created, Start results in "PANIC"
			
			This was due to a bug with ADT and the way my filesystem defaults to \\MI\DFS\Users\BPyne

			Since this isn't an NTFS drive I couldn't use the mklink trick.

			Added Environment Variable
				ANDROID_SDK_HOME=C:\Dev\adt-bundle\sdk

* Started Emulator

	emulator: ERROR: Could not load OpenGLES emulation library: Could not load DLL!
	emulator: WARNING: Could not initialize OpenglES emulation, using software renderer.

	Problem: Emulator was looking for required DLLs in the \tools instead of \tools\lib (C:\Dev\adt-bundle\tools)

	Solution: Copy Files 
		From "C:\Dev\adt-bundle\tools\lib" 
		To "C:\Dev\adt-bundle\tools"
			libEGL_translator.dll
			libGLES_CM_translator.dll
			libGLES_V2_translator.dll
			libOpenglRender.dll

* Started Emulator

* Ran Commands:
	npm install -g phonegap
	phonegap create my-app
	phonegap run android


### PhoneGap and AngularJS
* http://devgirl.org/2013/06/10/quick-start-guide-phonegap-and-angularjs/

### Top Coat CSS
* http://topcoat.io/