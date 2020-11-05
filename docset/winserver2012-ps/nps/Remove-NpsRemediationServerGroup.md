---
external help file: NPS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: B7DC72E8-0566-4193-BC73-8F71DAC4D404
manager: dansimp
---

# Remove-NpsRemediationServerGroup

## SYNOPSIS
Removes a remediation server group from an NPS.

## SYNTAX

```
Remove-NpsRemediationServerGroup -Name <String>
```

## DESCRIPTION
The **Remove-NpsRemediationServerGroup** cmdlet removes a remediation server group from a Network Policy Server (NPS).
A remediation server group is a group of remediation servers in a Microsoft Windows NPS configuration.

In Network Access Protection (NAP), the network policies on an NPS use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.

## EXAMPLES

### Example 1: Remove a remediation server group
```
PS C:\>Remove-NpsRemediationServerGroup -Name "RemServers01"
```

The following command removes a remediation server group named RemServers01.

## PARAMETERS

### -Name
Specifies the name of a remediation server group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NpsRemediationServer](./Get-NpsRemediationServer.md)

[Get-NpsRemediationServerGroup](./Get-NpsRemediationServerGroup.md)

[New-NpsRemediationServer](./New-NpsRemediationServer.md)

[New-NpsRemediationServerGroup](./New-NpsRemediationServerGroup.md)

[Remove-NpsRemediationServer](./Remove-NpsRemediationServer.md)

