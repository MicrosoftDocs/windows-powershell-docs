---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: HgsClient-help.xml
Module Name: HgsClient
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hgsclient/grant-hgskeyprotectoraccess?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Grant-HgsKeyProtectorAccess
---

# Grant-HgsKeyProtectorAccess

## SYNOPSIS
Grants access to a guardian for a key protector.

## SYNTAX

### InputObject

```
Grant-HgsKeyProtectorAccess -KeyProtector <CimInstance> -Guardian <CimInstance>
 [-AllowUntrustedRoot] [-AllowExpired] [<CommonParameters>]
```

### FriendlyName
```
Grant-HgsKeyProtectorAccess -KeyProtector <CimInstance> -GuardianFriendlyName <String>
 [-AllowUntrustedRoot] [-AllowExpired] [<CommonParameters>]
```

## DESCRIPTION

The `Grant-HgsKeyProtectorAccess` cmdlet grants a Host Guardian Service guardian access to a key
protector. This operation requires the private signing key of the owner of the key protector.

## EXAMPLES

### Example 1: Grant access to a guardian

```powershell
$Owner        = Get-HgsGuardian -Name "Guardian06"
$Guardian01   = Get-HgsGuardian -Name "Guardian11"
$KeyProtector = New-HgsKeyProtector -Owner $Owner
Grant-HgsKeyProtectorAccess -KeyProtector $KeyProtector -Guardian $Guardian01
```

The first command gets the guardian object named `Guardian06` by using the `Get-HgsGuardian` cmdlet,
and then stores that object in the `$Owner` variable.

The second commands get the guardian object named `Guardian11`, and then stores it in the `$Guardian01` variable.

The third command creates a key protector.
The command defines `Guardian06`, stored in `$Owner`, as the **Owner**.

The final command grants access to the guardian stored in `$Guardian01` for the key protector.

## PARAMETERS

### -AllowExpired

Indicates that this cmdlet can grant permissions to a guardian that contains certificates that are expired.

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

Indicates that this cmdlet can grant permissions to a guardian that uses self-signed certificates.

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

Specifies a guardian to which to grant access to the key.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GuardianFriendlyName

Specifies a friendly name for the guardian.

```yaml
Type: String
Parameter Sets: FriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyProtector

Specifies the key protector to which to grant access.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### CimInstance#MSFT_HgsKeyProtector

The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[New-HgsKeyProtector](./New-HgsKeyProtector.md)

[Revoke-HgsKeyProtectorAccess](./Revoke-HgsKeyProtectorAccess.md)

[Get-HgsGuardian](./Get-HgsGuardian.md)
