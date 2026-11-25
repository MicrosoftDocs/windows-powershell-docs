---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: WebApplicationProxy-help.xml
Module Name: WebApplicationProxy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/webapplicationproxy/get-webapplicationproxyavailableadfsrelyingparty?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebApplicationProxyAvailableADFSRelyingParty
---

# Get-WebApplicationProxyAvailableADFSRelyingParty

## SYNOPSIS
Retrieves a list of available relying parties configured on a federation server.

## SYNTAX

```
Get-WebApplicationProxyAvailableADFSRelyingParty [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebApplicationProxyAvailableADFSRelyingParty** cmdlet retrieves a list of all the relying parties configured on a federation server.
A relying party is a Federation Service or application that consumes claims or Windows Integrated authentication.

Web Application Proxy can publish all of the AD FS relying parties that this command retrieves.

## EXAMPLES

### Example 1: Retrieve a list of all relying parties
```
PS C:\> Get-WebApplicationProxyAvailableADFSRelyingParty
Enabled        : True
ID             : dad606b5-64b7-e211-9af2-00155d813cfa
IWA            : False
Name           : fedpassive
Published      : True
PSComputerName :

Enabled        : True
ID             : d34df8bf-64b7-e211-9af2-00155d813cfa
IWA            : True
Name           : WiaApp
Published      : False
PSComputerName :

Enabled        : True
ID             : 45e907cd-64b7-e211-9af2-00155d813cfa
IWA            : False
Name           : fedpassive2
Published      : False
PSComputerName :
```

This command retrieves all relying parties on this server.

### Example 2: Retrieve a list of all published relying parties
```
PS C:\> Get-WebApplicationProxyAvailableADFSRelyingParty | Where-Object {$_.Published -eq $True}
Enabled        : True
ID             : dad606b5-64b7-e211-9af2-00155d813cfa
IWA            : False
Name           : fedpassive
Published      : True
```

This command retrieves published relying parties on this server.

### Example 3: Retrieve a list of all relying parties and format the list
```
PS C:\> Get-WebApplicationProxyAvailableADFSRelyingParty | Format-Table -AutoSize
Enabled ID                                     IWA Name                        Published
------- --                                     --- ----                        ---------
   True dad606b5-64b7-e211-9af2-00155d813cfa False fedpassive                       True
   True d34df8bf-64b7-e211-9af2-00155d813cfa  True WiaApp                          False
   True 45e907cd-64b7-e211-9af2-00155d813cfa False fedpassive2                     False
   True ca8f1ed5-64b7-e211-9af2-00155d813cfa  True WiaApp2                         False
   True 4dd358e8-64b7-e211-9af2-00155d813cfa False msofba                          False
   True d7be97f6-64b7-e211-9af2-00155d813cfa False WSA                             False
```

This command retrieves the relying parties on this server, and then displays the output in table format.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#RelyingPartyMetadata

## NOTES

## RELATED LINKS

