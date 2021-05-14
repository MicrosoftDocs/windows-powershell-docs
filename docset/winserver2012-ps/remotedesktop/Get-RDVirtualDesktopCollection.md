---
external help file: RemoteDesktop.psm1-help.xml
Module Name: RDMgmt
online version: https://docs.microsoft.com/powershell/module/rdmgmt/get-rdvirtualdesktopcollection?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-RDVirtualDesktopCollection

## SYNOPSIS
Gets a list of virtual desktop collections in a remote desktop deployment.

## SYNTAX

```
Get-RDVirtualDesktopCollection [[-CollectionName] <String>] [-ConnectionBroker <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDVirtualDesktopCollection** cmdlet gets a list of existing virtual desktop collections in a remote desktop deployment.

## EXAMPLES

### Example 1: Get the list of the virtual desktop collections in a remote desktop deployment
```
PS C:\> Get-RDVirtualDesktopCollection -ConnectionBroker "rdcb.contoso.com"
```

This command lists the virtual desktop collections associated with the RD Connection Broker named "rdcb.contoso.com".

## PARAMETERS

### -CollectionName
Specifies the name of the virtual desktop collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a remote desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
The output type is Microsoft.RemoteDesktopServices.Management.RDVirtualDesktopCollection.

## NOTES

## RELATED LINKS

[New-RDVirtualDesktopCollection](./New-RDVirtualDesktopCollection.md)

[Remove-RDVirtualDesktopCollection](./Remove-RDVirtualDesktopCollection.md)

[Update-RDVirtualDesktopCollection](./Update-RDVirtualDesktopCollection.md)

