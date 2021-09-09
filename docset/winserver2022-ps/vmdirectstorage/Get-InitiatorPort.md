---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Get-InitiatorPort

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByNodeAddress (Default)
```
Get-InitiatorPort [[-NodeAddress] <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectId
```
Get-InitiatorPort [-ObjectId <String[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByInstanceName
```
Get-InitiatorPort [-InstanceName <String[]>] [-ConnectionType <ConnectionType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByVirtualDisk
```
Get-InitiatorPort [-VirtualDisk <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSISession
```
Get-InitiatorPort [-iSCSISession <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByiSCSIConnection
```
Get-InitiatorPort [-iSCSIConnection <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByiSCSITarget
```
Get-InitiatorPort [-iSCSITarget <CimInstance>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
{{ Fill AsJob Description }}

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
{{ Fill CimSession Description }}

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

### -ConnectionType
{{ Fill ConnectionType Description }}

```yaml
Type: ConnectionType[]
Parameter Sets: ByNodeAddress, ByInstanceName
Aliases:
Accepted values: Other, FibreChannel, iSCSI, SAS

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceName
{{ Fill InstanceName Description }}

```yaml
Type: String[]
Parameter Sets: ByInstanceName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -iSCSIConnection
{{ Fill iSCSIConnection Description }}

```yaml
Type: CimInstance
Parameter Sets: ByiSCSIConnection
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSISession
{{ Fill iSCSISession Description }}

```yaml
Type: CimInstance
Parameter Sets: ByiSCSISession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSITarget
{{ Fill iSCSITarget Description }}

```yaml
Type: CimInstance
Parameter Sets: ByiSCSITarget
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NodeAddress
{{ Fill NodeAddress Description }}

```yaml
Type: String[]
Parameter Sets: ByNodeAddress
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ObjectId
{{ Fill ObjectId Description }}

```yaml
Type: String[]
Parameter Sets: ByObjectId
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

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

### -VirtualDisk
{{ Fill VirtualDisk Description }}

```yaml
Type: CimInstance
Parameter Sets: ByVirtualDisk
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.InitiatorPort.ConnectionType[]

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorPort

## NOTES

## RELATED LINKS
