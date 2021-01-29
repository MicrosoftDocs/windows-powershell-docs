---
external help file: MSFT_DASiteTableEntry.cdxml-help.xml
Module Name: DirectAccessClientComponents
online version: 
schema: 2.0.0
title: Reset-DAEntryPointTableItem
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: FCA241CE-76A9-4937-A37E-CAD0B0622E78
---

# Reset-DAEntryPointTableItem

## SYNOPSIS
Resets the specified DirectAccess entry point configuration to the default configuration.

## SYNTAX

### ByPolicyStore (Default)
```
Reset-DAEntryPointTableItem [-EntryPointName <String[]>] -PolicyStore <String> [-TeredoServerIP]
 [-IPHttpsProfile] [-GslbIP] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByGpoSession
```
Reset-DAEntryPointTableItem [-EntryPointName <String[]>] -GPOSession <String> [-TeredoServerIP]
 [-IPHttpsProfile] [-GslbIP] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Reset-DAEntryPointTableItem -InputObject <CimInstance[]> [-TeredoServerIP] [-IPHttpsProfile] [-GslbIP]
 [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Reset-DAEntryPointTableItem** resets the configuration of the entry point specified by **EntryPointName** to the default configuration.
You can use the optional parameters to reset specific configuration settings to the default configuration.

## EXAMPLES

### Example: Reset an entry point property
```
PS C:\> Reset-DAEntryPointTableItem -GslbIP -EntryPointName "Paris" -PolicyStore "Contoso\GPO1"
```

This cmdlet resets the **GslbIP** property to not-configured for the **Paris** entry point.

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
Specifies the name of the entry point to modify.
The entry point name is usually the friendly name of the location, such as "Redmond" or "Paris".

Specify the name of the entry point by using double quotes ( " ").

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
Specifies the Group Policy session to send configuration information.
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

### -GslbIP
Resets the global server load balancing (GSLB) IP of the specified sites to a non-configured state.

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

### -IPHttpsProfile
Resets the IpHTTPsProfile property of the specified sites to a non-configured state.
For more information about IPHTTPs profiles, see the **NetIPHTTPsConfiguration** cmdlets in the **NetworkTransition** module.

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
Specifies the name of the object to modify.

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
Specifies the policy store into which the cmdlet adds the entry point.

To add the entry point to a Group Policy Object, specify the GPO name using the following format: "Domain\GPOName"

To add the entry point information to a computer's local GPO, specify the computer's local GPO name in the following format: "GPO:\<computername\>"

**PolicyStore** cannot be used in conjunction with **GPOSession**.

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

### -TeredoServerIP
Resets the TeredoServerIP property of the specified sites to a non-configured state.

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

[Rename-DAEntryPointTableItem](./Rename-DAEntryPointTableItem.md)

[Remove-DAEntryPointTableItem](./Remove-DAEntryPointTableItem.md)

