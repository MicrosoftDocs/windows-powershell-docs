---
external help file: MSFT_WdsInstallImageGroup_v1.0.cdxml-help.xml
Module Name: WDS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/wds/get-wdsinstallimagegroup?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WdsInstallImageGroup
---

# Get-WdsInstallImageGroup

## SYNOPSIS
Gets properties of install image groups.

## SYNTAX

```
Get-WdsInstallImageGroup [-Name <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WdsInstallImageGroup** cmdlet gets properties of install image groups on the Windows Deployment Services server.
If you do not specify the **Name** parameter, the cmdlet returns all image groups on the server.

## EXAMPLES

### Example 1: Get an install image group
```
PS C:\> Get-WdsInstallImageGroup -Name "Fabrikam LOB Images"
```

This command gets the install image group named Fabrikam LOB Images.

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

### -Name
Specifies a name.
This is the name of an install image group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: GroupName

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsInstallImageGroup

## NOTES

## RELATED LINKS

[Get-WdsInstallImageGroup](./Get-WdsInstallImageGroup.md)

[Set-WdsInstallImageGroup](./Set-WdsInstallImageGroup.md)

[New-WdsInstallImageGroup](./New-WdsInstallImageGroup.md)

[Remove-WdsInstallImageGroup](./Remove-WdsInstallImageGroup.md)

