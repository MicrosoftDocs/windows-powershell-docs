---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.HostGuardianService.Diagnostics.Payload.dll-Help.xml
Module Name: HgsDiagnostics
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsdiagnostics/new-hgstracetarget?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HgsTraceTarget
---

# New-HgsTraceTarget

## SYNOPSIS
Creates a HGS Diagnostics target object.

## SYNTAX

### Remote (Default)
```
New-HgsTraceTarget -HostName <String> [-Credential <PSCredential>] [-PSSessionConfigurationName <String>]
 [-Role <BaseHgsRoles[]>] [<CommonParameters>]
```

### NoAccess
```
New-HgsTraceTarget -HostName <String> [-NoAccess] -Role <BaseHgsRoles[]> [<CommonParameters>]
```

### Local
```
New-HgsTraceTarget [-Local] [-Role <BaseHgsRoles[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-HgsTraceTarget** cmdlet creates a Host Guardian Service (HGS) Diagnostics target object.
The **Get-HgsTrace** cmdlet can use this information to determine how to connect to a particular host as well as what aspects of the host to trace and diagnose.

## EXAMPLES

### Example 1: Create a default target object
```
PS C:\> New-HgsTraceTarget -Local
```

This command creates a target object named localhost.
Since this command does not specify a role, the cmdlet will use the credentials of the current session and then infers the role though the list of installed features on the target.

### Example 2: Create a target with different credentials and a specified role
```
PS C:\> New-HgsTraceTarget -HostName "hgs-01.contoso.com" -Credential (Get-Credential) -Role HostGuardianService
```

This command creates a target object with hostname named hgs-01.contoso.com that uses the provided credentials and makes the target a HGS node.

### Example 3: Create a target to which no access is available with a specified role
```
PS C:\> New-HgsTraceTarget -HostName "hyperv-02.contoso.com" -NoAccess -Role GuardedHost
```

This command creates a target object with hostname named hyperv-02.contoso.com that has no credentials but is regarded as a guarded host.
No attempt will be made to connect to a NoAccess target.

### Example 4: Create a target that reuses the current session's credentials and a specified role
```
PS C:\> New-HgsTraceTarget -HostName "hgs-01.contoso.com" -role HostGuardianService
```

This command creates a target object with hostname named hgs-01.contoso.com that reuses the credentials of the current session and makes the target a HGS node.

### Example 5: Create a target that reuses the current session's credentials and infer the role
```
PS C:\> New-HgsTraceTarget -HostName "hyperv-02.contoso.com"
```

This command creates a target object with hostname hyperv-02.contoso.com that reuses the credentials of the current session and then infers the role though the list of installed features on the target.

## PARAMETERS

### -Credential
Specifies a **PSCredential** object under which the management group connection runs.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

```yaml
Type: PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName
Specifies the hostname of the target.
This parameter is used to resolve an IP address when a remote Windows PowerShell® session is opened.

```yaml
Type: String
Parameter Sets: Remote, NoAccess
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Local
Indicates that the created target is the current local host.

```yaml
Type: SwitchParameter
Parameter Sets: Local
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoAccess
Indicates that no access is available to the target.
Therefore, connections will never be opened to this target.

```yaml
Type: SwitchParameter
Parameter Sets: NoAccess
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PSSessionConfigurationName
Specifies the remote Windows PowerShell session configuration to utilize when a remote runspace is opened.
If you omit this parameter, the default runspace is utilized by the **Get-HgsTrace** cmdlet, or the HGS configuration for targets that have the HostGuardianService role.

```yaml
Type: String
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Role
Specifies the role a particular target plays in a guarded fabric.
This can be a HGS node (HostGuardianService) or a Guarded Host (GuardedHost).
If you do not specify a role, it will be inferred by the open connection and the inspection of the installed Windows features.

```yaml
Type: BaseHgsRoles[]
Parameter Sets: Remote, Local
Aliases:
Accepted values: None, HostGuardianService, GuardedHost

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: BaseHgsRoles[]
Parameter Sets: NoAccess
Aliases:
Accepted values: None, HostGuardianService, GuardedHost

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Windows.HostGuardianService.Diagnostics.Payload.InputTarget
This cmdlet returns a target object that is a collection of metadata that contains connection information of a host operating in a guarded fabric as well as its role in the fabric.

## NOTES

## RELATED LINKS

[Test-HgsTraceTarget](./Test-HgsTraceTarget.md)

[Get-HgsTrace](./Get-HgsTrace.md)

