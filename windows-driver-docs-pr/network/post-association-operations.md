---
title: Post-Association Operations
description: Post-Association Operations
ms.assetid: e4c7ea7a-53ad-41b2-bf3f-03c770e58043
keywords: ["IHV Extensions DLL WDK Native 802.11 , post-association operations", "post-association operations WDK Native 802.11 IHV Extensions DLL", "Native 802.11 IHV Extensions DLL WDK , post-association operations"]
---

# Post-Association Operations


**Important**  The [Native 802.11 Wireless LAN](native-802-11-wireless-lan4.md) interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see [WLAN Universal Windows driver model](wifi-universal-driver-model.md).

 

When the wireless LAN (WLAN) adapter successfully completes an association operation with an access point (AP), the operating system creates a data port for the association. The operating system then initiates a post-association operation on the data port by calling the [*Dot11ExtIhvPerformPostAssociate*](https://msdn.microsoft.com/library/windows/hardware/ff547492) function.

**Note**  For Windows Vista, the IHV Extensions DLL supports only infrastructure basic service set (BSS) networks.

 

When performing the post-association operation, the IHV Extensions DLL can do the following:

-   Allocate any resources needed for the new data port.

-   Perform proprietary security processing for the data port, including sending and receiving packets for the authentication algorithm configured during the pre-association operation. For more information about this operation, see [Pre-Association Operations](pre-association-operations.md).

-   Derive cipher keys and download them to the WLAN adapter.

When the WLAN adapter completes a disassociation operation with the AP, the operating system terminates the post-association operation on the data port by calling the [*Dot11ExtIhvStopPostAssociate*](https://msdn.microsoft.com/library/windows/hardware/ff547521) function. Following this call, the operating system deletes the data port for the association.

The following topics describe what the IHV Extensions DLL must do to perform or stop a post-association operation.

[Performing a Post-Association Operation](performing-a-post-association-operation.md)

[Stopping a Post-Association Operation](stopping-a-post-association-operation.md)

[Interface to the Native 802.11 802.1X Module](interface-to-the-native-802-11-802-1x-module.md)

For more information about the association operation, see [Association Operations](association-operations.md).

For more information about the disassociation operation, see [Disassociation Operations](disassociation-operations.md).

For more information about the procedures involved in port management, see [Port-Based Network Access](port-based-network-access.md).

 

 





