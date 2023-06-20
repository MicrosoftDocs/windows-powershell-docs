---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: https://learn.microsoft.com/powershell/module/iscsitarget/new-iscsiservertarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-IscsiServerTarget

## SYNOPSIS
Creates a new iSCSI Target object with the specified name.

## SYNTAX

```
New-IscsiServerTarget [-TargetName] <String> [-InitiatorIds <InitiatorId[]>] [-ClusterGroupName <String>]
 [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-IscsiServerTarget** cmdlet creates a new iSCSI Target object with the specified name.
After creating a new iSCSI Target object, the target can be assigned to an iSCSI initiator, and a virtual disk can be associated with the target.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> New-IscsiServerTarget -Targetname "T1"
```

This example creates a target named T1 on the local server.

### EXAMPLE 2
```
PS C:\> New-IscsiServerTarget -Targetname "T1" -InitiatorId IPAddress:10.10.1.1,IPAddress:10.10.1.2
```

This example creates a target with the name T1 and assigns it to two initiators, with IP addresses 10.10.1.1 and 10.10.1.2.

### EXAMPLE 3
```
PS C:\> New-IscsiServerTarget -Targetname "T1" -ComputerName "fscluster.contoso.com" -ClusterGroupName "Group1"
```

This example creates a target with the name T1 in the cluster group named Group1 on the cluster named fscluster.contoso.com.

## PARAMETERS

### -ClusterGroupName
Specifies the name of the resource group or network within the resource group on which this cmdlet should be run.

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

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer. 

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorIds
Specifies the iSCSI initiator identifiers (IDs) to which the iSCSI target is assigned. 

Use this parameter to filter out the iSCSI Target object that are associated with the specified initiators. 

The format of this parameter is IdType:Value. 
The acceptable values for this parameter are: DNSName, IPAddress, IPv6Address, IQN, or MACAddress.

```yaml
Type: InitiatorId[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the iSCSI target.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.iSCSIServerTarget

## NOTES

## RELATED LINKS

[Get-IscsiServerTarget](./Get-IscsiServerTarget.md)

[Remove-IscsiServerTarget](./Remove-IscsiServerTarget.md)

[Set-IscsiServerTarget](./Set-IscsiServerTarget.md)

