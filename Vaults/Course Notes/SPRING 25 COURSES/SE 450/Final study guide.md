All Modules EXCEPT the Mid Materials.
Mid term was: Module 1 to Module 8

Final will have assembly on it

Mod 8
- Process Injection
	- DLL Injection
		- malicious DLL into another process
	- Direct Injection
		- malicious code directly into targeted space
	- COMMON API CALLS
		- VitualAllocEx - space allocation
		- WriteProcessMemory - write to the location
	- Privilege Escalation
		- If the malware doesn't have admin off the bat
			- it will perform privilege escalation
		- They typically use SeDebugPrivilege
	- SeDebugPrivilege
		- intended for debugging
		- grants anyone essential equivalent to local system account access
		- adjust the access token to grant them SeDebugPrivilege
![[{45F70745-F8B9-42AA-B70F-67C12D730ADA}.png]]
	- LoadLibrary injects code into remote process
	- Forces the DLL into the process context
	- On load OS calls DLLMain which contains malicious code
![[{1AE929F5-9258-4A6F-B61C-84A37C5D571A}.png]]
	- DLL Injection
		1. ID the target process
			- ![[{66E32B34-1C54-494E-BE7B-675322577548}.png]]
			- Get the PID then use to handle a call to OpenProcess
		 2. VitualAllocEx allocates space in a remote process
		 3. WriteProcessMemory - writes malicious library name string into the mem space
		4. CreateRemoteThread - uses the parameters, IpStartAddress (LoadLibrary), malicious code is in the DLLMain
	- Direct Injection
		- directly into remote process
		- doesnt need separate malicious DLL
		- 2 calls VirtualAllocEx and WriteProcessMemory
			- allocate then write the malicious code
			- write in arguments of CreateRemoteThread
		- CreateRemoteThread is called to start it
	- Process Replacement (process hollowing)
		- Overwrites the memory space of a running obj with mal code
		- mal is disguised as a legit process
		- avoids crash that a process injection could happen
		- commonly replaces svchost.exe
		- uses the CREATE_SUSPENDED val
		- in dwCreationFlags
		- in a call to the CreateProcess
		- ![[{1DD07032-07C8-452B-A0CF-BD213CCD517F}.png]]
		Immunity Debugger
			- perform basic reverse engineering steps on Windows executables, including navigating the interface, setting breakpoints, and examining registers, memory, and control flow
			- how to analyze common malware-like behaviors—such as file renaming, registry modifications, socket communications, and ROT13-encoded URL decoding—at the assembly level
Mod 9
- Common Malware Behavior
	- Back doors
		- remote access to a machine
		- most common
		- communicates over http port 80
			- network signatures can be used for detection
		- can change registry, enumerate, display windows, create directories, search files, etc.
		- Infected machines calls out to the attackers asking for commands to execute
		- Windows reverse shells
			- CreateProcess and change STARTUPINFOR
			- create socket to remote machine
			- tie socket to standard input, output and error cm.exe
			- also look for CreateThread and CreatePipe
			- 2 threads for stdin and stdout
	- Credentials stealers - hash dumping
		- windows logins/pass stored in hash
		- Pwdump and pass-the-hash toolkit
			- free hacking tools that have hash dumping
			- injects Isaext.dll into lasass.exe
		- Inject DLL into LSASS
			- get hashes from SAM secuirty account manager
			- injected dll run inside another process
			- gets all the privileges of that process
			- LSASS is most likely the target
		- keylogging
			- difficult to detect
			- normally part of a rootkit
			- user-space keyloggers
				- use windows api
			- hooking
				- SetWindowsHookEx
			- Polling
				- GetAsyncKeyState and GetForegroundWindow
	- Data Encoding
		- simple ciphers easier to hide
		- obfuscation 
			- make it had to id data but not impossible
	- 