---
title: Költségvetés-tervezési adatfelosztás
description: Ez a témakör ismerteti Microsoft Dynamics a 365 Pénzügyben elérhető felosztási módokat és azok használhatóját.
author: panolte
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5788f6dc8aa6cddad5c8eaba748827307a4d38a1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901460"
---
# <a name="budget-planning-data-allocation"></a>Költségvetés-tervezési adatfelosztás

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti Microsoft Dynamics a 365 Pénzügyben elérhető felosztási módokat és azok használhatóját.  

A költségvetési tervben számos módon eloszthatja az adatokat a tervezett összegek pontos megjelenítése érdekében.

## <a name="allocation-methods"></a>Felosztási mód
Háromféle felosztási móddal (időszakok közötti felosztás, felosztás dimenziókra és főkönyvi felosztási szabályok használata) hozhat létre sorokat a költségvetésben; ezek az azonos költségvetési tervben lévő sorokra épülnek. Más költségvetési tervekben a költségvetésiterv-sorokat három másik módon (összesítés, felosztás és másolás a költségvetési tervből) hozhatja létre. Mind a hat felosztási mód esetén Ön határozza meg a felosztási célváltozatot. A célváltozat megegyezhet a forrásváltozattal, de el is térhet attól. Ezenkívül megadhatja, hogy az új sorokat a rendszer hozzárendelje a költségvetési tervhez, vagy cserélje az aktuális sorokat.

> [!NOTE] 
> Az aggregációhoz olyan egyedi tervváltozatot kell használni, amely eltér a fölérendelt tervben korábban elvégzett felosztáshoz vagy más módosításokhoz használt tervváltozattól.  

[![Időszakok közötti felosztás módja.](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Időszakok közötti felosztás** – A költségvetési terv sorait a forrásként szolgáló költségvetési tervváltozatból időszaki felosztási kategória segítségével oszthatja fel a célváltozat pénzügyi időszakai között. A forrásösszeget a rendszer több sorhoz is hozzárendeli a célváltozatban az időszaki felosztókategóriában meghatározott százalék és dátumon szerint.         

[![A dimenziókra való felosztás módja.](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Felosztás dimenziókra** – A költségvetési terv sorai a forrásként szolgáló költségvetési tervváltozatból a célváltozat pénzügyi sorai között kerülnek felosztásra a kiválasztott költségvetés-felosztási feltételben meghatározott százalékok és pénzügyi dimenziók alapján.           

![Összesítő diagram.](./media/aggregatechart-300x230.png)
**Összesítés** – A költségvetési terv sorai a szülő költségvetési terv forrásként szolgáló költségvetési tervváltozatából a társított (gyermek) költségvetési terv célváltozatában kerülnek összesítésre. Ezzel a módszerrel a szervezet alsóbb szintjein elkészített költségvetési összegek magasabb szinten is konszolidálhatók.          

[![Felosztási diagram.](./media/distributechart-300x230.png)](./media/distributechart.png)
**Felosztás** – A költségvetési terv sorai a szülő költségvetési terv forrásként szolgáló költségvetési tervváltozatából kerülnek felosztásra a társított (gyermek) költségvetési tervek célváltozatával a társított tervek szervezeti egységeinek pénzügyi dimenziói alapján. Ezzel a módszerrel a szervezet magasabb szintjén elkészített költségvetési összegeket lokalizáltabb ellenőrzésre terjesztheti szét.           

[![Főkönyvi felosztási szabályok.](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Főkönyvi felosztási szabályok használata** – A költségvetési terv sorai a forrásként szolgáló költségvetési tervváltozat soraiból a kiválasztott főkönyvi felosztási szabály alapján, a cél költségvetési tervváltozatba kerülnek felosztásra. 

[![Másolás a költségvetési tervből.](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Másolás a költségvetési tervből** – A Felosztási mód elosztása eljáráshoz hasonlóan a költségvetési terv sorainak létrehozása itt is a célban történik, a kapcsolódó költségvetési terv sorai alapján. Ehhez a módszerhez ugyanakkor a forrás költségvetési tervnek nem muszáj szülőnek lenni, de lehet magasabban a hierarchiában. Ez a felosztási mód akkor hasznos, ha a konszolidált összegeket eredetileg jóval magasabb szinten irányozták elő, és azokat át kell adni a szervezet alacsonyabb szintjeire is részletes ellenőrzésre és kiigazításra a magasabb szintű jóváhagyás előtt.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Felosztási módszerek használata a költségvetési tervben
Ha felosztásokat szeretne végrehajtani a költségvetési terv lapon, válassza ki a felosztani kívánt sorokat, majd kattintson a **Költségvetés felosztása** lehetőségre.

[![Költségvetés felosztása gomb.](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Ezután válasszon egy felosztási módszert. A többi mezőt a rendszer ezután a kiválasztott módszer alapján állítja be. Ezekben a mezőkben található a költségvetési terv adatainak forrása és célja, valamint egy beállítás, amellyel megadott tényezővel szorozhatja meg a forrást a célösszegek létrehozásakor a tömeges kiigazítás megkönnyítése érdekében. Ezenfelül beállíthatja a **Hozzáfűzés tervhez** lehetőséget. A meglévő költségvetésiterv-sorok felülírásához válassza a **Nem**, azok megtartásához az **Igen** lehetőséget, majd adjon hozzá új sorokat a felosztott összegekhez.

## <a name="automating-allocations-during-a-workflow"></a>Felosztások automatizálása munkafolyamat során
Egy hatékony funkciónak köszönhetően automatikusan elvégezheti a felosztások a költségvetés tervezési munkafolyamata részeként. Mikor a költségvetési terv halad a munkafolyamatban, megadott tervezési szakaszok esetén automatizált feladatok kezdeményezhetik a felosztást. 

Az automatikus felosztás beállításához először felosztási ütemezést kell létrehoznia a **Költségvetés-tervezési konfiguráció** oldalon. A felosztási ütemezés meghatározza az automatizált felosztás futtatása során használt felosztási módszert, valamint az egyes felosztási beállításokhoz tartozó értékeket (a leírásokért lásd az előző szakaszt). 

Ezután hozzon létre szakaszfelosztást a **Költségvetés-tervezési konfiguráció** oldalon. A szakaszfelosztás felosztási ütemet rendel hozzá a költségvetés-tervezési munkafolyamathoz és szakaszhoz. 

Végül hozzá kell adni egy automatizált feladatot a költségvetés-tervezési szakaszhoz a kívánt munkafolyamat-szakaszban. A következő példában két költségvetés-tervezési szakaszfelosztás (pirossal jelölve) került a munkafolyamatba.

[![Költségvetés-tervezési szakasz felosztásai.](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
