---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/stop-iiscommitdelay?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-IISCommitDelay
---

# Stop-IISCommitDelay

## SYNOPSIS
Instructs the IIS configuration system to resume the commitment of changes.

## SYNTAX

```
Stop-IISCommitDelay [[-Commit] <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-IISCommitDelay** cmdlet instructs the Internet Information Services (IIS) configuration system to resume the commitment of changes.

## EXAMPLES

### Example 1: Commit configuration changes
```
PS C:\> Stop-IISCommitDelay -Commit $True
```

This command commits the configuration changes made since the **Start-IISCommitDelay** cmdlet was executed.

### Example 2: Discard configuration changes
```
PS C:\> Stop-IISCommitDelay -Commit $False
```

This command discards the configuration changes made since the **Start-IISCommitDelay** cmdlet was executed.

## PARAMETERS

### -Commit
Indicates that the cmdlet commits the changes if True; Otherwise, if False, the cmdlet discards the changes.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Boolean

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Start-IISCommitDelay](./Start-IISCommitDelay.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

