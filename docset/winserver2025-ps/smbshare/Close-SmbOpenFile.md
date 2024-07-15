---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbOpenFile.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/close-smbopenfile?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Close-SmbOpenFile
---

# Close-SmbOpenFile

## SYNOPSIS
Closes a file that is open by one of the clients of the SMB server.

## SYNTAX

### Query (cdxml) (Default)
```
Close-SmbOpenFile [[-FileId] <UInt64[]>] [-SessionId <UInt64[]>] [-ClientComputerName <String[]>]
 [-ClientUserName <String[]>] [-ScopeName <String[]>] [-ClusterNodeName <String[]>]
 [-SmbInstance <SmbInstance>] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Close-SmbOpenFile -InputObject <CimInstance[]> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Close-SmbOpenFile** cmdlet forcibly closes a file that is open by one of the clients of the Server Message Block (SMB) server.
This cmdlet can cause data loss to the client for which the file is being closed if the client has not flushed all of the file modifications back to the server before the file is closed.

## EXAMPLES

### Example 1: Close an open file
```powershell
PS C:\> Close-SmbOpenFile -FileId 4415226383589
```
```output
Confirm
Are you sure you want to perform this action?
Performing operation 'Close-File' on Target '4415226383589'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
```

This command closes a file identified as 4415226383589 that is open by one of the clients of the SMB server.

### Example 2: Close open files for a session
```powershell
PS C:\> Close-SmbOpenFile -SessionId 4415226380393
```
```output
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

This command closes one or more files that are open by one of the clients identified with the session ID 4415226380393 of the SMB server.

### Example 3: Close open files that match a file name extension
```powershell
PS C:\> Get-SmbOpenFile | Where-Object -Property ShareRelativePath -Match "\.DOCX" | Close-SmbOpenFile -Force
```

This command closes, without user confirmation, one or more files that are open by one of the clients of the SMB server and that match the file name extension .DOCX.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

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
Parameter Sets: Query (cdxml)
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
Parameter Sets: Query (cdxml)
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
Parameter Sets: Query (cdxml)
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
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: 1
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
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: Query (cdxml)
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
Parameter Sets: Query (cdxml)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: Query (cdxml)
Aliases:
Accepted values: Default, CSV, SBL, SR

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
Aliases: cf

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
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-SmbOpenFile](./Get-SmbOpenFile.md)
