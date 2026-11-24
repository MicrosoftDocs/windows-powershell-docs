---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.BackgroundIntelligentTransfer.Management.dll-Help.xml
Module Name: BitsTransfer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitstransfer/remove-bitstransfer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-BitsTransfer
---

# Remove-BitsTransfer

## SYNOPSIS
Cancels a BITS transfer job.

## SYNTAX

```
Remove-BitsTransfer [-BitsJob] <BitsJob[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-BitsTransfer** cmdlet cancels a Background Intelligent Transfer Service (BITS) transfer job.
It deletes the underlying transfer job, removes any temporary files from the client, and deletes the associated **BitsJob** object.

When the **Remove-BitsTransfer** cmdlet cancels a transfer job, it deletes all the transfers.
Consider a scenario is which you are transferring three files.
One file is completely transferred, one file is pending, and one file is currently being transferred.
In this scenario, **Remove-BitsTransfer** cancels the whole transfer and deletes the underlying files.
Any files that were already transferred are not available after you use the **Remove-BitsTransfer** cmdlet to cancel the transfer job.
Optionally, you can use the **Complete-BitsTransfer** cmdlet to commit any files that are completely downloaded and to cancel the pending and current transfers.
The transferred file is not be deleted and is available.

## EXAMPLES

### Example 1: Cancel all BITS transfer jobs owned by the current user
```
PS C:\> Get-BitsTransfer | Remove-BitsTransfer
```

This command cancels all the BITS transfer jobs that are owned by the current user.

The output of the **Get-BitsTransfer** cmdlet is piped to the **Remove-BitsTransfer** cmdlet.
The output is a set of **BitsJob** objects.

### Example 2: Cancel all BITS transfer jobs on the computer
```
C:\PS>$Bits = Get-BitsTransfer -AllUsers
PS C:\> Remove-BitsTransfer -BitsJob $Bits
```

This command cancels all the BITS transfer jobs on the computer.

The first command gets all the **BitsJob** objects on the computer and then stores them in the $Bits variable.

The second command uses the *BitsJob* parameter to pass the **BitsJob** objects that are stored in the $Bits variable to the **Remove-BitsTransfer** cmdlet.

## PARAMETERS

### -BitsJob
Specifies an array of BITS transfer jobs to cancel.
You can pipe a value to this parameter from other cmdlets that return **BitsJob** objects, such as the **Get-BitsTransfer** cmdlet.

```yaml
Type: BitsJob[]
Parameter Sets: (All)
Aliases: b

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet accepts one or more **BitsJob** objects as input that populates the *BitsJob* parameter.

## OUTPUTS

### None
This cmdlet does not generate any output.

## NOTES
* After a job is removed or completed, any job objects that were previously cached in variables or in scripts are no longer valid.

## RELATED LINKS

[Add-BitsFile](./Add-BitsFile.md)

[Complete-BitsTransfer](./Complete-BitsTransfer.md)

[Get-BitsTransfer](./Get-BitsTransfer.md)

[Resume-BitsTransfer](./Resume-BitsTransfer.md)

[Set-BitsTransfer](./Set-BitsTransfer.md)

[Start-BitsTransfer](./Start-BitsTransfer.md)

[Suspend-BitsTransfer](./Suspend-BitsTransfer.md)

