---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
Module Name: DirectAccessClientComponents
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/directaccessclientcomponents/remove-daentrypointtableitem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DAEntryPointTableItem
---

# Remove-DAEntryPointTableItem

## SYNOPSIS
Removes a DirectAccess entry point from the specified configuration store.

## SYNTAX

### ByPolicyStore (Default)
```
Remove-DAEntryPointTableItem [-EntryPointName <String[]>] -PolicyStore <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByGpoSession
```
Remove-DAEntryPointTableItem [-EntryPointName <String[]>] -GPOSession <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-DAEntryPointTableItem -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DAEntryPointTableItem** cmdlet removes a DirectAccess entry point from the specified configuration store.
You must specify both the configuration store, by using either *GPOSession* or *PolicyStore*, and name of the entry point to remove.

## EXAMPLES

### Example 1: Remove an entry point by using the pipeline
```
PS C:\> Get-DAEntryPointTableItem -EntryPointName "Redmond" -PolicyStore "Contoso\GPO1" | Remove-DAEntryPointTableItem
```

This cmdlet removes the entry point named Redmond by first getting the entry point information using Get-DAEntryPointTableItem and then passing the information to **Remove-DAEntryPointTableItem**.

### Example 2: Remove an entry point directly
```
PS C:\>Remove-DAEntryPointTableItem -EntryPointName "Redmond" -PolicyStore "Contoso\GPO1"
```

This cmdlet removes an entry point named Redmond by specifying the *EntryPointName* and *PolicyStore* parameters.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -EntryPointName
Specifies the name of the entry point to remove.
This parameter supports wildcards.

```yaml
Type: String[]
Parameter Sets: ByPolicyStore, ByGpoSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GPOSession
Specifies the Group Policy session from which to read configuration information.
You can use *GPOSession* with the *NetGPO* cmdlets to aggregate multiple operations performed on a Group Policy Object.

*GPOSession* cannot be used in conjunction with *PolicyStore*.

```yaml
Type: String
Parameter Sets: ByGpoSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Sends items from an interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output.
However, to send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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

### -PolicyStore
Specifies the policy store from which the cmdlet retrieves the entry point information.

To retrieve the entry point information from a Group Policy Object, specify the GPO name using the format "Domain\GPOName".

To retrieve the entry point information from a computer's local GPO, specify the computer's local GPO name in the format "GPO:\<computername\>".

*PolicyStore* cannot be used in conjunction with *GPOSession*.

The default value for *PolicyStore* is ActiveStore.

```yaml
Type: String
Parameter Sets: ByPolicyStore
Aliases:

Required: True
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

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DASiteTableEntry
This cmdlet accepts as input a CIM object which contains a DA site table entry.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-DAEntryPointTableItem](./Get-DAEntryPointTableItem.md)

[New-DAEntryPointTableItem](./New-DAEntryPointTableItem.md)

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

[Reset-DAEntryPointTableItem](./Reset-DAEntryPointTableItem.md)

[Set-DAEntryPointTableItem](./Set-DAEntryPointTableItem.md)

