---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: FileIntegrity.cdxml-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-fileintegrity?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FileIntegrity
---

# Get-FileIntegrity

## SYNOPSIS
Gets integrity information for a file on an ReFS volume.

## SYNTAX

```
Get-FileIntegrity [-FileName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-FileIntegrity** cmdlet gets integrity information for a file on a Resilient File System (ReFS) volume.

## EXAMPLES

### Example 1: Get file integrity information
```
PS C:\>Get-FileIntegrity -FileName 'H:\Temp\New Text Document.txt'
FileName                                Enabled                              Enforced

--------                                -------                              --------

H:\Temp\New Text Document.txt           False                                True
```

This command gets file integrity information for a file.

### Example 2: Get file integrity information for multiple files by using the pipeline
```
PS C:\>Get-Item -Path 'H:\Temp\*' | Get-FileIntegrity
FileName                                Enabled                              Enforced

--------                                -------                              --------

H:\Temp\New Text Document 07 21         False                                True

H:\Temp\New Text Document 08 19         False                                True

H:\Temp\New Text Document 08 22         False                                True

H:\Temp\New Text Document 09 07         False                                True
```

This command uses the [Get-Item](https://go.microsoft.com/fwlink/?LinkID=290495) cmdlet to get all the files in the specified folder, and then passes them to the current cmdlet by using the pipeline operator.
For more information, type `Get-Help Get-Item`.
The command gets file integrity information for all the files in the folder.

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
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileName
Specifies a file name.
The cmdlet gets integrity settings for the file that you specify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FullName

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.IO.FileInfo

To obtain a **FileInfo** object, use the [Get-Item](https://go.microsoft.com/fwlink/?LinkID=290495) cmdlet for a specified file name.
The cmdlet uses the **FullName** property as the value of the *FileName* parameter.

### System.IO.DirectoryInfo

To obtain a **DirectoryInfo** object, use **Get-Item** for a specified directory name.
The cmdlet uses the **FullName** property as the value of the *FileName* parameter.

## OUTPUTS

### MSFT_FileIntegrity

This cmdlet generates an **MSFT_FileIntegrity** object.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Repair-FileIntegrity](./Repair-FileIntegrity.md)

[Set-FileIntegrity](./Set-FileIntegrity.md)

