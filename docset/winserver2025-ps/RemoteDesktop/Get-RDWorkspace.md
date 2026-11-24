---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdworkspace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDWorkspace
---

# Get-RDWorkspace

## SYNOPSIS
Gets the workspace name for a Remote Desktop deployment.

## SYNTAX

```
Get-RDWorkspace [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDWorkspace** cmdlet gets the workspace name for a Remote Desktop deployment.
Users see this name in their RemoteApp and Desktop Connection environment and their Remote Desktop Web Access (RD Web Access) environment.

## EXAMPLES

### Example 1: Get a workspace name
```
PS C:\> Get-RDWorkspace -ConnectionBroker "RDCB.Contoso.com"
```

This command gets the workspace name for the Remote Desktop deployment associated with the RD Connection Broker server named RDCB.Contoso.com.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
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

### Microsoft.RemoteDesktopServices.Management.WorkspaceClass

## NOTES

## RELATED LINKS

[Set-RDWorkspace](./Set-RDWorkspace.md)

