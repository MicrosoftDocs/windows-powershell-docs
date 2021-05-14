---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://docs.microsoft.com/powershell/module/nps/get-npsremediationservergroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NpsRemediationServerGroup

## SYNOPSIS
Retrieves all remediation server groups from a Network Policy Server.

## SYNTAX

```
Get-NpsRemediationServerGroup
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

