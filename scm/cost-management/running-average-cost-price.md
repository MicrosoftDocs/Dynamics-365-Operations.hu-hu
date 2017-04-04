---
title: "Mozgóátlagon alapuló önköltségi ár"
description: "A készlet lezárása folyamat kiadási tranzakciók bevételezési tranzakciók a cikk cikkcsoport modell kiválasztott készletértékelési módszer alapján rendezi. Azonban közel készlet futtatása előtt a rendszer kiszámítja a kiadási tranzakciók könyvelésekor használt általában fut átlagos önköltségi ár."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Mozgóátlagon alapuló önköltségi ár

A készlet lezárása folyamat kiadási tranzakciók bevételezési tranzakciók a cikk cikkcsoport modell kiválasztott készletértékelési módszer alapján rendezi. Azonban közel készlet futtatása előtt a rendszer kiszámítja a kiadási tranzakciók könyvelésekor használt általában fut átlagos önköltségi ár.

A rendszer megbecsüli a futó elem átlagos önköltségi ára a következő képlet segítségével: becsült ár = (tényleges összeg + pénzügyi) ÷ (fizikai mennyiség + pénzügyi mennyiség)

## <a name="using-the-running-average-cost-price"></a>A mozgóátlagon alapuló önköltségi ár alkalmazása
A következő táblázat azt mutatja, amikor a rendszer feladja fut átlagos önköltségi ára a készlettranzakciók, és amikor az önköltségi ár definiált cikk fő rekord helyett használja.

| Feltétel                                               | A rendszer használja a becsült futó átlagos önköltségi ár | A rendszer használja az önköltségi ár a cikk fő definiált |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| Mindkét számláló\* és a nevező\*\* pozitív.  | Igen                                                      | Nincs                                                                |
| A számláló\*, nevező\*\*, vagy mindkettő negatív. | Nincs                                                       | Igen                                                               |
| A nevező\*\* értéke 0 (nulla).                        | Nincs                                                       | Igen                                                               |

\*Számláló = (tényleges összeg + pénzügyi) \*\*nevező (fizikai mennyiség + pénzügyi mennyiség) = **Megjegyzés:** Ha a **tényleges értékkel együtt** beállítás nincs bejelölve a cikkhez, a rendszer a 0 (nulla) használja a fizikai mennyiség és a fizikai mennyiség. Az ezzel a beállítással kapcsolatos további tudnivalókért: [Tényleges értékkel együtt](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>A túlárazás elkerülése
Ritka esetekben a rendszer előtt van elég bevételezési ár alapjául szolgáló árak számos problémát. Az ilyen esetek a mozgóátlagon alapuló önköltségi ár túlbecslésével járhatnak. Vannak azonban olyan lépések, amelyekkel elkerülhető a túlárazási probléma, illetve annak előfordulása esetén enyhíthető a hatása. **Eset** A következő tranzakciók mennek végbe a **tényleges értékkel együtt** beállítás alkalmazása során:

1.  Pénzügyileg a 100 mennyiséget kapja 100,00 USD-nél.
2.  Pénzügyileg a 200-at adja meg, mint mennyiség.
3.  Fizikailag a 101 mennyiséget kapja 202,00 USD-nél.

Amikor megvizsgálja a cikk becsült mozgóátlagon alapuló önköltségi árát, a várt önköltségi ár 1,51 USD. Ehelyett talál egy becsült átlagos USD 102.00, a következő képlet alapján a futó: becsült ár = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 az árképzési erősítés az okozza, hogy 200 elemeket ki a 2 pénzügyileg is, mielőtt bármilyen vonatkozó bevételek van a rendszer kell ár 100 cikkek. Ez a helyzet negatív készletet okoz. A rendszer az egységár a USD 1.00, majd becslést ad, előfordulhat, hogy mikorra várható. Azonban a megfelelő 100 bevételezés megérkezésekor, már 2,00 USD az egységár. **Megjegyzés:** Bár a kiadások negatív készletet eredményeznek, a kiadási ár számításakor pozitív lesz a készlet. Ezért, a cikktörzsben szereplő ár helyett, inkább a mozgóátlagon alapuló önköltségi árat használja a rendszer. Ezen a ponton a rendszer rendelkezik a USD 100.00 érték készlet eltolása. Annak ellenére, hogy az ellenoldal 100 darabból épült fel, azokon a helyeken ahol az egységnyi ellenoldal 1,00 USD volt, most csak egyetlen darab található a készletben. Emiatt a 100,00 USD értékű ellenoldal, ehhez az egy darabhoz van hozzárendelve. Ennek eredménye a becsült önköltségi ár túlbecslése. **Megjegyzés:** Összehasonlításképpen érdemes megfigyelni, hogy a fenti példa 2. és 3. lépésének felcserélése esetén 200 darab kiadása 1,51 USD egységárral történik, egy darab pedig megmarad az 1,51 USD egységáron. Mivel ez a túlárazási helyzet negatív készlet előfordulása esetén állhat elő, a következő helyzetekben nehéz elkerülni:

-   A kiadási árakat az aktuális készlet értéke és mennyisége alapján kell megbecsülni.
-   Az aktuális készlet értékét és mennyiségét korrigálni kell a kiadások és a bevételezések alapján.
-   Az ön üzleti modellje lehetővé teszi az aktuális mennyiségnél több darab kiküldését vagy beárazását.
-   Az önnek benyújtott bármely bevételezési értéket és mennyiséget el kell fogadnia.

Ha az ön üzleti modellje lehetővé teszi a következő gyakorlatokat, azok segíthetik a túlárazást lehetővé tevő negatív mennyiségek elkerülését.

-   Ha bejelöli a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Tényleges negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.
-   Amennyiben *nem* jelöli be a **Tényleges értékkel együtt** lehetőséget egy cikkhez, törölje a jelet a **Pénzügyi negatív készlet** jelölőnégyzetből, a **Cikkmodell csoportok** oldalon.

Érdemes azt is szem előtt tartani, hogy a fizikai készletérték maximális ellenoldali értékét korlátozza a fizikai tranzakciók száma, illetve a fizikai és pénzügyi árak közötti különbség. Feltéve, hogy megtörténik az összes fizikai tranzakció pénzügyi frissítése, a fizikai érték nem emelkedhet extrém szintre. Végül pedig, vegye figyelembe, hogy a túlárazási hatás jelentős mértékben csökken, amikor az összesített ellenérték egy helyett, számos aktuális készleten lévő darab között kerül elosztásra.


