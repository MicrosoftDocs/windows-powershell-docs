---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/debug-fileshare?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-FileShare
---

# Debug-FileShare

## SYNOPSIS
Finds problems with a file share and recommends solutions.

## SYNTAX

### ByName (Default)
```
Debug-FileShare [-Name] <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByUniqueId
```
Debug-FileShare -UniqueId <String[]> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### InputObject
```
Debug-FileShare -InputObject <CimInstance> [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Debug-FileShare** cmdlet finds problems with a file share and recommends solutions.

## EXAMPLES

### Example 1: Debug a file share by using the pipeline
```
PS C:\>Get-FileShare | Debug-FileShare
EventTime                 :
FaultId                   : 0ef62dbe-657a-483e-a248-7c5c1dc82477
FaultingObject            :
FaultingObjectDescription : Storage appliance server '{ac906082-8b7e-44fc-b9e5-7bd8aa749958}:SN:GalenB-VM6'.
FaultingObjectLocation    :
FaultType                 : ServerDownFault
PerceivedSeverity         : Minor
Reason                    : The server cannot be reached.
RecommendedActions        : {Start or replace storage server.}
PSComputerName            :
```

This command gets any faults and remediation actions associated with all file shares local to the Windows PowerShell session.

### Example 2: Debug a file share by name
```
PS C:\>Debug-FileShare -Name "ContosoShare"
EventTime                 :
FaultId                   : 0ef62dbe-657a-483e-a248-7c5c1dc82477
FaultingObject            :
FaultingObjectDescription : Storage appliance server '{ac906082-8b7e-44fc-b9e5-7bd8aa749958}:SN:GalenB-VM6'.
FaultingObjectLocation    :
FaultType                 : ServerDownFault
PerceivedSeverity         : Minor
Reason                    : The server cannot be reached.
RecommendedActions        : {Start or replace storage server.}
PSComputerName            :
```

This command gets any faults and remediation actions associated the file share named ContosoShare.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the file share about which you want to get information.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -UniqueId
Specifies the ID of the file share about which you want to get information.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FileShare

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageDiagnoseResult

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-FileShare](./Get-FileShare.md)

[New-FileShare](./New-FileShare.md)

[Remove-FileShare](./Remove-FileShare.md)

[Set-FileShare](./Set-FileShare.md)

