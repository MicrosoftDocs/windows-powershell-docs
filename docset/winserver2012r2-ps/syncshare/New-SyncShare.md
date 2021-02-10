---
external help file: SyncShare.cdxml-help.xml
Module Name: SyncShare
online version: 
schema: 2.0.0
title: New-SyncShare
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 2E1F761F-D922-4C65-BEFF-15034F0F964D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-SyncShare

## SYNOPSIS
Creates a sync share.

## SYNTAX

```
New-SyncShare [-Name] <String> [-Description <String>] [-Type <String>] [-Path] <String>
 [-UserFolderName <String>] [-User] <String[]> [-InheritParentFolderPermission] [-MaxUploadFile <UInt64>]
 [-RequireEncryption <Boolean>] [-RequirePasswordAutoLock <Boolean>] [-FallbackEnterpriseID <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SyncShare** cmdlet creates a sync share.
Sync shares are used by Work Folders to store user files and sync them with user PCs and devices.

## EXAMPLES

### Example 1: Create a new sync share
```
PS C:\> New-SyncShare Share01 K:\Share01 -User ContosoEngGroup 
ConflictResolutionPolicy : KeepBoth
Description              : 
DevicePolicy             : Share01
Enabled                  : True
ExclusiveAccessToUser    : True
Name                     : Share01
Path                     : K:\Share01
StagingFolder            : K:\EcsStagingArea\Share01
StagingQuota             : 1099511627776
StagingQuotaPerUser      : 10737418240
Type                     : User Data
User                     : {ContosoEngGroup}
UserFolderName           : %username%
PSComputerName           :
```

This command creates a new sync share named Share01.
The path for the share is K:\Share01, and the cmdlet grants members of the ContosoEngGroup security group access to the share.
The device policy associated with the share is also named Share01.

### Example 2: Create a new sync share by using full usernames to name user folders
```
PS C:\> New-SyncShare Share01 K:\Share01 -User ContosoEngGroup -UserFolderName [user]@[domain]
```

This command creates a sync share and specifies that user folders should use the user @ domain folder-naming format.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies the description for a sync share configuration.
The description is visible in Server Manager and in Windows PowerShell®, but does not appear to end users.
The description can have a maximum of a 150 characters.

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

### -FallbackEnterpriseID
Specifies the fallback Enterprise ID that the sync share uses if it cannot successfully query Active Directory® Domain Services (nextref_adds).
If the server cannot successfully query nextref_adds, the server uses the fully qualified domain name (FQDN) of the sync server as the fallback Enterprise ID unless you specify a different Enterprise ID by using this parameter.
The Enterprise ID is issued by the Work Folders client to encrypt data on the PC or device.

The Enterprise ID is typically constructed by querying nextref_adds for the primary SMTP address of the user, removing the username and ampersand (user@), and sending the remainder to the client as the Enterprise ID.
For example, EvanNarvaez@Contoso.com yields the contoso.com Enterprise ID.

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

### -InheritParentFolderPermission
Indicates that the sync share inherits the permissions of the parent folder.
If you specify this parameter, user folders inherit permissions from the parent folder of the sync share, and administrators can access the data.
If you do not specify this parameter, by default each user is granted exclusive access to their user folder, and administrators have no access rights.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxUploadFile
Specifies the maximum file size, in bytes, that users can upload to the server.
The minimum value that you can specify is 1 MB.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies a name for the sync share.
The name that you specify has the following requirements: 

- The name must be unique on the sync server
- The name can have a maximum of 75 characters
- You cannot start or end a name with a space
- You cannot end a name with a period
- You cannot used a reserved name, such as COM1, LPT1, or NUL
- You cannot use the following characters: \<\>:\"/\\\\|?*

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the full path of a folder on an NTFS volume to use for the sync share.
This is the folder that acts as the parent to the user folders.
You can specify the path with a drive letter or UNC format, but the path must be local to the server or failover cluster.
You cannot create a sync share inside another sync share, and the path cannot contain any mount points.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequireEncryption
Indicates whether the sync server requests that the contents of Work Folders be encrypted on each PC and device that accesses the sync share.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequirePasswordAutoLock
Indicates whether the device must meet the following policies: 

- Password minimum length of six characters
- Lock screen activates after a maximum of 15 minutes
- User account lockout after a maximum of 10 failed sign-in attempts

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of the sync share.
By default, all shares are of type User Data, and you should not change this value.

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

### -User
Specifies an array of user names or security groups who are allowed to sync data with this sync share.
Add accounts or security groups in Security Accounts Manager (SAM) account format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: AllowedAccount, AllowedUser

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserFolderName
Specifies a folder-naming format for the user folder on the sync share.
To maintain compatibility with existing user folders that use aliases for their names, specify \[user\], which is required, or omit this parameter.
To eliminate conflicts between identical user aliases in different domains, specify \[user\]@\[domain\].
You can also specify a relative path under the sync share root; for example, UserData\\\[user\].

Sync share creates each user folder during the first sync operation, if it doesn't already exist.
If the user folder exists, confirm that the user has Read/Write or Full Control permissions and is the owner of their folder, unless the folder is owned by an Administrators group.

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

## OUTPUTS

### SyncShare
This cmdlet outputs an object that represents the new sync share.

## NOTES

## RELATED LINKS

[Disable-SyncShare](./Disable-SyncShare.md)

[Enable-SyncShare](./Enable-SyncShare.md)

[Get-SyncShare](./Get-SyncShare.md)

[Remove-SyncShare](./Remove-SyncShare.md)

[Set-SyncShare](./Set-SyncShare.md)

