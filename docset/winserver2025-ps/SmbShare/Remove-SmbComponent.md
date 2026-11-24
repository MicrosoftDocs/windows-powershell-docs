---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbComponent.cdxml-help.xml
Module Name: SmbShare
ms.date: 08/31/2021
online version: https://learn.microsoft.com/powershell/module/smbshare/remove-smbcomponent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-SmbComponent
---

# Remove-SmbComponent

## SYNOPSIS
Removes SMB1 components.

## SYNTAX

```
Remove-SmbComponent [-Name] <String[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-SmbComponent cmdlet removes SMB1 components. SMB1 is a deprecated and unsafe protocol that’s no longer installed by default in most versions of Windows and Windows Server. For more information, review [SMBv1 is not installed by default in Windows 10 version 1709, Windows Server version 1709, and later versions](/windows-server/storage/file-server/troubleshoot/smbv1-not-installed-by-default-in-windows).

## EXAMPLES


### Example 1 - Remove all SMB1 components, including SMB1 server, SMB1 client, and the SMB1 automatic removal service

This command removes all SMB1 components, including SMB1 server, SMB1 client, and the SMB1 automatic removal service.

```powershell
PS C:\> Remove-SmbComponent -Name SMB1Protocol
```

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
Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. The default is the current session on the local computer.

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

### -Name
Specifies the SMB1 component to remove. The acceptable values for this parameter are:

- `SMB1Protocol` Remove all SMB1 components.
- `SMB1Protocol-Client` Remove the SMB1 client components.
- `SMB1Protocol-Server` Remove the SMB1 server components.
- `SMB1Protocol-Deprecation` Remove the SMB1 automatic removal service component (only applies to Windows, not Windows Server).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If this parameter is omitted or a value of 0 is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer. The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
