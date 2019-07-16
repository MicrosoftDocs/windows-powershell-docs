---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 70EF1E21-21D0-47CD-BA75-BC214E32A490
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-FsrmFileManagementJob

## SYNOPSIS
Gets file management jobs.

## SYNTAX

```
Get-FsrmFileManagementJob [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmFileManagementJob** cmdlet gets a file management job or all file management jobs on the server.

## EXAMPLES

### Example 1: Get a file management job
```
PS C:\>Get-FsrmFileManagementJob
```

This command gets all the file management jobs on the server.

### Example 2: Get a file management job by using a name
```
PS C:\>Get-FsrmFileManagementJob -Name "Encrypt sensitive files"
```

This command gets the file management job named Encrypt sensitive files.

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
Specifies an array of names of file management jobs.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileManagementJob

## NOTES

## RELATED LINKS

[Set-FsrmFileManagementJob](./Set-FsrmFileManagementJob.md)

[New-FsrmFileManagementJob](./New-FsrmFileManagementJob.md)

[Remove-FsrmFileManagementJob](./Remove-FsrmFileManagementJob.md)

[Start-FsrmFileManagementJob](./Start-FsrmFileManagementJob.md)

[Wait-FsrmFileManagementJob](./Wait-FsrmFileManagementJob.md)

[Stop-FsrmFileManagementJob](./Stop-FsrmFileManagementJob.md)

