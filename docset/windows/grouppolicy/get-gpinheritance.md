---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-GPInheritance
ms.reviewer:
ms.assetid: 2B4BA841-DD58-4384-A6E4-70909BDD77A1
---

# Get-GPInheritance

## SYNOPSIS
Gets Group Policy inheritance information for a specified domain or OU.

## SYNTAX

```
Get-GPInheritance [-Target] <String> [-Domain <String>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-GPInheritance** cmdlet gets information about Group Policy inheritance for a specified domain or organizational unit (OU).

This information includes the following:

- A list of GPOs that are linked directly to the location (the GpoLinks property).
- A list of GPOs that are applied to the location when Group Policy is processed on a client (the **InheritedGpoLinks** property).
- Whether inheritance is blocked for the location (the **GpoInheritanceBlocked** property).

The **InheritedGpoLinks** property contains a list of the GPOs are applied to the OU or domain when Group Policy is processed on a client.
The GPOs are listed according to the order of precedence with which they are applied.
This list includes (in the following order):

- Inherited GPOs that are linked, enabled, and enforced at higher levels of the Group Policy hierarchy (for example, a site).
- GPOs that are linked and enabled directly at the specified location.
- If inheritance is not blocked for the specified location, inherited GPOs that are linked and enabled -- but not enforced -- at higher levels of the Group Policy hierarchy.

## EXAMPLES

### Example 1: Get Group Policy inheritance information for a specific OU
```
PS C:\> Get-GPInheritance -Target "ou=MyOU,dc=contoso,dc=com" 
ContainerName         : myou 

ContainerType         : OU 

Path                  : ou=myou,dc=contoso,dc=com 

GpoInheritanceBlocked : No 

GpoLinks              : {TestGPO-0, TestGPO-1, TestGPO-2, TestGPO-3...} 

InheritedGpoLinks     : {TestGPO-2, TestGPO-3, Default Domain Policy}
```

This command gets Group Policy inheritance information for the OU named MyOU in the contoso.com domain.

The **GpoLinks** property contains a list of all the GPOs that are linked directly to the GPO, whether their links are enabled or not.

The **InheritedGpoLinks** property contains a list of all the GPOs that are applied when Group Policy is processed on the client.
TestGPO-2 and TestGPO-3 appear in this list because their links are enabled.

The Default Domain Policy GPO is inherited from the contoso.com domain.
If inheritance is blocked, it does not appear in the **InheritedGpoLinks** property unless its link is enforced at the domain.
If its link is enforced, it appears first in the list.

### Example 2: Get Group Policy inheritance for a specific domain
```
PS C:\> Get-GPInheritance -Target "dc=contoso,dc=com" -Domain "contoso.com" -Server "DomainController1"
Name                  : contoso.com 

ContainerType         : Domain 

Path                  : dc=contoso,dc=com 

GpoInheritanceBlocked : No 

GpoLinks              : {Default Domain Policy} 

InheritedGpoLinks     : {Default Domain Policy}
```

This command gets Group Policy inheritance information for the contoso.com domain.
The domain controller with the host name DomainController1 is contacted to complete the operation.

The domain does not have to be explicitly specified using the *Domain* parameter in this example.
If the domain of the user that is running the session (or, for startup and shutdown scripts, the computer) is the same as the target domain, or a trust exists between it and the target domain, you do not have to specify the *Domain* parameter.

### Example 3: Get GPOs that are linked to a specific organizational unit by evaluating the SOM object
```
PS C:\> (Get-GPInheritance -Target "ou=myou,dc=contoso,dc=com").GpoLinks | foreach-object { Get-GPO -Name ($_.DisplayName)} 

DisplayName      : TestGPO-3 

DomainName       : contoso.com 

Owner            : CONTOSO\Domain Admins 

Id               : d02126d4-82e8-4e87-b4a0-2d44b6891411 

GpoStatus        : AllSettingsEnabled 

Description      : 

CreationTime     : 2/27/2009 2:59:51 PM 

ModificationTime : 2/27/2009 4:00:44 PM 

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

ModificationTime : 3/1/2009 11:07:30 AM 

UserVersion      : AD Version: 0, SysVol Version: 0 

ComputerVersion  : AD Version: 1, SysVol Version: 1 

WmiFilter        :
```

This command evaluates the SOM object (Microsoft.GroupPolicy.SOM) returned by **Get-GPInheritance** and returns the GPOs that are linked to the MyOU organizational unit.
You can use this command to set properties of the GPOs by piping its output into other cmdlets.
For instance, you can pipe the output to the **Set-GPPermissions** cmdlet to delegate permissions to administrators of the OU for each of the GPOs linked to the OU.

The **GpoLinks** property of the SOM object contains a list of all the GPO links for the OU.
Each object in this list is of type **Microsoft.GroupPolicy.GpoLink**.
The following shows one such object:

GpoId : d02126d4-82e8-4e87-b4a0-2d44b6891411

DisplayName : TestGPO-3

Enabled : True

Enforced : False

Target : ou=myou,dc=contoso,dc=com

Order : 1

The collection is piped into a foreach-object command, which retrieves each GPO by using the DisplayName property of the GpoLink object.

## PARAMETERS

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain.

For the **Get-GPInheritance** cmdlet, this is typically the domain of the container (domain or OU) for which you want to retrieve inheritance information.
If the specified domain is different than the domain of the container, a trust must exist between the two domains.

If you do not specify the *Domain* parameter, the domain of the user that is running the current session is used.
If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.
For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user or the computer.

You can also refer to the *Domain* parameter by its built-in alias, domainname.
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

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the *Server* parameter, the primary domain controller (PDC) emulator is contacted.

You can also refer to the *Server* parameter by its built-in alias, dc.

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
Specifies the domain or the OU for which to retrieve the Group Policy inheritance information by its Lightweight Directory Access Protocol (LDAP) distinguished name.
For instance, the MyOU organizational unit in the contoso.com domain is specified as ou=MyOU,dc=contoso,dc=com.

You can also refer to the *Target* parameter by its built-in alias, path.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Som
An object that represents a domain or an OU.

## OUTPUTS

### Microsoft.GroupPolicy.Som
This cmdlet returns an object that represents the domain or OU.
The **GpoInheritanceBlocked** property indicates whether inheritance is blocked.
You can modify inheritance for the domain or OU by using the **Set-GPInheritance** cmdlet.

## NOTES
* You can use the *Domain* parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Set-GPInheritance](./Set-GPInheritance.md)

