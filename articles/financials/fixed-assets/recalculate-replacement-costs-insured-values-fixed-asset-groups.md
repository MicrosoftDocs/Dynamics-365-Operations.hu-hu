---
title: Tárgyieszköz-csoportok helyettesítési költségének és biztosított értékének újraszámítása
description: Ez a cikk ismerteti a tárgyi eszközök helyettesítési költségének és biztosított értékének frissítésének folyamatát.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0756287406ad12237632ffbd455dbc6ba15d9915
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563365"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Tárgyieszköz-csoportok helyettesítési költségének és biztosított értékének újraszámítása

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti a tárgyi eszközök helyettesítési költségének és biztosított értékének frissítésének folyamatát.

A felhasználók időnként értesítést kaphatnak arról, hogy egy meghatározott tárgyi eszköz helyettesítési vagy biztosítási költsége megváltozott. Például a felettes küldhet számukra egy üzenetet, hogy az infláció három százalék volt az előző évben, ezért minden tárgyi eszköz helyettesítési költségét meg kell növelni három százalékkal. 

Bár a **Tárgyi eszközök** képernyőn is módosíthatja az egyes tárgyi eszközök helyettesítési költségét és biztosított értékét, a **Helyettesítési költségek és biztosított értékek frissítése** oldalon egyszerre frissítheti ezeket az értékeket egy teljes tárgyieszköz-csoportban. Ez a témakör leírja, hogy hogyan frissítheti tárgyieszköz-csoportok vagy csoportokon belüli egyedi eszközök értékeit.

## <a name="how-values-are-updated"></a> Az értékek frissítése
A tárgyieszköz-csoportok helyettesítési költségének és biztosított értékének újraszámításához először meg kell határoznia egy százalékos kulcsot, amellyel módosítja a meglévő helyettesítési költségeket és biztosított értékeket, majd az időszakos frissítés végrehajtásával ténylegesen újraszámíthatja az értékeket. A százalékos kulcsot a **Tárgyieszköz-csoportok** képernyő **Helyettesítési költség tényezője** és **Biztosított érték tényezője** mezőiben adhatja meg. Bár a **Helyettesítési költségek és biztosított értékek frissítése** oldal használatakor ezeket a tényezőket a tárgyieszköz-csoportra határozza meg, a tárgyieszköz-csoporton belül kijelölheti, hogy mely tárgyi eszközökön kívánja végrehajtani a helyettesítési költség és a biztosított érték újraszámítását. 

Ha a **Helyettesítési költségek és biztosított értékek frissítése** oldallal számítja újra az eszközök helyettesítési költségét és biztosított értékét, akkor a rendszer a következő képleteket alkalmazza:

-   \[(Eszközcsoport helyettesítési költségének tényezője / 100) + 1\] \* Eszköz helyettesítési költsége
-   \[(Eszközcsoport biztosított értékének tényezője / 100) + 1\] \* Eszköz jelenlegi biztosított értéke

> [!NOTE] 
> Ha a **Helyettesítési költségek és biztosított értékek frissítése** oldalt alkalmazza, mind a helyettesítési költséget, mind a biztosított értéket újraszámítja a kiválasztott eszközöknél, azt nem állíthatja be, hogy a program csak az egyiket számítsa újra. Ha az egyik értéket meg szeretné hagyni, miközben a másikat frissíti, adjon meg 0 (nulla) értéket a tényező a **Tárgyieszköz-csoportok** oldalon látható mezőjében. A nulla tényező vagy üres mező esetén a frissítés kihagyja a számítást. Az időszaki frissítés nem érinti a tárgyi eszközök könyv szerinti értékét és nettó könyv szerinti értékét. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a> Frissítendő elemek kiválasztása dátum segítségével
Alapértelmezés szerint a frissítési folyamat azokat a kiválasztott eszközöket frissíti, amelyeket az aktuális napon nem frissítettek, de a korábbi napokon már frissíthetők lehettek volna. Például &lt; az aktuális dátum azt jelenti, „a mai nap előtt”. A **Kijelölés** gombra kattintva módosíthatja a **Helyettesítési költségek és biztosított értékek frissítése** oldal dátumát. A program összeveti a megadott dátumfeltételt az eszköz legutóbbi időszaki frissítésének dátumával (a **Tárgyi eszközök** képernyő **Időszaki érték/költség utolsó frissítése** mezőjével). Minden alkalommal, amikor sikeresen frissíti egy tárgyi eszköz helyettesítési költségét vagy biztosított értékét, a rendszer automatikusan frissíti az aktuális dátummal az **Időszaki érték/költség utolsó frissítése** mező tartalmát. 

