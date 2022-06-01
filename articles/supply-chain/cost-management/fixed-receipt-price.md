---
title: Rögzített bevételezési ár
description: Ez a témakör bemutatja, hogy hogyan konfigurálhatja és használhatja a rögzített bevételezési árakat a Microsoftban Dynamics 365 Supply Chain Management.
author: raprofit
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 8e26d84ddc309249d8bd6e54987ad3ae8eed68f0
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770337"
---
# <a name="fixed-receipt-price"></a>Rögzített bevételezési ár

[!include [banner](../includes/banner.md)]

**A rögzített bevételezési** ár *·* *olyan lehetőség, amely akkor választható egy cikkmodellcsoportnál, ha nem az elszámolóárra vagy a Súlyozott átlag áthelyezésre használt készletmodellt használja*. A beállítás korábbi verzióiban Microsoft Dynamics AX elszámoló költségnek **lett nevezve**. A rendszer átnevezte a **rögzített** bevételezési árat, amikor a Dynamics AX 2012 új elszámolóáras készletmodellt bevezették. Ez a témakör bemutatja, hogy hogyan konfigurálhatja és használhatja a rögzített bevételezési árakat a következőben Dynamics 365 Supply Chain Management:

## <a name="about-fixed-receipt-prices"></a>Rögzített bevételezési árak

Ha egy cikk **cikkmodellcsoport** **lapján** bejel választja a Rögzített bevételezési ár jelölőnégyzetet, akkor a rendszer a bevételezési árat használja a készletbevételezés elszámolóáraként. Ha egy termékhez beállított beszerzési ár és alapértelmezett cikk-önköltségi ár eltér, akkor a program feladja a különbözetet a Rögzített bevételezési ár nyeresége vagy a Rögzített bevételezési ár **veszteség** **·** **számlájára,** **és** ellentételét a Készletfeladási profil oldalon megadott rögzített bevételezési ár ellenszámlája határozza meg.

Mivel a **Rögzített bevételezési ár** beállítás különböző készletmodellekkel (például elsőként be, elsőként ki (FIFO); utolsóként be, elsőként ki (LIFO) és súlyozott átlag), a *Készletzárás és -korrekció* folyamat továbbra is a **Cikkmodellcsoport** lapon kiválasztott készletelv szerint hozza létre a kiegyenlítéseket és helyesbítéseket. A korrekciók azonban csak a készletből való problémákra vannak megszabadva.

Egy termékhez például olyan cikkmodellcsoportot konfigurált, ahol a Készletmodell mező BEÁLLÍTÁSA **FIFO** *, és be van jelölve a* **Rögzített** bevételezési ár beállítás. Ha a készlet beszerzési rendelésen keresztül bevételezésre kerül, akkor a készletérték a cikk alapértelmezett önköltségi árának az értékét adja meg a termékbevételezéskor. Ha a beszerzési rendelés számlázása különbözik, a rendszer a kiadott termék alapértelmezett önköltségi árát a készletszámlára ad fel. A különbözetet a rögzített bevételezési ár eredmény-számlájára könyveli. Később, amikor a terméket értékesíti vagy felhasználja, a rendszer az értékesítési rendelés számlájának feladásakor a cikk mozgóátlagát használja (hacsak nem használ jelölést).

A készletzárási *és helyesbítési* folyamat futtatásakor a rendszer az első kiadással létrehoz egy kiegyenlítést az első bevételezéssel szemben. A bevételezéskor használt bevételezési ár és a kiadáshoz használt mozgóátlag közötti különbséget egy új bizonylatra feladja a program.

## <a name="enable-fixed-receipt-prices"></a>Rögzített bevételezési árak engedélyezése

A cikkek rögzített bevételezési árainak engedélyezéséhez kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Beállítás \> Készlet \> Cikkmodellcsoportok** pontra.
2. Új cikkmodellcsoport létrehozása vagy meglévő modellcsoport kiválasztása.
3. Jelölje be **a Rögzített bevételezési ár jelölőnégyzetet a Költségszámítási módszer &** **Költségfelismerés** gyorsmenüben.

    > [!NOTE]
    > Ha **a** **·** *·* *Készletmodell mező beállítása Elszámolóár vagy Mozgóátlag, nem jelölheti be a Rögzített bevételezési ár jelölőnégyzetet.*

4. Zárja be a lapot.

Miután engedélyezi a Rögzített bevételezési **ár** beállítást, a következő lépések szerint frissítenie kell a készletfeladási profilt.

1. Nyissa meg a **Készletkezelés \> Beállítás \> Feladás \> Feladás** menüt.
1. A Beszerzési **rendelés lap** Kijelölés oszlopában **válassza** a Rögzített **bevételezési ár nyeresége lehetőséget**.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Állítsa be az új sort úgy, hogy az a cikkmodellcsoportra vonatkozjon, amelynél engedélyezte a rögzített bevételezési árképzést, és adja meg azt a fő számlát, amely a beszerzési rendelések rögzített bevételezési árának nyereségét rögzíti. Szükség szerint konfigurálja az egyéb beállításokat.
1. Válassza a Rögzített **bevételezési** ár **vesztesége lehetőséget a Kijelölés oszlopban**. Adjon meg egy új sort, amely ahhoz a cikkmodellcsoporthoz tartozik, amelynél engedélyezte a rögzített bevételezési árképzést, és adja meg azt a fő számlát, amely a beszerzési rendelések rögzített bevételezési árveszteségeit rögzíti. Szükség szerint konfigurálja az egyéb beállításokat.
1. A Kijelölés oszlopban **válassza** a Rögzített **bevételezési ár ellentételét**. Adjon meg egy új sort, amely a rögzített bevételezési árképzésű cikkmodellcsoportra vonatkozik, és adja meg azt a fő számlát, amely a beszerzési rendelések rögzített bevételezési árának ellentételeit rögzíti. Szükség szerint konfigurálja az egyéb beállításokat.
1. A Készlet **lap** Kijelölés oszlopában **válassza** a Rögzített **bevételezési ár nyeresége lehetőséget**. Adjon meg egy új sort, amely a rögzített bevételezési árképzésű cikkmodellcsoportra vonatkozik, és adja meg azt a fő számlát, amely a készlet rögzített bevételezési ár nyereségének rögzítésére használható. Szükség szerint konfigurálja az egyéb beállításokat.
1. Válassza a Rögzített **bevételezési** ár **vesztesége lehetőséget a Kijelölés oszlopban**. Adjon meg egy új sort, amely a rögzített bevételezési árképzésű cikkmodellcsoportra vonatkozik, és adja meg azt a fő számlát, amely a készlet rögzített bevételezési árveszteségeit rögzíti. Szükség szerint konfigurálja az egyéb beállításokat.

> [!NOTE]
> Általában javasolt, hogy **·** **a** rögzített bevételezési ár nyeresége és a Rögzített bevételezési ár veszteség mezői ugyanazt a fő számlát használják a beszerzési rendelésekhez és a készlethez is.

> [!IMPORTANT]
> Ha **módosítja** **·** **a** Kiadott termékek lap Költségek kezelése gyorslapJán található Ár mező értékét, a rendszer nem számítja át automatikusan az aktuális készletet. Kézi megoldásként nyissa **meg** a Zárás és a helyesbítés lapot, és **\>** válassza az Ön által használt beállítási lehetőséget a munkaablakban. Ezután válassza ki a aktuális cikkeket, és módosítsa azokat az aktuális árra. Az elszámolóár készletmodell használatának egyik egyértelmű előnye az, hogy a rendszer automatikusan újraértékelje az aktuális készletet.
