---
author: Kateyanne
external help file: FSRM_Cmdlets.xml
manager: dansimp
Module Name: FileServerResourceManager
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/fileserverresourcemanager/get-fsrmadrsetting?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-FsrmAdrSetting

## SYNOPSIS
Gets access denied remediation settings for events.

## SYNTAX

```
Get-FsrmAdrSetting [[-Event] <FsrmAdrEventEnum[]>] [-AsJob] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmAdrSetting** cmdlet gets access denied remediation (ADR) settings in File Server Resource Manager (FSRM) for one or more events.

Windows Server® 2012 uses the ADR settings when a client cannot access a file.
Users get an access-denied message when they try to access shared files and folders on a file server for which they do not have permissions.

## EXAMPLES

### Example 1: Get FSRM access denied settings
```
PS C:\>Get-FsrmAdrSetting -Event AccessDenied
```

This command gets all access denied settings in FSRM.

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

### -Event
Specifies an array of types of events that ADR handles.
The acceptable values for this parameter are: AccessDenied and FileNotFound.

```yaml
Type: FsrmAdrEventEnum[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMADRSettings

## NOTES

## RELATED LINKS

[Set-FsrmAdrSetting](./Set-FsrmAdrSetting.md)

