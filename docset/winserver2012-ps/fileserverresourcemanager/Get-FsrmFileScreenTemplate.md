---
external help file: FSRM_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A0B83E87-52D7-42A0-B3FD-35A6C40055B7
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-FsrmFileScreenTemplate

## SYNOPSIS
Gets file screen templates.

## SYNTAX

```
Get-FsrmFileScreenTemplate [[-Name] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-FsrmFileScreenTemplate** cmdlet gets one or more file screen templates.

## EXAMPLES

### Example 1: Get all file screen templates
```
PS C:\>Get-FsrmFileScreenTemplate
```

This command gets all file screen templates on the server.

### Example 2: Get a file screen template by using a name
```
PS C:\>Get-FsrmFileScreenTemplate -Name "Block media files"
```

This command gets the file screen template named "Block media files".

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
Specifies an array of names of file screen templates.

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

### Microsoft.Management.Infrastructure.CimInstance#MSFT_FSRMFileScreenTemplate

## NOTES

## RELATED LINKS

[Set-FsrmFileScreenTemplate](./Set-FsrmFileScreenTemplate.md)

[New-FsrmFileScreenTemplate](./New-FsrmFileScreenTemplate.md)

[Remove-FsrmFileScreenTemplate](./Remove-FsrmFileScreenTemplate.md)

