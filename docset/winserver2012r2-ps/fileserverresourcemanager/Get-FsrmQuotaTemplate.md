---
external help file: FsrmQuotaTemplate.cdxml-help.xml
Module Name: FileServerResourceManager
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmquotatemplate?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FsrmQuotaTemplate
---

# Get-FsrmQuotaTemplate

## SYNOPSIS
Gets FSRM quota templates

## SYNTAX

```
Get-FsrmQuotaTemplate [[-Name] <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FsrmQuotaTemplate** cmdlet gets one or more File Server Resource Manager (FSRM) quota templates on the server.

## EXAMPLES

### Example 1: Get all quota templates
```
PS C:\>Get-FsrmQuotaTemplate
```

This command gets all quota templates on the server.

### Example 1: Get a quota template by using a name
```
PS C:\>Get-FsrmQuotaTemplate -Name "128MB limit"
```

This command gets the quota templates named "128MB limit".

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
Specifies an array of names of quota templates.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMQuotaTemplate

## NOTES

## RELATED LINKS

[Set-FsrmQuotaTemplate](./Set-FsrmQuotaTemplate.md)

[New-FsrmQuotaTemplate](./New-FsrmQuotaTemplate.md)

[Remove-FsrmQuotaTemplate](./Remove-FsrmQuotaTemplate.md)

