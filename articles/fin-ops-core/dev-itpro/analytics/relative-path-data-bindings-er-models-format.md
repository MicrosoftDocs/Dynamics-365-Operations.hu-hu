---
title: Relatív elérési út használata az ER-modellek és -formátumok adatkötéseiben
description: Az elektronikus jelentéskészítési (ER) eszköz használatakor a felhasználók definiálhatják az elektronikus formátum struktúráját, majd leírhatják, hogy hogyan kell feltölteni ezeket a struktúrákat az alkalmazás adatainak és algoritmusainak használatával.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable , ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2940d99243ac52ee0d56a1c4423c4f0250f42f57
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091772"
---
# <a name="use-a-relative-path-in-data-bindings-of-er-models-and-formats"></a>Relatív elérési út használata az ER-modellek és -formátumok adatkötéseiben

[!include[banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) eszköz használatakor a felhasználók definiálhatják az elektronikus formátum struktúráját, majd leírhatják, hogy hogyan kell feltölteni ezeket a struktúrákat az alkalmazás adatainak és algoritmusainak használatával. További információ: [Elektronikus jelentéskészítési (ER) konfigurációk létrehozása](electronic-reporting-configuration.md). Ha meg szeretné adni a Finance and Operations adatainak a lekéréséhez és az adatok elektronikus dokumentumok előállításához használt adatáramlást, akkor a következőket kell tennie:

- A konfigurált adatforrásokat össze kell kötni a megtervezett tartományalapú adatmodell elemeivel. A modell szerkezete és a kiválasztott adatforrások összetett hierarchikus szerkezet részei lehetnek. Emiatt a végső kötések elég nagyok lehetnek, és számos különböző típusú elemből állhatnak (például kapcsolatok, táblák, módszerek). A kötések nehezebben olvashatóvá válhatnak, és elég bonyolult lehet az áttekintésük és a megértésük (különösen a nem tulajdonosok számára). 
- A formátum-összetevőkkel rendelkező adatmodellelemek kötésével meghatározhatja, hogy milyen adatok kerüljenek az adatmodellből a létrejövő formátum kimenetébe.

Az elektronikus jelentéskészítési leképezések tervezőinek használhatóságát javítja a relatív elérési út funkció megjelentetése. A relatív elérési út ábrázolási beállítása alapértelmezés szerint be van kapcsolva az alkalmazás összes olyan új példányához, amelynél engedélyezve van az elektronikus jelentéskészítési környezet (Microsoft Dynamics 365 Finance 365 for Finance and operations, Microsoft Regulatory Configuration Service). Bevezettük a relatív elérési út paramétert, hogy a felhasználók a teljes elérési utat tudják használni az elektronikus jelentéskészítési kötések megjelenítésével végzett munka során.

[![Felhasználói paraméterek](./media/relative-path-01.png)](./media/relative-path-01.png)

 
Ha be van kapcsolva a relatív elérési út használati paraméter, egyetlen @ karakter helyettesíti a szülő elem elérési útját az aktuális modellelem kötésében. A teljes kötési út rövidebb lesz, így a teljes hozzárendelés egyértelműbbé és könnyebben érthetővé válik. Az esetek többségében az elektronikus jelentéskészítési tervezőben nincs szükség további görgetésre az adatmodell összes kötésének a megtekintéséhez.

[![Modell-hozzárendelési tervező](./media/relative-path-02.png)](./media/relative-path-02.png)
 
Az új elektronikus jelentéskészítési kifejezések tervezésének megkezdésekor csak egy karaktert kell beírnia, hogy kötést határozzon meg a szülő elem mezőjéhez.

[![Képletszerkesztő](./media/relative-path-03.png)](./media/relative-path-03.png)
 
Ha abszolút elérési út használatával szeretné módosítani a szülő modellelemhez tartozó adatforrást, akkor manuálisan újra kell kötnie az új adatforráshoz ezt a modellelemet és a beágyazott elemeket. Ha a relatív elérési út használata be van kapcsolva, és új adatforrást szeretne kötni egy szülő elemhez, akkor lehetősége van arra, hogy a szülő elem minden beágyazott elemét egy kattintással automatikusan újrakösse.

[![Elérési út meglévő üzenetének cseréje](./media/relative-path-04.png)](./media/relative-path-04.png)
 
Ha megerősíti a beágyazott elemek újrakötését, akkor az új szülő elem a meglévő szülő elemet tartalmazó beágyazott elemek elérési útjába kerül.
Ez a funkció nincs hatással az elektronikus jelentéskészítési keretrendszer visszamenőleges kompatibilitására. A korábban tervezett elektronikus jelentéskészítési konfigurációk együttműködnek az új funkcióval; nincs szükség frissítésre vagy konverzióra.

> [!NOTE]
> A program minden olyan változtatást megfelelően ment a konfigurációs változások közé, amely a modell-hozzárendelések beágyazott elemeihez tartozó kötések tömeges módosításából következik (a módosítások nyomon követése). Ez lehetővé teszi, hogy a vevők a modell-hozzárendelések származtatott változatát a változat bármilyen olyan új alapverziójára módosíthassák, amelyet az új funkcióval módosítottak.
