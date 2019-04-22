---
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
ms.assetid: D72C061A-C5BE-4BEE-B4AE-4CC157E94E88
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
online version: 
schema: 2.0.0
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
**Remove-DAEntryPointTableItem** removes a DirectAccess entry point from the specified configuration store.
You must specify both the configuration store, by using either **GPOSession** or **PolicyStore**, and name of the entry point to remove.

## EXAMPLES

### Example 1: Remove an entry point by using the pipeline
```
PS C:\> Get-DAEntryPointTableItem -EntryPointName "Redmond" -PolicyStore "Contoso\GPO1" | Remove-DAEntryPointTableItem
```

This cmdlet removes the entry point named **Redmond** by first getting the entry point information using **Get-DAEntryPointTableItem** and then passing the information to **Remove-DAEntryPointTableItem**.

### Example 2: Remove an entry point directly
```
PS C:\>Remove-DAEntryPointTableItem  -EntryPointName "Redmond" -PolicyStore "Contoso\GPO1"
```

This cmdlet removes an entry point named **Redmond** by using specifying the **EntryPointName** and **PolicyStore**.

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
You can use **GPOSession** with the **NetGPO** cmdlets to aggregate multiple operations performed on a Group Policy Object.

**GPOSession** cannot be used in conjunction with **PolicyStore**.

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
Passes the object that contains the entry point to be deleted.

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

To retrieve the entry point information from a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To retrieve the entry point information from a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

**PolicyStore** cannot be used in conjunction with **GPOSession**.

The default value for **PolicyStore** is ActiveStore.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/StandardCimv2/MSFT_DASiteTableEntry
This cmdlet accepts as input a CIM object which contains a DA site table entry.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-DAEntryPointTableItem](./New-DAEntryPointTableItem.md)

[Get-DAEntryPointTableItem](./Get-DAEntryPointTableItem.md)

[Set-DAEntryPointTableItem](./Set-DAEntryPointTableItem.md)

[Reset-DAEntryPointTableItem](./Reset-DAEntryPointTableItem.md)

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

