---
title: "Műszak és pénztárgépfiók kezelés"
description: "Ez a cikk a kiskereskedelmi pénztár műszakok két típusa, az önálló és megosztott beállítását és használatát mutatja be. A megosztott műszakokat több felhasználó több helyen is használhatja viszont az önálló műszakokat egyszerre csak egy dolgozó használhatja."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 72f73404f99330c3ff8b23dabed78477a0cd30cd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="shift-and-cash-drawer-management"></a>Műszak és pénztárgépfiók kezelés

[!include[banner](includes/banner.md)]


Ez a cikk a kiskereskedelmi pénztár műszakok két típusa, az önálló és megosztott beállítását és használatát mutatja be. A megosztott műszakokat több felhasználó több helyen is használhatja viszont az önálló műszakokat egyszerre csak egy dolgozó használhatja.

A kiskereskedelmi pénztár műszakoknak két típusa létezik: önálló és megosztott. Az önálló műszakokat egyszerre csak egy dolgozó használhatja. A megosztott műszakokat több felhasználó több helyen is használhatja. Ezért hatékonyan hoznak létre különálló műszakokat több dolgozónak az üzletben.

## <a name="standalone-shifts"></a>Önálló műszakok
Az önálló műszakokat hagyományos rögzített pénztár esetében használják, ahol a készpénz egyeztetése minden pénztárjegyzéktől függetlenül történik. Például egy élelmiszerboltban beállítás esetén általában több rögzített pénztárjegyzék van, a pénztáros egyesével van hozzárendelve a jegyzékekhez. Ebben az esetben minden jegyzék valószínűleg önálló műszakot használ és a pénztáros felelős a kasszáért vagy a fizikai készpénzért a jegyzéknél. Az önálló műszak magába foglalja a pénztáros által műszak során végzett összes tevékenységet a jegyzéken. A tevékenységek magukba foglalhatják a kasszában jóváírt nyitó összeget, készpénz elvételét és hozzáadását olyan műveleteken keresztül, mint banki befizetés és váltópénzbetét, és a fizetőeszköz-elszámolást a műszak végén.

### <a name="set-up-a-stand-alone-shift"></a>Önálló műszak beállítása

Önálló műszak a pénztárfiók szintjén van jelölve. Ez az eljárás ismerteti, hogyan állítható be önálló műszak a pénztárjegyzéken.

1.  Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Pénztárprofilok** &gt; **Hardverprofilok** gombra.
2.  Válassza ki a hardverprofilt az önálló műszak használatához.
3.  A **Fiók** Gyorslapon végezzen el megerősítést, hogy a **Megosztott műszakfiók** beállítás **Nem** értékre legyen állítva.
4.  Kattintson a **Mentés** gombra.
5.  Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Jegyzékek** lehetőségekre.
6.  Válassza ki az önálló műszakot igénylő jegyzéket, majd kattintson a **Szerkesztés** lehetőségre.
7.  A **Hardverprofil** mezőben válassza ki a 2. lépésben kiválasztott hardverprofilt.
8.  Kattintson a **Mentés** gombra.
9.  Kattintson a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.
10. Válassza a **1090** elosztási ütemezést, és kattintson a **Futtatás most** lehetőségre a pénztár módosításainak szinkronizálásához.

### <a name="use-a-stand-alone-shift"></a>Önálló műszak használata

1.  Bejelentkezés a pénztárba.
2.  Ha nincs nyitott műszak, válassza a **Új műszak megnyitása** lehetőséget.
3.  Ugrás a **Nyitó összeg elszámolása** művelethez, és adja meg a kasszához adott készpénz összegét a munkanap elkezdéséhez.
4.  Tranzakciók végrehajtása.
5.  A nap végén válassza a **Fizetőeszköz-elszámolás** pénztárgépfiókban fennmaradt készpénz összegének elszámolásához.
6.  Adja meg a készpénz összegét, majd kattintson a **Mentés** gombra a fizetőeszköz-elszámolás elmentéséhez.
7.  Válassza a **Műszakzárás** lehetőséget a műszak lezárásához.

**Megjegyzés:** Helyben történő üzleti folyamatoktól függően a műszak alatt más műveletek is elérhetők. A **Széfes befizetés**, **Banki befizetés**, és **Fizetőeszköz kivétele** műveletek segítségével távolítható el pénz a kasszából a nap folyamán vagy a műszak lezárása előtt. Ha egy kasszában elfogy a készpénz a **Váltópénzbetét** művelet használható készpénz hozzáadásához.

