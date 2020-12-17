---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Disable-RDVirtualDesktopADMachineAccountReuse
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 156B1FE2-0A43-4198-8412-1D5D56CD689B
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Disable-RDVirtualDesktopADMachineAccountReuse

## SYNOPSIS
Prevents the RD Connection Broker server from reusing existing Active Directory (AD) computer accounts.

## SYNTAX

```
Disable-RDVirtualDesktopADMachineAccountReuse [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-RDVirtualDesktopADMachineAccountReuse** cmdlet prevents the Remote Desktop Connection Broker (RD Connection Broker) server from reusing existing Active Directory Domain Services (AD DS) computer accounts when you create new virtual desktops in a managed virtual desktop collection.
After you run this cmdlet, the RD Connection Broker server returns an error if it identifies existing AD computer accounts when you create new virtual desktop accounts.
This helps to prevent you from modifying accounts inadvertently.

## EXAMPLES

### Example 1: Disable account reuse on the RD Connection Broker
```
PS C:\> Disable-RDVirtualDesktopADMachineAccountReuse -ConnectionBroker "rdcb.contoso.com"
```

This command prevents the Remote Desktop Connection Broker server named "rdcb.contoso.com" from reusing existing AD DS computer accounts when you create virtual machines in a managed virtual desktop collection.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this remote desktop deployment.
If not supplied, defaults to the fully qualified domain name (FQDN) of the local host.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null
None.

## NOTES

## RELATED LINKS

[Enable-RDVirtualDesktopADMachineAccountReuse](./Enable-RDVirtualDesktopADMachineAccountReuse.md)

[Test-RDVirtualDesktopADMachineAccountReuse](./Test-RDVirtualDesktopADMachineAccountReuse.md)

