---
external help file: Microsoft.HCS.Management.dll-Help.xml
Module Name: HCS
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/hcs/enable-hcssupportaccess?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-HcsSupportAccess
---

# Enable-HcsSupportAccess

## SYNOPSIS
Enables access to this device for Customer Service and Support.

## SYNTAX

```
Enable-HcsSupportAccess [-Scope <ClusterScope>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-HcsSupportAccess** cmdlet enables access to this device for Microsoft Customer Service and Support.

This cmdlet temporarily opens the appliance for support, and it creates an encrypted password.
Customer Service and Support can decrypt the password to gain access to the device.
You can retrieve that encrypted password by using the Get-HcsSupportAccess cmdlet.

Provide the encrypted password to Customer Service and Support through email or other means.

Share your desktop with Customer Service and Support.
From there, you and support personnel access the appliance over the StorSimple Serial Console or remote Windows PowerShell® management.

Log on to the appliance by using serial console or remote Windows PowerShell management.
Enter the support configuration session.
This session allows only the following cmdlets to run: Enable-HcsSupportAccess, Disable-HcsSupportAccess, Get-HcsSupportAccess, and **Enter-HcsSupportSession**.
After you establish the session by using your SSAdminConsole password, the **Enter-HcsSupportSession** cmdlet provides unrestricted access to the appliance.
Customer Service and Support enters the decrypted password.
All password input is hidden or obscured.
After the password is validated, you receive access to the unrestricted session.
This is an interactive session.

Customer Service and Support accesses the system to perform troubleshooting.
You maintain full control over the session.
You can stop sharing your desktop with Customer Service and Support at any time.

Finally, you turn off support access by using the **Disable-HcsSupportAccess** cmdlet.
Disabling the support session invalidates the support password.

## EXAMPLES

### Example 1: Enable support access
```
PS C:\> Enable-HcsSupportAccess
UAAACBAMAQEAADYAMgAyADYAMgBBAEEANgA3ADcARgA1ADUANgA2ADYAQQAxAEMARQA1ADUAQQAyADcANgAwADkARQAyADgANgBDADAAMgBBAEYANIGbnvh
Z1Ja4lHQfnyI9+quGgser6YmxNPP+GeHJQ3oVThNgf5fhjsuoc0fss6ygaxZKPZLXyLFpw93YMeTp90+sbuEr1yh26cmjZHUwW70aZLNtJ6svqYIvdasW0v
Tc8TWbcMsTvOLJdvnmdX7rfMTnfwWJjcsgBGFz+O60uC5Sh633q4nRx3R0jtUMpJ5tcW5wVmHKfFX4OpaPLS9jJ+IrrlBP+EajW655qktkKdqk0EbcNCXck
gqun+nhDhqCeHMBNKJzCp8y+AgbpTPzswvbJuqDUGiaEubnchnpKkdBY0Hp+y27Lo8Zke9LuYu+RzzGsEmW1DEpyZvgQA/ynw==
```

This command enables support access and generates an encrypted password.
Share the password with Customer Service and Support personnel.
They can decrypt it to get a temporary support password to access your device.

## PARAMETERS

### -Scope
Specifies the scope.
The acceptable values for this parameter are:

- Cluster.
Provides support access for both nodes.
This is the default. 
- Controller.
Provides support access for the local node only.

```yaml
Type: ClusterScope
Parameter Sets: (All)
Aliases: 
Accepted values: Cluster, Controller

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Disable-HcsSupportAccess](./Disable-HcsSupportAccess.md)

[Get-HcsSupportAccess](./Get-HcsSupportAccess.md)

