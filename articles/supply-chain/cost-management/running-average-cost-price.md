---
title: "Mozgóátlagon alapuló önköltségi ár"
description: "A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aeb23f78d9bec93cf92214470e9ace3cd88b92c3
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="running-average-cost-price"></a>Mozgóátlagon alapuló önköltségi ár

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. Azonban, a készletzárás futtatása előtt a rendszer kiszámít egy mozgóátlagon alapuló önköltségi árat, amely általában a bevételi tranzakciók feladásakor kerül felhasználásra.

A rendszer a cikkek mozgóátlagon alapuló önköltségi árát a következő képlet alkalmazásával becsüli meg: 

becsült ár = (fizikai összeg + pénzügyi összeg) ÷ (fizikai mennyiség + pénzügyi mennyiség)

## <a name="using-the-running-average-cost-price"></a>A mozgóátlagon alapuló önköltségi ár alkalmazása
A következő táblázat két eshetőséget mutat be. Az első során a rendszer a mozgóátlagon alapuló önköltségi ár alapján ad fel készlettranzakciókat, a második esetben pedig a cikk törzsadataiban meghatározott önköltségi ára alapján teszi meg ugyan ezt.

| Feltétel                                               | A rendszer a becsült mozgóátlagon alapuló önköltségi árat alkalmazza. | A rendszer a cikk törzsadataiban meghatározott önköltségi árat alkalmazza. |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| A számláló\* és a nevező\*\* is pozitív.  | Igen                                                      | Nincs                                                                |
| A számláló\*, a nevező\*\* vagy mind a kettő negatív. | Nincs                                                       | Igen                                                               |
| Ha a nevező\*\* 0 (nulla).                        | Nincs                                                       | Igen                                                               |

\* számláló = (fizikai összeg + pénzügyi összeg) \*\* nevező = (fizikai mennyiség + pénzügyi mennyiség) 

**Megjegyzés:** Ha a **Tényleges értékkel együtt** lehetőség nincs bejelölve egy cikkhez, akkor a rendszer 0 (nulla) értéket használ a fizikai összeghez és a tényleges mennyiséghez egyaránt. Az ezzel a beállítással kapcsolatos további tudnivalókért: [Tényleges értékkel együtt](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>A túlárazás elkerülése
Nagyritkán a rendszer több kiadást áraz be azelőtt, hogy elégséges számú bevételezéssel rendelkezne az ár megállapításához. Az ilyen esetek a mozgóátlagon alapuló önköltségi ár túlbecslésével járhatnak. Vannak azonban olyan lépések, amelyekkel elkerülhető a túlárazási probléma, illetve annak előfordulása esetén enyhíthető a hatása. **Eset** A következő tranzakciók mennek végbe a **tényleges értékkel együtt** beállítás alkalmazása során:

1.  Pénzügyileg a 100 mennyiséget kapja 100,00 USD-nél.
2.  Pénzügyileg a 200-at adja meg, mint mennyiség.
3.  Fizikailag a 101 mennyiséget kapja 202,00 USD-nél.

Amikor megvizsgálja a cikk becsült mozgóátlagon alapuló önköltségi árát, a várt önköltségi ár 1,51 USD. Ehelyett az ön által talált mozgóátlagon alapuló önköltségi ár 102,00 USD, amely a következő receptúra alapján került kiszámításra: Becsült ár = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 A túlárazás oka az, hogy a 200 darab pénzügyileg megadott cikkből a második lépésben a rendszernek 100 cikket bekellett áraznia, mielőtt bármilyen megfelelő bevételezéssel rendelkezne. Ez a helyzet negatív készletet okoz. Ezután a rendszer várhatóan 1,00 USD-t becsül egységárként. Azonban a megfelelő 100 bevételezés megérkezésekor, már 2,00 USD az egységár. 

**Megjegyzés:** Bár a kiadások negatív készletet eredményeznek, a kiadási ár számításakor pozitív lesz a készlet. Ezért, a cikktörzsben szereplő ár helyett, inkább a mozgóátlagon alapuló önköltségi árat használja a rendszer. Ekkor a rendszerben a készlet ellenoldali értéke 100,00 USD. Annak ellenére, hogy az ellenoldal 100 darabból épült fel, azokon a helyeken ahol az egységnyi ellenoldal 1,00 USD volt, most csak egyetlen darab található a készletben. Emiatt a 100,00 USD értékű ellenoldal, ehhez az egy darabhoz van hozzárendelve. Ennek eredménye a becsült önköltségi ár túlbecslése. 

**Megjegyzés:** Összehasonlításképpen érdemes megfigyelni, hogy a fenti példa 2. és 3. lépésének felcserélése esetén 200 darab kiadása 1,51 USD egységárral történik, egy darab pedig megmarad az 1,51 USD egységáron. Mivel ez a túlárazási helyzet negatív készlet előfordulása esetén állhat elő, a következő helyzetekben nehéz elkerülni:

-   A kiadási árakat az aktuális készlet értéke és mennyisége alapján kell megbecsülni.
-   Az aktuális készlet értékét és mennyiségét korrigálni kell a kiadások és a bevételezések alapján.
-   Az ön üzleti modellje lehetővé teszi az aktuális mennyiségnél több darab kiküldését vagy beárazását.
-   Az önnek benyújtott bármely bevételezési értéket és mennyiséget el kell fogadnia.

Ha az ön üzleti modellje lehetővé teszi a következő gyakorlatokat, azok segíthetik a túlárazást lehetővé tevő negatív mennyiségek elkerülését.

-   Ha bejelöli a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Tényleges negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.
-   Amennyiben *nem* jelöli be a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Pénzügyi negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.

Érdemes azt is szem előtt tartani, hogy a fizikai készletérték maximális ellenoldali értékét korlátozza a fizikai tranzakciók száma, illetve a fizikai és pénzügyi árak közötti különbség. Feltéve, hogy megtörténik az összes fizikai tranzakció pénzügyi frissítése, a fizikai érték nem emelkedhet extrém szintre. Végül pedig, vegye figyelembe, hogy a túlárazási hatás jelentős mértékben csökken, amikor az összesített ellenérték egy helyett, számos aktuális készleten lévő darab között kerül elosztásra.




