---
author: Kateyanne
external help file: RemoteDesktop.psm1-help.xml
manager: dansimp
Module Name: RDMgmt
ms.author: v-kaunu
ms.reviewer:
online version: https://docs.microsoft.com/powershell/module/rdmgmt/set-rdworkspace?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-RDWorkspace

## SYNOPSIS
Assigns a workspace name for a Remote Desktop deployment.

## SYNTAX

```
Set-RDWorkspace [-Name] <String> [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-RDWorkspace** cmdlet assigns a workspace name for a Remote Desktop deployment.
Users see this name in their RemoteApp and Desktop Connection environment and their Remote Desktop Web Access (RD Web Access) environment.

## EXAMPLES

### Example 1: Assign a workspace name
```
PS C:\> Set-RDWorkspace -Name "Contoso Resources"
```

This command assigns the workspace name Contoso Resources for the Remote Desktop deployment that has the current computer as an RD Connection Broker server.
To specify a different RD Connection Broker server, use the **ConnectionBroker** parameter.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
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

### -Name
Specifies a workspace name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

[Get-RDWorkspace](./Get-RDWorkspace.md)

