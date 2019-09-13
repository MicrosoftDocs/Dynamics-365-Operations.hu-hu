---
title: Költség- és dátumellenőrzés
description: Ez a cikk az Eszközkezelés költség és dátum kontroll funkcióját ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918395"
---
# <a name="cost-and-date-control"></a>Költség- és dátumellenőrzés

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az eszközkezelésben kiszámíthatja a költségeket, és így áttekintést kaphat a tényleges költségekről a költségvetésben meghatározott költségekkel szemben az eszközökön, munkavégzési helyszínekn vagy munkarendeléseken. A tényleges költségek a feladott tranzakciókon alapulnak. Ha a munkarendelések tényleges kezdési és befejezési dátumaival szeretné összehasonlítani az ütemezett kezdési és befejezési dátumokat, akkor dátumszámítást is végezhet.

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a>Költség-ellenőrzés az eszközökhöz, a munkavégzési helyszínekhez és a munkarendelésekhez

Az eszközökre, munkavégzési helyszínekre és munkarendelésekre vonatkozó számítások szinte megegyeznek. Az egyetlen különbség az, hogy az eszközök és munkavégzési helyszínek esetén a számításban szerepelnek aleszközök és al-munkavégzési helyszínek is. A dátum a tranzakció dátuma, amikor a regisztráció rögzítése megtörtént.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközköltség ellenőrzése** vagy **Munkavégzési helyszín költségeinek ellenőrzése** elemre, vagy az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelések költségellenőrzése** elemre.

2. Válassza ki a kiszámítani kívánt időszakot itt: **Eszköz költségkontrollja** / **Munkavégzési helyszín költségellenőrzése** / **Munkarendelés költségének ellenőrzése**.

3. Szükség szerint válasszon egy pénzügyi dimenziókészlet elemet, amit szerepeltetni szeretne a számításban.

4. Ha a nulla költséget tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.

5. A **Szint** mezőben megadhatja, hogy a költségellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínek hierarchiájához, akkor a munkavégzési helyszínekhez tartozó költségellenőrzési sorok a legfelső szinten jelennek meg, így a sorban szereplő órák hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely az költségellenőrzés minden sorát megjeleníti az összes olyan munkavégzési helyszín szintnél, amelyhez a sor kapcsolódik.

6. Ha a számításban szerepeltetni szeretné ezt az oszlopot, válassza az „Igen” beállítást a **Nyitott vállalt költség megjelenítése** gombbal.

7. Ha az aleszközökhöz tartozó költségeket külön sorként szeretné megjeleníteni, állítsa az **Aleszközök szerepeltetése** beállítást „Igen” értékre.

8. Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket/munkavégzési helyszíneket/munkarendeléseket a **Szerepeltetni kívánt rekordok** gyorslapon.

9. Kattintson az **OK** gombra az számítás indításához.

Az alábbi ábrán az **Eszközköltség ellenőrzése** párbeszédpanel egyik példája látható.

![1. ábra](media/01-controlling-and-reporting.png)

10. Az **Eszközköltség ellenőrzése** lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott műveleti ablaktábla gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

Az alábbi ábrán az **Eszközköltség kontrollja** számítási eredmény egyik példája látható.

![2. ábra](media/02-controlling-and-reporting.png)

A költség számításának másik módja az, ha többszörös kiválasztással kiválasztja az eszközöket az **Összes eszköz** vagy **Aktív eszközök** pontban. Ezután kattintson a **Költségellenőrzés** gombra az **Általános** lapon. Az **Eszközköltség ellenőrzése** párbeszédpanelen a program automatikusan beilleszti a kiválasztott eszközöket az **Eszköz** mezőbe a **Belefoglalandó rekordok** gyorslapon. Kattintson az **OK** gombra, és megjelenik a kiválasztott eszközökre vonatkozó költségszámítás. Ugyanez az eljárás hajtható végre az **Összes munkavégzési helyszín** vagy **Aktív munkavégzési helyszínek** pontban található munkavégzési helyszíneknél, valamint a munkarendeléseknél az **Összes munkarendelés** vagy **Aktív munkarendelések** pontban.

>[!NOTE]
>Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési költségek láthatók. A **Vállalt költség** mező a jogi személy által vállalt fizetendő összes költséget mutatja. A **Nyitott vállalt költség** mező a megrendelt vagy bevételezett, de még ki nem fizetett cikkek, órák vagy szolgáltatások kifizetésére vonatkozó kötelezettségeket mutatja. Ha minden felhasználási regisztráció fel van adva, a kapcsolódó költségek a **Tényleges költség** mezőben szerepelnek.

## <a name="work-order-date-control"></a>Munkarendelési dátum ellenőrzése

Ezen a lapon áttekintést kaphat a munkarendelések várható kezdő és befejező dátumairól, a tényleges kezdési és befejezési dátumokhoz képest.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Munkarendelések** > **Munkarendelés dátumkontrollja** elemre.

2. Kattintson a **Számítás** lehetőségre.

3. A **Munkavégzési helyszín** mezőben válassza ki a munkavégzési helyszínt.

4. A **Kezdő dátum** és **Záró dátum** mezőben válassza ki azt az időszakot, amelyhez el szeretné végezni a számítást. Minden olyan munkarendelést tartalmaz, amely várhatóan az adott időszakon belül kezdődik.

5. Kattintson az **OK** gombra.

6. Az Eszközórák ellenőrzése lapon a **Csoportosítási szempont...** műveleti ablaktáblacsoportjaiban kattintson a megfelelő gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott műveleti ablaktábla gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

Az alábbi ábrán a **Munkarendelés dátumkontrollja** számítási eredmény egyik példája látható.

![3. ábra](media/03-controlling-and-reporting.png)

- Az **Átlagos kezdő késleltetés** mező a munkarendelés tervezett kezdési dátuma és a tényleges kezdési dátum közötti különbséget jeleníti meg napokban. Ha például a tényleges kezdési dátum két nappal az ütemezett kezdési dátum előtt volt, akkor ebben a mezőben a „-2” jelenik meg.  
- Az **Átlagos záró késleltetés** mező a munkarendelés tervezett záró dátuma és a tényleges záró dátum közötti különbséget jeleníti meg napokban. Ha például a tényleges záró dátum három nappal az ütemezett kezdési dátum után volt, akkor ebben a mezőben a „3” jelenik meg.  
- Az **Előfordulások** mező mutatja, hogy hányszor fordulnak elő eltérések az ütemezett és a tényleges kezdési dátumra nézve, valamint az ütemezett és a tényleges befejezési dátumra nézve a munkarendelésen.

