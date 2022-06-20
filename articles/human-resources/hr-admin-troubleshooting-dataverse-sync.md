---
title: Dataverse szinkronizáció visszaállítása
description: Ez a témakör olyan rekordok hibakeresését mutatja be, amelyek nem szinkronizálódnak megfelelően a Microsoft Dynamics 365 Human Resources és az Emberi erőforrások kezelése (HCM) általános megoldás között Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: b69390538fa28e18e5abf8aef548d67b6afb8496
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895989"
---
# <a name="reset-dataverse-synchronization"></a>Dataverse szinkronizáció visszaállítása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Probléma

A rekordok nem szinkronizálódnak a Microsoft Dynamics 365 Human Resources és az Emberi erőforrások kezelése (HCM) általános megoldásában található entitások között a következőben a Microsoft Dataverse-ben. A szinkronizálással kapcsolatos további tudnivalókat a [Dataverse Integráció konfigurálása](hr-admin-integration-common-data-service.md) oldalon találhatja meg. A megfelelő szinkronizálás akkor lehet sikertelen ha a **Dataverse-integráció újrapróbálkozás** vagy a **Dataverse integráció kihagyott kérelem szinkronizálása** kötegelt feladatok **Végrehajtás** állapotban maradnak.

## <a name="resolution"></a>Megoldás

Ha a **Dataverse-integráció újrapróbálkozás** vagy a **Dataverse integráció kihagyott kérelem szinkronizálása** kötegelt feladatok **Végrehajtás** vagy **Megszakítás** állapotban maradnak. Ez a kötegelt feladatnak a [Megakadt kötegelt feladatok visszaállítása](hr-admin-troubleshooting-batch-execution.md) útmutatója alapján állítható be a kötegelt feladat megszakításával. A kötegelt feladat megszakítása után visszaállíthatja a kötegelt feldolgozást **Várakozás** állapotra. A kötegelt feladat ezt követően a következő ütemezett futási idő során fog lefutni.

1. Ha még nem tette meg, engedélyezze a **Továbbfejlesztett kötegek megszakítása** funkciót a **Funkciókezelésben**.
   1. Menjen a **Funkciókezelés** oldalra (**Rendszerfelügyeleti** > **Összegzés** > **Funkciókezelés**).
   2. Válassza ki az **Összes** fület.
   3. Jelölje ki a **Funkció neve** oszlopot és szűrjön a **Továbbfejlesztett kötegek megszakítása** szerint.
   4. Válassza be az **Engedélyezés** műveletet, ha még nincs engedélyezve.

2. A Dataverse-integráció kikapcsolása.
   1. Ugrás az **Microsoft Dataverse-integráció** lapra (A **Rendszerfelügyelet** alatt válassza a **Hivatkozások** > **Integrációk** > **Dataverse-konfiguráció** menüpontot).
   2. Állítsa a **Dataverse-integráció engedélyezése** beállítást **Nem** lehetőségre.

3. Válassza a **Dataverse-integráció-újrapróbálkozás** kötegelt feladatot.
   1. Nyissa meg a **Kötegelt feladatok** oldalt (A **Rendszerfelügyelet** alatt ugorjon a **Hivatkozások** > **Kötegelt feladatok** > **Kötegelt feladatok** menüpontra).
   2. A **Feladatleírás** oszlopot szűrje **Integráció** szerint.
   3. Válassza a **Dataverse-integráció-újrapróbálkozás** kötegelt feladatot.
   4. Válassza a művelet menüszalagon a **Kötegelt feladat**, **Megszakítás kényszerítése** lehetőséget, majd a megerősítéshez válassza az **Igen** lehetőséget.

   > [!NOTE]
   > Az integráció első engedélyezésének időpontjától függően előfordulhat, hogy a kötegelt feladat leírása **Common Data Service integráció újrapróbálkozás**. Válassza ki ezt a kötegelt feladatot, ha fel van sorolva, a **Dataverse integráció újrapróbálkozás** kötegelt feladat helyett.

4. Az összes Dataverse-integráció kötegelt feladat törlése.
   1. Jelölje ki a **Kötegelt feladatok** lapon a **Kihagyott Dataverse integráció szinkronizálási kérés**, **Dataverse integráció-újrapróbálkozás** és **Dataverse integrációs kezdeti szinkronizálás** kötegelt feladatokat.
   2. A művelet menüszalagján válassza az **Állapot módosítása** műveletet. 
   3. Válassza ki a **Visszatartás** lehetőséget, majd kattintson az **OK** gombra.
   4. Válassza a **Törlés** műveletet a művelet menüszalagján, majd válassza az **Igen** lehetőséget a művelet megerősítéséhez.

5. A Dataverse integrációs kötegelt feladatok bekapcsolása.
   1. Ugorjon a **Microsoft Dataverse-integráció** lapra (**Rendszerfelügyelet** > **Hivatkozások** > **Integrációk** > **Dataverse-konfiguráció**).
   2. Állítsa a **Dataverse-integráció engedélyezése** beállítást **Igen** lehetőségre.

6. Menjen a **Kötegelt feladatok** lapra, és erősítse meg, hogy a **Dataverse-integráció újrapróbálkozás** és a **Dataverse-integráció kihagyott szinkronizálás kérése** kötegelt feladatok létrejöttek.

A kötegelt feladatok újbóli létrehozása után megfigyelheti a **Dataverse integráció újrapróbálása** kötegelt feladatot annak ellenőrzésére, hogy mennyi ideig tart a feladat végrehajtása. Ezután ellenőrizheti, hogy a rekordok megfelelően szinkronizálva vannak-e a HCM Common megoldással a Microsoft Dataverse-ben.

## <a name="see-also"></a>Lásd még

[A Dataverse-integráció konfigurálása](hr-admin-integration-common-data-service.md)<br>
[Beragadt kötegelt feladatok alaphelyzetbe állítása](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
