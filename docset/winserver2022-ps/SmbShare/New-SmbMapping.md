---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/smbshare/new-smbmapping?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-SmbMapping
---

# New-SmbMapping

## SYNOPSIS
Creates an SMB mapping.

## SYNTAX

```
New-SmbMapping [[-LocalPath] <String>] [[-RemotePath] <String>] [-UserName <String>] [-Password <String>]
 [-Persistent <Boolean>] [-SaveCredentials] [-HomeFolder] [-RequireIntegrity <Boolean>]
 [-RequirePrivacy <Boolean>] [-UseWriteThrough <Boolean>] [-TransportType <TransportType>]
 [-SkipCertificateCheck] [-CompressNetworkTraffic <Boolean>] [-GlobalMapping] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SmbMapping** cmdlet creates a Server Message Block (SMB) mapping on the SMB client to an SMB share.

## EXAMPLES

### Example 1: Create an SMB mapping
```
PS C:\>New-SmbMapping -LocalPath 'X:' -RemotePath '\\Contoso-SO\VMFiles'
Status                                  Local Path                              Remote Path
------                                  ----------                              -----------
OK                                      X:                                      \\Contoso-SO\VMFiles
```

This command creates an SMB mapping.

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

### -CompressNetworkTraffic
Indicates that SMB compression is requested for the mapped drive if the SMB server supports it.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalMapping
Indicates that the SMB mapping is global instead of user-specific and is equivalent to using New-SmbGlobalMapping without any explicit allow or deny settings.

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

### -HomeFolder
Indicates that the connection is made to the home folder of the user.

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

### -LocalPath
Specifies the local path to which the remote path is mapped.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies the password to be used to connect to the SMB share.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistent
Indicates that this connection is persistent.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemotePath
Specifies the remote path that is accessed from this computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireIntegrity
Indicates that SMB signing is required for the mapped drive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequirePrivacy
Indicates that SMB encryption is required for the mapped drive.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SaveCredentials
Indicates that the credentials provided should be saved for when a mapping to the same SMB server also is created.

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

### -SkipCertificateCheck
Indicates that the client does not need to trust the server certificate's issuer in order to connect using SMB over QUIC.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -TransportType
Specifies the network transport used by SMB. The acceptable values for this parameter are:

- `TCP`: Use TCP network transport.
- `QUIC`: Use QUIC network transport.
- `None`: Use default transport behavior (first try TCP then try QUIC).

```yaml
Type: TransportType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the user name to use to connect to the SMB share.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseWriteThrough
Indicates that forced unit access ("write through") is required and bypasses all OS caches, forcing IO to disk.

```yaml
Type: Boolean
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
Aliases: cf

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
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMapping
This cmdlet returns a **MSFT_SmbMapping** object that represents the newly created SMB mapping.

## NOTES

## RELATED LINKS

[Get-SmbMapping](./Get-SmbMapping.md)

[Remove-SmbMapping](./Remove-SmbMapping.md)

