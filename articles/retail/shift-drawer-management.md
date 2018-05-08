---
title: "Műszak és pénztárgépfiók kezelés"
description: "Ez a cikk a kiskereskedelmi pénztár műszakok két típusa, az önálló és megosztott beállítását és használatát mutatja be. A megosztott műszakokat több felhasználó több helyen is használhatja viszont az önálló műszakokat egyszerre csak egy dolgozó használhatja."
author: rubencdelgado
manager: AnnBe
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8a24f8adc4f7886a1f942d83f7a4eb12e7034fcd
ms.openlocfilehash: c1483d3240d266845cea7789b70c038cb98fdfcc
ms.contentlocale: hu-hu
ms.lasthandoff: 03/22/2018

---

# <a name="shift-and-cash-drawer-management"></a>Műszak és pénztárgépfiók kezelés

[!include [banner](includes/banner.md)]

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

## <a name="shift-operations"></a>Műszakműveletek
Különféle műveletek állnak rendelkezésre a műszak állapotának módosítására, vagy a fiókban levő pénzösszeg növelésére vagy csökkentésére. Az alábbi témakör ezeket a műszakműveleteket írja le a Dynamics 365 for Retail Modern POS és Cloud POS esetében.

**Nyitott műszak**

A pénztár megköveteli, hogy a felhasználó aktív, nyitott műszakban végezze mindazon műveleteket, amelyek pénzügyi tranzakciót eredményezhetnek, például eladás, visszaváltás vagy vevői megrendelés.  

A pénztárba történő bejelentkezéskor a rendszer ellenőrzi, hogy a felhasználó rendelkezik-e aktív műszakkal az aktuális pénztárgépen. Ellenkező esetben a felhasználó dönthet úgy, hogy megnyit egy új műszakot, folytat egy meglévő műszakot, vagy folytatja a bejelentkezést „nem fiókos” üzemmódban, a rendszerkonfigurációtól és az engedélyektől függően.

**Nyitó összeg elszámolása**

Ez a művelet gyakran az első, amelyet az újonnan megnyitott műszakokon végrehajtanak. A felhasználók megadják a fiókban levő kezdő pénzösszeget a műszakra. Ez azért fontos, mivel a műszakok lezárásakor fellépő többlet/hiány-számítás felel ezért az összegért.

**Váltópénz betétele**

A váltópénzbetétek olyan nem értékesítési tranzakciók, amelyeket az aktív műszakon lehet elvégezni, növelve a fiókban a készpénz mennyiségét. A váltópénzbetét gyakori példája az, ha további aprót kíván betenni a fiókba, amikor kifogyóban van.

**Fizetőeszköz kivétele**

A fizetőeszköz-törlések olyan nem értékesítési tranzakciók, amelyeket az aktív műszakon lehet elvégezni, csökkentve a fiókban a készpénz mennyiségét. Ezt leggyakrabban egy másik műszakbeli váltópénzbetéttel együtt használjuk. Például az 1. pénztárban kevés az apró, ezért a 2. pénztár fizetőeszköz-eltávolítást hajt végre a a fiókban lévő mennyiség csökkentésére. Az 1. pénztárgép használója ezután az összeg növelése érdekében váltópénzbetétet végez el.

**Műszak felfüggesztése**

A felhasználók felfüggeszthetik az aktív műszakjukat, hogy felszabadítsák az aktuális pénztárgépet egy másik felhasználó számára, vagy a műszakot áthelyezhetik egy másik pénztárgépre (ezt gyakran „mozgó kasszának” nevezik). 

A műszak felfüggesztése megakadályozza az új tranzakciókat vagy a műszak változtatásait, mindaddig, amíg a folytatást nem választja.

**Műszak folytatása**

Ez a művelet lehetővé teszi, hogy a felhasználó folytasson egy felfüggesztett műszakot egy olyan pénztárgépen, amelyiken még nincs aktív műszak.

**Fizetőeszköz-elszámolás**

A fizetőeszköz-elszámolás műveletben a felhasználó adja meg a teljes összeget, ami jelenleg a fiókban van, általában a műszak lezárása előtt. Ezt az értéket veti össze a rendszer a várt műszakkal a többlet/hiány összeg kiszámításához.

**Széfes befizetés**

Széfes befizetések az aktív műszak alatt bármikor elvégezhetők. Ez a művelet eltávolítja a pénzt a fiókból, hogy biztonságosabb helyre legyen átvihető, például egy széfben a hátsó helyiségben. A széfes befizetésekhez rögzített teljes összeg továbbra is szerepel a műszak összegében, de nem kell feltétlenül beszámítani a fizetőeszköz-elszámolásba.

**Banki befizetés**

A széfes befizetésekhez hasonlóan a banki befizetések szintén aktív műszakban futnak le. Ez a művelet eltávolítja a műszakból a pénz, előkészítve a banki letétre.

**Műszakzárás számlálás nélkül**

A számlálás nélkül lezárt műszak egy olyan műszak, amely már nem aktív, de még nem lett teljesen lezárva. A számlálás nélkül lezárt műszakok nem folytathatók, mint a felfüggesztett műszakok, de később vagy másik pénztárból különböző eljárások végezhetők, mint kezdőösszegek megadása és fizetőeszköz-elszámolások.

A számlálás nélkül lezárt műszakok gyakran használatosak pénztár új felhasználó vagy a műszak részére történő felszabadításához, anélkül, hogy teljes mértékű számlálást, egyeztetést és zárást végeznénk előbb ezen a műszakon. 

**Műszakzárás**

Ez a művelet számítja ki a műszak összegeit, a többlet/hiány összegeket, és ezután véglegesít egy aktív és számlálás nélkül lezárt műszakot. A lezárt műszakok nem folytathatók és nem módosíthatók.  

**Műszakok kezelése**

A művelet segítségével a felhasználók megtekinthetik az üzlet aktív, felfüggesztett és számlálás nélkül lezárt műszakjait. Engedélyeiktől függően a felhasználók a végleges zárási eljárásaikat is végrehajthatják, például a fizetőeszköz-elszámolásokat és műszakzárást számlálás nélkül lezárt műszakok számára. Ez a művelet azt is lehetővé teszi a felhasználó számára, hogy megtekintsék és töröljék az érvénytelen műszakokat abban a ritka esetben, amikor a műszak az offline és online módok közötti átváltást követően hibás állapotban marad. Ezek az érvénytelen műszakok nem tartalmaznak az egyeztetéshez szükséges pénzügyi információkat vagy tranzakciós adatokat. 

