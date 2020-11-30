---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 636F18BD-3619-48ED-B68E-7F1EAB89C744
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Stop-FsrmClassification

## SYNOPSIS
Stops the running instance of a classification.

## SYNTAX

```
Stop-FsrmClassification [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Stop-FsrmClassification** cmdlet stops the running instance of a classification job on the server.
If the cmdlet cannot stop the running or queued classification on the server, the cmdlet fails and returns an error.

This cmdlet returns a status of success in the following conditions: 
- The classification is not currently running on the server. 
- The classification is currently running and the server has started the process of cancelling the classification. 
- The classification is queued on the server and the server has successfully removed the classification from the queue.

## EXAMPLES

### Example 1: Stop the running classification
```
PS C:\>Stop-FsrmClassification
```

This command stops the running instance of a classification.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-FsrmClassification](./Get-FsrmClassification.md)

[Set-FsrmClassification](./Set-FsrmClassification.md)

[Start-FsrmClassification](./Start-FsrmClassification.md)

[Wait-FsrmClassification](./Wait-FsrmClassification.md)

