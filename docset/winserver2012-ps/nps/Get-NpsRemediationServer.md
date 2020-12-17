---
external help file: NPS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 42367CB1-3ACA-49EB-B893-B2C80D2E4285
manager: dansimp
---

# Get-NpsRemediationServer

## SYNOPSIS
Retrieves a list of remediation servers from a remediation server group.

## SYNTAX

```
Get-NpsRemediationServer [-RemediationServerGroup] <String>
```

## DESCRIPTION
The **Get-NpsRemediationServer** cmdlet retrieves a list of remediation servers from the specified remediation server group.

In Network Access Protection (NAP), the network policies on the Microsoft Windows Network Policy Server (NPS) use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.

For more information about remediation, see NAP Configuration Overviewhttp://technet.microsoft.com/library/dd125319(v=ws.10).aspx (http://technet.microsoft.com/library/dd125319(v=ws.10).aspx) on TechNet.

## EXAMPLES

### Example 1: Get a list of remediation servers from a remediation server group
```
PS C:\>$MyRemediationServers = Get-NpsRemediationServer -RemediationServerGroup "ContosoRemediationServers"
```

This command gets a list of the remediation servers from the remediation server group named "ContosoRemediationServers" and assigns them to the variable named **$MyRemediationServers**.

## PARAMETERS

### -RemediationServerGroup
Specifies the name of the remediation server group from which to return remediation servers.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### NpsRemediationServer[]

## NOTES

## RELATED LINKS

[Get-NpsRemediationServerGroup](./Get-NpsRemediationServerGroup.md)

[New-NpsRemediationServer](./New-NpsRemediationServer.md)

[New-NpsRemediationServerGroup](./New-NpsRemediationServerGroup.md)

[Remove-NpsRemediationServer](./Remove-NpsRemediationServer.md)

[Remove-NpsRemediationServerGroup](./Remove-NpsRemediationServerGroup.md)

