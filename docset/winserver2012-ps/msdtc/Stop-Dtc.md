---
external help file: MsDTC_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 5EBC9066-0159-4753-88C2-F4E116861997
manager: dansimp
---

# Stop-Dtc

## SYNOPSIS
Stops a DTC instance.

## SYNTAX

```
Stop-Dtc [-CimSession <CimSession[]>] [-DtcName <String>] [-Recursive] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Stop-Dtc** cmdlet stops the Distributed Transaction Coordinator (DTC) instance that the **DtcName** parameter specifies.

## EXAMPLES

### Example 1: Stop a local DTC instance
```
This command uses the Get-Dtc cmdlet to view the status of the local DTC instance. 
PS C:\> Get-Dtc -DtcName "Local"
__GENUS           : 2
__CLASS           : DtcInstance
__SUPERCLASS      :
__DYNASTY         : DtcInstance
__RELPATH         : 
__PROPERTY_COUNT  : 7
__DERIVATION      : {}
__SERVER          : 
__NAMESPACE       : 
__PATH            : 
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Started
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd

This command stops the local DTC instance. The first command shows that the instance is started, and, therefore, it is safe to stop that instance. 
PS C:\> Stop-Dtc -DtcName "Local"

This command uses **Get-Dtc**, again, to confirm that the DTC instance is stopped.
PS C:\> Get-Dtc -DtcName "Local"
__GENUS           : 2
__CLASS           : DtcInstance
__SUPERCLASS      :
__DYNASTY         : DtcInstance
__RELPATH         :
__PROPERTY_COUNT  : 7
__DERIVATION      : {}
__SERVER          : 
__NAMESPACE       :
__PATH            : 
DtcName           : Local
KtrmEndpointCid   : b6628c9f-46ff-404d-a0fa-62657cb828af
OleTxEndpointCid  : f3027ea1-4ee5-45b5-a01c-06f41221111b
Status            : Stopped
UisEndpointCid    : e9385758-8092-4dd7-8b09-587aa427a58e
VirtualServerName : Contoso093
XAEndpointCid     : ced49d85-82a9-49d9-a6ee-8c5b4bd7b5bd
```

This example stops the local DTC instance.
To stop a different instance, specify a different value for the **DtcName** parameter.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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

### -DtcName
Specifies the DTC instance to stop.
If you do not specify this parameter, or if you specify a value of Local, this cmdlet stops the local DTC instance.

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

### -Recursive
Indicates that the cmdlet stops any services that rely on the specified DTC instance, such as Microsoft SQL Server.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Dtc](./Get-Dtc.md)

[Install-Dtc](./Install-Dtc.md)

[Start-Dtc](./Start-Dtc.md)

[Test-Dtc](./Test-Dtc.md)

[Uninstall-Dtc](./Uninstall-Dtc.md)

