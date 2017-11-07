---
title: "Költségvetés-tervezési adatfelosztás"
description: "A cikk ismerteti a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerben elérhető különféle felosztási módszereket és bemutatja azok használatát."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fd7ec30c8253f343b3d41d54c78696cd512b2ef7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="budget-planning-data-allocation"></a>Költségvetés-tervezés – adatok megadása

[!include[banner](../includes/banner.md)]


A cikk ismerteti a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerben elérhető különféle felosztási módszereket és bemutatja azok használatát.  

A költségvetési tervben számos módon eloszthatja az adatokat a tervezett összegek pontos megjelenítése érdekében.

## <a name="allocation-methods"></a>Felosztási mód
Háromféle felosztási móddal (időszakok közötti felosztás, felosztás dimenziókra és főkönyvi felosztási szabályok használata) hozhat létre sorokat a költségvetésben; ezek az azonos költségvetési tervben lévő sorokra épülnek. Más költségvetési tervekben a költségvetésiterv-sorokat három másik módon (összesítés, felosztás és másolás a költségvetési tervből) hozhatja létre. Mind a hat felosztási mód esetén Ön határozza meg a felosztási célváltozatot. A célváltozat megegyezhet a forrásváltozattal, de el is térhet attól. Ezenkívül megadhatja, hogy az új sorokat a rendszer hozzárendelje a költségvetési tervhez, vagy cserélje az aktuális sorokat.

[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Időszakok közötti felosztás** – A költségvetési terv sorait a költségvetési forrás tervváltozatából időszaki felosztókategória segítségével oszthatja fel a célváltozat pénzügyi időszakai között. A forrásösszeget a rendszer több sorhoz is hozzárendeli a célváltozatban az időszaki felosztókategóriában meghatározott százalék és dátumon szerint.         

[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Felosztás dimenziókra** – A költségvetési terv sorai a költségvetési forrás tervváltozatából a célváltozat pénzügyi sorai között kerülnek felosztásra a kiválasztott költségvetés-felosztási feltételben meghatározott százalékok és pénzügyi dimenziók alapján.           

![AggregateChart](./media/aggregatechart-300x230.png)
**Összesítés** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából a társított (gyermek) költségvetési terv célváltozatában kerülnek összesítésre. Ezzel a módszerrel a szervezet alsóbb szintjein elkészített költségvetési összegek magasabb szinten is konszolidálhatók.          

[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Felosztás** – A költségvetési terv sorai a szülő költségvetési terv költségvetési forrás tervváltozatából kerülnek felosztásra a társított (gyermek) költségvetési tervek célváltozatával a társított tervek szervezetének pénzügyi dimenziói alapján. Ezzel a módszerrel a szervezet magasabb szintjén elkészített költségvetési összegeket lokalizáltabb ellenőrzésre terjesztheti szét.           

[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Főkönyvi felosztási szabályok használata** – A költségvetési terv sorai a forrás költségvetési tervváltozat soraiból a kiválasztott főkönyvi felosztásszabály alapján a cél költségvetési tervváltozatba kerülnek felosztásra. 

[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Másolás a költségvetési tervből** – A Felosztási mód elosztása eljáráshoz hasonlóan a költségvetési terv sorainak létrehozása itt is a célban történik a kapcsolódó költségvetési terv sorai alapján. Ehhez a módszerhez ugyanakkor a forrás költségvetési tervnek nem muszáj szülőnek lenni, de lehet magasabban a hierarchiában. Ez a felosztási mód akkor hasznos, ha a konszolidált összegeket eredetileg jóval magasabb szinten irányozták elő, és azokat át kell adni a szervezet alacsonyabb szintjeire is részletes ellenőrzésre és kiigazításra a magasabb szintű jóváhagyás előtt.          

## <a name="using-allocation-methods-in-a-budget-plan"></a>Felosztási módszerek használata a költségvetési tervben
Ha felosztásokat szeretne végrehajtani a költségvetési terv lapon, válassza ki a felosztani kívánt sorokat, majd kattintson a **Költségvetés felosztása** lehetőségre.

[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png) 

Ezután válasszon egy felosztási módszert. A többi mezőt a rendszer ezután a kiválasztott módszer alapján állítja be. Ezekben a mezőkben található a költségvetési terv adatainak forrása és célja, valamint egy beállítás, amellyel megadott tényezővel szorozhatja meg a forrást a célösszegek létrehozásakor a tömeges kiigazítás megkönnyítése érdekében. Ezenfelül beállíthatja a **Hozzáfűzés tervhez** lehetőséget. A meglévő költségvetésiterv-sorok felülírásához válassza a **Nem**, azok megtartásához az **Igen** lehetőséget, majd adjon hozzá új sorokat a felosztott összegekhez.

## <a name="automating-allocations-during-a-workflow"></a>Felosztások automatizálása munkafolyamat során
Egy hatékony funkciónak köszönhetően automatikusan elvégezheti a felosztások a költségvetés tervezési munkafolyamata részeként. Mikor a költségvetési terv halad a munkafolyamatban, megadott tervezési szakaszok esetén automatizált feladatok kezdeményezhetik a felosztást. 

Az automatikus felosztás beállításához először felosztási ütemezést kell létrehoznia a **Költségvetés-tervezési konfiguráció** oldalon. A felosztási ütemezés meghatározza az automatizált felosztás futtatása során használt felosztási módszert, valamint az egyes felosztási beállításokhoz tartozó értékeket (a leírásokért lásd az előző szakaszt). 

Ezután hozzon létre szakaszfelosztást a **Költségvetés-tervezési konfiguráció** oldalon. A szakaszfelosztás felosztási ütemet rendel hozzá a költségvetés-tervezési munkafolyamathoz és szakaszhoz. 

Végül hozzá kell adni egy automatizált feladatot a költségvetés-tervezési szakaszhoz a kívánt munkafolyamat-szakaszban. A következő példában két költségvetés-tervezési szakaszfelosztás (pirossal jelölve) került a munkafolyamatba.

[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)




