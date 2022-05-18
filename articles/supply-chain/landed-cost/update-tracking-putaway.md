---
title: Betárolás frissítéskövetése
description: Ez a témakör azt ismerteti, hogyan lehet beállítani és futtatni a Frissítéskövetést az betárolási időszakos feladathoz.
author: Weijiesa
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f02ba71b4eb32551cebc6cf160f0285eac8ae7ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673970"
---
# <a name="update-tracking-for-put-away"></a>Betárolás frissítéskövetése

[!include [banner](../includes/banner.md)]

A *Frissítéskövetést az betároláshoz* időszakos feladat úgy van kialakítva, hogy éjszakánként ismétlődő kötegként fusson. Azt határozza meg, hogy mely hajóutak fogadtak minden készlettranzakciót, és mely hajóútnak nincs értéke a tényleges záró dátumhoz. Ezután szükség szerint az aktuális dátumra állítja a tényleges záró dátumot.

A *Konténertevékenységek* a hajúút minden *szakaszára* létrejönnek minden egyes *konténerhez*. Ezeket az értékeket a hajóút létrehozásakor kiválasztott sablon határozza meg. Minden konténertevékenység-rekordhoz be lehet állítani értékeket a **Kezdő dátum**, a **Becsült záró dátum** és a **Tényleges záró dátum** mezőkben. Ezek a mezők akkor frissíthetők, ha meg lett erősítve, hogy az utazási szakasz megkezdődött vagy befejeződött.

A visszaigazolt dátumokhoz kapcsolódó adatokat általában egy harmadik fél biztosítja, például egy fuvarozó, mivel ezek a műveletek a Microsoft Dynamics 365 Supply Chain Management alkalmazáson kívül vannak karbantartva. Harmadik féltől származó információra azonban nincs szükség annak nyomon követéséhez, hogy egy utazás szakaszából megérkeztek-e az áruk a raktárba (ezeket az áruk berakodása jelöli). Ebből következően a nyomon követés a Dynamics 365 Supply Chain Management alkalmazásban található információk alapján határozható meg:

A *Frissítéskövetést az betároláshoz* időszakos feladat beállításához és futtatásához kövesse az alábbi lépéseket:

1. Ugorjon a **Partraszállási költség \> Időszakos feladatok \> Frissítéskövetés az betároláshoz** menübe.
1. Állítsa be a következő mezőket a **Paraméterek** szakaszban található **Frissítéskövetés betároláshoz** párbeszédpanelen:

    - **Szakasz** – annak a hajóútszakasznak az egyedi azonosító nevének/számának kiválasztása, amelyhez frissíteni szeretné a követést. A kiválasztott értéknek az hajóútnak a raktárba való megérkezésének kell lennie.
    - **Tevékenység** – Válassza ki azt tevékenységet, ami el lett végezve a kijelölt szakaszban. Ezek az értékek hajóútsablonsoronként vannak hozzárendelve a nyomon követési vezérlőközpontban.

1. Annak korlátozásához, hogy mely rekordok szerepeljenek a frissítéseben, válassza ki a **Szűrő** gombot a **Belefoglalandó rekordok** gyorslapon. Megjelenik egy standard lekérdezési párbeszédpanel, ahol meghatározhatja a kiválasztási feltételeket, a rendezési feltételeket és az illesztéseket. A mezők ugyanúgy működnek, mint a Supply Chain Management más lekérdezéstípusai. Az alábbi mezők írásvédettek, és a lekérdezéshez kapcsolódó értékeket is megmutatja.
1. A **Futtatás a háttérben** gyorslapon adja meg a kívánt köteg- és ütemezési beállításokat, akár csak az Supply Chain Management többi feladattípusához.
1. A beállítások alkalmazáséhoz, valamint a frissítés futtatásához vagy ütemezéséhez kattintson az **OK** gombra.
