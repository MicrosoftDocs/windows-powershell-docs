---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: B106E9C9-1BD8-48F7-A820-60D7E77225CA
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-DhcpServerAuditLog

## SYNOPSIS
Sets the Dynamic Host Configuration Protocol (DHCP) server service audit log configuration on the DHCP server service running on the computer.

## SYNTAX

```
Set-DhcpServerAuditLog [[-Enable] <Boolean>] [[-Path] <String>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-DiskCheckInterval <UInt32>] [-MaxMBFileSize <UInt32>] [-MinMBDiskSpace <UInt32>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerAuditLog** cmdlet sets the Dynamic Host Configuration Protocol (DHCP) server service audit log configuration on the DHCP server service running on the computer This cmdlet also sets the enabled state for the DHCP server service audit log.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerAuditLog -ComputerName dhcpserver.contoso.com -Enable True -Path D:\dhcpauditlog\ -MaxMBFileSize 100
```

This example enables the audit log of the DHCP server service and sets the path for the audit log to D:\dhcpauditlog\ directory.
This cmdlet also sets the maximum size for the audit log file to 100 MB.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### -DiskCheckInterval
Specifies the number of audit log events after which the DHCP server service will check the available disk space as specifies in the **MinMBDiskSpace** parameter.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Enable
Specifies the enabled state of the DHCP server service audit log.
The acceptable values for this parameter are: True or False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxMBFileSize
Specifies the maximum size of the audit log, in megabytes (MB).

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinMBDiskSpace
Specifies the minimum required disk space, in megabytes (MB), for audit log storage. 

Before logging a new audit log message, the DHCP server service checks if the minimum disk space specified by this parameter is available on the disk. 

If minimum disk space is not available, then the DHCP server service stops audit logging until the required minimum disk space is available. 

If this parameter value is set to `0` or left as default, then the minimum disk space is set to `20` MB.

```yaml
Type: UInt32
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

### -Path
Specifies the path to the directory where the audit log files are created by the DHCP server service.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerAuditLog
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerAuditLog
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerAuditLog](./Get-DhcpServerAuditLog.md)

