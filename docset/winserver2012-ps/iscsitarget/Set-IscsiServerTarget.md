---
author: Kateyanne
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
manager: dansimp
Module Name: IscsiTarget
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/iscsitarget/set-iscsiservertarget?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-IscsiServerTarget

## SYNOPSIS
Modifies settings for the specified iSCSI target.

## SYNTAX

### TargetName (Default)
```
Set-IscsiServerTarget [-TargetName] <String> [-TargetIqn <Iqn>] [-Description <String>] [-Enable <Boolean>]
 [-EnableChap <Boolean>] [-Chap <PSCredential>] [-EnableReverseChap <Boolean>] [-ReverseChap <PSCredential>]
 [-MaxReceiveDataSegmentLength <Int32>] [-FirstBurstLength <Int32>] [-MaxBurstLength <Int32>]
 [-ReceiveBufferCount <Int32>] [-EnforceIdleTimeoutDetection <Boolean>] [-InitiatorIds <InitiatorId[]>]
 [-PassThru] [-ComputerName <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### InputObject
```
Set-IscsiServerTarget -InputObject <IscsiServerTarget> [-TargetIqn <Iqn>] [-Description <String>]
 [-Enable <Boolean>] [-EnableChap <Boolean>] [-Chap <PSCredential>] [-EnableReverseChap <Boolean>]
 [-ReverseChap <PSCredential>] [-MaxReceiveDataSegmentLength <Int32>] [-FirstBurstLength <Int32>]
 [-MaxBurstLength <Int32>] [-ReceiveBufferCount <Int32>] [-EnforceIdleTimeoutDetection <Boolean>]
 [-InitiatorIds <InitiatorId[]>] [-PassThru] [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-IscsiServerTarget** cmdlet modifies settings for the iSCSi target and returns the corresponding iSCSI Target object if the **PassThru** parameter is specified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-IscsiServerTarget -TargetName Test -InitiatorId @()
```

This example removes all of the initiators that are associated with the target named Test.

### EXAMPLE 2
```
PS C:\>Set-IscsiServerTarget -TargetName "TargetOne" -Description "Target for initiator Appsvr"
```

This example sets the description for a target named TargetOne to Target for initiator Appsvr.

### EXAMPLE 3
```
PS C:\>$password = ConvertTo-SecureString -String "passwordpass" -AsPlainText -Force



PS C:\>$chap = New-Object -ComObject System.Management.Automation.PSCredential("user", $password)



PS C:\>Set-IscsiServerTarget -TargetName "T1" -EnableChap $true -Chap $chap
```

This example enables and sets the forward CHAP on a target named T1 with the credentials user and password.

### EXAMPLE 4
```
PS C:\>Set-IscsiServerTarget -TargetName Test -InitiatorId "IPAddress:10.10.1.10","IPAddress:10.10.1.11"
```

This example assigns more IDs to the same target.

### EXAMPLE 5
```
PS C:\>Set-IscsiServerTarget -TargetName Test -InitiatorId "IQN:*"
```

This example assigns the target to all initiators that attempt to connect to it.
Because no validation is performed the iSCSI target when an initiator makes a connection, be very cautious when using this configuration.
It is most useful when troubleshooting connection issues ─ removing the possibility of Target-Initiator assignment errors.

## PARAMETERS

### -Chap
Specifies the settings for CHAP user name and secret.
This parameter should be used in combination with the **EnableChap** parameter if the Chap is not enabled.

```yaml
Type: PSCredential
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

### -Description
Specifies a description for the iSCSI target.

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

### -Enable
Determines whether the specified iSCSI target is enabled or disabled. 

If this parameter is set to True is specified, then the target is enabled.
If the target is already enabled, no action occurs. 

If this parameter is set to False is specified, then the target is disabled.
If the target is already disabled, no action occurs.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableChap
Sets whether CHAP is enabled for the iSCSI target.

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

### -EnableReverseChap
Sets whether reverse CHAP is enabled for the iSCSI target.

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

### -EnforceIdleTimeoutDetection
Sets whether to enforce idle timeout detection.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FirstBurstLength
Sets the length of the first burst.

```yaml
Type: Int32
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

To assign a LUN or VHD to an iSCSI initiator, an iSCSI target is first created.
After the target is assigned to the initiator, then a LUN is associated with the target. 

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

### -InputObject
Accepts an iSCSI target object from the input pipeline.

```yaml
Type: IscsiServerTarget
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxBurstLength
Specifies the maximum burst length.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxReceiveDataSegmentLength
Specifies the maximum receiver data segment length.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
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

### -ReceiveBufferCount
Specifies the receiver buffer count.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReverseChap
Sets the reverse CHAP user name and secret.
This parameter should be used in combination with the **EnableReverseChap** parameter if the Reverse Chap is not enabled.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetIqn
Specifies the target iSCSI Qualified Name (IQN).

```yaml
Type: Iqn
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
Note: The target name cannot be changed here.
This parameter can be used to filter out the iSCSI Target objects.

```yaml
Type: String
Parameter Sets: TargetName
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

### Microsoft.Iscsi.Target.Commands.IscsiServerTarget

## OUTPUTS

### Microsoft.Iscsi.Target.Commands.IscsiServerTarget

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](https://go.microsoft.com/fwlink/p/?LinkId=113291)

[New-Object](https://go.microsoft.com/fwlink/p/?LinkId=113355)

[Get-IscsiServerTarget](./Get-IscsiServerTarget.md)

[New-IscsiServerTarget](./New-IscsiServerTarget.md)

[Remove-IscsiServerTarget](./Remove-IscsiServerTarget.md)

