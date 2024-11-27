---
external help file: CCPPSH.dll-Help.xml
Module Name: HPC
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hpc/get-hpcjobcredential?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-HpcJobCredential
---

# Get-HpcJobCredential

## SYNOPSIS
Gets the credentials for submitting jobs.

## SYNTAX

```
Get-HpcJobCredential [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcJobCredential** cmdlet gets the certificate credentials for submitting jobs.
This cmdlet returns a list of HPC soft card certificates with their thumbprints and the dates for which they are valid.
For most users, this list will have only one entry.
If none exist, nothing is returned.

## EXAMPLES

### Example 1: Get all certificates for the job scheduler
```
PS C:\>$List = Get-HpcJobCredential -Scheduler "MyHeadNode"
```

This command gets a list of all certificates that are currently being used by the HPC scheduler.

## PARAMETERS

### -Scheduler
Specifies the host name or IP address of the head node that contains the credentials.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.

```yaml
Type: String[]
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

## NOTES
This cmdlet was introduced in HPC Pack 2008 R2 with Service Pack 2 (SP2). It is not supported in previous versions.

## RELATED LINKS

[New-HpcSoftCard](./New-HpcSoftCard.md)

[Remove-HpcJobCredential](/powershell/module/hpcpack2016/remove-hpcjobcredential?view=hpc16-ps)

[Set-HpcJobCredential](/powershell/module/hpcpack2016/set-hpcjobcredential?view=hpc16-ps)
