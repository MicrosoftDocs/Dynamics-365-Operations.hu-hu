---
title: Bizományosi készlet figyelése szállítói együttműködéssel
description: Ez az eljárás bemutatja, hogyan használható a szállítói együttműködés információk megtekintésére az olyan termékek készletszintjével kapcsolatban, amelyeket bizományba helyeztek a vevőnél.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8186b553e8518f3153bfd88b89121d4b0567501b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "329436"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Bizományosi készlet figyelése szállítói együttműködéssel

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

