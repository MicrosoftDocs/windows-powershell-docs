---
author: Kateyanne
external help file: GPv2_Cmdlets.xml
manager: dansimp
Module Name: GroupPolicy
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/grouppolicy/get-gpstartergpo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-GPStarterGPO

## SYNOPSIS
Gets one Starter GPO or all Starter GPOs in a domain.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-GPStarterGPO [-All] [-Domain <String>] [-Server <String>] -Guid <Guid>
```

### UNNAMED_PARAMETER_SET_2
```
Get-GPStarterGPO [-All] [-Domain <String>] [-Server <String>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-GPStarterGPO [-Name] <String> [-All] [-Domain <String>] [-Server <String>]
```

## DESCRIPTION
The Get-GPStarterGPO cmdlet gets one Starter GPO or all Starter GPOs in a domain.
You can specify the Starter GPO to retrieve either by display name or by GUID, or you can specify the All parameter to get all the Starter GPOs in the domain.

You can use this cmdlet to get information about a StarterGPO, or you can create a new GPO from a specified Starter GPO by piping the output of this cmdlet into the New-GPO cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-GPStarterGPO -Name "Windows Vista EC User" 

DisplayName       : Windows Vista EC User 
Id                : 8780588e-ef91-442b-bd5f-2d50de7abf76 
Owner             : BUILTIN\Administrators 
Created           : 9/10/2008 12:18:46 PM 
Modified          : 4/26/2008 3:25:52 PM 
UserVersion       : 
ComputerVersion   : 
StarterGpoVersion : 0 
StarterGpoType    : System 
Author            : Microsoft 
Description       : This Starter GPO contains the user Group Policy settings recommended for the Enterprise Client (EC) environment described in the Windows Vista security guide. 

For more information about each of these settings, see the Windows Vista Security Guide (http://go. microsoft.com/fwlink/?LinkID=121852).
```

Description

-----------

This command gets the "Windows Vista EC User" Starter GPO.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-GPStarterGPO -Name "Windows Vista EC User" | New-GPO -Name TestGPO-Comment "Create a GPO by using a Starter GPO" 

DisplayName       : TestGPO 
DomainName        : contoso.com 
Owner             : CONTOSO\Domain Admins 
GpoId             : f2828b5c-363a-41f6-afb1-5fa111df715f 
GpoStatus         : AllSettingsEnabled 
Description       : Create a GPO by using a Starter GPO 
CreatedTime       : 2/5/2009 6:46:04 PM 
LastModified      : 2/5/2009 6:46:04 PM 
UserVersion       : AD Version: 1, SysVol Version: 1 
ComputerVersion   : AD Version: 1, SysVol Version: 1 
WmiFilter         :
```

Description

-----------

This command creates a GPO named TestGPO from the "Windows Vista EC User" Starter GPO.
The Starter GPO is retrieved by the Get-GPStarterGPO command and is then piped into the New-GPO command to create the new GPO.

## PARAMETERS

### -All
Returns all the Starter GPOs in the domain.

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

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Get-GPStarterGPO cmdlet, the Starter GPO must exist in this domain.

If you do not specify the Domain parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to Domain by its built-in alias, "domainname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: domainname

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid
Specifies the Starter GPO to retrieve by its globally unique identifier (GUID).
The GUID uniquely identifies the Starter GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the Starter GPO to retrieve by its display name.

The display name is not guaranteed to be unique in the domain.
If another Starter GPO with the same display name exists in the domain an error occurs.
You can use the Guid parameter to uniquely identify a Starter GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: displayname

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

FQDN: DomainController1.SalesDomain.Contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.StarterGpo
A Starter GPO.

## OUTPUTS

### Microsoft.GroupPolicy.StarterGpo object
Get-GPStarterGPO returns a Starter GPO object.

## NOTES
* You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session, for example, the domain of the user who started the session by opening Windows PowerShell® or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[New-GPO](./New-GPO.md)

[New-GPStarterGPO](./New-GPStarterGPO.md)

