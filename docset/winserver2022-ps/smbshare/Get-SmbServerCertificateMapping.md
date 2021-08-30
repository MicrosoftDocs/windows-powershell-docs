---
external help file: SmbServerCertificateMapping.cdxml-help.xml
Module Name: SmbShare
online version:
schema: 2.0.0
---

# Get-SmbServerCertificateMapping

## SYNOPSIS
Retrieves a certificate association with the SMB server for SMB over QUIC.

## SYNTAX

```
Get-SmbServerCertificateMapping [[-Name] <String[]>] [[-Subject] <String[]>] [-Thumbprint <String[]>]
 [-DisplayName <String[]>] [-StoreName <String[]>] [-Type <Type[]>] [-Flags <Flags[]>] [-IncludeHidden]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The Get-SmbServerCertificateMapping cmdlet retrieves the certificates associated with the SMB server for SMB over QUIC on ‘Windows Server 2022 Datacenter: Azure Edition’. This cmdlet is not used for Windows or other Windows Server editions. For more information, review SMB over QUIC.

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-SmbServerCertificateMapping
```

This command retrieves the certificate mapped to two SMB over QUIC server names that clients can connect to, “fs2.contoso.com” and “2022-ae-02.corp.contoso.com”.

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
Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session object, such as the output of a New-CimSession or Get-CimSession cmdlet. The default is the current session on the local computer.

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

### -DisplayName
Specifies a friendly name to display for the mapping.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Flags
Specifies if Named Pipes are enabled for SMB over QUIC. The acceptable values for this parameter are: 


- **None** Remove all flags 
- **NamedPipes** Enable use of named pipes in SMB over QUIC connections for this mapping (off by default, overrides value of RestrictNamedPipeAccessOverQuic) 
- **DefaultCert** Not used

```yaml
Type: Flags[]
Parameter Sets: (All)
Aliases:
Accepted values: None, AllowNamedPipe, DefaultCert

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeHidden
Not used.

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

### -Name
Specifies a fully-qualified DNS name or NetBIOS name that must match the certificate’s subject name or an entry in the certificate’s subject alternative names.

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

### -StoreName
Specifies the path to the certificate store for the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject
Specifies the subject name of the certificate.

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If this parameter is omitted or a value of 0 is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer. The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -Thumbprint
Specifies the thumbprint value of the certificate.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Type
Specifies the type of certificate mapping. The acceptable value for this parameter is:  

**QUIC** Certificate mapping is for SMB over QUIC.

```yaml
Type: Type[]
Parameter Sets: (All)
Aliases:
Accepted values: QUIC

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Type[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.SmbServerCertificateMapping.Flags[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/SMB/MSFT_SmbServerCertificateMapping

## NOTES

## RELATED LINKS
