---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nps/get-npssharedsecrettemplate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NpsSharedSecretTemplate
---

# Get-NpsSharedSecretTemplate

## SYNOPSIS
Returns a list of available shared secret templates.

## SYNTAX

```
Get-NpsSharedSecretTemplate [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NpsSharedSecretTemplate** cmdlet returns a list of available shared secret templates.
Network Policy Server (NPS) includes a template type that you can use to assign a shared secret when you configure a Remote Authentication Dial-In User Service (RADIUS) client or server.

A shared secret is a text string that serves as a password between a RADIUS client and a RADIUS server, a RADIUS client and a RADIUS proxy, or a RADIUS proxy and a RADIUS server.
RADIUS clients, servers, and proxies use shared secrets to verify that the RADIUS messages they receive originate with a RADIUS-enabled device that is configured with the same shared secret.

## EXAMPLES

### Example 1: Get shared secrets templates from a Network Policy Server
```
PS C:\>Get-NPSSharedSecretTemplate
```

This command gets the shared secrets templates from an NPS.

## PARAMETERS

### -Name
Specifies the name of the shared secret template to return.
If you do not specify this parameter, the cmdlet returns all shared secret templates.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### NpsSharedSecretTemplate[]

## NOTES

## RELATED LINKS

