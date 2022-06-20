---
title: Hullámcímke-nyomtatás ütemezése hullám közben
description: Ez a témakör leírja, hogyan lehet beállítani és használni a feladatalapú hullámcímke-nyomtatásban használható funkciókat.
author: perlynne
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ac2bc4cce42bada43334b82301d716414cd6d654
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889457"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Hullámcímke-nyomtatás ütemezése hullám közben

[!include [banner](../../includes/banner.md)]

A *Feladatalapú hullámcímke-nyomtatási* funkció a hullámba ásási folyamat részeként a hatékonyság javítása, valamint a rendszer hullámcímkék létrehozása és külön feladatokban való végrehajtása érdekében használható.

A hullámcímke-nyomtatás konfigurálása összetett feladat, a pontos konfiguráción és az alapadatokon alapul. Ez nem jelenti azt, hogy a hullámcímkerekordok generálása sikertelen lesz, és ha így tesz, akkor az egész hullámfeldolgozás visszagörgetésre kerül. A *Feladatalapú hullámcímke-nyomtatási* funkcióval elkerülhető a munka és munkasorok újra létrehozása a hullámcímke helytelen nyomtatása esetén.

A *Feladat alapú hullámcímke-nyomtatási* funkció használata esetén a rendszer először munka- és munkasorokat hoz létre. Ezután létrehozza és kinyomtatja a hullámcímkéket. Végül, ha a hullámcímkék helyesen vannak létrehozva, kiadja a munkát és a hullámot kitárolásra.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>A Feladat alapú hullámcímke-nyomtatási funkció bekapcsolva a funkciókezelésben

Az ebben a cikkben leírt funkciók csak akkor használhatók, ha a rendszerben be van kapcsolva. Használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a következő funkcióknak az alábbi sorrendben történő bekapcsolásához:

1. *Hullámcímke-nyomtatás* – Ez a funkció szükséges a hullámfolyamat metódusának engedélyezéséhez hullámcímke-nyomtatáshoz.
1. *Szervezeti szintű munkazárolás* – Az ütemezett munkalétrehozás kézi és automatikus konfigurálásához egyaránt szükséges ez a funkció. (Az Ellátásilánc-kezelés 10.0.21-es verziója esetén ez a funkció kötelező, ezért alapértelmezés szerint be van kapcsolva, és nem lehet újra kikapcsolni.)
1. *Feladatalapú hullámcímke-nyomtatás* – Ez a funkció szükséges a hullámcímke-nyomtatás külön tranzakció-hatókörre való felosztásához.

## <a name="manually-enable-the-new-wave-step-method"></a>Az új hullámlépés metódus manuális engedélyezése

Először készítse el az új hullámlépés-metódust, majd engedélyezze az aszinkron feladatok párhuzamos feldolgozását.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. A Művelet ablaktáblán válassza ki a **Metódus újragenerálása** elemet. A *waveLabelPrinting* megjelenik a szállítási hullámsablonok során használható hullámfolyamati metódusok listájában.
1. Válassza ki azt a rekordot, amelyben a **Metódus neve** mezőben a *waveLabelPrinting* beállítás van beállítva, majd a műveletpanelen válassza ki a **Feladat** konfigurációt.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Raktár** – A munka-létrehozás feldolgozásának ütemezése során használt raktár kiválasztása. (Ha tesztelési célokra bemutatóadatokat használ, a *24*-es raktárat választhatja ki.)
    - **Kötegelt feladatok maximális száma** – Adja meg a kötegelt feladatok maximális számát. A legtöbb esetben az értéknek *8* és *16* között kell lennie. Ugyanakkor javasoljuk, hogy csak egy kísérlettel keresse meg az optimális beállítást az esetekhez.
    - **Hullámfeldolgozási kötegcsoport** – A kötegelt várólistájának feldolgozásának optimalizálása érdekében válasszon ki egy külön hullámfeldolgozási kötegcsoportot.

