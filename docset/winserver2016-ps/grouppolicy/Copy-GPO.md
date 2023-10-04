---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/copy-gpo?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-GPO
---

# Copy-GPO

## SYNOPSIS
Copies a GPO.

## SYNTAX

### SourcebyGUID (Default)
```
Copy-GPO -SourceGuid <Guid> -TargetName <String> [-SourceDomain <String>] [-TargetDomain <String>]
 [-SourceDomainController <String>] [-TargetDomainController <String>] [-MigrationTable <String>] [-CopyAcl]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SourcebyName
```
Copy-GPO [-SourceName] <String> -TargetName <String> [-SourceDomain <String>] [-TargetDomain <String>]
 [-SourceDomainController <String>] [-TargetDomainController <String>] [-MigrationTable <String>] [-CopyAcl]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-GPO** cmdlet creates a destination Group Policy Object (GPO) and copies the settings from the source GPO to the new GPO.
The cmdlet can be used to copy a GPO from one domain to another domain within the same forest.
You can specify a migration table to map security principals and paths when copying across domains.
You can also specify whether to copy the access control list (ACL) from the source GPO to the destination GPO.

This cmdlet does not copy the source GPO if a GPO with the specified target display name already exists in the destination domain.
In this case, an error occurs and the GPO is not copied.

## EXAMPLES

### Example 1: Copy a GPO
```
PS C:\> Copy-GPO -SourceName "TestGpo1" -TargetName "TestGpo2"
DisplayName      : TestGpo2 

DomainName       : contoso.com 

Owner            : CONTOSO\Domain 

Admins Id        : 37eeb072-cc31-42bb-8c3a-446c2b6ddd3f 

GpoStatus        : AllSettingsEnabled 

Description      : 

CreationTime     : 2/25/2009 9:12:05 PM 

ModificationTime : 2/25/2009 9:12:05 PM 

UserVersion      : AD Version: 1, SysVol Version: 1 

ComputerVersion  : AD Version: 1, SysVol Version: 1 

WmiFilter        :
```

This command copies the TestGpo1 GPO to a GPO named TestGpo2.
The GPOs exist in the domain of the user that is running the session.

### Example 2: Copy a GPO from a domain to another domain
```
PS C:\> Copy-GPO -SourceName "TestGpo1" -SourceDomain "test.contoso.com" TargetName "TestGpo1" -TargetDomain "sales.contoso.com"
```

This command copies the TestGpo1 GPO from the test.contoso.com domain to a GPO named TestGpo1 in the sales.contoso.com domain.

A trust relationship must exist between the source domain and the destination domain.
In addition, if the source domain or the destination domain (or both) is different than the domain of the user that is running the session a trust must exist between that domain and the domain of the user.

### Example 3: Copy all GPOs from a domain to another domain
```
PS C:\> Get-GPO -All -Domain "sales1.contoso.com" | ForEach-Object {$_ | Copy-GPO -TargetName ($_.DisplayName) -TargetDomain "sales2.contoso.com" -CopyAcl -MigrationTable "c:\tables\MigrationTable.migtable"}
```

This command copies all the GPOs in the sales1.contoso.com domain to the sales2.contoso.com domain.

All the GPOs in the source domain are retrieved by using the **Get-GPO** cmdlet using the *All* parameter.
The output of **Get-GPO** is piped into the ForEach-Object command.
When each GPO is evaluated, it is piped into **Copy-GPO** and its display name is specified for the *TargetName* parameter "-TargetName ($_.DisplayName)".
The *CopyACL* parameter is specified to copy the ACLs for each GPO to the destination domain.
The *MigrationTable* parameter specifies a migration table to use to migrate Security principals and UNC paths to the destination domain.
Both the *CopyACL* and the *MigrationTable* parameters are optional.

If a GPO with the same display name as a source GPO already exists in the destination domain, an error occurs when this command attempts to copy the source GPO.
Because this command copies all GPOs in the source domain, errors occur for default GPOs; for instance, the Default Domain Policy GPO and the Default Domain Controllers Policy GPO.
These GPOs are not copied.
You can suppress these error messages by supplying the *ErrorAction* parameter with a value of SilentlyContinue to **Copy-GPO**.
For more information about the *ErrorAction* parameter, see about_CommonParameters.

The destination GPOs that were successfully copied are returned by this command.
By default, they are printed to the display, but you can add commands to the end of the pipeline to further configure these GPOs.
For example you can add a Set-GPLink cmdlet to the end of the pipeline to link all the destination GPOs to a site, domain, or organizational unit.

A trust relationship must exist between the source domain and the destination domain.
In addition, if the source domain or the destination domain (or both) is different than the domain of the user that is running the session a trust must exist between that domain and the domain of the user or the computer.

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

### -CopyAcl
Indicates that the cmdlet copies the ACL of the source GPO to the destination GPO.

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

### -MigrationTable
Specifies the location of the migration table to use for the command.
You must specify the full path to the file; for instance, \\\\Server1\MigrationTables\TestToSalesTable.migtable.
If you supply a migration table, security principals and Universal Naming Convention (UNC) paths are mapped to the destination GPO when you copy a GPO across domains.
If you do not supply a migration table, security principals and UNC paths are not modified in the destination GPO.

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

### -SourceDomain
Specifies the domain of the source GPO.
You must specify the fully qualified domain name (FQDN) of the domain.

If you do not specify the *SourceDomain* parameter, the domain of the user that is running the current session is used.
If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.
For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user or the computer.

You can also refer to the *SourceDomain* parameter by its built-in alias, domainname.
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DomainName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDomainController
Specifies the name of the domain controller that this cmdlet contacts for the source domain.
You can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the *SourceDomainController* parameter, the primary domain controller (PDC) emulator is contacted.

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

### -SourceGuid
Specifies the source GPO by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the *SourceGuid* parameter by its built-in alias, id.

```yaml
Type: Guid
Parameter Sets: SourcebyGUID
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceName
Specifies the source GPO by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain an error occurs.
You can use the *SourceGuid* parameter to uniquely identify a GPO.

You can also refer to the *SourceName* parameter by its built-in alias, displayname.

```yaml
Type: String
Parameter Sets: SourcebyName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetDomain
Specifies the domain to which you want to copy the GPO.
You must specify the fully qualified domain name (FQDN) of the domain.

If you do not specify the *TargetDomain* parameter, the domain of the user that is running the current session is used.
If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.
For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current session, a trust must exist between that domain and the domain of the user or the computer.

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

### -TargetDomainController
Specifies the name of the domain controller that this cmdlet contacts for the destination domain.
You can specify either the FQDN or the host name.

If you do not specify the name by using the *TargetDomainController* parameter, the primary domain controller primary domain controller (PDC) emulator is contacted.

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
Specifies the display name for the destination GPO.
If another GPO with the same display name exists in the target domain, an error occurs.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo
The cmdlet takes a GPO as input.
GPO objects that are piped into the cmdlet are used as the source GPO.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
This cmdlet outputs a copy of the specified GPO.

## NOTES
* You can use the **Copy-GPO** cmdlet to copy a GPO within a domain or from one domain to another within the same forest.

  You can use the *SourceDomain* and *TargetDomain* parameters to explicitly specify the source domain or the target domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPO](./Get-GPO.md)

[Import-GPO](./Import-GPO.md)

[New-GPO](./New-GPO.md)

[Restore-GPO](./Restore-GPO.md)

[Set-GPLink](./Set-GPLink.md)

