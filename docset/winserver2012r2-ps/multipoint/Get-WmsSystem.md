---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://docs.microsoft.com/powershell/module/multipoint/get-wmssystem?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsSystem
---

# Get-WmsSystem

## SYNOPSIS
Returns Windows MultiPoint Server system information.

## SYNTAX

```
Get-WmsSystem [-SerializeString] [-WindowsEdition] [-ConnectionCount] [-LicenseCount] [-SystemMode]
 [-IsWmsServiceRunning] [-GetRemoteCredential] [-IdentifyMode] [-ManagedServerList] [-MPMConnectionString]
 [-WMSConnectionString] [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsSystem cmdlet returns Windows MultiPoint Server system information or the information requested based on the command line.

## EXAMPLES

### Example
```
PS C:\> Get-WmsSystem
WmsVersion                 : 2.0


NetJoinStatus              : NetSetupDomainName


DomainOrWorkgroupName      : TestDomain


SystemMode                 : Normal


IsIdentifyStarted          : False


WMSConnectionString        : 


MPMConnectionString        : 


ConnectionCount            : 1


LicenseCount               : 0


State                      : Connected


ConnectionError            : 0


ComputerName               : Test1


Sku                        : Oem


WindowsEdition             : Windows MultiPoint Server 2011


IsPremium                  : True


MaxCombinedLicenseCount    : 24


VLAcademicCalCount         : 0


OemCalCount                : 0


VLOpenCalCount             : 0


IsSingleSessionPerUser     : True


ManagedServers             : {}


IsSQMOn                    : True


IsWatsonOn                 : True


IsIPPerSessionEnabled      : False


NonLoopbackAdapterCount    : 1


MacUsedForVirtualIP        : 


IsDesktopMonitoringAllowed : True


IsRemoteFxEnabled          : False


IsWmsSvcRunning            : True


ReservedAccount            : 


ReservedAccountPassword    :
```

The Get-WmsSystem cmdlet returns MultiPoint Server system information.

### 1:
```
PS C:\>
```

## PARAMETERS

### -ConnectionCount
Total count of active Remote Desktop sessions.

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

### -GetRemoteCredential
Returns the MultiPoint Server reserved remote management account credentials.

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

### -IdentifyMode
The current system operating mode (either normal or maintenance mode).

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

### -IsWmsServiceRunning
Queries whether Windows MultiPoint Server Core Service is currently running.

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

### -LicenseCount
Returns total number of installed licenses.

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

### -ManagedServerList
Returns a list of managed servers that are being managed by the current user.

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

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SystemMode
The current system operating mode (either normal or maintenance mode).

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

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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

### -WindowsEdition
Displays the product name.

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

### -MPMConnectionString
{{Fill MPMConnectionString Description}}

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

### -WMSConnectionString
{{Fill WMSConnectionString Description}}

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsSystem collection as PSObject collection.

## NOTES

## RELATED LINKS