## <a name="shared-shifts"></a>Megosztott műszakok
Megosztott műszakot olyan környezetben használnak, ahol több pénztáros osztozik egy vagy több pénztárfiókon a munkanap során. Általában a megosztott műszak mobil pénztárkörnyezetben használatos. Mobil környezetben a pénztárosok nincsenek hozzárendelve egyetlen pénztárfiókhoz sem és felelősséggel sem tartoznak érte. Ehelyett minden pénztáros képes kell, hogy legyen értékesítés fizetésére és készpénz hozzáadására a pénztárfiókhoz bármelyik legközelebbi pénztárfióknál. Ebben az esetben a pénztárosok közt megosztott pénztárgépfiókokat tartalmazza a megosztott műszak. Minden megosztott műszakban levő pénztárgépfiók megtalálható ugyanabban a műszakban a műszak készpénzkezeléshez kapcsolódó tevékenységei miatt. Ezért a műszak kezdő összegének ki kell terjednie valamennyi készpénz összegére a megosztott műszak összes pénztárgépfiókjában. Hasonlóképpen a fizetőeszköz-elszámolás a megosztott műszak összes pénztárgépfiókjának készpénz összege lesz. **Megjegyzés:** Csak egy megosztott műszak lehet nyitott egyidejűleg az egyes üzletekben. Megosztott műszakok és önálló műszakok ugyanabban az üzletben használhatók.

### <a name="set-up-a-shared-shift"></a>Megosztott műszak beállítása

1.  Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Pénztárprofilok** &gt; **Hardverprofilok** gombra.
2.  Válassza ki a hardverprofilt az megosztott műszak használatához.
3.  A **Fiók** Gyorslapon állítsa be a **Megosztott műszakfiók** beállítást **Igen** értékre.
4.  Kattintson a **Mentés** gombra.
5.  Kattintson a **Kiskereskedelem** &gt; **Csatorna beállítása** &gt; **Pénztár beállítása** &gt; **Jegyzékek** lehetőségekre.
6.  Válassza ki az megosztott műszakot igénylő jegyzéket, majd kattintson a **Szerkesztés** lehetőségre.
7.  A **Hardverprofil** mezőben válassza ki a 2. lépésben kiválasztott hardverprofilt.
8.  Kattintson a **Mentés** gombra.
9.  Kattintson a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.
10. Válassza a **1090** elosztási ütemezést, és kattintson a **Futtatás most** lehetőségre a pénztár módosításainak szinkronizálásához.

### <a name="use-a-shared-shift"></a>Megosztott műszak használata

1.  Bejelentkezés a pénztárba.
2.  Ha még nincs csatlakoztatva a pénztár a hardverállomásra, válassza a **Nem pénztárgépfiókkal kapcsolatos művelet** lehetőséget, és válassza a **Hardverállomás kiválasztása** műveletet hardverállomás aktiválásához a megosztott műszakban. Ez a lépés csak a jegyzék megosztott műszak környezethez adásának első alkalmával szükséges.
3.  Jelentkezzen ki a pénztárból, majd ismét jelentkezzen be.
4.  Válassza a **Új műszak létrehozása** lehetőséget.
5.  Válassza a **Nyitó összeg elszámolása** lehetőséget.
6.  Adja meg az üzlet minden, megosztott műszakban használt pénztárgépfiókjának kezdőösszegét, majd kattintson a **Mentés** gombra.
    -   A nyitóösszeg részének minden későbbi pénztárgépfiókhoz való hozzáadásához használja a **Hardverállomás kiválasztása** műveletet a hardverállomás aktiválásához.
    -   Kassza adott pénztárgépfiókhoz való hozzáadásához használja a **Fiók kinyitása** műveletet.
    -   Folytassa, amíg a megosztott műszak összes pénztárgépfiókja rendelkezik a nyitó összeg egy részével.

7.  A nap végén minden pénzfiókot nyisson meg, és távolítsa el a készpénzt.
8.  Miután eltávolította a készpénzt a pénztárgépfiókból, számolja meg az összes pénztárgépfiók összes készpénzét.
9.  Használja a **Fizetőeszköz-elszámolás** műveletet a megosztott műszak összes pénztárgépfiókjának teljes készpénzösszegének elszámolásához.
10. Használja a **Műszakzárás** a műveletet a megosztott műszak bezárásához.





