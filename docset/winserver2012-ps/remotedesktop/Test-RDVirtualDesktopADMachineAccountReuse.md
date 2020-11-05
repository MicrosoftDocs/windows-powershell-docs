---
external help file: 
ms.assetid: A1305ECB-EC4B-4580-8667-1554C7B746BA
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Test-RDVirtualDesktopADMachineAccountReuse

## SYNOPSIS
Detects whether the RD Connection Broker server is configured to reuse existing AD DS computer accounts.

## SYNTAX

```
Test-RDVirtualDesktopADMachineAccountReuse [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-RDVirtualDesktopADMachineAccountReuse** cmdlet detects whether the Remote Desktop Connection Broker (RD Connection Broker) server is configured to reuse existing Active Directory Domain Services (AD DS) computer accounts when you create new virtual machines in a managed virtual desktop collection.

## EXAMPLES

### Example 1: Detect whether account reuse is configured
```
PS C:\> Test-RDVirtualDesktopADMachineAccountReuse -ConnectionBroker "rdcb.contoso.com"
```

This command detects whether the RD Connection Broker server is configured to reuse existing AD DS computer accounts when you create new virtual machines in a managed virtual desktop collection.

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

[Disable-RDVirtualDesktopADMachineAccountReuse](./Disable-RDVirtualDesktopADMachineAccountReuse.md)

