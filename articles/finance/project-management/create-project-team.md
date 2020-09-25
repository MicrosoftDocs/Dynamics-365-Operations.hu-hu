---
title: Projektcsapat létrehozása
description: Ez a témakör a projektcsapatok létrehozásával és kezelésével kapcsolatban tartalmaz tájékoztatást.
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
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760564"
---
# <a name="create-a-project-team"></a>Projektcsapat létrehozása.

[!include [banner](../includes/banner.md)]

A projektben korábban beállított szerepkörök használatához egy projektmenedzsernek a szerepköröket társítania kell a projekthez. Több szerepkör is hozzárendelhető egy projekthez. A félreértések elkerülésére a rendszer automatikusan felcímkézi e szerepköröket a foglalás során. Ha például a projektmenedzsernek három szoftverfejlesztőre van szüksége, a rendszer automatikusan létrehoz három szoftverfejlesztő szerepkört  **szoftverfejlesztő 1**, **szoftverfejlesztő 2** és **szoftverfejlesztő 3** címkékkel. Ha a szerepkör jellemzőit korábban beállították a szerepkörhöz, ezek szűrőként működnek erőforrás keresése során. A keresést finomíthatja a további szükség szerint további jellemzői lehet adni.

A beállítások megtekintése is testreszabható, hogy jobb áttekintést adjon a rendelkezésre álló erőforrásról. Lehetőség van óránkénti, napi, heti, havi, negyedéves vagy éves elérhetőség megjelenítésére. Lehetőség van megjeleníteni az elérhető és fennmaradó erőforrások kapacitását. Ez a beállítás jól használható időkezelésre tevékenységek idejének vagy erőforrás elérhetőségének becslésekor.

A projektmenedzser szerepkört választhat az oldalon, és ha elérhető szabad erőforrás, amely megfelel a követelménynek, válassza az erőforrás fenntartását a szerepkör betöltéséhez. Ne feledje, hogy az erőforrások fenntartása nem szükséges ezen a ponton a tervezési szakaszban. Amikor létrehoz egy WBS-t, a szerepkörök lecserélhetők a projekt személyzettel ellátott erőforrásaira. Ha a WBS-ben a szerepköröket lecserélték a személyzettel ellátott erőforrásokra, az erőforrás beállítása automatikusan frissíti a projektcsapat listáját és az ütemezést.

[![Projektcsapat listázása, amely tartalmazza a szerepköröket és a tényleges erőforrásokat](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

A projektmenedzser több lehetőséggel rendelkezik egy erőforrás projekthez történő lefoglalásához, például **Fennmaradó kapacitás**, **Teljes kapacitás**, **Kapacitás százaléka** és **Óraszám megadása**. Ezek a foglalási beállítások bármikor visszavonhatók, ha az erőforrás-hozzárendelések módosulnak. A foglalásnak két típusa támogatott:

- **Végleges lefoglalás** – Az erőforrás-fenntartást jóváhagyták és megerősítették, hogy az előjegyzésen dolgozni lehessen a megadott időtartamban.
- **Ideiglenes lefoglalás** – Az erőforrás-fenntartásokat feltételesen állították be, hogy az előjegyzéssel dolgozni lehessen a megadott időtartamban.

Az alábbi eljárás ismerteti, hogyan lehet projektcsapatot létrehozni.

## <a name="create-a-project-team"></a>Projektcsapat létrehozása.

1. Jelöljön ki egy projektet az **Összes projekt** listaoldalon, és válassza a **Szerkesztés** lehetőséget.
2. A **Projektcsapat és ütemezés** lapon a **Záró dátum ütemezése** mezőbe írja be az ütemezés kezdő dátumát, egy hónapot hozzáadva. Például ha az ütemezés kezdő dátuma 2017. június 24. (24/06/2017), írja be **24/07/2017**.
3. Válassza a **Hozzáadás** lehetőséget.
4. A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör** mezőben válassza a **Projektmenedzser** lehetőséget.
5. Válassza a **Szükséges kompetenciák** lehetőséget.
6. A **Jellemző választása** oldalon a Vezető projektmenedzser szerepkörhöz korábban beállított jellemzők alapértelmezés szerint be vannak jelölve. Válassza ki az **OK** lehetőséget.
7. A **Szerepkörök hozzáadása projekthez** oldalon az **Erőforrások száma** mezőbe írja be a következőt: **1**.
8. Az **Erőforrás** mezőben a keresés megjeleníti az összes erőforrást, amely a szükséges kompetenciákkal rendelkezik. Válassza a **Daniel Goldschmidt** nevet, majd válassza a **Létrehozás** lehetőséget.
9. A **Projekt** oldalon válassza a **Hozzáadás** lehetőséget.
10. A **Szerepkör hozzáadása a projekthez** ablakban, a **Szerepkör** mezőben válassza a **Csapattag** lehetőséget. Az **Erőforrások száma** mezőben adja meg a következőt: **5**.
11. Válassza a **Létrehozása** lehetőséget.
12. A **Projektek** oldalon válassza az **Erőforrás teljesítése** lehetőséget.

## <a name="monitor-project-teams"></a>Projektcsoportok figyelése
1. A **Minden projekt** oldalon válassza a **Projektazonosító** hivatkozást az **XYZ Frissítési Fázis 2** projektnél.
2. A **Projektcsapat és ütemezés** gyorslapon győződjön meg róla, hogy a felsorolt projekterőforrások helyesek.
