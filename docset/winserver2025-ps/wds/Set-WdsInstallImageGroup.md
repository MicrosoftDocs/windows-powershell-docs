---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_WdsInstallImageGroup_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/wds/set-wdsinstallimagegroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WdsInstallImageGroup
---

# Set-WdsInstallImageGroup

## SYNOPSIS
Modifies the name and access permissions of an install image group.

## SYNTAX

```
Set-WdsInstallImageGroup [-NewName <String>] -Name <String> [-SecurityDescriptorSDDL <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WdsInstallImageGroup** cmdlet modifies the name and access permissions of an install image group.
Specify a group to modify by using the *Name* parameter.
Specify the access permissions on the image group using the *SecurityDescriptorSDDL* parameter.

## EXAMPLES

### Example 1: Rename an install image group
```
PS C:\> Set-WdsInstallImageGroup -Name "Fabrikam LOB Images" -NewName "Fabrikam Customized System Images"
```

This command renames the install image group named Fabrikam LOB Images.

### Example 2: Modify access permissions of an install image group
```
PS C:\> Set-WdsInstallImageGroup -Name "Fabrikam System Images" -SecurityDescriptorSDDL "O:BAG:DUD:(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;0x1200a9;;;AU)(A;OICI;FA;;;S-1-5-80-1688844526-3235337491-1375791646-891369040-3692469510)"
```

This command modifies the access permissions that users require for the session configuration of the install image group named Fabrikam System Images.
The command specifies the security descriptor for the image group in SDDL format.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -Name
Specifies a name.
This is the name of an install image group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: GroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the install image group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: NewGroupName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityDescriptorSDDL
Specifies the security descriptor for the image group in SDDL format.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImageGroup

## NOTES

## RELATED LINKS

[Get-WdsInstallImageGroup](./Get-WdsInstallImageGroup.md)

[New-WdsInstallImageGroup](./New-WdsInstallImageGroup.md)

[Remove-WdsInstallImageGroup](./Remove-WdsInstallImageGroup.md)

