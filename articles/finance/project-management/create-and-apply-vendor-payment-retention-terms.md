---
title: Szállítói kifizetések visszatartási feltételeinek létrehozása és alkalmazása
description: Ez a témakör a szállítói kifizetések visszatartási feltételeinek beállításával és karbantartásával kapcsolatban tartalmaz tájékoztatást.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410229"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Szállítói kifizetések visszatartási feltételeinek létrehozása és alkalmazása

[!include [banner](../includes/banner.md)] 

Szállítói fizetés-visszatartási feltételek beállítása egy projekthez akkor hasznos, ha a szervezet vissza szeretné tartani a szállítónak teljesített kifizetések egy részét. Például, ha a kifizetést egy szállítónál vissza szeretné tartani, addig, amíg a szállított termékek megfelelnek az elvárásainak. A szállítóval való egyeztetés során meghatározhatja a szállító kifizetésének visszatartási feltételeit.

## <a name="create-vendor-payment-retention-terms"></a>Szállító fizetés-visszatartási feltételek létrehozása

Megadhatja a szállítói kifizetés visszatartani kívánt részének százalékos arányát, illetve a korábban visszatartott összegek feloldani kívánt százalékát is. Az érintett összegeket a rendszer automatikusan visszatartja a szállítói számlákon, amíg a szerződés eléri a megadott teljesítési szakaszt. Miután visszatartási feltételeket állított be, azokat bármely projektre alkalmazhatja, amely az adott szállítóhoz tartozik.

A szállítói kifizetések visszatartási feltételeinek beállítását és karbantartását az alábbi lépésekkel végezheti el. 

1. Nyissa meg a **Projektvezetés és könyvelés** > **Visszatartás** > **Szállító fizetés-visszatartási feltételei** lehetőséget.
2. Új szállítói visszatartási feltétel hozzáadásához válassza az **Új** lehetőséget. Az új feltétel **Szabály azonosítója** értéke automatikusan megjelenik a mezőben. 
3. Írjon be egy rövid leírást a **Leírás** mezőbe, majd a **Feltételek** gyorslapon válassza a **Sor hozzáadása** parancsot a következő feltétel-értékek megadásához:

   - **Szállított cikkek százaléka**: Adja meg a feltételhez tartozó teljesítési százalékot. A rendszer automatikusan visszatartja a megfelelő összegeket a szállítói számlákon egészen addig, amíg a projekt teljesítési aránya el nem éri a megadott százalékos értéket. Ha például az 50,00 értéket adja meg, a rendszer a projekt 50%-ának teljesítéséig visszatartja a kifizetendő összegeket.
   - A **Visszatartandó százalék** Adja meg a szállítói számla visszatartandó összegének százalékos arányát. Ha például a 10,00 értéket adja meg a mezőben, a rendszer a szállítói számlán szereplő összeg 10 százalékát tartja vissza addig, amíg a projekt el nem éri a **Szállított cikkek százaléka** mezőben megadott teljesítési százalékot.
   - **Felszabadítandó százalék** Válassza a **Sor hozzáadása** lehetőséget a százalékos érték megadásához, amelyet a korábban visszatartott összegekből fel kíván szabadítani a projekt teljesítésének kiválasztott szintjén.

> [!NOTE]
> Ha több mérföldkő van meghatározva a projekt teljesítésének különböző szintjeihez, minden egyes visszatartási szabályhoz külön szállítói visszatartási feltételsort adjon meg. Minden sorban különböző százalékos értéket adhat meg a visszatartandó és a felszabadítandó százalékokhoz a projekt teljesítésének minden egyes szintjén.

Miután szállítói visszatartási feltételeket állított be, a feltételeket alkalmazhatja egy projektre.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Szállítói visszatartási feltételek alkalmazása egy projektre

1. Nyissa meg a **Projektvezetés és könyvelés** > **Projektek** > **Összes projekt** lehetőséget majd nyissa meg a projektet a projektek listaoldaláról.
2. A **Szállítói megállapodások** gyorslapon válassza a **Sor hozzáadása** lehetőséget.
3. A **Számlakód mezőben** válasszon egyet a következő lehetőségek közül: 

   - **Tábla**: – A szállítói visszatartási feltételek egyetlen szállítóra vonatkoznak.
   - **Csoport**: – A szállítói visszatartási feltételek egy adott szállítócsoport összes szállítójára vonatkoznak.
   - **Mind**: – A szállítói visszatartási szabályok az összes szállítóra vonatkoznak.

4. A **Szállító/szállítói csoport mezőben** jelölje ki azt a szállítót vagy szállítócsoportot, amelyre a szállítói visszatartási feltételek vonatkoznak. Ha az előző lépésben a **Mind** lehetőséget választotta, ez a mező nem érhető el.
5. A **Szállítói visszatartási feltételek** mezőben válasszon egyet az előző eljárás során létrehozott visszatartási feltételek közül.
6. Ha a projektben „saját fizetés beérkezésekor fizetendő” (pay-when-paid; PWP) feltételek is be vannak állítva a szállítóhoz, a **PWP-küszöbérték százaléka** mezőben adja meg a kívánt küszöbérték-százalékot a projekthez.

A szállítói visszatartási szabályok a szállító számára létrehozott beszerzési rendeléseken is megjelennek.
