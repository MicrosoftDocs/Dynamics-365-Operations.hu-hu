---
title: A Munkalebontási struktúra sablonjaihoz tartozó szerepkörök beállítása
description: Ez a témakör a munkalebontási struktúra sablonjaival kapcsolatos szerepkör-információk beállításával kapcsolatban tartalmaz tájékoztatást.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760566"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>A Munkalebontási struktúra sablonjaihoz tartozó szerepkörök beállítása

[!include [banner](../includes/banner.md)]

A projektvezetők beállíthatnak olyan munkalebontási struktúra (WBS) sablonokat, amelyek felhasználhatók új WBS-projektek létrehozásakor. A projektvezetők létrehozáskor szerepköröket adhatnak a sablonokhoz. Használja a következő eljárást, hogy szerepet rendeljen egy WBS-sablonhoz. 

1. Válassza a **Projektvezetés és könyvelés** > **Beállítás** > **Projektek** > **Munkalebontási struktúra sablonjai** lehetőséget.
2. Válassza a **Részletek** lehetőséget a kiválasztott WBS-sablonnál.
3. Jelöljön ki egy feladatot a listán, majd a **Szerepkör** mezőben válassza ki a feladathoz társítandó szerepkört.

## <a name="work-with-a-wbs"></a>A WBS használata

Létrehozhat egy új WBS-t, vagy másolhat egyet egy meglévő WBS-sablonból. Egy projektvezető egyszerűen kezelheti az erőforrásokat szerepkörök hozzárendelésével új feladatokhoz a WBS rendszerében. Egy erőforrás beszerzését, vagy a feladathoz tartozó megerősített erőforrások azonosítását követően lecserélhetők a szerepkörök. Ez a rugalmasság a következő feladatok végrehajtását teszi lehetővé a projektmenedzsernek:

- Szükséges számú erőforrások azonosítása WBS munkacsomagok számára.
- Projektköltség becslése.
- Előzetes költségvetés megállapítása.
- Tevékenységi időtartam becslése, szerepkörök és erőforrások alapján.
- Projektvezetési tervek fejlesztése, a rendelkezésre álló projektinformációk alapján.

A WBS további lehetőségekkel bővült az erőforrás funkció jobb használhatósága érdekében.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lehetőség</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Erőforrás-hozzárendelések</td>
<td>A hozzárendelt erőforrások, dátumok, óraszámok és feladatokhoz tartozó foglalástípus megtekintése a WBS-en.</td>
</tr>
<tr class="even">
<td>Csapat automatikus előállítása</td>
<td>Tervezett erőforrások automatikus hozzáadása társított feladattal rendelkező szerepkörök használatával. A Finance automatikusan javasol tervezett erőforrásokat, egy szerepkörökön alapuló több kritérium felhasználásával történő döntéshozatal használatával. Miután a szerepkörök és munka (órák) be lettek állítva a WBS-ben található feladatokhoz, és miután a struktúra ki lett adva, válassza a <strong>Csapat automatikus létrehozása</strong> lehetőséget. A tervezett erőforrások szükséges száma hozzáadódik a WBS-hez és a <strong>Projekt és csapat ütemezés</strong> laphoz.</td>
</tr>
<tr class="odd">
<td>Erőforrás (legördülő lista)</td>
<td>Az <strong>Erőforrás-hozzárendelés indítása </strong>lapon kiválaszthatja az erőforrásokat végleges vagy ideiglenes lefoglalásra, a megadott időtartam alapján. Módosíthatja a nézetbeállításokat, hogy megtekintse és beállítsa az erőforrás-tevékenységek időtartamát. Kiválaszthat és társíthat erőforrásokat a munkacsomag szintjén, a következő beállítások használatával:
<ul>
<li><strong>Elfogadás</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások megerősítése.</li>
<li><strong>Mégse</strong> – A feladathoz társított erőforrásban bekövetkezett módosítások érvénytelenítése.</li>
<li><strong>Automatikus hozzárendelés</strong> – egy rendelkezésre álló, személyzettel ellátott, megfelelő szerepkörrel rendelkező erőforrást jelöl ki és rendel hozzá automatikusan a kiválasztott feladathoz.</li>
</ul></td>
</tr>
</tbody>
</table>

1. A **Minden projekt** oldalon válassza az **XYZ frissítési fázis 2** projektet.
2. Válassza a **Terv** > **Tevékenységek** > **Munkalebontási struktúra** lehetőséget.
3. Válassza az **Új** gombot, hogy a WBS-hez adja a következő elsőszintű tevékenységeket:

    - Indítás
    - Tervezés
    - Végrehajtás folyamatban
    - Rendszerfigyelés és ellenőrzés
    - Zárás

4. Állítsa be a dátumokat és a munkát (óra), ahogy az alábbi ábra.

    [![A dátumok és a munka beállítása](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Válassza ki az **Indítás** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki **Vezető Projektmenedzser** lehetőséget.
6. Válassza a **Közzététel** lehetőséget.
7. Ugyanabban a sorban az **Erőforrás** mezőben válassza ki a **Daniel Goldschmidt** lehetőséget, majd az **Elfogadás** elemet.
8. Válassza ki a **Tervezés** tevékenység-sort, majd a **Szerepkör** mezőben válassza ki az **Üzleti elemző** lehetőséget.
9. Válassza a **Közzététel**, majd a **Csapat automatikus előállítása** lehetőséget.
10. A megjelenő párbeszédpanelen válassza az **Igen** gombot.
11. Győződjön meg róla, hogy az **Erőforrás** mezőben az érték **Üzleti elemző 1**.
12. Az **Üzleti elemző 1** erőforráshoz nyissa meg a keresőt és válassza az **Erőforrás-hozzárendelések indítása** lehetőséget. Ezután válassza ki a dolgozót a feladathoz.
13. Válassza az **Ideiglenes hozzárendelés** &gt; **Teljes kapacitás** lehetőséget.

    > [!NOTE] 
    > Nem kap figyelmeztetést, hogy az adott erőforrás most 2, mivel az erőforrások száma 1 marad.

14. A **munkalebontási struktúra** oldalon érvényesítse a WBS erőforrás-hozzárendelését, és válassza a **Mentés** lehetőséget.
