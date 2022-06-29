---
title: Cikkszükséglet létrehozása szervizrendelésekhez
description: Ez a témakör azt ismerteti, hogyan lehet cikkkövetelményeket létrehozni a szervizrendelések számára.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f21cda0abb334432d22cc7e0ccfdab724253d91e
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016949"
---
# <a name="create-item-requirements-for-service-orders"></a>Cikkszükséglet létrehozása szervizrendelésekhez

[!include [banner](../includes/banner.md)]

Létrehozhat egy szervizrendelést a vevőknek nyújtott szolgáltatások kezelésére és nyomon követésére. A szolgáltatási rendelésekhez létrehozhat cikkszükségleteket, ha a szervizrendelésekhez konkrét cikkekre van szüksége. Egy cikkszükséglet azonnali felhasználása történhet közvetlenül a készletből, vagy kezdeményezhető termelési megrendelés az adott cikkre.

Ha cikktranzakció helyett cikkszükségletet használ, közvetlenül a cikk tényleges felhasználása előttre tervezheti a szállítást, beszerzési rendelést hozhat létre, a cikket szerepeltetheti a kereskedelmi megállapodási keretrendszerben, és a cikkszükségletet szerepeltetheti a gyártástervezésben.

Szervizrendelések cikkszükségleteinek feldolgozása projekten keresztül történik. Egy cikkszükséglet szervizrendelésben való létrehozásához szükséges, hogy a szervizrendelés egy kapcsolódó projekthez társuljon. Miután létrehozta a cikkszükségletet egy szervizrendeléshez, a cikkszükséglet megtekintheti a kiválasztott projekthez kapcsolódó **Projektek** képernyőn.

## <a name="create-an-item-requirement-for-a-service-order"></a>Cikkszükséglet létrehozása szervizrendeléshez

1. Ugrás a Szolgáltatáskezelés **szervizrendelések** \> **szervizrendeléséhez** \> **·**
1. Válassza ki azt a szervizrendelést, amelyhez cikkszükségletet szeretne létrehozni.
1. A **Műveleti ablaktábla** **Elküldés lapján** válassza a **Cikkszükséglet** elemet.
1. A **Cikkszükséglet** képernyőn írja be a kívánt cikkre vonatkozó megfelelő adatokat. További információk az adott mezőkről: [Cikkszükséglet (képernyő)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))..

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Cikkszükséglet létrehozása szolgáltatási szerződéshez

1. Menjen a **Szolgáltatáskezelés szolgáltatási** \> **szerződések szolgáltatási** \> **szerződéseibe.**
1. Nyissa meg azt a szolgáltatási szerződést, amelyhez cikkszükségletet szeretne létrehozni.
1. A **Sorok** gyorslapon válassza a **Hozzáadás** lehetőséget egy új sor létrehozásához.
1. Válassza ki a **Cikk** elemet a **Tranzakció típusa** mezőben.
1. A **Cikk beállítása** mezőben válassza ki a **Cikkszükséglet** elemet.
1. A **Cikkszám** mezőben válassza ki a szolgáltatási szerződéshez szükséges cikket.
1. A **Sor adatai** gyorslapon, a **Termékdimenziók** lapon a **Hely** mezőben válassza ki a cikkhez tartozó a készlethelyet.
1. A szolgáltatásiszerződés-sorból szervizrendelés létrehozásához a **Sorok** gyorslapon válassza a **Szervizrendelések létrehozása** elemet, majd a **Szervizrendelések létrehozása** képernyőn adja meg a lényeges adatokat.

## <a name="see-also"></a>Lásd még

[Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
