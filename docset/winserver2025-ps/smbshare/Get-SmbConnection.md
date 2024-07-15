---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbConnection.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbconnection?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbConnection
---

# Get-SmbConnection

## SYNOPSIS
Retrieves the connections established from the SMB client to the SMB servers.

## SYNTAX

```
Get-SmbConnection [[-ServerName] <String[]>] [[-UserName] <String[]>] [-SmbInstance <SmbInstance>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmbConnection** cmdlet retrieves the connections established from the Server Message Block (SMB) client to the SMB servers.
Users can connect to an SMB share using credentials different than the associated logon credentials so that there will be a connection listed per share per user logon per credential used.

## EXAMPLES

### Example 1: Get connections from an SMB client to SMB servers
```
PS C:\>Get-SmbConnection
ServerName          ShareName           UserName             Credential           Dialect             NumOpens
----------          ---------           --------             ----------           -------             --------
Contoso-FS1         VMS5                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1
Contoso-FS1         VMS5                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                3
Contoso-FS          VMS1                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1
Contoso-FS          VMS1                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                5
Contoso-SO          VMS3                Contoso\Contoso-HV1$ Contoso\Contoso-HV1$ 3.00                1
Contoso-SO          VMS3                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                1
Contoso-SO          VMS3                NT VIRTUAL MACHI...  Contoso\Contoso-HV1$ 3.00                2
```

This command retrieves the connections established from the SMB client to the SMB servers.

### Example 2: Get connections from an SMB server
```
PS C:\>Get-SmbConnection -ServerName Contoso-FS | Select-Object -Property *
ContinuouslyAvailable : True
Credential            : Contoso\Contoso-HV1$
Dialect               : 3.00
Encrypted             : False
NumOpens              : 1
ServerName            : Contoso-FS
ShareName             : VMS1
UserName              : Contoso\Contoso-HV1$
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbConnection
CimInstanceProperties : {ContinuouslyAvailable, Credential, Dialect, Encrypted...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties

ContinuouslyAvailable : True
Credential            : Contoso\Contoso-HV1$
Dialect               : 3.00
Encrypted             : False
NumOpens              : 5
ServerName            : Contoso-FS
ShareName             : VMS1
UserName              : NT VIRTUAL MACHINE\F357A523-592B-4CA5-B61E-C06D5627E1C9
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbConnection
CimInstanceProperties : {ContinuouslyAvailable, Credential, Dialect, Encrypted...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command retrieves the connections established from the SMB client to the SMB server named Contoso-FS.

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

### -ServerName
Specifies that the connections made to the server are enumerated.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SmbInstance
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: SmbInstance
Parameter Sets: (All)
Aliases:
Accepted values: Default, CSV, SBL, SR

Required: False
Position: Named
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

### -UserName
Specifies that the connections made by the user are enumerated.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbConnection
This cmdlet returns a **MSFT_SmbConnection** object that represents the per share per user logon per credentials used to connect.

## NOTES

## RELATED LINKS

[Get-SmbMultichannelConnection](./Get-SmbMultichannelConnection.md)

[Update-SmbMultichannelConnection](./Update-SmbMultichannelConnection.md)

