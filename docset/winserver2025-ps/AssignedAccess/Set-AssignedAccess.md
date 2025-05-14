---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/assignedaccess/set-assignedaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AssignedAccess
---

# Set-AssignedAccess

## SYNOPSIS
Configures a user to launch only one app.

## SYNTAX

### UserNameANDAppName (Default)
```
Set-AssignedAccess -UserName <String> -AppName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserNameANDAppId
```
Set-AssignedAccess -UserName <String> -AppUserModelId <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserSidANDAppId
```
Set-AssignedAccess -UserSID <String> -AppUserModelId <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UserSidANDAppName
```
Set-AssignedAccess -UserSID <String> -AppName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AssignedAccess** cmdlet configures the specified user account so that it can use only one Windows Store app.
The user cannot exit the app, sign out, or access any system settings.

If a user is signed-in or the computer has a PS/2 keyboard, you must restart the computer to apply the changes.

To sign out of assigned access, quickly press the left Windows logo key five times.

Assigned Access cmdlets are supported on Windows 10 and Windows 11 client operating systems only.

## EXAMPLES

### Example 1: Set assigned access by SID and app name
```
PS C:\> Set-AssignedAccess -UserSID "S-1-5-21-523423449-2432423479-234123443-1004" -AppName "CustomApp"
```

This command configures assigned access by using the user SID and the app name.

### Example 2: Set assigned access by user name and AppUserModelID
```
PS C:\> Set-AssignedAccess -UserName "UserName" -AppUserModelId "microsoft.windowsphotos_8wekyb3d8bbwe!app"
```

This command configures assigned access by using the user name and AppUserModelID.

## PARAMETERS

### -AppName
Specifies the name of the installed Windows Store app to use for assigned access.
Wildcard characters are accepted.

```yaml
Type: String
Parameter Sets: UserNameANDAppName, UserSidANDAppName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AppUserModelId
Specifies the Application User Model ID (AppUserModelID) for the installed Windows Store app to use for assigned access.
The AppUserModelID is found in the app's AUMIDs.txt file.

```yaml
Type: String
Parameter Sets: UserNameANDAppId, UserSidANDAppId
Aliases: AUMID

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
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the local user account name to use for assigned access.
This cannot be a domain account or an administrator account.

```yaml
Type: String
Parameter Sets: UserNameANDAppName, UserNameANDAppId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserSID
Specifies the security identifier (SID) for the local user account to use for assigned access.
This account cannot be a domain account or an administrator account.

```yaml
Type: String
Parameter Sets: UserSidANDAppId, UserSidANDAppName
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Object

## NOTES
* To get all the Windows Store apps installed for a user account, use the Get-AppxPackage cmdlet as follows:

`Get-AppxPackage -User "username"`

## RELATED LINKS

[Clear-AssignedAccess](./Clear-AssignedAccess.md)

[Get-AssignedAccess](./Get-AssignedAccess.md)

