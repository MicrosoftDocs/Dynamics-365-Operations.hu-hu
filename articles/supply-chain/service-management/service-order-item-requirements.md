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
ms.openlocfilehash: 376cda6bbe1800611e6f24c347b9035469a30a14
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015172"
---
# <a name="service-order-item-requirements"></a>Szervizrendelés cikkszükségletei

[!include [banner](../includes/banner.md)]

Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére. A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége. Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.

Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. Egy cikkszükséglet szervizrendelésben való létrehozásához a szervizrendelésnek projekthez kell kapcsolódnia.

Amikor már létre van hozva cikkszükséglet egy szervizrendeléshez, az megtekinthető az adott szervizrendelés **Projekt** lapjáról, illetve az **Értékesítési rendelés** képernyőn keresztül.

## <a name="view-an-item-requirement-from-a-service-order"></a>Szervizrendelés cikkszükségletének megtekintése

1. Ugrás a Szolgáltatáskezelés **szervizrendelések** \> **szervizrendeléséhez** \> **·**
1. Válassza az **Elküldés** lehetőséget, és válassza a **Cikkszükséglet** elemet a **Cikkszükségletek** képernyő megnyitásához.
1. Válassza a **Projekt** lapot és ellenőrizze a **Szervizrendelés** mezőt a cikkszükséglethez tartozó szervizrendelések megtekintéséhez.

## <a name="delete-service-orders-with-item-requirements"></a>Cikkszükségletekkel rendelkező szervizrendelések törlése

Ha egy szervizrendelésen cikkszükséglet van létrehozva, a szervizrendelést nem tudja törölni. Törölnie kell a cikkszükségletet mielőtt a szervizrendelést törölni tudja.

1. Ugrás a Szolgáltatáskezelés **szervizrendelések** \> **szervizrendeléséhez** \> **·**
1. Válassza az **Elküldés** lehetőséget, és válassza a **Cikkszükséglet** elemet a **Cikkszükségletek** képernyő megnyitásához. A képernyő a szervizrendelésen létrehozott cikkszükségleteket tartalmazza.
1. Válassza ki a törölni kívánt cikkszükségletet, majd válassza a **Törlés** lehetőséget.

– vagy –

1. Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.
1. Nyissa meg az azt a szervizrendelést tartalmazó projektet, amelyen a cikkszükséglet létrehozása történik.
1. A **Projektek** képernyőn a jobb oldali ablakban válassza a **Cikkszükségletek** elemet. Megnyílik a **Cikkszükségletek** képernyő, és tartalmazza a kijelölt projekthez társított cikkszükségletek listáját.
1. Válassza ki a törölni kívánt cikkszükségletet, majd válassza a **Törlés** lehetőséget.

## <a name="see-also"></a>Lásd még

[Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]