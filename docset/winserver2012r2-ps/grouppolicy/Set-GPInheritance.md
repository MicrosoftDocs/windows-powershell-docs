---
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gpinheritance?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GPInheritance
---

# Set-GPInheritance

## SYNOPSIS
Blocks or unblocks inheritance for a specified domain or organizational unit (OU).

## SYNTAX

```
Set-GPInheritance [-Target] <String> -IsBlocked <BlockInheritance> [-Domain <String>] [-Server <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-GPInheritance cmdlet blocks or unblocks inheritance for a specified domain or organizational unit (OU).

GPOs are applied according to the Group Policy hierarchy in the following order: local GPO, GPOs linked to the site, GPOs linked to the domain, GPOs linked to OUs.
By default, an Active Directory container inherits settings from GPOs that are applied at the next higher level in the hierarchy.
Blocking inheritance prevents the settings in GPOs that are linked to higher-level sites, domains, or organizational units from being automatically inherited by the specified domain or OU, unless the link (at the higher-level container) for a GPO is enforced.

You use the Target parameter to specify the LDAP distinguished name of the domain or OU, and use the IsBlocked parameter to specify whether to block or unblock inheritance.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\> Set-GPInheritance -Target "ou=MyOU,dc=contoso,dc=com" -IsBlocked Yes 

Name                  : myou 
ContainerType         : OU 
Path                  : ou=myou,dc=contoso,dc=com 
GpoInheritanceBlocked : Yes 
GpoLinks              : {TestGPO-1, TestGPO-2} 
InheritedGpoLinks     : {TestGPO-1, TestGPO-2}
```

Description

-----------

This command blocks inheritance for the "MyOU" OU in the contoso.com domain.
GPOs that are linked to higher-level sites or domains, or to OUs that are parent OUs of the "MyOU" OU are not applied (unless their links are enforced) when Group Policy is processed for the OU on the client.

Because inheritance is blocked, only GPOs that are linked directly to the "MyOU" OU (and those that are enforced at higher-level containers) appear in the InheritedGpoLinks list.

### -------------------------- EXAMPLE 2 --------------------------
```
PS C:\> Set-GPInheritance -Target "dc=northwest, dc=contoso, dc=com" -IsBlocked No
```

Description

-----------

This command unblocks inheritance for the northwest.contoso.com domain.
GPOs linked to higher-level sites or domains are applied to this domain when Group Policy is processed on the client.

### -------------------------- EXAMPLE 3 --------------------------
```
PS C:\> Set-GPInheritance -Target "ou=MyOU,dc=contoso,dc=com" -IsBlocked No 

Name                  : myou 
ContainerType         : OU 
Path                  : ou=myou,dc=contoso,dc=com 
GpoInheritanceBlocked : No 
GpoLinks              : {TestGPO-1, TestGPO-2} 
InheritedGpoLinks     : {TestGPO-1, TestGPO-2, Default Domain Policy}
```

Description

-----------

This command blocks inheritance for the "MyOU" OU in the contoso.com domain.
GPOs that are linked to higher-level sites or domains, or to OUs that are parent OUs of the "MyOU" OU, are applied when Group Policy is processed for the OU on the client.

Because inheritance is not blocked, GPOs that are inherited from higher-level containers appear in the InheritedGpoLinks list (together with GPOs that are linked directly to the OU).
For example, the "Default Domain Policy" GPO is linked at the domain level.

## PARAMETERS

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

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Set-GPInheritance cmdlet, this is typically the domain of the Active Directory container (domain or OU) for which you want to block or unblock inheritance.
If the domain for the cmdlet is different than the domain of the container, a trust must exist between the two domains.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Domain parameter by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsBlocked
Specifies whether to block inheritance for the domain or OU.
You must specify Yes or No.

The following values are permitted for this object type.

```yaml
Type: BlockInheritance
Parameter Sets: (All)
Aliases: 
Accepted values: No, Yes

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Specifies the domain or the OU for which to block or unblock inheritance by its LDAP distinguished name.
For example, the "MyOU" organizational unit in the contoso.com domain is specified as "ou=MyOU,dc=contoso,dc=com".

You can also refer to the Target parameter by its built-in alias, "path".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: path

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### Microsoft.GroupPolicy.Som
This cmdlet takes an object that represents a domain or an OU as input.

## OUTPUTS

### Microsoft.GroupPolicy.Som
Set-GPInheritance returns an object that represents the domain or OU after the operation is applied.
The properties of this object that are displayed by default describe the Group Policy inheritance information for the domain or OU.
The GpoInheritanceBlocked property indicates whether inheritance is blocked.

## NOTES
* GPO links that are enforced cannot be blocked. This cmdlet should be used sparingly. Casual use of this cmdlet can complicate troubleshooting.

  You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPInheritance](./Get-GPInheritance.md)

