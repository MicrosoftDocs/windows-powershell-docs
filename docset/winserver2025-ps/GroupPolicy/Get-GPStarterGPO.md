---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gpstartergpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPStarterGPO
---

# Get-GPStarterGPO

## SYNOPSIS

Gets one Starter GPO or all Starter GPOs in a domain.

## SYNTAX

### ByGUID (Default)

```
Get-GPStarterGPO -Guid <Guid> [-Domain <String>] [-Server <String>] [-All] [<CommonParameters>]
```

### ByName

```
Get-GPStarterGPO [-Name] <String> [-Domain <String>] [-Server <String>] [-All] [<CommonParameters>]
```

### GetAll

```
Get-GPStarterGPO [-Domain <String>] [-Server <String>] [-All] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPStarterGPO` cmdlet gets one Starter Group Policy Object (GPO) or all Starter GPOs in a
domain. You can specify the Starter GPO to get either by display name or by GUID, or you can specify
the **All** parameter to get all the Starter GPOs in the domain.

You can use this cmdlet to get information about a StarterGPO, or you can create a new GPO from a
specified Starter GPO by piping the output of this cmdlet into the `New-GPO` cmdlet.

## EXAMPLES

### Example 1: Get a Starter GPO by name

```powershell
Get-GPStarterGPO -Name "Windows Vista EC User"
```

```Output
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


Description : This Starter GPO contains the user Group Policy settings recommended for the
              Enterprise Client (EC) environment described in the Windows Vista security guide.

              For more information about each of these settings, see the
              [Windows Vista Security Guide](http://go.microsoft.com/fwlink/?LinkID=121852).
```

This command gets the Starter GPO named `Windows Vista EC User`.

### Example 2: Get a Starter GPO by name using the pipeline operator

```powershell
Get-GPStarterGPO -Name "Windows Vista EC User" |
    New-GPO -Name "TestGPO" -Comment "Create a GPO by using a Starter GPO"
```

```Output
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

This command creates a GPO named `TestGPO` from the GPO named `Windows Vista EC User` Starter. The
command uses the `Get-SPStarterGPO` cmdlet to get the Starter GPO and is then piped into the
`New-GPO` cmdlet to create the GPO.

## PARAMETERS

### -All

Returns all the Starter GPOs in the domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Get-GPStarterGPO` cmdlet, the Starter GPO must exist in this domain.

If you do not specify the **Domain** parameter, the domain of the user that is running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user, or the computer.

You can also refer to the **Domain** parameter by its built-in alias, **DomainName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid

Specifies the Starter GPO that this cmdlet gets by its globally unique identifier (GUID). The GUID
uniquely identifies the Starter GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: ByGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the display name of the Starter GPO that this cmdlet.

The display name is not guaranteed to be unique in the domain. If another Starter GPO with the same
display name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely
identify a Starter GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.StarterGpo

You can pipe a Starter GPO to this cmdlet.

## OUTPUTS

### Microsoft.GroupPolicy.StarterGpo object

This cmdlet returns a Starter GPO object.

## NOTES

* You can use the **Domain** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session, for instance, the domain of the user who started the session by opening Windows
  PowerShell or the domain of a user that is specified in a runas command. However, computer startup
  and shutdown scripts run under the context of the LocalSystem account. The LocalSystem account is
  a built-in local account, and it accesses network resources under the context of the computer
  account. Therefore, when this cmdlet is run from a startup or shutdown script, the default domain
  is the domain to which the computer is joined.

## RELATED LINKS

[New-GPO](./New-GPO.md)

[New-GPStarterGPO](./New-GPStarterGPO.md)

