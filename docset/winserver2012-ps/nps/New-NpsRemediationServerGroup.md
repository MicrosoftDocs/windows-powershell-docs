---
external help file: NPS_Cmdlets.xml
Module Name: NPS
online version: https://docs.microsoft.com/powershell/module/nps/new-npsremediationservergroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-NpsRemediationServerGroup

## SYNOPSIS
Creates a remediation server group.

## SYNTAX

```
New-NpsRemediationServerGroup [-Name] <String>
```

## DESCRIPTION
The **New-NpsRemediationServerGroup** cmdlet creates a remediation server group.
A remediation server group is a group of remediation servers in a Microsoft Windows Network Policy Server (NPS) configuration.
In Network Access Protection (NAP), the network policies on an NPS use remediation to enforce NAP for clients whose health state does not comply with policy requirements and to bring those clients into a compliant state.
Remediation servers provide the resources that clients need to become compliant including the client management point, the software update point, or distribution points that contain software updates.

You must configure remediation servers in a remediation server group on NPS if you use Dynamic Host Configuration Protocol (DHCP) enforcement.
A remediation server group usually includes infrastructure servers such as Domain Name Service (DNS) servers, Windows Internet Naming Service (WINS) servers, and domain controllers.
However, do not add servers that are configured as management points, software update points, and distribution points to a remediation server group because clients that undergo remediation dynamically supply these servers.

## EXAMPLES

### Example 1: Create a remediation server group
```
PS C:\>$NWRemedServers01 = New-NpsRemediationServerGroup -Name "NWRemedServers01"
```

This command creates a remediation server group named NWRemedServers01 and assigns it to the variable named **$NWRemedServers01**.

## PARAMETERS

### -Name
Specifies the name of a remediation server group that you add to a Network Policy Server (NPS) configuration.

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

### NpsRemediationServerGroup

## NOTES

## RELATED LINKS

[Get-NpsRemediationServer](./Get-NpsRemediationServer.md)

[Get-NpsRemediationServerGroup](./Get-NpsRemediationServerGroup.md)

[New-NpsRemediationServer](./New-NpsRemediationServer.md)

[Remove-NpsRemediationServer](./Remove-NpsRemediationServer.md)

[Remove-NpsRemediationServerGroup](./Remove-NpsRemediationServerGroup.md)

