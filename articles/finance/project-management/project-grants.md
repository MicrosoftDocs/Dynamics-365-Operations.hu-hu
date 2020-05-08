---
title: Projekttámogatások
description: Ez a témakör egy támogatás létrehozásának vagy módosításának lépéseit mutatja be.
author: RadhikaRS
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: f4f7d347dab9f02fc474656e2f4cfba8e374480d
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282830"
---
# <a name="project-grants"></a>Projekttámogatások

[!include [banner](../includes/banner.md)]

A támogatás meghatározott célra vagy projektre fordítható pénzadomány. A támogatások felhasználására általában meghatározott korlátozások vonatkoznak. A támogatásokat a Projektvezetés és könyvelés modulban adhatja meg és követheti nyomon, valamint megadhatja azok kapcsolatait a projektekkel és projektszerződésekkel. Például a következő műveleteket is elvégezheti:

- Támogatás társítása a projektekhez és a finanszírozási forrásokhoz a **Projekt** és a **Projekt-szerződéses részletei** oldalakra mutató hivatkozásokkal.
- Megadhatja a támogatásokat, és nyomon követheti az állapotuk változásait.
- Megadhatja és nyomon követheti a költségeket, a kért összegeket és a megítélt összegeket.
- Létrehozhat főtámogatásokat, és résztámogatásokat rendelhet hozzájuk.

Támogatást létrehozhat úgy, hogy egy új rekordban adja meg az összes adatot, vagy úgy is, hogy átmásolja és frissíti egy meglévő támogatás adatait.

## <a name="create-a-new-grant"></a>Új támogatás létrehozása

1. Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.
2. Válassza az **Új** \> **Támogatás** lehetőséget.
3. A támogatás részletei lap **Általános** gyorslapján, a **Támogatás azonosítója** mezőben adjon meg egy alfanumerikus azonosítót a támogatáshoz.
4. Adja meg a támogatás nevét a **Támogatás neve** mezőben.
5. A **Leírás** mezőben adja meg az új támogatás részleteit.

    Az oldal további mezőinek többségét nem kötelező kitölteni, így lehetősége van arra, hogy csak a minimálisan szükségesnek tartott mennyiségű adatot adja meg.

    A következő lista bemutatja a támogatási részletek lap egyes gyorslapján megadott adatokat:

    - **Általános** – Adja meg a támogatás nevét, állapotát, leírását, célját és összegét.
    - **Kapcsolattartási adatok** – Adja meg a támogatást kezelő munkatársakkal és a részleggel kapcsolatos adatokat, valamint annak a vevőnek vagy szervezetnek az adatait, aki vagy amely a támogatás forrása. Azt is jelezheti, hogy a szervezet egy továbbító entitás-e, amely megkapja a támogatást, majd továbbítja azt egy másik címzettnek. Válassza a **Hozzáadás** lehetőséget a támogatást nyújtó szervezet kapcsolattartási adatainak, például a telefonszámának és az e-mail címének megadásához.
    - **Dátumok és határidők** – Adja meg a támogatáshoz és a támogatási pályázathoz kapcsolódó dátumokat. Példák erre a pályázat esedékességi dátuma, a benyújtás dátuma, valamint azt a dátumot, amikor a támogatás jóváhagyása vagy elutasítása megtörténik.
    - **Kapcsolódó projektek és projektszerződések** – Csak akkor adhat meg információt erre a gyorslapra, ha a **Támogatási állapot** mező az **Általános** gyorslapon **Aktív** vagy **Megítélt** értékre van állítva. A kapcsolódó feladat végrehajtásához a következő lehetőségek közül választhat:

        - **Finanszírozási forrás hozzáadása** – Új finanszírozási forrás bevonása a támogatásba. Az adatokat megadhatja azonnal, vagy használhatja az alapértelmezett adatokat, amelyeket később módosíthat.
        - **Projektszerződés hozzáadása** – Projektszerződések-adatok hozzáadása vagy módosítása.
        - **Projekt hozzáadása** – A projekt részletes adatainak hozzáadása vagy módosítása.

    - **Beállítás** – Adja meg a kiegészítő finanszírozások adatait, ha ez az információ szükséges. Számos szervezet, amely támogatásokat nyújt, előírja, hogy a támogatottak a saját pénzükből vagy erőforrásaikból meghatározott összeggel kiegészítsék a támogatás megítélt összegét. A **Helyi projekt vagy nyomkövetési azonosító** mezőben adjon meg egy azonosítót, amely eltér a projekt azonosítójától.

        > [!NOTE]
        > Állítsa az **Altámogató** lehetőséget **Igen** értékre támogatás egy része egy másik szervezetnek lesz odaítélve. Az Egyesült Államok területén odaítélt támogatások esetében meghatározhatja, hogy a támogatást állami megbízás vagy szövetségi megbízás alapján kell odaítélni.

    - **Lehívás részletei** – Adja meg vagy módosítsa a támogatási alapok visszavonhatóságának, számlázhatóságának vagy felhasználhatóságának gyakoriságára vonatkozó információt.

## <a name="create-a-new-grant-from-a-copy"></a>Új támogatás létrehozása másolatból

1. Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.
2. Válassza az **Új** \> **Másolat kiválasztása a támogatásból** lehetőséget.
3. Adjon meg egy alfanumerikus azonosítót és egy nevet az új támogatásnak, és válassza az **OK** lehetőséget.
4. A támogatás részletei lapon tekintse át a másolt támogatás adatait, és végezze el a szükséges módosításokat. Az oldal legtöbb mezője nem kötelező.

## <a name="view-or-modify-grant-details"></a>A támogatás részleteinek megtekintése vagy módosítása

1. Ugorjon a **Projektvezetés és könyvelés** \> **Támogatások** \> **Támogatások** lehetőségre.
2. Válassza ki a módosítani kívánt támogatást.
3. A Műveleti ablaktáblán a **Támogatás** lapján a **Karbantartás** csoportban válassza a **Szerkesztés** lehetőséget.
4. Tekintse át a támogatás adatait, és végezze el a szükséges módosításokat.
