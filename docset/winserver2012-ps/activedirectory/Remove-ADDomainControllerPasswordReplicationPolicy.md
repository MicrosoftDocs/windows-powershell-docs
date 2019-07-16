---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: DAE1C8E0-DCB8-4E66-856E-4647DA065B22
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Remove-ADDomainControllerPasswordReplicationPolicy

## SYNOPSIS
Removes users, computers and groups from the allowed or denied list of a read-only domain controller password replication policy.

## SYNTAX

### AllowedPRP
```
Remove-ADDomainControllerPasswordReplicationPolicy [-WhatIf] [-Confirm] -AllowedList <ADPrincipal[]>
 [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADDomainController> [-PassThru]
 [-Server <String>] [<CommonParameters>]
```

### DeniedPRP
```
Remove-ADDomainControllerPasswordReplicationPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] -DeniedList <ADPrincipal[]> [-Identity] <ADDomainController> [-PassThru]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Remove-ADDomainControllerPasswordReplicationPolicy cmdlet removes one or more users, computers and groups from the allowed or denied list of a read-only domain controller (RODC) password replication policy.

The Identity parameter specifies the RODC that uses the allowed and denied lists to apply the password replication policy.
You can identify a domain controller by its GUID, IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the name of the server object that represents the domain controller, the Distinguished Name (DN) of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the DN of the computer object that represents the domain controller.
You can also set the Identity parameter to a domain controller object variable, such as $\<localDomainControllerObject\>, or pass a domain controller object through the pipeline to the Identity parameter.
For example, you can use the Get-ADDomainController cmdlet to retrieve a domain controller object and then pass the object through the pipeline to the Remove-ADDomainControllerPasswordReplicationPolicy cmdlet.
You must provide a read-only domain controller.

The AllowedList parameters specify the users, computers and groups to remove from the allowed list.
Similarly, the DeniedList parameter specifies the users, computers and groups to remove from the denied list.
You must specify either one or both of the AllowedList and DeniedList parameters.
You can identify a user, computer or group by distinguished name (DN), GUID, security identifier (SID) or security accounts manager (SAM) account name.
You can also specify user, computer or group variables, such as $\<localUserObject\>.
If you are specifying more than one item, use a comma-separated list.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-ADDomainControllerPasswordReplicationPolicy -Identity "FABRIKAM-RODC1" -AllowedList "JesperAaberg", "AdrianaAdams"
```

Description

-----------

Remove the users with samAccountNames 'JesperAaberg' and 'AdrianaAdams' from the Allowed list on the RODC 'FABRIKAM-RODC1'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-ADDomainControllerPasswordReplicationPolicy -Identity "FABRIKAM-RODC1" -DeniedList "MichaelAllen", "ElizabethAndersen"
```

Description

-----------

Remove the users with samAccountNames 'MichaelAllen' and 'ElizabethAndersen' from the Denied list on the RODC 'FABRIKAM-RODC1'.

## PARAMETERS

### -AllowedList
{{Fill AllowedList Description}}

```yaml
Type: ADPrincipal[]
Parameter Sets: AllowedPRP
Aliases: 

Required: True
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -DeniedList
{{Fill DeniedList Description}}

```yaml
Type: ADPrincipal[]
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
{{Fill PassThru Description}}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomainController
A read-only domain controller (RODC) object is received by the Identity parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADDomainController
Returns the modified read-only domain controller object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  By default, this cmdlet has the -Confirm parameter set, which prompts you to confirm before a removal of the specified object type can occur.
To bypass prompting for confirmation before removal, you can specify -Confirm:$false when using this cmdlet.

## RELATED LINKS

[Add-ADDomainControllerPasswordReplicationPolicy](./Add-ADDomainControllerPasswordReplicationPolicy.md)

[Get-ADDomainController](./Get-ADDomainController.md)

[Get-ADDomainControllerPasswordReplicationPolicy](./Get-ADDomainControllerPasswordReplicationPolicy.md)

