---
external help file: SmbShare_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: EE0F1C10-6128-461A-B74D-878821DED8F1
manager: dansimp
---

# Close-SmbOpenFile

## SYNOPSIS
Forcibly closes a file that is open by one of the clients of the Server Message Block (SMB) server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Close-SmbOpenFile [[-FileId] <UInt64[]>] [-AsJob] [-CimSession <CimSession[]>] [-ClientComputerName <String[]>]
 [-ClientUserName <String[]>] [-ClusterNodeName <String[]>] [-Force] [-PassThru] [-ScopeName <String[]>]
 [-SessionId <UInt64[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Close-SmbOpenFile [-AsJob] [-CimSession <CimSession[]>] [-Force] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Close-SMBOpenFile** cmdlet forcibly closes a file that is open by one of the clients of the Server Message Block (SMB) server.
This cmdlet should be used with care as it may result in data loss to the client for which the file is being closed if the client has not flushed all of the file modifications back to the server before the file is closed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Close-SmbOpenFile -FileId 4415226383589
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Close-File' on Target '4415226383589'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
```

This example closes a file identified as 4415226383589 that is open by one of the clients of the SMB server.

### EXAMPLE 2
```
PS C:\>Close-SmbOpenFile -SessionId 4415226380393
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Close-File' on Target '4415226383589'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N 
 
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Close-File' on Target '4415226383529'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N 
 
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Close-File' on Target '4415226383517'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N 
 
Confirm 
Are you sure you want to perform this action?
Performing operation 'Close-File' on Target '4415226383521'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N 
 
Confirm 
Are you sure you want to perform this action? 
Performing operation 'Close-File' on Target '4415226383569'. 
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
```

This example closes one or more files that are open by one of the client identified with the session identifier (ID) 4415226380393 of the SMB server.

### EXAMPLE 3
```
PS C:\>Get-SmbOpenFile | Where-Object -Property ShareRelativePath -Match ".DOCX" | Close-SmbOpenFile -Force
```

This example closes, without user confirmation, one or more files that are open by one of the clients of the SMB server and that match the file extension ".DOCX".

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

### -ClientComputerName
Specifies the client computer name to filter the returned open files so that only the matching files are opened.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientUserName
Specifies the name of the user for which the open files are retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClusterNodeName
Specifies, if a share is hosted by a windows cluster, the name of the server which is hosting the open files to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileId
Specifies the file identifier (ID) of the file to forcibly close.

```yaml
Type: UInt64[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ScopeName
Specifies the scope of the open files to be retrieved.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionId
Specifies a session ID.
Only files that have been opened in the specified session will be returned.

```yaml
Type: UInt64[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
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

### None

## NOTES

## RELATED LINKS

[Get-SmbOpenFile](./Get-SmbOpenFile.md)

