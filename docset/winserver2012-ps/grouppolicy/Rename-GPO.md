---
author: Kateyanne
external help file: GPv2_Cmdlets.xml
manager: dansimp
Module Name: GroupPolicy
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/grouppolicy/rename-gpo?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-GPO

## SYNOPSIS
Assigns a new display name to a GPO.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-GPO [-Domain <String>] [-Server <String>] -Guid <Guid> -TargetName <String> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-GPO [-Name] <String> [-Domain <String>] [-Server <String>] -TargetName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Rename-GPO cmdlet assigns a different, non-null display name to a GPO.
This cmdlet has no effect on the GUID of the GPO.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>rename-gpo -name sampleGPO -targetname securityGPO 

DisplayName      : securityGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 2c08f9b5-32c3-43fa-af8f-f1939b1ac8a0 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/6/2009 4:20:25 PM 
ModificationTime : 3/6/2009 4:20:24 PM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        :
```

Description

-----------

This command renames the GPO named sampleGPO to securityGPO.

## PARAMETERS

### -Domain
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com).

For the Rename-GPO cmdlet, this is the domain of the GPO that you want to rename.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies the GPO to rename by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
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
Specifies the GPO to rename by its current display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain, an error occurs.
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

### -TargetName
Specifies the new display name of the GPO.
Because the display name may not be unique, an error is returned if another GPO in the domain has the same display name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### Microsoft.GroupPolicy.Gpo
The GPO to rename.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
Rename-GPO returns the GPO (with the new display name).

## NOTES
* You can use the Domain parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Copy-GPO](./Copy-GPO.md)

[Get-GPO](./Get-GPO.md)

[New-GPO](./New-GPO.md)

