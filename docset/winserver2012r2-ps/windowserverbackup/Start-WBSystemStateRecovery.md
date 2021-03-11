---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
online version: 
schema: 2.0.0
title: Start-WBSystemStateRecovery
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 9C76B714-7FCD-4DF4-A988-F4E27113EB02
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Start-WBSystemStateRecovery

## SYNOPSIS
Starts a system state recovery operation.

## SYNTAX

### SSR (Default)
```
Start-WBSystemStateRecovery [-BackupSet] <WBBackupSet> [[-TargetPath] <String>] [-AuthoritativeSysvolRecovery]
 [-RestartComputer] [-Async] [-Force] [<CommonParameters>]
```

### ADIFM
```
Start-WBSystemStateRecovery [-BackupSet] <WBBackupSet> [-ADIFM] [-TargetPath] <String> [-Async] [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-WBSystemStateRecovery** cmdlet starts a system state recovery operation.
If the System State recovery operation is performed on the actual computer, completion of the operation requires a restart.
If recovery is performed on an Active Directory (AD) computer, this cmdlet must be run in Directory Services Restore Mode (DSRM).

## EXAMPLES

### Example 1: Start a system state recovery operation
```
PS C:\> $Backup = Get-WBBackupSet
PS C:\> Start-WBSystemStateRecovery -BackupSet $Backup -Force -RestartComputer -Async
```

This example starts a system state recovery operation, and then restarts the computer at the end of the recovery operation.

The first command stores the result of Get-WBBackupSet in a variable named **$Backup**.

The second command starts the system state recovery from the backup set in **$Backup**.
The command also uses the **Force** parameter to perform the recovery without prompting, the **RestartComputer** parameter to restart the computer when recovery finishes, and the **Async** parameter to suppress status output.

## PARAMETERS

### -ADIFM
Indicates an install from media (IFM) operation to recover all the related data needed for Active Directory Domain Services.
Active Directory Install From Media (ADIFM) creates a copy of the Active Directory database, registry, and SYSVOL state, and then saves this information in the location specified by **RecoveryTarget**.
Use this parameter only when **RecoveryTarget** is specified.
This parameter is valid only if the backup set contains an Active Directory system state backup.

```yaml
Type: SwitchParameter
Parameter Sets: ADIFM
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Async
Indicates that Windows PowerShell return immediately after starting the backup, and not output status to the screen.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthoritativeSysvolRecovery
Indicates an authoritative recovery of SYSVOL, the System Volume shared directory.
This parameter is valid only if the backup set contains an Active Directory system state backup.

```yaml
Type: SwitchParameter
Parameter Sets: SSR
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupSet
Specifies the backup set from which system state recovery is to be done.

```yaml
Type: WBBackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Starts the system state recovery without prompting you for confirmation.
By default, the cmdlet prompts you for confirmation before it proceeds.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestartComputer
Indicates a system restart at the completion of the system state recovery operation.
Use this parameter only for a recovery to the original location.
Do not use this parameter if you need to perform steps after the recovery operation.

```yaml
Type: SwitchParameter
Parameter Sets: SSR
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPath
Specifies an alternate location where the files belonging to system state can be recovered from the backup set.
If you do not specify this parameter, system state recovery is performed for the actual computer, which will need a restart at the end of the operation. 
ADIFM recovery requires this parameter.

```yaml
Type: String
Parameter Sets: SSR
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: ADIFM
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WBBackupSet
Specifies the backup set that contains volume backup of all the system critical volumes, or contains backup of the system state for the system state recovery operation.

## OUTPUTS

### System.String
If you do not specify the **Async** parameter, the recovery operation outputs status at periodic intervals until the recovery operation completes.
You can also call Get-WBJob to get the status of the current recovery operation.
After completion of recovery, run Get-WBJob with the Previous parameter and an argument of 1to get the final recovery status.

## NOTES

## RELATED LINKS

