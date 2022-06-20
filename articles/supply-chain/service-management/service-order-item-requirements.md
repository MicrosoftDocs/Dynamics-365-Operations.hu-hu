---
title: Szervizrendelés cikkszükségletei
description: Ez a témakör a szervizrendelés cikkekkel kapcsolatos követelményeit ismerteti.
author: sorenva
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
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6f12b0dd1facc753bfcde820eea26a4052caf67
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882402"
---
# <a name="service-order-item-requirements"></a>Szervizrendelés cikkszükségletei

[!include [banner](../includes/banner.md)]

Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére. A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége. Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.

Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. Egy cikkszükséglet szervizrendelésben való létrehozásához a szervizrendelésnek projekthez kell kapcsolódnia.

Amikor már létre van hozva cikkszükséglet egy szervizrendeléshez, az megtekinthető az adott szervizrendelés **Projekt** lapjáról, illetve az **Értékesítési rendelés** képernyőn keresztül.

## <a name="view-an-item-requirement-from-a-service-order"></a>Szervizrendelés cikkszükségletének megtekintése

1. Lépjen ide: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.
1. Válassza az **Elküldés** lehetőséget, és válassza a **Cikkszükséglet** elemet a **Cikkszükségletek** képernyő megnyitásához.
1. Válassza a **Projekt** lapot és ellenőrizze a **Szervizrendelés** mezőt a cikkszükséglethez tartozó szervizrendelések megtekintéséhez.

## <a name="delete-service-orders-with-item-requirements"></a>Cikkszükségletekkel rendelkező szervizrendelések törlése

Ha egy szervizrendelésen cikkszükséglet van létrehozva, a szervizrendelést nem tudja törölni. Törölnie kell a cikkszükségletet mielőtt a szervizrendelést törölni tudja.

1. Lépjen ide: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.
1. Válassza az **Elküldés** lehetőséget, és válassza a **Cikkszükséglet** elemet a **Cikkszükségletek** képernyő megnyitásához. A képernyő a szervizrendelésen létrehozott cikkszükségleteket tartalmazza.
1. Válassza ki a törölni kívánt cikkszükségletet, majd válassza a **Törlés** lehetőséget.

– vagy –

1. Lépjen a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.
1. Nyissa meg az azt a szervizrendelést tartalmazó projektet, amelyen a cikkszükséglet létrehozása történik.
1. A **Projektek** képernyőn a jobb oldali ablakban válassza a **Cikkszükségletek** elemet. Megnyílik a **Cikkszükségletek** képernyő, és tartalmazza a kijelölt projekthez társított cikkszükségletek listáját.
1. Válassza ki a törölni kívánt cikkszükségletet, majd válassza a **Törlés** lehetőséget.

## <a name="see-also"></a>Lásd még

[Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]