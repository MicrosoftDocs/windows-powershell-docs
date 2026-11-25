---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.BackgroundIntelligentTransfer.Management.dll-Help.xml
Module Name: BitsTransfer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/bitstransfer/complete-bitstransfer?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-BitsTransfer
---

# Complete-BitsTransfer

## SYNOPSIS
Completes a BITS transfer job.

## SYNTAX

```
Complete-BitsTransfer [-BitsJob] <BitsJob[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Complete-BitsTransfer** cmdlet ends one or more Background Intelligent Transfer Service (BITS) transfer jobs and then saves the files on the client computer.
If an error occurs, the associated **BitsJob** object is written to the error pipeline.

## EXAMPLES

### Example 1: Complete all BITS transfer jobs owned by the current user
```
C:\PS>Get-BitsTransfer | Complete-BitsTransfer
```

This command completes all the BITS transfer jobs that are owned by the current user.

In this command, the output of the **Get-BitsTransfer** cmdlet is piped to the **Complete-BitsTransfer** cmdlet.
The output is a set of **BitsJob** objects.

### Example 2: Complete all BITS transfer jobs on the computer
```
PS C:\> $Bits = Get-BitsTransfer -AllUsers
PS C:\> Complete-BitsTransfer -BitsJob $Bits
```

These commands complete all the BITS transfer jobs on the computer.

The first command retrieves all the **BitsJob** objects on the computer and then stores them in the $Bits variable.

The second command uses the *BitsJob* parameter to pass the **BitsJob** objects that are stored in the $Bits variable to the **Complete-BitsTransfer** cmdlet.

### Example 3: Complete a BITS transfer job by display name
```
PS C:\> Get-BitsTransfer -Name testjob1 | Complete-BitsTransfer
```

This command completes the BITS transfer job that is identified by the specified display name.

The output of the **Get-BitsTransfer** cmdlet is a **BitsJob** object.
This output is piped to the **Complete-BitsTransfer** cmdlet.

## PARAMETERS

### -BitsJob
Specifies the BITS transfer jobs to complete.
You can pipe a value to this parameter from other cmdlets that return **BitsJob** objects, such as **Get-BitsTransfer**.

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

## RELATED LINKS

[Add-BitsFile](./Add-BitsFile.md)

[Get-BitsTransfer](./Get-BitsTransfer.md)

[Remove-BitsTransfer](./Remove-BitsTransfer.md)

[Resume-BitsTransfer](./Resume-BitsTransfer.md)

[Set-BitsTransfer](./Set-BitsTransfer.md)

[Start-BitsTransfer](./Start-BitsTransfer.md)

[Suspend-BitsTransfer](./Suspend-BitsTransfer.md)

