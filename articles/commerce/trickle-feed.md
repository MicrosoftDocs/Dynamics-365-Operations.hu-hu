---
title: A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi áruház tranzakcióihoz
description: Ez a témakör bemutatja az áruházi tranzakciók folyamatos, apránkénti rendelés-létrehozási folyamatát a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: 7d5812893edff24a60a0e2eb3607701ac47a8a78
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057157"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>A rendelések folyamatos, apránkénti létrehozása a kiskereskedelmi áruház tranzakcióihoz (Nyilvános előzetes verzió)

[!include [banner](includes/banner.md)]

A Dynamics 365 Retail 10.0.4-es és korábbi verzióiban a kimutatások feladása nap végi műveletnek tekinthető, ahol az összes tranzakciót a nap végén számolják el a könyvekben. A nagy méretű tranzakciókat ezután korlátozott idő alatt kell feldolgozni, amely bizonyos esetekben terhelési és zárolási, valamint kimutatásfeladási hibákat okozhat. A kiskereskedők emellett nap közben nem tudják elszámolni bevételeiket és kifizetéseiket a könyvelésben.

A rendelések folyamatos, apránkénti létrehozásának nyilvános előzetes verziójának köszönhetően, amelyet a Retail 10.0.5-ös verziójában vezettünk be, a rendszer napközben folyamatosan feldolgozza a tranzakciókat, és csak a fizetőeszközök pénzügyi egyeztetése és az egyéb készpénzkezelési tranzakciók feldolgozása történik a nap végén. A funkció a nap folyamán felosztja az értékesítési rendelések, számlák és fizetések létrehozásának terhét, így jobb észlelt teljesítményt képes nyújtani, és lehetővé teszi a könyvelésben a bevételek és kifizetések szinte valós idejű elszámolását. 


## <a name="how-to-use-trickle-feed-based-posting"></a>A folyamatos, apránkénti feladás használata
  
1. Ha engedélyezni szeretné a tranzakciók folyamatos, apránkénti feladását, lépjen a **Rendszerfelügyelet > Beállítás > Licenckonfiguráció** pontra, és tiltsa le a **Kimutatások** kulcsot.

2. Ugyanezen az oldalon engedélyezze a **Kimutatások (folyamatos, apránkénti feldolgozás) – előzetes verzió** licenckulcsot. A kulcs engedélyezésekor győződjön meg arról, hogy nincsenek feladásra váró, függőben lévő kimutatások. 

    > [!Important]
    > A **Kimutatások (folyamatos, apránkénti feldolgozás) – előzetes verzió** licenckulcs ellenőrzése előtt győződjön meg arról, hogy nincsenek feladásra váró, függőben lévő kimutatások.

3. A rendszer a jelenlegi kimutatási bizonylatot két különböző típusra osztja: tranzakciós kimutatásra és pénzügyi kimutatásra.

      - A tranzakciós kimutatásban szerepel majd az összes fel nem adott és ellenőrzött tranzakció, és ez a kimutatás az Ön által megadott sorrendben hozza létre az értékesítési rendeléseket, értékesítési számlákat, fizetési és engedménynaplókat, valamint bevétel-költség tranzakciókat. Ezt a folyamatot úgy állítsa be, hogy sűrű gyakorisággal fusson, így a bizonylatok létrehozása akkor történik, amikor a tranzakciókat a rendszer a P-feladattal feltölti a Headquarters felületére. Mivel a tranzakciós kimutatás már létrehozza az értékesítési rendeléseket és értékesítési számlákat is, nincs szükség a **Készlet feladása** kötegelt feladat konfigurálására. Természetesen továbbra is használhatja az esetleges specifikus üzleti követelmények teljesítéséhez.  
      
     - A pénzügyi kimutatás terv szerint a nap végén jön létre, és csak a **Műszak** zárási módszert támogatja. Ez a kimutatás csak a pénzügyi egyeztetésre használható, és csak a különböző fizetőeszközök számított összege és tranzakciós összege közti összegeltérésekről készít naplókat, valamint a további készpénzkezelési tranzakciók naplóit hozza létre.   

4. A tranzakciós kimutatás kiszámításához kattintson a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Tranzakciós kimutatások kötegelt kiszámítása** lehetőségre. A tranzakciós kimutatások kötegelt feladásához kattintson a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Tranzakciós kimutatások kötegelt feladása** lehetőségre.

5. A pénzügyi kimutatás kiszámításához kattintson a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Pénzügyi kimutatások kötegelt kiszámítása** lehetőségre. A pénzügyi kimutatások kötegelt feladásához kattintson a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Pénzügyi kimutatások kötegelt feladása** lehetőségre.

> [!NOTE]
> Az új funkcióban már nincsenek jelen a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Kimutatások kötegelt kiszámítása** és a **Kiskereskedelem és kereskedelem > Kiskereskedelem és kereskedelem IT > Pénztárfeladás > Kimutatások kötegelt feladása** menüpontok.

Másik lehetőségként manuálisan is létre lehet hozni a tranzakciós és pénzügyi kimutatások típusait. Nyissa meg a **Kiskereskedelem és kereskedelem > Csatornák > Áruházak** pontot, és kattintson a **Kimutatások** lehetőségre. Kattintson az **Új** elemre, majd válassza ki a létrehozni kívánt kimutatás típusát. A **Kimutatások** mezőiben és az oldal **Kimutatáscsoport** részében található műveletek között a kiválasztott kimutatástípus szempontjából releváns adatok és műveletek jelennek meg.
