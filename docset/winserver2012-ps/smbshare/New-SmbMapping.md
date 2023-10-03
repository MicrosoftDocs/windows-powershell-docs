---
external help file: SmbShare_Cmdlets.xml
Module Name: SmbShare
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbmapping?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-SmbMapping

## SYNOPSIS
Creates a new Server Message Block (SMB) mapping.

## SYNTAX

```
New-SmbMapping [[-LocalPath] <String>] [[-RemotePath] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-HomeFolder] [-Password <String>] [-Persistent <Boolean>] [-SaveCredentials] [-ThrottleLimit <Int32>]
 [-UserName <String>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **New-SmbMapping** cmdlet creates a new Server Message Block (SMB) mapping on the SMB client to an SMB share.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-SmbMapping -LocalPath X: -RemotePath \\Contoso-SO\VMFiles
Status                                  Local Path                              Remote Path 
------                                  ----------                              ----------- 
OK                                      X:                                      \\Contoso-SO\VMFiles
```

This example creates a new SMB mapping.

### EXAMPLE 2
```
PS C:\>New-SmbMapping Y: -RemotePath \\Contoso-FS\VMS1
Status                                  Local Path                              Remote Path
------                                  ----------                              -----------
OK                                      Y:                                      \\Contoso-FS\VMS1
```

This example creates a new SMB mapping.

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

### -HomeFolder
Indicates that the connection is made to the home folder of the user.

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

### -LocalPath
Specifies the local path to which the remote path is mapped.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password to be used to connect to the SMB share.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistent
Indicates that this connection is persistent.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePath
Specifies the remote path that is accessed from this computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SaveCredentials
Indicates that the credentials provided should be saved for when a mapping to the same SMB server also is created.

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

### -UserName
Specifies the user name to use to connect to the SMB share.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMapping
The MSFT_SmbMapping object represents the newly created SMB mapping.

## NOTES

## RELATED LINKS

[Get-SmbMapping](./Get-SmbMapping.md)

[Remove-SmbMapping](./Remove-SmbMapping.md)

