---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbScriptModule.psm1-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/set-smbpathacl?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-SmbPathAcl
---

# Set-SmbPathAcl

## SYNOPSIS
Sets the ACL for the file system folder to match the ACL used by an SMB share.

## SYNTAX

```
Set-SmbPathAcl [-ShareName] <String> [[-ScopeName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmbPathAcl** cmdlet sets the access control list (ACL) for the file system folder to match the ACL for the server message block (SMB) share.
The cmdlet sets the ACL to match the SMB share itself.
This action simplifies the configuration of NTFS or ReFS file system permissions by copying the SMB share permissions.

## EXAMPLES

### Example 1: Set the SMB path ACL by share name
```
PS C:\> Set-SmbPathAcl -ShareName "Share01"
```

This command sets the ACL on the file system folder used by the Share01 share to match the ACL of the share.

### Example 2: Set the SMB path ACL by share name and scope name
```
PS C:\> Set-SmbPathAcl -ShareName "Share01" -ScopeName "SOFS01"
```

This command sets the ACL on the file system folder used by the Share01 share on the SOFS01 scope to match the ACL of the share.

## PARAMETERS

### -ScopeName
Specifies the scope name of the SMB share.
The cmdlet sets the ACL for the scope that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareName
Specifies the name of the SMB share.
The cmdlet sets the ACL on the file system folder to the ACL used by the SMB share that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES
* The previous syntax for the same task, `((Get-SmbShare -Name \<ShareName\> ).PresetPathACL | Set-Acl)`, continues to work with newer versions of the Windows Server operating system, but the new syntax is much simpler and therefore recommended.

## RELATED LINKS

[SMB Share Cmdlets in Windows PowerShell](./smbshare.md)

