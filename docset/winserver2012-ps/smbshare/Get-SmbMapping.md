---
external help file: SmbShare_Cmdlets.xml
Module Name: SmbShare
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbmapping?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SmbMapping

## SYNOPSIS
Retrieves the Server Message Block (SMB) client directory mappings created for a server.

## SYNTAX

```
Get-SmbMapping [[-LocalPath] <String[]>] [[-RemotePath] <String[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-SmbMapping** cmdlet retrieves the Server Message Block (SMB) client directory mappings created for a server.
This can be a mapping from a local drive letter to a remote shared folder, or it can be a mapping without a local path.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-SmbMapping
Status                                  Local Path                              Remote Path 
------                                  ----------                              ----------- 
OK                                      X:                                      \\Contoso-SO\VMFiles 
OK                                      Y:                                      \\Contoso-FS\VMS1
```

This example retrieves the SMB client directory mappings created for the SMB server.

### EXAMPLE 2
```
PS C:\>Get-SmbMapping -LocalPath X: | Select-Object - Property *
Status                : OK 
LocalPath             : X: 
RemotePath            : \\Contoso-SO\VMFiles 
PSComputerName        : 
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbMapping 
CimInstanceProperties : {LocalPath, RemotePath, Status} 
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This example retrieves the SMB client directory mapping for the X: directory created for the SMB server.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPath
Specifies the local path used to map the remote path on this computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemotePath
Specifies the remote path that is accessed from this computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMapping
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The MSFT_SmbMapping object represents the mappings created from the SMB client to SMB shares.

## NOTES

## RELATED LINKS

[New-SmbMapping](./New-SmbMapping.md)

[Remove-SmbMapping](./Remove-SmbMapping.md)

