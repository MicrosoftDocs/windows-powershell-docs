---
external help file: GPv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 0550DC8B-73FE-4758-9B62-6342880F43BD
manager: dansimp
---

# Remove-GPLink

## SYNOPSIS
Removes a GPO link from a site, domain or OU.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-GPLink [-Domain <String>] [-Server <String>] -Guid <Guid> -Target <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-GPLink [-Name] <String> [-Domain <String>] [-Server <String>] -Target <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Remove-GPLink cmdlet deletes the link between a GPO and a specified site, domain, or OU.
This cmdlet does not delete the actual GPO or any other links between the specified GPO and other sites, domains, or OUs.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Remove-GPLink -Name "MyGPO" -Target "ou=MyOU,dc=contoso,dc=com" 

DisplayName      : MyGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 375865b2-3b5f-480f-8f56-2a994ea6e725 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/26/2009 11:28:08 PM 
ModificationTime : 3/5/2009 3:36:34 PM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 1, SysVol Version: 1 
WmiFilter        :
```

Description

-----------

This command removes the link between the "MyGPO" GPO and the "MyOU" organizational unit in the contoso.com domain.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Remove-GPLink -Name "MyGPO" -Target "Default-First-Site-Name"
```

Description

-----------

This command removes the link between the "MyGPO" GPO and the default site.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>(Get-GPInheritance -Target "ou=myou,dc=contoso,dc=com").GpoLinks | Rem ove-GPLink 

DisplayName      : TestGPO-3 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : d02126d4-82e8-4e87-b4a0-2d44b6891411 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/27/2009 2:59:51 PM 
ModificationTime : 3/5/2009 3:36:37 PM 
UserVersion      : AD Version: 13, SysVol Version: 13 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        : 

DisplayName      : TestGPO-2 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 375865b2-3b5f-480f-8f56-2a994ea6e725 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 2/26/2009 11:28:08 PM 
ModificationTime : 3/5/2009 3:36:34 PM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 1, SysVol Version: 1 
WmiFilter        :
```

Description

-----------

This command removes the links for all the GPOs that are linked to the "MyOU" organizational unit in the contoso.com domain.

Get-GPInheritance is used to get a Microsoft.GroupPolicy.Som object for the OU.
The GpoLinks property of the SOM object contains all the GPO links for GPOs that are linked to the OU (links that are inherited from higher-level containers are not included).
This collection is piped into Remove-GPLink.
The GPOs for which links have been removed are returned.

## PARAMETERS

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Remove-GPLink cmdlet:

- The GPO that is linked must exist in this domain.

- The Active Directory container (site, domain, or OU) that is linked must exist in a domain that has a trust relationship with this domain.

Note: To specify a domain to link to, use the Target parameter.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Domain parameter by its built-in alias, "domainname".
For more information, see about_Aliases.

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

### -Guid
Specifies the GPO for which to remove the link by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in aliases, "id" and "gpoid".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the GPO for which to remove the link by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

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

### -Target
Specifies the LDAP distinguished name of the site, domain, or OU from which to remove the link.
For example, for the "MyOU" organizational unit in the contoso.com domain, the LDAP distinguished name is "ou=MyOU,dc=contoso,dc=com".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.GpoLink
An object that represents the link between a GPO and a site, domain, or OU.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
Remove-GPLink returns the GPO for which the link has been removed.

## NOTES

## RELATED LINKS

[New-GPLink](./New-GPLink.md)

[Set-GPLink](./Set-GPLink.md)

