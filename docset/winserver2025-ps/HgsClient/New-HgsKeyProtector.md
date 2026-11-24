---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/new-hgskeyprotector?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-HgsKeyProtector
---

# New-HgsKeyProtector

## SYNOPSIS
Creates a key protector.

## SYNTAX

```
New-HgsKeyProtector [-Owner] <CimInstance> [[-Guardian] <CimInstance[]>] [-AllowExpired] [-AllowUntrustedRoot]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-HgsKeyProtector** cmdlet creates a key protector.
This cmdlet generates a key and wraps it for the specified guardian owner.
You cannot change the owner for this key protector.
You can grant or revoke access to the key for other guardians by using the **Grant-HgsKeyProtectorAccess** and **Revoke-HgsKeyProtectorAccess** cmdlets.

This cmdlet can create a key protector based on the raw byte stream of an existing key protector.

## EXAMPLES

### Example 1: Create a key protector
```
PS C:\> $Owner = Get-HgsGuardian -Name "Guardian11"
PS C:\> $GuardianA = Get-HgsGuardian -Name "GuardianA"
PS C:\> $GuardianB = Get-HgsGuardian -Name "GuardianB"
PS C:\> New-HgsKeyProtector -Owner $Owner -Guardians @($GuardianA, $GuardianB)
```

The first command gets the guardian object named Guardian11 by using the **Get-HgsGuardian** cmdlet, and then stores that object in the **$Owner** variable.

The second and third commands get two guardians named GuardianA and GuardianB.
These commands store the guardians in the **$GuardianA** and **$GuardianB** variables.

The final command creates a key protector.
The command defines Guardian11 as the **Owner**.
The command also grants access to the guardians stored in **$GuardianA** and **$GuardianB**.

## PARAMETERS

### -AllowExpired
Indicates that this cmdlet can create a key protector by using certificates that are expired.

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

### -AllowUntrustedRoot
Indicates that this cmdlet can create a key protector by using self-signed certificates.

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

### -Guardian
Specifies an array of guardians to grant access to the key in addition to the guardian specified by the **Owner** parameter.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Owner
Specifies a guardian for the new key protector.
The cmdlet grants access to this guardian.
This guardian cannot be changed for this key protector.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#MSFT_HgsKeyProtector
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Grant-HgsKeyProtectorAccess](./Grant-HgsKeyProtectorAccess.md)

[Revoke-HgsKeyProtectorAccess](./Revoke-HgsKeyProtectorAccess.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)

