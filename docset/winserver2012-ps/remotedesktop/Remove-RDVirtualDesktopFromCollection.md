---
external help file: 
ms.assetid: FCB82045-2029-4874-BEEA-F0653C4B46B0
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-RDVirtualDesktopFromCollection

## SYNOPSIS
Removes virtual desktops from a virtual desktop collection.

## SYNTAX

```
Remove-RDVirtualDesktopFromCollection [-CollectionName] <String> -VirtualDesktopName <String[]>
 [-ConnectionBroker <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDVirtualDesktopFromCollection** cmdlet removes one or more virtual desktops from a virtual desktop collection.

## EXAMPLES

### Example 1: Remove a virtual desktop from a virtual desktop collection
```
PS C:\> Remove-RDVirtualDesktopFromCollection -CollectionName "Virtual Desktop Pool" -VirtualDesktopName @("RDS-WKS-A27") -ConnectionBroker "rdcb.contoso.com"
```

This command removes the virtual desktop named "RDS-WKS-A27" from the virtual desktop collection named "Virtual Desktop Pool".

## PARAMETERS

### -CollectionName
Specifies the name of a virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Performs the action without a confirmation message.

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

### -VirtualDesktopName
Specifies an array of names of virtual desktops.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-RDVirtualDesktopCollection](./Get-RDVirtualDesktopCollection.md)

[Get-RDVirtualDesktop](./Get-RDVirtualDesktop.md)

