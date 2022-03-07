---
title: A termelési rendelés állapotának sztornírozása
description: Ez a témakör ismerteti, hogyan lehet sztornírozni a termelési rendelés állapotát.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdParmStatusDecrease, ProdSetupStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0dd17bc48bfb6c78e1baca4faf78d6bc5b3ce426c5f0530174eccd95536a5859
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760418"
---
# <a name="reverse-the-production-order-status"></a>A termelési rendelés állapotának sztornírozása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan lehet sztornírozni a termelési rendelés állapotát. 

Egy termelési rendelés állapotának visszaállításakor a program a rendelést és az útvonalakhoz társított valamennyi műveletet visszaállítja a termelési rendelés életciklusának egy korábbi állapotára. Például egy termelési rendelés állapota **Ütemezett**, és az állapotát visszamódosítja **Létrehozva** állapotra. Ebben az esetben a rendszernek először módosítania kell az állapotot **Becsült** értékre, ez az állapot közvetlenül megelőzi az **Ütemezett** értéket. Az állapotot ekkor a kívánt állapotra módosíthatja, ami **Létrehozva**. **Megjegyzés:** Ha a rendelés elérte a **Készként jelentés** állapotot, még visszaállíthatja egy korábbi állapotra. Azonban újra futtatnia kell a becslést és a műveletek ütemezését, a feladatütemezést vagy mindkét ütemezési típust, hogy frissüljenek a rendelés adatai. Erre a lépésre azért van szükség, mert a hátralévő cikkfelhasználás és az üzemi erőforrások felhasználásának foglalásait is alaphelyzetbe kell állítani. A cikk további része ismerteti, hogy mi történik, ha a következő módosításokkal visszaállítja egy termelési rendelés állapotát:

-   **Becsült** állapotról **Létrehozva** állapotra
-   **Ütemezve** állapotról **Becsült** állapotra
-   **Kiadva** állapotról **Ütemezve** állapotra
-   **Elindítva** állapotról **Kiadva** állapotra

## <a name="from-estimated-to-created"></a>Becsült állapotról Létrehozva állapotra
A termelési rendelés állapotának sztornírozásakor **Becsült** állapotról **Létrehozva** állapotra törlődik a cikkfelhasználás, amely az anyagjegyzékben (AJ) szereplő cikkekhez volt kiszámítva. A termelési sorban készlettranzakciók törlődnek, és a **Fennmaradó állapot** mezője a termelési rendelés anyagjegyzéksoraiban visszaáll **Befejezve** állapotra. Ha a **Származtatott beszerzések** és a **Származtatott termelés** lehetőség be van jelölve, minden alárendelt beszerzési rendelés vagy termelési rendelés törlődik. Ha megbecsülte a termelési rendelés költségeit, vagy manuálisan lefoglalt cikkeket, hogy lehessen őket a termelésben használni, ezek a tranzakciók el lesznek távolítva.

## <a name="from-scheduled-to-estimated"></a>Ütemezve állapotról Becsült állapotra
Ha a termelési rendelés állapotát **Ütemezett** állapotról **Becsült** állapotra állítja vissza, akkor a program törli az ütemezett kezdő és befejező dátumokat és időpontokat. Az ütemezés során készített kapacitásfoglalásokat is törli, mint ahogy a feladatütemezés során készített feladatokat is. Minden adatát, amely rögzítve van a műveletütemezéssel és feladatütemezéssel kapcsolatban a **Termelési rendelés adatai** oldalon, visszaáll alaphelyzetbe.

## <a name="from-released-to-scheduled"></a>Kiadva állapotról Ütemezve állapotra
Ha a termelési rendelés állapotát **Kiadva** állapotról **Ütemezett** állapotra, akkor csak az állapotmezőben lévő érték változik.

## <a name="from-started-to-released"></a>Elindítva állapotról Kiadva állapotra
Ha a termelési rendelés állapotát **Elindítva** állapotról **Kiadva** állapotra állítja vissza, akkor a program az összes készként jelentett cikket visszaállítja. Ha anyag kivételére is sor került, vagy bejövő és kimenő szállítások történtek a termelés során, akkor a program ezeket is visszaállítja. A **Fennmaradó állapot** mező a termelési rendelés anyagjegyzéksoraiban **Befejezve** állapotról **Anyagfelhasználás** állapotra módosul. Ha a regisztrált időt, vagy mennyiségeket jelentett készként a műveletekhez a termelési útvonalon, ezeket a beállításokat a program sztornírozza. A **Fennmaradó állapot** mező a termelési útvonalban **Befejezve** állapotról **Anyagfelhasználás** állapotra módosul. Az összes folyamatban lévőként feladott cikk és folyamatban lévő munka beállításai vissza lesznek állítva. A **Termelési rendelés adatai** oldalon a mezők, amelyek elindított vagy készként jelentett mennyiséget mutatnak, alaphelyzetbe kerülnek. Az ezen tranzakciókhoz tartozó dátumok is alaphelyzetbe kerülnek.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]