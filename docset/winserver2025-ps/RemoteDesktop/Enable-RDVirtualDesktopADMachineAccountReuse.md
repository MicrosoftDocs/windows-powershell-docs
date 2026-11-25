---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/enable-rdvirtualdesktopadmachineaccountreuse?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RDVirtualDesktopADMachineAccountReuse
---

# Enable-RDVirtualDesktopADMachineAccountReuse

## SYNOPSIS
Configures the RD Connection Broker server to reuse existing AD DS computer accounts.

## SYNTAX

```
Enable-RDVirtualDesktopADMachineAccountReuse [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-RDVirtualDesktopADMachineAccountReuse** cmdlet configures the Remote Desktop Connection Broker (RD Connection Broker) server to reuse existing Active Directory Domain Services (AD DS) computer accounts for pooled virtual desktops when you create new virtual machines in a managed virtual desktop collection.

## EXAMPLES

### Example 1: Enable account reuse on the RD Connection Broker
```
PS C:\> Enable-RDVirtualDesktopADMachineAccountReuse -ConnectionBroker "rdcb.contoso.com"
```

This command enables the Remote Desktop Connection Broker server named rdcb.contoso.com to reuse existing Active Directory Domain Services computer accounts when you create new virtual machines in a managed virtual desktop collection.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

[Disable-RDVirtualDesktopADMachineAccountReuse](./Disable-RDVirtualDesktopADMachineAccountReuse.md)

[Test-RDVirtualDesktopADMachineAccountReuse](./Test-RDVirtualDesktopADMachineAccountReuse.md)

