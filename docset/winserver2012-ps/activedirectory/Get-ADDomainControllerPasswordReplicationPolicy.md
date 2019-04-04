---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 7974AE6F-264B-498C-893F-4069DF974E8D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-ADDomainControllerPasswordReplicationPolicy

## SYNOPSIS
Gets the members of the allowed list or denied list of a read-only domain controller's password replication policy.

## SYNTAX

### AllowedPRP (Default)
```
Get-ADDomainControllerPasswordReplicationPolicy [-Allowed] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

### DeniedPRP
```
Get-ADDomainControllerPasswordReplicationPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Denied]
 [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADDomainControllerPasswordReplicationPolicy gets the users, computers, service accounts and groups that are members of the applied list or denied list for a read-only domain controller's (RODC) password replication policy.
To get the members of the applied list, specify the AppliedList parameter.
To get the members of the denied list, specify the DeniedList parameter.

The Identity parameter specifies the RODC that uses the allowed and denied lists to apply the password replication policy.
You can identify a domain controller by its GUID, IPV4Address, IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the Distinguished Name (DN) of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the DN of the computer object that represents the domain controller.

You can also set the Identity parameter to a domain controller object variable, such as $\<localDomainControllerObject\>, or pass a domain controller object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomainController cmdlet to retrieve a domain controller object and then pass the object through the pipeline to the Get-ADDomainControllerPasswordReplicationPolicy cmdlet.

If you specify a writeable domain controller for this cmdlet, the cmdlet returns a non-terminating error.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADDomainControllerPasswordReplicationPolicy -Identity "FABRIKAM-RODC1" -Allowed | ft Name,ObjectClass
```

Description

-----------

Get from an RODC domain controller password replication policy the allowed accounts showing the name and object class of each

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDomainController -Filter {IsReadOnly -eq $true} | Get-ADDomainControllerPasswordReplicationPolicy -Allowed

DistinguishedName : CN=Allowed RODC Password Replication Group,CN=Users,DC=Fabrikam,DC=com
Name              : Allowed RODC Password Replication Group
ObjectClass       : group
ObjectGUID        : 239b0470-7f49-472d-8fcb-4911e90b2c5e
SamAccountName    : Allowed RODC Password Replication Group
SID               : S-1-5-21-41432690-3719764436-1984117282-571
```

Description

-----------

Get the password replication policy allowed lists from all RODCs in the domain.

## PARAMETERS

### -Allowed
{{Fill Allowed Description}}

```yaml
Type: SwitchParameter
Parameter Sets: AllowedPRP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthType
{{Fill AuthType Description}}

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
{{Fill Credential Description}}

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Denied
{{Fill Denied Description}}

```yaml
Type: SwitchParameter
Parameter Sets: DeniedPRP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
{{Fill Identity Description}}

```yaml
Type: ADDomainController
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
{{Fill Server Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADDomainController
A domain controller object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns one or more objects that represent the users, computers, service accounts and groups that are members of the applied list or denied list of the domain controller password replication policy.
The list returned depends on the parameters specified.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Remove-ADDomainControllerPasswordReplicationPolicy](./Remove-ADDomainControllerPasswordReplicationPolicy.md)
