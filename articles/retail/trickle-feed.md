---
title: A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi üzlet tranzakcióihoz
description: Ez a témakör a Microsoft Dynamics 365 Retail kiskereskedelmi üzleti tranzakcióira vonatkozóan mutatja be a folyamatos, apránkénti rendelés-létrehozási folyamatot.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: deb8399aa401af16b6fe123a433eb21864e178c6
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693089"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi üzlet tranzakcióihoz (Nyilvános előzetes verzió)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

A Dynamics 365 Retail 10.0.4-es és korábbi verzióiban a kiskereskedelmi kimutatások feladása nap végi műveletnek tekinthető, ahol az összes tranzakciót a nap végén számolják el a könyvekben. A nagy méretű tranzakciókat ezután korlátozott idő alatt kell feldolgozni, amely bizonyos esetekben terhelési és zárolási, valamint kimutatásfeladási hibákat okozhat. A kiskereskedők emellett nap közben nem tudják elszámolni bevételeiket és kifizetéseiket a könyvelésben.

A rendelések folyamatos, apránkénti létrehozásának nyilvános előzetes verziójának köszönhetően, amelyet a Retail 10.0.5-ös verziójában vezettünk be, a rendszer napközben folyamatosan feldolgozza a tranzakciókat, és csak a fizetőeszközök pénzügyi egyeztetése és az egyéb készpénzkezelési tranzakciók feldolgozása történik a nap végén. A funkció a nap folyamán felosztja az értékesítési rendelések, számlák és fizetések létrehozásának terhét, így jobb észlelt teljesítményt képes nyújtani, és lehetővé teszi a könyvelésben a bevételek és kifizetések szinte valós idejű elszámolását. 


## <a name="how-to-use-trickle-feed-based-posting"></a>A folyamatos, apránkénti feladás használata
  
1. Ha engedélyezni szeretné a kiskereskedelmi tranzakciók folyamatos, apránkénti feladását, lépjen a **Rendszerfelügyelet > Beállítás > Licenckonfiguráció** pontra, és tiltsa le a **Kiskereskedelmi kimutatások** kulcsot.

2. Ugyanezen az oldalon engedélyezze a **Kiskereskedelmi kimutatások (folyamatos, apránkénti feldolgozás) – előzetes verzió** licenckulcsot. A kulcs engedélyezésekor győződjön meg arról, hogy nincsenek feladásra váró, függőben lévő kimutatások. 

> [!Important]
> A **Kiskereskedelmi kimutatások (folyamatos, apránkénti feldolgozás) – előzetes verzió** licenckulcs ellenőrzése előtt győződjön meg arról, hogy nincsenek feladásra váró, függőben lévő kimutatások.

3. A rendszer a jelenlegi kimutatási bizonylatot két különböző típusra osztja: tranzakciós kimutatásra és pénzügyi kimutatásra.

      - A tranzakciós kimutatásban szerepel majd az összes fel nem adott és ellenőrzött kiskereskedelmi tranzakció, és ez a kimutatás az Ön által megadott sorrendben hozza létre az értékesítési rendeléseket, értékesítési számlákat, fizetési és engedménynaplókat, valamint bevétel-költség tranzakciókat. Ezt a folyamatot úgy állítsa be, hogy sűrű gyakorisággal fusson, így a bizonylatok létrehozása akkor történik, amikor a kiskereskedelmi tranzakciókat a rendszer a P-feladattal feltölti a Retail Headquarters felületére. Mivel a tranzakciós kimutatás már létrehozza az értékesítési rendeléseket és értékesítési számlákat is, nincs szükség a **Készlet feladása** kötegelt feladat konfigurálására. Természetesen továbbra is használhatja az esetleges specifikus üzleti követelmények teljesítéséhez.  
      
     - A pénzügyi kimutatás terv szerint a nap végén jön létre, és csak a **Műszak** zárási módszert támogatja. Ez a kimutatás csak a pénzügyi egyeztetésre használható, és csak a különböző fizetőeszközök számított összege és tranzakciós összege közti összegeltérésekről készít naplókat, valamint a további készpénzkezelési tranzakciók naplóit hozza létre.   

4. A tranzakciós kimutatás kiszámításához kattintson a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Tranzakciós kimutatások kötegelt kiszámítása** lehetőségre. A tranzakciós kimutatások kötegelt feladásához kattintson a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Tranzakciós kimutatások kötegelt feladása** lehetőségre.

5. A pénzügyi kimutatás kiszámításához kattintson a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Pénzügyi kimutatások kötegelt kiszámítása** lehetőségre. A pénzügyi kimutatás kötegelt feladásához kattintson a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Pénzügyi kimutatások kötegelt feladása** lehetőségre.

> [!NOTE]
> Az új funkcióban már nincsenek jelen a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Kimutatások kötegelt kiszámítása** és a **Kiskereskedelem > Kiskereskedelmi IT > Pénztárfeladás > Kimutatások kötegelt feladása** menüpontok.

Másik lehetőségként manuálisan is létre lehet hozni a tranzakciós és pénzügyi kimutatások típusait. Nyissa meg a **Kiskereskedelem > Csatornák > Kiskereskedelmi üzletek** pontot, és kattintson a **Kiskereskedelmi kimutatások** lehetőségre. Kattintson az **Új** elemre, majd válassza ki a létrehozni kívánt kimutatás típusát. A **Kiskereskedelmi kimutatások** mezőiben és az oldal **Kimutatáscsoport** részében található műveletek között a kiválasztott kimutatástípus szempontjából releváns adatok és műveletek jelennek meg.
