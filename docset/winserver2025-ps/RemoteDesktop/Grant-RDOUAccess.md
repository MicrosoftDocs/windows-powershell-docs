---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/grant-rdouaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-RDOUAccess
---

# Grant-RDOUAccess

## SYNOPSIS
Grants the Remote Desktop Connection Broker server access to one or more organizational units in a given domain of Active Directory Domain Services.

## SYNTAX

```
Grant-RDOUAccess [[-Domain] <String>] [-OU] <String> [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Grant-RDOUAccess** cmdlet grants the Remote Desktop Connection Broker (RD Connection Broker) server access to one or more organizational units (OUs) in a given domain of Active Directory Domain Services (AD DS).

The RD Connection Broker must have Read access to an OU to query user account information.

## EXAMPLES

### Example 1: Grant the RD Connection Broker access to the Computers OU
```
PS C:\> Grant-RDOUAccess -ConnectionBroker "Rdcb.Contoso.com" -OU "Computers"
```

This command grants the RD Connection Broker server named Rdcb.Contoso.com access to the OU named Computers.

## PARAMETERS

### -ConnectionBroker
Specifies an RD Connection Broker server for a remote desktop deployment.
If you do not supply a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies an Active Directory (AD) domain to which to grant access.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OU
Specifies one or more OUs to which to grant access.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Test-RDOUAccess](./Test-RDOUAccess.md)

