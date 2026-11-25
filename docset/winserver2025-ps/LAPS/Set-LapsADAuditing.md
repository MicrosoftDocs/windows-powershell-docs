---
description: Configures an Active Directory (AD) Organizational Unit (OU) to enable auditing on the Windows Local Administrator Password Solution (LAPS) password schema attributes.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/set-lapsadauditing?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Set-LapsADAuditing
---

# Set-LapsADAuditing

## SYNOPSIS
Configures an Active Directory (AD) Organizational Unit (OU) to enable auditing on the Windows Local
Administrator Password Solution (LAPS) password schema attributes.

## SYNTAX

```
Set-LapsADAuditing [-Credential <PSCredential>] -Identity <String[]> -AuditedPrincipals <String[]>
 [-AuditType <AuditFlags>] [-Domain <String>] [-DomainController <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1

```powershell
Set-LapsADAuditing -Identity LapsTestOU -AuditedPrincipals "laps.com\LapsAdmin" -AuditType Success
OU=LapsTestOU,DC=laps,DC=com
```

This example demonstrates configuring `Success` audits on an OU.

### Example 2

```powershell
Set-LapsADAuditing -Identity LapsTestOU -AuditedPrincipals "laps.com\LapsAdminsGroup" -AuditType Failure
OU=LapsTestOU,DC=laps,DC=com
```

This example demonstrates configuring `Failure` audits on an OU.

## PARAMETERS

### -AuditedPrincipals

Specifies the name of the users or groups should be configured for auditing. Users or groups may be
specified in either name or SID format. If specified in name format, the name must always include
the identifying domain name portion unless the name maps to a well-known or built-in account.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuditType

Specifies whether to configure Success or Failure auditing.

```yaml
Type: System.Security.AccessControl.AuditFlags
Parameter Sets: (All)
Aliases:
Accepted values: None, Success, Failure

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the credentials to use when updating AD. If not specified, the current user's credentials
are used.

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
