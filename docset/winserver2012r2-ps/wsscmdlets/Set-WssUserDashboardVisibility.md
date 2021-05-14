---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/set-wssuserdashboardvisibility?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WssUserDashboardVisibility
---

# Set-WssUserDashboardVisibility

## SYNOPSIS
Modifies whether to make a user account visible in the dashboard.

## SYNTAX

### UserVisible
```
Set-WssUserDashboardVisibility [-Name] <String> [-Visible] [<CommonParameters>]
```

### UserHidden
```
Set-WssUserDashboardVisibility [-Name] <String> [-Hidden] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WssUserDashboardVisibility** cmdlet modifies whether to make a user account visible in the Windows Server Essentials dashboard.

## EXAMPLES

### Example 1: Show a user in the dashboard
```
PS C:\> Set-WssUserDashboardVisibility -Name "PattiFuller" -Visible
```

This command shows the specified user account in the dashboard by specifying the **Visible** parameter.

### Example 2: Hide a user in the dashboard
```
PS C:\> Set-WssUserDashboardVisibility -Name "PattiFuller" -Hidden
```

This command hides the specified user account in the dashboard by specifying the **Hidden** parameter.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Hidden
Indicates that the cmdlet hides the user account in the dashboard.

```yaml
Type: SwitchParameter
Parameter Sets: UserHidden
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name.
The cmdlet modifies the visibility for the user account that has the name that you specify.

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

### -Visible
Indicates that the cmdlet shows the user account in the dashboard.

```yaml
Type: SwitchParameter
Parameter Sets: UserVisible
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssUser](./Get-WssUser.md)

