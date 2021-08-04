# Windows Sandbox Quick Guide




### Quick Config File

Sample config file for windows sandbox to open 'Downloads' folder to test any potentially mallicious file inside sandbox environment with networking disabled and with 'Downloads' folder in read-only mode to prevent any unwanted changes to the file system while opening the file.

File Extension :  ***.wsb**

```xml
<Configuration>
  <VGpu>Disable</VGpu>
  <Networking>Disable</Networking>
  <MappedFolders>
    <MappedFolder>
      <HostFolder>C:\Users\DJ\Downloads</HostFolder>
      <SandboxFolder>C:\Users\Sandbox\Downloads</SandboxFolder>
      <ReadOnly>true</ReadOnly>
    </MappedFolder>
  </MappedFolders>
  <LogonCommand>
    <Command>explorer.exe C:\Users\Sandbox\Downloads</Command>
  </LogonCommand>
</Configuration>
```


'Command' Executes the given command on sandbox startup. 





##### Additional Parameters:

###### Audio input 
- Enable: Enables audio input in the sandbox. If this value is set, the sandbox will be able to receive audio input from the user. Applications that use a microphone may require this capability.
- Disable: Disables audio input in the sandbox. If this value is set, the sandbox can't receive audio input from the user. Applications that use a microphone may not function properly with this setting.
- Default: This is the default value for audio input support. Currently this means audio input is enabled.

```xml
<AudioInput>value</AudioInput>
```


###### Video input 
- Enable: Enables video input in the sandbox.
- Disable: Disables video input in the sandbox. Applications that use video input may not function properly in the sandbox.
- Default: This is the default value for video input support. Currently this means video input is disabled. Applications that use video input may not function properly in the sandbox.

```xml
<VideoInput>value</VideoInput>
```


###### Protected client 
- Enable: Runs Windows sandbox in Protected Client mode. If this value is set, the sandbox runs with extra security mitigations enabled.
- Disable: Runs the sandbox in standard mode without extra security mitigations.
- Default: This is the default value for Protected Client mode. Currently, this means the sandbox doesn't run in Protected Client mode.

```xml
<ProtectedClient>value</ProtectedClient>
``` 

###### Clipboard redirection
- Disable: Disables clipboard redirection in the sandbox. If this value is set, copy/paste in and out of the sandbox will be restricted.
- Default: This is the default value for clipboard redirection. Currently copy/paste between the host and sandbox are permitted under Default.

```xml
<ClipboardRedirection>value</ClipboardRedirection>
```

###### Memory in MB 

```xml
<MemoryInMB>value</MemoryInMB>
```


