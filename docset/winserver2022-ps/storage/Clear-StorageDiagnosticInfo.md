---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageSubSystem.cdxml-help.xml
Module Name: Storage
ms.date: 08/30/2021
online version: https://docs.microsoft.com/powershell/module/storage/clear-storagediagnosticinfo?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-StorageDiagnosticInfo
---

# Clear-StorageDiagnosticInfo

## SYNOPSIS

## SYNTAX

### ByFriendlyName (Default)
```
Clear-StorageDiagnosticInfo [-StorageSubSystemFriendlyName] <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByUniqueId
```
Clear-StorageDiagnosticInfo -StorageSubSystemUniqueId <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### ByName
```
Clear-StorageDiagnosticInfo -StorageSubSystemName <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [<CommonParameters>]
```

### InputObject (cdxml)
```
Clear-StorageDiagnosticInfo -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -StorageSubSystemFriendlyName
{{ Fill StorageSubSystemFriendlyName Description }}

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemName
Specifies the name of the storage subsystem.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId
Specifies the UniqueID of the storage subsystem to use.

```yaml
Type: String[]
Parameter Sets: ByUniqueId
Aliases: StorageSubsystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance
### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubSystem
## NOTES

## RELATED LINKS
