---
description: Configures permissions on an Active Directory (AD) Organizational Unit (OU) to enable computers in that OU to update their Windows Local Administrator Password Solution (LAPS) passwords.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/set-lapsadcomputerselfpermission?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Set-LapsADComputerSelfPermission
---

# Set-LapsADComputerSelfPermission

## SYNOPSIS
Configures permissions on an Active Directory (AD) Organizational Unit (OU) to enable computers in
that OU to update their Windows Local Administrator Password Solution (LAPS) passwords.

## SYNTAX

```
Set-LapsADComputerSelfPermission -Identity <String[]> [-Domain <String>]
 [-DomainController <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-LapsADComputerSelfPermission` cmdlet is used by administrators to configure security
permissions on an OU to allow computers in that OU to update their LAPS passwords.

## EXAMPLES

### Example 1

```powershell
Set-LapsADComputerSelfPermission -Identity LapsTestOU
```

```Output
Name       DistinguishedName
----       -----------------
LapsTestOU OU=LapsTestOU,DC=laps,DC=com
```

This example demonstrates how to run the cmdlet.

## PARAMETERS

### -Credential

Specifies the credentials to use when updating AD. If not specified, the current
user's credentials are used.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the name of the domain to connect to.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

Specifies the name of the domain controller to connect to.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies the name of the OU to update.

This parameter accepts several different name formats that influence the criteria used in the
resultant AD search. The supported name formats are as follows:

- distinguishedName (begins with a `CN=`)
- name (for all other inputs)

Setting permissions on the domain root is only supported using the distinguishedName input format, for example 'DC=laps,DC=com'.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet isn't run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)