Most frissíthet egy meglévő hullámsablont, hogy az a *Hullámcímke-nyomtatási* mhullámfeldolgozási metódust használja. Másik lehetőségként létrehozhat egy új hullámsablont, amely azt használja.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A lista ablaktáblában válassza ki a frissíteni kívánt hullámsablont. (Ha tesztelési célokra bemutatóadatokat használ, a *24 Szállítási alapértelmezés* választhatja ki.)
1. A **Módszerek** Gyorslapon a **Fennmaradó módszerek** oszlopban válassza ki a sort, ahol a **Név** mező a *waveLabelPrinting* értékre van beállítva.
1. Válassza ki a **hozzáadás** (jobbra nyíl gombot), hogy a kiválasztott sort áthelyezze a **Kiválasztott metódusok** oszlopba.
1. A **Hullámlépés kódja** mezőben adja meg a hullámlépés kódját, amely a hullámsablon és egy hullámcímkesablon kapcsolatának adható.

## <a name="set-wave-task-processing-threshold-data"></a>Hullámfeladat-feldolgozási küszöbérték adatainak beállítása

Az első alkalommal, amikor egy hullámfolyamat bármilyen feladatalapú feldolgozással fut, a rendszer létrehozza az alapértelmezett hullámfeladat-feldolgozási küszöbadatokat. Ennek az adatnak a segítségével lehet szabályozni, hogy fusson-e aszinkron módon és feladatalapúan a hullámfeldolgozás, így lehetővé válik a feldolgozás és a hullámcímkék létrehozása párhuzamosan.

Az alapértelmezett adatok kezdetben *1*-es küszöbértéket használnak a munkaazonosítók minimális számára (`MinimumWorkThresholdForLabelPrinting`). Ezért amikor a rendszer egynél több munkaazonosítójú hullámot dolgoz fel, a hullámcímkék feladat alapú feldolgozását fogja használni egy külön tranzakcióban. A tesztkörnyezetben manuálisan is beszúrhatja, vagy frissítheti a `WHSWaveTaskProcessingThresholdParameters` táblázat adatait. Ha éles környezetben módosítja a beállítást, forduljon a Microsoft ügyfélszolgálatához, és kérje a frissítés kérését.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>A hullámfeldolgozási logika változtatása feladatalapú hullámcímke-nyomtatás használata esetén

Ha a hullámcímke-feldolgozás meghaladja a hullámfeladatok feldolgozásának küszöbértékét, a rendszer elindítja a feladat alapú feldolgozást. A hullámsablonnak megfelelő következő hullámfeldolgozásban a hullámcímke-nyomtatás közvetlenül a munka létrehozása után, önálló *ttsbegin*/*ttscommit* tranzakcióban fog futni. Ha a hullámsablonban be van állítva a munka feloldása (zárolás feloldása) automatikus futásra, csak a hullámcímke-nyomtatási folyamat sikeres befejezése után fordul elő.

Ha a hullámcímke létrehozása sikertelen (például a munkamennyiség hullámcímke-mennyiségre történő konvertálása sikertelen, és hibát eredményez), csak a megfelelő tranzakció sikertelen. A korábban létrehozott munka befagyasztva marad. A hibák kijavítása és a hullámcímkék nyomtatása érdekében hajtsa végre a következő lépéseket.

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a releváns hullámot a rácsban.
1. A Műveleti ablaktáblán a **Hullám** lapon a **Nyomtatás** csoportban válassza a **Hullámcímkék** lehetőséget.
1. A címkék nyomtatásához kövesse a képernyőn látható utasításokat.
1. A műveletpanel **Hullám** lapján, a **Hullám** csoportban válassza a **Kiadás** lehetőséget a kiválasztott hullám munkához való manuális kiadáshoz.

## <a name="additional-resources"></a>További erőforrások

- [Hullámcímke nyomtatása](configure-wave-label-printing.md)
- [Munka létrehozásának ütemezése a hullám során](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
