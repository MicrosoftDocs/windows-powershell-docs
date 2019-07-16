---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Test-RDOUAccess
ms.reviewer:
ms.assetid: FB468190-FA3E-4A38-BC4A-8F2645373055
---

# Test-RDOUAccess

## SYNOPSIS
Verifies that the Remote Desktop Connection Broker  server can access an Active Directory Domain Services  organizational unit.

## SYNTAX

```
Test-RDOUAccess [[-Domain] <String>] [-OU] <String> [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-RDOUAccess** cmdlet verifies that the RD Connection Broker server has access to the organizational units (OUs) in a given domain of Active Directory Domain Services (AD DS).

The RD Connection Broker must have Read access to an OU to query user account information.

## EXAMPLES

### Example 1: Verify access to an OU
```
PS C:\> Test-RDOUAccess -ConnectionBroker "Rdcb.Contoso.com" -OU "Computers"
```

This command tests access to an OU named Computers by the RD Connection Broker server named Rdcb.Contoso.com.

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
Specifies the Active Directory (AD) domain for which to verify access.

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
Specifies one or more OUs for which to verify access.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Grant-RDOUAccess](./Grant-RDOUAccess.md)

