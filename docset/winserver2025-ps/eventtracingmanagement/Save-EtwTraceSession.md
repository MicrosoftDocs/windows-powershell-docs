---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: EventTracingManagement-help.xml
Module Name: EventTracingManagement
ms.date: 01/05/2017
online version: https://learn.microsoft.com/powershell/module/eventtracingmanagement/save-etwtracesession?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-EtwTraceSession
---

# Save-EtwTraceSession

## SYNOPSIS
Saves the events collected by the ETW session to an .etl file.

## SYNTAX

```
Save-EtwTraceSession [-Name] <String> [-OutputFile <FileInfo>] [-OutputFolder <DirectoryInfo>] [-Stop]
 [-Overwrite] [-CimSession <CimSession>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Save-EtwTraceSession** cmdlet saves the events collected by the ETW session to an .etl file.

## EXAMPLES


## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
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

### -Name
Specifies the name of the ETW session.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFile
Specifies the file to save the .etl file to for the ETW session.

```yaml
Type: FileInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputFolder
Specifies the folder to save the .etl file to for the ETW session.

When this parameter is set, the file name of the .etl will be selected automatically based on the session properties.

If the session is a buffering mode session, the file name will be the name of the session.

If the session is a file mode session, the file name will be the file name of the currently being written to.

To control the file name as well as the output folder, use the *OutputFile* parameter instead.

```yaml
Type: DirectoryInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Overwrite
Controls whether an existing file should be overwritten by saving this session.

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

### -Stop
Controls whether the session should be stopped after the save is complete.

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

### System.IO.FileInfo, System.IO.DirectoryInfo

## OUTPUTS

### System.IO.FileInfo, CIM_DataFile
This cmdlet returns a **System.IO.FileInfo** object that represents a file on the local computer.
The object is returned when the current session is saved successfully to a file on the local machine.

This cmdlet returns a **CIM_DataFile** object when the current session is saved successfully to a file over a CIM session.

## NOTES

## RELATED LINKS

[Get-EtwTraceSession](./Get-EtwTraceSession.md)

[New-EtwTraceSession](./New-EtwTraceSession.md)

[Send-EtwTraceSession](./Send-EtwTraceSession.md)

[Start-EtwTraceSession](./Start-EtwTraceSession.md)

[Stop-EtwTraceSession](./Stop-EtwTraceSession.md)

[Update-EtwTraceSession](./Update-EtwTraceSession.md)

