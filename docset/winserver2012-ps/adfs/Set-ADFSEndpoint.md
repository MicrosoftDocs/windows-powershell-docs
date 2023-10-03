---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsendpoint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSEndpoint

## SYNOPSIS
Sets the properties of a Federation Service endpoint.

## SYNTAX

### Address
```
Set-ADFSEndpoint [[-TargetAddressPath] <String>] -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TargetObject
```
Set-ADFSEndpoint -TargetEndpoint <Endpoint> -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### FullUrl
```
Set-ADFSEndpoint [-TargetFullUrl] <Uri> -Proxy <Boolean> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSEndpoint cmdlet can be used to enable and disable endpoints on the federation server proxy.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADFSEndpoint -TargetAddress /adfs/services/trust/13/Windows -Proxy $true
```

Description

-----------

Enables the WS-Trust 1.3 endpoint for proxy use.

## PARAMETERS

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

### -PassThru
Passes an object to the pipeline.
By default, this cmdlet does not generate any output.

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

### -Proxy
Specifies whether the endpoint is available on the federation server proxy.
This is the only field of the endpoint that can be set.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetAddressPath
```yaml
Type: String
Parameter Sets: Address
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetEndpoint
Specifies the endpoint that will be modified by the cmdlet. 
his value is typically taken from the pipeline.

```yaml
Type: Endpoint
Parameter Sets: TargetObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetFullUrl
Specifies the full URL of the endpoint that will be modified by the cmdlet.

```yaml
Type: Uri
Parameter Sets: FullUrl
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.Endpoint
A class structure that represents an endpoint.

## OUTPUTS

### None

## NOTES
* This cmdlet has three parameter-sets. You can use Address, FullUrl, or TargetEndpoint (over the pipeline) to identify the endpoint. Set-ADFSEndpoint only allows you to modify the Proxy property of the endpoint.

  Endpoints provide access to the federation server functionality of Active Directory Federation Services (AD FS) 2.0, such as token issuance, Information Card issuance, and the publishing of federation metadata.
Depending on the type of endpoint, you can enable or disable the endpoint or control whether the endpoint is published to AD FS 2.0 proxies.

## RELATED LINKS

[Disable-ADFSEndpoint](./Disable-ADFSEndpoint.md)

[Enable-ADFSEndpoint](./Enable-ADFSEndpoint.md)

[Get-ADFSEndpoint](./Get-ADFSEndpoint.md)

