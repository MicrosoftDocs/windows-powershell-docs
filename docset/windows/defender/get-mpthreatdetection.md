---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: coreyp
author: coreyp-at-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_MpThreatDetection.cdxml-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 09/19/2018
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-MpThreatDetection
ms.assetid: F8A11A2D-8E09-4C0C-93A5-8B8097CFDF75
---

# Get-MpThreatDetection

## SYNOPSIS
Gets active and past malware threats that Windows Defender detected.

## SYNTAX

### DefaultSet (Default)
```
Get-MpThreatDetection [<CommonParameters>]
```

### ById
```
Get-MpThreatDetection [-ThreatID <Int64[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-MpThreatDetection** cmdlet gets active and past malware threats that Windows Defender detected on the computer.
If Windows Defender has detected the threat that you specify, this cmdlet returns a list that shows each time Windows Defender detected the threat.

## EXAMPLES

### Example 1: Get threats that Windows Defender detected
```
PS C:\> Get-MpThreatDetection
```

This command returns the list of past malware detections for the local computer.

**Error codes**

The following table lists the error codes for this cmdlet. Each error code has a 0x8050 prefix. Therefore, an ERROR_MP_BAD_SCANID error corresponds to error code 0x80508012. Additionally, an ERR_MP_REMOVE_FAILED error corresponds to error code 0x80508017. 

For a list of error codes, along with possible reasons and resolutions, see [Windows Defender Antivirus client error codes](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus#windows-defender-antivirus-client-error-codes) in the topic [Review event logs and error codes to troubleshoot issues with Windows Defender Antivirus](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus#windows-defender-antivirus-client-error-codes).

|Symbolic Name                       | Error Number |
|------------------------------------|--------------|
|ERROR_MP_UI_CONSOLIDATION_BASE    	 | 0x80501000   |
|ERROR_MP_ACTIONS_FAILED           	 | 0x80501001   |
|ERROR_MP_BAD_INIT_MODULES         	 | 0x80508001   |
|ERROR_MP_BAD_DATABASE             	 | 0x80508002   |
|ERROR_MP_BAD_UFS                  	 | 0x80508004   |
|ERROR_MP_NO_MEMORY                	 | 0x80508007   |
|ERROR_MP_BAD_INPUT_DATA           	 | 0x8050800C   |
|ERROR_MP_BAD_GLOBAL_STORAGE       	 | 0x8050800D   |
|ERROR_MP_OBSOLETE                 	 | 0x8050800E   |
|ERROR_MP_NOT_SUPPORTED            	 | 0x8050800F   |
|ERROR_MP_NO_MORE_ITEMS            	 | 0x80508010   |
|ERROR_MP_DUPLICATE_SCANID         	 | 0x80508011   |
|ERROR_MP_BAD_SCANID               	 | 0x80508012   |
|ERROR_MP_BAD_USERDB_VERSION       	 | 0x80508013   |
|ERROR_MP_RESTORE_FAILED           	 | 0x80508014   |
|ERROR_MP_FAILED_TO_SPYNET         	 | 0x80508015   |
|ERROR_MP_BAD_ACTION               	 | 0x80508016   |
|ERROR_MP_REMOVE_FAILED            	 | 0x80508017   |
|ERROR_MP_SCAN_ABORTED             	 | 0x80508018   |
|ERROR_MP_NOT_FOUND                	 | 0x80508019   |
|ERROR_MP_BAD_CONFIGURATION        	 | 0x80508020   |
|ERROR_MP_QUARANTINE_FAILED        	 | 0x80508021   |
|ERROR_MP_REBOOT_REQUIRED          	 | 0x80508022   |
|ERROR_MP_THREAT_NOT_FOUND         	 | 0x80508023   |
|ERROR_MP_FULL_SCAN_REQUIRED       	 | 0x80508024   |
|ERROR_MP_MANUAL_STEPS_REQUIRED    	 | 0x80508025   |
|ERROR_MP_REMOVE_NOT_SUPPORTED     	 | 0x80508026   |
|ERROR_MP_REMOVE_LOW_MEDIUM_DISABLED | 0x80508027   |
|ERR_MP_RESCAN_REQUIRED      	     | 0x80508029   |
|ERROR_RELO_BAD_EHANDLE            	 | 0x80509001   |
|ERROR_RELO_KERNEL_NOT_LOADED      	 | 0x80509003   |
|ERROR_MP_BADDB_OPEN               	 | 0x8050A001   |
|ERROR_MP_BADDB_HEADER             	 | 0x8050A002   |
|ERROR_MP_BADDB_OLDENGINE          	 | 0x8050A003   |
|ERROR_MP_BADDB_CONTENT            	 | 0x8050A004   |
|ERROR_MP_BADDB_NOTSIGNED          	 | 0x8050A005   |

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete. 

The cmdlet immediately returns an object that represents the job and then displays the command prompt. 
You can continue to work in the session while the job completes. 
To manage the job, use the `*-Job` cmdlets. 
To get the job results, use the [Receive-Job](http://go.microsoft.com/fwlink/?LinkID=113372) cmdlet. 

For more information about Windows PowerShell background jobs, see [about_Jobs](http://go.microsoft.com/fwlink/?LinkID=113251).

```yaml
Type: SwitchParameter
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer. 
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet. 
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: ById
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThreatID
Specifies an array of threat IDs.
This cmdlet gets the threats that you specify.

```yaml
Type: Int64[]
Parameter Sets: ById
Aliases: ID

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
Parameter Sets: ById
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-MpThreat](./Get-MpThreat.md)

[Remove-MpThreat](./Remove-MpThreat.md)

[Get-MpThreatCatalog](./Get-MpThreatCatalog.md)

