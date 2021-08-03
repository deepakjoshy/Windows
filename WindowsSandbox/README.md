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
