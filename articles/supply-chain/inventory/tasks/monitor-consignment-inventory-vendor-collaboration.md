---
title: Bizományosi készlet figyelése szállítói együttműködéssel
description: Ez az eljárás bemutatja, hogyan használható a szállítói együttműködés információk megtekintésére az olyan termékek készletszintjével kapcsolatban, amelyeket bizományba helyeztek a vevőnél.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0d194728805cd1eee741069538352b497867981
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571833"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Bizományosi készlet figyelése szállítói együttműködéssel

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan használható a szállítói együttműködés információk megtekintésére az olyan termékek készletszintjével kapcsolatban, amelyeket bizományba helyeztek a vevőnél. A készlet fogyasztása is megfigyelhető, amikor a vevő átveszi a készlet tulajdonjogát. Az USMF bemutatócég adataiban használhatja ezt az eljárást. Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="view-consumed-inventory"></a>Felhasznált készlet megjelenítése
1. Ugrás a Szállítói együttműködés > Bizományosi készlet > Bizományosi készletből kapott termékek elemre.
    * A lista azokat a termékbevételezési sorokat tartalmazza, amelyek akkor jöttek létre, amikor a bizományosi készlet tulajdonjoga átszállt a szállítóról a vevőre. Előfordulhat, hogy jobbra kell görgetnie a mennyiségek és az egyéb információk megtekintéséhez. A listában található információ számlák létrehozására használható a vevő számára. Az adatok a Microsoft Excel programba is exportálhatók.   
2. Kattintson a Beszerzési rendelés megtekintése elemre.
3. Bontsa ki a Soradatok szakaszt.
    * A sor Bizományosként van megjelölve, és a fejléc szakasz azt mutatja, hogy a beszerzési rendelés állapota Beérkezett.  
4. Zárja be a lapot.

## <a name="view-on-hand-inventory"></a>Megtekinti az aktuális készletet
1. Ugrás a Szállítói együttműködés > Bizományosi készlet > Aktuális bizományosi készlet elemre.
    * Az aktuális készlet lap a vevő raktárában levő, az ön tulajdonában álló készletet mutatja. További dimenziók, például a hely és a raktár, a Dimenziók megjelenítése fülre kattintva jeleníthetők meg.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]