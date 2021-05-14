---
external help file: Microsoft.NPS.Commands.dll-Help.xml
Module Name: NPS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/nps/get-npsremediationservergroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NpsRemediationServerGroup
---

# Get-NpsRemediationServerGroup

## SYNOPSIS
Retrieves all remediation server groups from a Network Policy Server.

## SYNTAX

```
Get-NpsRemediationServerGroup [<CommonParameters>]
```

## DESCRIPTION
The **Get-NpsRemediationServerGroup** retrieves all remediation server groups from a Network Policy Server (NPS).
A remediation server group is a group of remediation servers in a Microsoft Windows NPS configuration.
In Network Access Protection (NAP), the network policies on an NPS use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.

## EXAMPLES

### Example 1: Get remediation groups from a Network Policy Server
```
PS C:\>$NPSRemedGroups01 = Get-NpsRemediationServerGroup
```

This command gets the remediation groups from an NPS and assigns them to the variable named **$NPSRemedGroups01**.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RemediationServerGroup[]

## NOTES

## RELATED LINKS

[Get-NpsRemediationServer](./Get-NpsRemediationServer.md)

[New-NpsRemediationServer](./New-NpsRemediationServer.md)

[New-NpsRemediationServerGroup](./New-NpsRemediationServerGroup.md)

[Remove-NpsRemediationServer](./Remove-NpsRemediationServer.md)

[Remove-NpsRemediationServerGroup](./Remove-NpsRemediationServerGroup.md)

