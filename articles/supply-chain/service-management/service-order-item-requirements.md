---
title: Szervizrendelési cikkre vonatkozó követelmények
description: A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bbd15ca83ab116286a3d681887f076896653c76
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810582"
---
# <a name="service-order-item-requirements"></a>Szervizrendelési cikkre vonatkozó követelmények   

[!include [banner](../includes/banner.md)]


Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére. A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége. Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.

Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. Egy cikkszükséglet szervizrendelésben való létrehozásához a szervizrendelésnek projekthez kell kapcsolódnia.

Amikor már létre van hozva cikkszükséglet egy szervizrendeléshez, az megtekinthető az adott szervizrendelés **Projekt** lapjáról, illetve az **Értékesítési rendelés** képernyőn keresztül.

## <a name="view-an-item-requirement-from-a-service-order"></a>Szervizrendelés cikkszükségletének megtekintése

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Kattintson az **Elküldés**, és kattintson a **Cikkszükséglet** elemre a **Cikkszükségletek** képernyő megnyitásához.

3.  Kattintson a **Projekt** lapra és ellenőrizze a **Szervizrendelés** mezőt a cikkszükséglethez tartozó szervizrendelések megtekintéséhez.

## <a name="delete-service-orders-with-item-requirements"></a>Cikkszükségletekkel rendelkező szervizrendelések törlése

Ha egy szervizrendelésen cikkszükséglet van létrehozva, a szervizrendelést nem tudja törölni. Törölnie kell a cikkszükségletet mielőtt a szervizrendelést törölni tudja.

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Kattintson az **Elküldés**, és kattintson a **Cikkszükséglet** elemre a **Cikkszükségletek** képernyő megnyitásához. A képernyő a szervizrendelésen létrehozott cikkszükségleteket tartalmazza.

3.  Válassza ki a törölni kívánt cikkszükségletet, majd kattintson a **Törlés** lehetőségre.

– vagy –

1.  Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.

2.  Nyissa meg az azt a szervizrendelést tartalmazó projektet, amelyen a cikkszükséglet létrehozása történik.

3.  A **Projektek** képernyőn a jobb oldali ablakban kattintson a **Cikkszükségletek** elemre. Megnyílik a **Cikkszükségletek** képernyő, és tartalmazza a kijelölt projekthez társított cikkszükségletek listáját.

4.  Válassza ki a törölni kívánt cikkszükségletet, majd kattintson a **Törlés** lehetőségre.

## <a name="see-also"></a>Lásd még

[Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]