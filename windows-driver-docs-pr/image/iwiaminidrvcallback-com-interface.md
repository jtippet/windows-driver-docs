---
title: IWiaMiniDrvCallBack COM Interface
author: windows-driver-content
description: IWiaMiniDrvCallBack COM Interface
MS-HAID:
- 'WIA\_arch\_e1978c90-692e-4473-84fa-c644d59de8e9.xml'
- 'image.iwiaminidrvcallback\_com\_interface'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a535d718-e34f-4cd0-9137-83d28d0b8e9c
---

# IWiaMiniDrvCallBack COM Interface


## <a href="" id="ddk-iwiaminidrvcallback-com-interface-si"></a>


The [IWiaMiniDrvCallBack Interface](https://msdn.microsoft.com/library/windows/hardware/ff543943) provides one link in a communication chain between a minidriver and an application. Because a minidriver cannot communicate directly with an application, and vice versa, any communication between the two must go through an intermediary: the WIA service. To enable this communication, the application implements the **IWiaDataCallback** interface (described in the Microsoft Windows SDK documentation). This interface includes the **IWiaDataCallback::BandedDataCallback** method, which the WIA service can call. If an application provides this callback routine, the WIA service creates another callback, the [**IWiaMiniDrvCallBack::MiniDrvCallback**](https://msdn.microsoft.com/library/windows/hardware/ff543946) method, which it provides for use by the minidriver.

When the minidriver is ready to send image data from the imaging device or to transfer status messages (the percentage of data transferred, for example), it calls the WIA service's **IWiaMiniDrvCallBack**::**MiniDrvCallback**. The WIA service then passes the data or messages along to the application when it calls the application's callback.

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bimage\image%5D:%20IWiaMiniDrvCallBack%20COM%20Interface%20%20RELEASE:%20%288/17/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


