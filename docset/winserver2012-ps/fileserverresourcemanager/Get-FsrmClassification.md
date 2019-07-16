---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: CC9F0F9B-25E3-4AF7-8BB5-0FD384F31009
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-FsrmClassification

## SYNOPSIS
Gets the status of the running file classification.

## SYNTAX

```
Get-FsrmClassification [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmClassification** cmdlet gets the status of the file classification process that the server is currently running.
This cmdlet returns a status value of Unknown, NotRunning, Queued, or Running.

## EXAMPLES

### Example 1: Get the status of the running classification
```
PS C:\>Get-FsrmClassification
```

This command gets the status of the classification that the server is currently running.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMClassification

## NOTES

## RELATED LINKS

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Stop-FsrmClassification](./Stop-FsrmClassification.md)

[Start-FsrmClassification](./Start-FsrmClassification.md)

[Stop-FsrmClassification](./Stop-FsrmClassification.md)

[Wait-FsrmClassification](./Wait-FsrmClassification.md)

