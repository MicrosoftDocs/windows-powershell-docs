---
external help file: Microsoft.BackgroundIntelligentTransfer.Management.dll-Help.xml
Module Name: BitsTransfer
ms.date: 10/29/2017
online version: https://docs.microsoft.com/powershell/module/bitstransfer/suspend-bitstransfer?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-BitsTransfer
---

# Suspend-BitsTransfer

## SYNOPSIS
Suspends a Background Intelligent Transfer Service (BITS) transfer job.

## SYNTAX

```
Suspend-BitsTransfer [-BitsJob] <BitsJob[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Suspend-BitsTransfer** cmdlet suspends (pauses) one or more BITS transfer jobs.
If the transfer is already suspended, the cmdlet does nothing.
You can restart the BITS transfer job by using the **Resume-BitsTransfer** cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-BitsTransfer | Suspend-BitsTransfer
```

This command suspends all the BITS transfer jobs that are owned by the current user.

The output of **Get-BitsTransfer** is a set of BitsJob objects.
This output is piped to the **Suspend-BitsTransfer** cmdlet.

### EXAMPLE 2
```
PS C:\>$b = Get-BitsTransfer -AllUsers
PS C:\>Suspend-BitsTransfer -BitsJob $b
```

This command suspends all the BITS transfer jobs on the computer.

The first command retrieves all the BitsJob objects on the computer and then stores them in the $b variable.

The second command uses the **BitsJob** parameter to pass the BitsJob objects that are stored in the $b variable to the **Suspend-BitsTransfer** cmdlet.

## PARAMETERS

### -BitsJob
Specifies the BITS transfer jobs to suspend.
You can pipe a value to this parameter from other cmdlets that return BitsJob objects, such as **Get-BitsTransfer**.

```yaml
Type: BitsJob[]
Parameter Sets: (All)
Aliases: b

Required: True
Position: 1
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet accepts one or more BitsJob objects as input that populates the BitsJob parameter.

## OUTPUTS

### Microsoft.BackgroundIntelligentTransfer.Management.BitsJob[]
This cmdlet generates the BitsJob objects that are associated with the BITS transfer jobs that were suspended.

## NOTES

## RELATED LINKS

[Add-BitsFile](./Add-BitsFile.md)

[Complete-BitsTransfer](./Complete-BitsTransfer.md)

[Get-BitsTransfer](./Get-BitsTransfer.md)

[Remove-BitsTransfer](./Remove-BitsTransfer.md)

[Resume-BitsTransfer](./Resume-BitsTransfer.md)

[Set-BitsTransfer](./Set-BitsTransfer.md)

[Start-BitsTransfer](./Start-BitsTransfer.md)

