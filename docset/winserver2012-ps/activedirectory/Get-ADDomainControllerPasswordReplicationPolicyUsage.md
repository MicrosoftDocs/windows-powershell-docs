---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 06AF4146-74B1-4F1D-A4A8-7B626C3535E2
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-ADDomainControllerPasswordReplicationPolicyUsage

## SYNOPSIS
Gets the Active Directory accounts that are authenticated by a read-only domain controller or that are in the revealed list of the domain controller.

## SYNTAX

### RevealedAccounts (Default)
```
Get-ADDomainControllerPasswordReplicationPolicyUsage [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADDomainController> [-RevealedAccounts] [-Server <String>] [<CommonParameters>]
```

### AuthenticatedAccounts
```
Get-ADDomainControllerPasswordReplicationPolicyUsage [-AuthenticatedAccounts] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADDomainController> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get-ADDomainControllerPasswordReplicationPolicyUsage cmdlet gets the user or computer accounts that are authenticated by a read-only domain controller (RODC) or that have passwords that are stored on that RODC.
The list of accounts that are stored on a RODC is known as the revealed list.

To get accounts that are authenticated by the RODC, use the AuthenticatedAccounts parameter.
To get the accounts that have passwords stored on the RODC, use the RevealedAccounts parameter.

The Identity parameter specifies the RODC.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the Distinguished Name (DN) of the NTDS settings object of the server object, the GUID of the NTDS settings object of the server object under the configuration partition, or the DN of the computer object that represents the domain controller.
You can also set the Identity parameter to a domain controller object variable, such as $\<localDomainControllerObject\>, or pass a domain controller object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomainController cmdlet to retrieve a domain controller object and then pass the object through the pipeline to the Get-ADDomainControllerPasswordReplicationPolicyUsage cmdlet.
If you specify a writeable domain controller for this cmdlet, the cmdlet returns a non-terminating error.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADDomainControllerPasswordReplicationPolicyUsage -Identity "FABRIKAM-RODC1" -AuthenticatedAccounts | ft Name,ObjectClass -A
```

Description

-----------

Get the authenticated accounts for a given RODC showing the name and object class of each

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADDomainControllerPasswordReplicationPolicyUsage -Identity "FABRIKAM-RODC1" -RevealedAccounts | ft Name,ObjectClass -A
```

Description

-----------

Gets the revealed accounts for a given RODC showing the name and object class of each account returned.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADDomainController -Filter {IsReadOnly -eq $true} | Get-ADDomainControllerPasswordReplicationPolicyUsage

DistinguishedName : CN=krbtgt_35512,CN=Users,DC=Fabrikam,DC=com
Enabled           : False
Name              : krbtgt_35512
ObjectClass       : user
ObjectGUID        : 8c7268f9-add3-409c-968b-de029e517211
SamAccountName    : krbtgt_35512
SID               : S-1-5-21-41432690-3719764436-1984117282-1106
UserPrincipalName :

DistinguishedName : CN=CSD2722780,OU=Domain Controllers,DC=Fabrikam,DC=com
Enabled           : True
Name              : CSD2722780
ObjectClass       : computer
ObjectGUID        : 63a5e005-e01f-4fc9-ae71-9d9367f808bc
SamAccountName    : CSD2722780$
SID               : S-1-5-21-41432690-3719764436-1984117282-1105
UserPrincipalName :
```

Description

-----------

Gets the list of accounts cached across all RODCs in the domain.

## PARAMETERS

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

### -AuthenticatedAccounts
{{Fill AuthenticatedAccounts Description}}

```yaml
Type: SwitchParameter
Parameter Sets: AuthenticatedAccounts
Aliases: 

Required: True
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

### -RevealedAccounts
{{Fill RevealedAccounts Description}}

```yaml
Type: SwitchParameter
Parameter Sets: RevealedAccounts
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### Microsoft.ActiveDirectory.Management.ADAccount
Returns one or more account objects that represent the users, computers, and service accounts that are authenticated by the specified read-only domain controller (RODC) or that have passwords that are stored on the RODC.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Get-ADDomainController](./Get-ADDomainController.md)

