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
title: Remove-RDSessionHost
ms.reviewer:
ms.assetid: 15C9F651-79E7-4DFC-8C1B-56E69744EE54
---

# Remove-RDSessionHost

## SYNOPSIS
Removes one or more RD Session Host servers from a session collection.

## SYNTAX

```
Remove-RDSessionHost [-SessionHost] <String[]> [-ConnectionBroker <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDSessionHost** cmdlet removes one or more Remote Desktop Session Host (RD Session Host) servers from a session collection.
The servers remain part of the deployment.

RD Session Host is a Remote Desktop Services role service that lets users share Windows-based programs or the full Windows desktop.
Users can connect to an RD Session Host server to run programs, save files, and use network resources on that server.

## EXAMPLES

### Example 1: Remove a session host
```
PS C:\> Remove-RDSessionHost -SessionHost @("rdsh.contoso.com") -ConnectionBroker "rdcb.contoso.com" -Force
```

This command removes the session host named rdsh.contoso.com from the session collection.

## PARAMETERS

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
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for this Remote Desktop deployment.
If this parameter does not appear, the default value is the fully qualified domain name (FQDN) of the local host.

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
Forces the command to run without asking for user confirmation.

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

### -SessionHost
Specifies an array that contains the name(s) of one or more servers that run the RD Session Host role and that you remove from the session collection.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Add-RDSessionHost](./Add-RDSessionHost.md)

[Get-RDSessionHost](./Get-RDSessionHost.md)

[Set-RDSessionHost](./Set-RDSessionHost.md)

