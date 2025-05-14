---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/disable-rdvirtualdesktopadmachineaccountreuse?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-RDVirtualDesktopADMachineAccountReuse
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

This command prevents the Remote Desktop Connection Broker server named rdcb.contoso.com from reusing existing AD DS computer accounts when you create virtual machines in a managed virtual desktop collection.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Enable-RDVirtualDesktopADMachineAccountReuse](./Enable-RDVirtualDesktopADMachineAccountReuse.md)

[Test-RDVirtualDesktopADMachineAccountReuse](./Test-RDVirtualDesktopADMachineAccountReuse.md)