Példa 

A Járművek, Irodabútorok és Épületek csoportok helyettesítési értékét a tegnapi napon 5 százalékkal növelte, és most úgy gondolja, hogy ezek az eszközök a pontos értékre vannak frissítve. Ha a mai napon ki szeretné zárni ezeket az eszközöket a tárgyi eszközök frissítéséből, megadhat egy a tegnapi napot megelőző dátumot (&lt; tegnapi nap) az **Időszaki érték/költség utolsó frissítése** mezőben, mivel ekkor a **Járművek**, **Irodabútorok** és **Épületek** csoportok utolsó időszaki frissítése a megadott dátumfeltételen kívül történt meg.

## <a name="cumulative-effect-of-each-update"></a> Az egyes frissítések kumulatív hatása
Minden frissítésnek van kumulatív hatása. Ezért a frissítéseket gondosan meg kell tervezni. Ha például kedden minden eszköz értékét 3 százalékkal növeli, majd az irodabútorok értékét pénteken további négy százalékkal, akkor az irodabútorok értéke összesen 7,12 százalékkal nő.

## <a name="scenario"></a>Eset
Felettese a tárgyi eszközöket érintő következő változásokról értesíti:
-   Minden tárgyi eszköz helyettesítési költsége 3,25 százalékkal növelendő, kivéve a számítógépeket.
-   Minden irodabútor helyettesítési költsége további 1 százalékkal növelendő.
-   Minden számítógép helyettesítési költsége és biztosított értéke 10 százalékkal csökkentendő.

Az alábbi módosításokat hajtja végre:
1.  A **Tárgyieszköz-csoportok** oldalon az **Irodabútorok** és a **Számítógépek** csoport kivételével minden tárgyieszköz-csoportnál 3,25 értéket ír a **Helyettesítési költség tényezője** mezőbe, és 0 értéket a **Biztosított érték tényezője** mezőbe.
2.  Az **Irodabútorok** csoport esetén 4,25 értéket ír a **Helyettesítési költség tényezője** mezőbe és 0 értéket a **Biztosított érték tényezője** mezőbe.
3.  A **Számítógépek** csoport esetén -10 értéket ír a **Helyettesítési költség tényezője** mezőbe és -10 értéket a **Biztosított érték tényezője** mezőbe.
4.  A minden tárgyi eszközre vonatkozó újraszámítás végrehajtásához az **OK** gombra kattint a **Helyettesítési költségek és biztosított értékek frissítése** oldalon.

A következő napon felettese közli, hogy a számítógépek értékei 10 százalék helyett 8 százalékkal csökkentek, ezért korrigálni kell a helyettesítési költségeket és biztosított értékeket. A hibát a következő két módszerrel javíthatja ki:
-   Kézzel módosítja a **Számítógépek** tárgyieszköz-csoport minden tárgyi eszközének **Biztosított érték** és **Helyettesítési költség** mezőit a **Tárgyi eszközök** oldalon. Kiszámítja és kézzel beírja az értékeket, mintha 8 százalékkal csökkentette volna az eredeti összeget. Ehhez a módszerhez nem szükséges a **Helyettesítési költségek és biztosított értékek frissítése** oldal.
-   Beírja a **Számítógépek** csoport helyettesítési költségének, illetve biztosított értékének tényezőjét a **Tárgyieszköz-csoportok** képernyő **Helyettesítési költség tényezője** és **Biztosított érték tényezője** mezőibe. Ez visszaállítja az eszközök értékét az eredeti értékre (amely a 10 százalékos csökkentés előtt volt), majd rögtön ezután alkalmazza arra a 8 százalékos csökkentést. Ezután a **Helyettesítési költségek és biztosított értékek frissítése** oldallal újraszámíthatók az értékek a megadott tényezők alapján.

> [!NOTE]  
> A -10 százalékos tényező alkalmazását nem lehet 10 százalékos tényezővel visszaállítani (és a -10 és -8 százalék különbsége, a 2 százalék sem vezet eredményre), mivel az értékek számítása ekkor nem a kívánt eredményt adja. 





