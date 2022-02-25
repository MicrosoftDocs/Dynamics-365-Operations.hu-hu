---
title: Az Eszközkezelés paraméterei
description: Az Eszközkezelésben be kell állítani az eszközökkel, a munkarendelésekkel és a munkarendelések ütemezésével kapcsolatos általános paramétereket.
author: johanhoffmann
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1659fd3b4c173ffe09f245631309d329bba5b1bd
ms.sourcegitcommit: f2a78e0d7d461ca843ac2f9abff7690275db9196
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8105489"
---
# <a name="asset-management-parameters"></a>Az Eszközkezelés paraméterei

[!include [banner](../../includes/banner.md)]

Az Eszközkezelésben be kell állítani az eszközökkel, a munkarendelésekkel és a munkarendelések ütemezésével kapcsolatos általános paramétereket. Ez a cikk ezeknek a paramétereknek a beállítását ismerteti. Az oldal megnyitásához válassza az **Eszközkezelés** > **Beállítás** > **Eszközkezelési paraméterek** lehetőséget.

> [!NOTE]
> Ha be szeretne állítani egy olyan rendszert, amely az Eszközkezelési funkciók teszteléséhez tartalmaz bemutató adatokat, akkor a következő témakör tartalmaz további tájékoztatást: [Bemutató környezet bevezetése](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md).

## <a name="the-assets-tab"></a>Az Eszközök lap

Az **Eszközök lap** a következő beállításokat tartalmazza:

- Az **Alapértelmezett munkavégzési helyszín** a normál munkavégzési helyszín; az új eszközök létrehozásakor automatikusan ez van kiválasztva az eszközökhöz.  
- A **Szokásos naptár** mezőben válassza ki, hogy melyik naptárat szeretné használni az eszköz fő teljesítménymutatóinak kiszámításához, ha nincs erőforrás megadva az eszközhöz.  
- A **Nézet** mezőben válassza ki, hogy melyik normál nézet jelenjen meg az **Eszköz megtekintése** űrlap megnyitásakor (**Eszközkezelés** > **Közös** > **Eszközök** > **Eszköz megtekintése**).
- Az **Alapértelmezett kéréstípus** a karbantartási kérés normál típusa; az új kérések létrehozásakor automatikusan ez van kiválasztva.  
- A feladattípusok előrejelzéseit az **Előrejelzési projekt** mezőben kiválasztott projektben tárolja a rendszer. Minden feladattípushoz automatikusan létrejön egy új tevékenység az előrejelzési projekthez. Ezután az előrejelzési projektben menti a rendszer a feladattípusok előrejelzéseit.  
- A **Modell** mezőben válassza ki a feladattípus és a munkarendelés előrejelzéseihez használt előrejelzési modellt.

## <a name="the-work-orders-tab"></a>A Munkarendelések lap

A **Munkarendelések lap** a következő beállításokat tartalmazza:

- Az **Alapértelmezett munkarendelési típus** határozza meg a munkarendelés létrehozásakor használt normál beállításokat.  
- A **Megelőző munkarendelés típusa** határozza meg a munkarendelések karbantartási tervekből történő létrehozásakor használt munkarendelési típust. Ha üresen hagyja a mezőrt a rendszer az **Alapértelmezett munkarendelési típus** mezőben megadott munkarendelési típust használja.  
- A **Kapcsolódó munkarendelési maszk** mezőben határozható meg az egy munkarendeléssel összekapcsolható munkarendelések maximális száma. Példa: a ## értékkel maximálisan 99 összekapcsolt munkarendelés hozható létre. Ha az itt leírt módon határoz meg egy maszkot, a társított munkarendelések számozása a következő mintát követi: [annak a munkarendelésnek az azonosítója, amelyhez társítva van egy munkarendelés]-01, -02, -03, stb. Ha nem definiál maszkot ebben a mezőben, akkor a társított munkarendelés a sorban következő munkarendelési azonosítót kapja.  
- Válassza **az Igen** **lehetőséget a Hibák másolása beállításhoz**, ha automatikusan szeretné átmásolni a karbantartási kérések során regisztrált hibákat a kapcsolódó munkarendelésekbe. 
- A **Szint** mezőben határozhatja meg a munkavégzési helyszín azon szintjét, amelyet a rendszer automatikusan beszúr egy munkarendeléshez, ha minden összekapcsolt munkarendelési feladat ugyanarra a munkavégzési helyszínre utal. Ha nem az összes munkarendelési feladat van a meghatározott szint ugyanazon munkavégzési helyszínéhez kapcsolva, a **Munkavégzési helyszín** mező üresen marad a munkarendeléshez. Példa: ha az „1” számot írja be a mezőbe, az lesz a felső szint a munkavégzési helyszín struktúrájában. Ha a „0” számot írja be a mezőbe, akkor nem határozza meg konkrétan a munkavégzési helyszín szintjét, csak azt, hogy egy munkarendelés összes munkarendelési feladatát ugyanahhoz a munkavégzési helyszínhez kell kapcsolni, hogy az adott munkavégzési helyszínt hozzá lehessen adni a munkarendeléshez.  
- A munkarendelésekhez tartozó felhasználás feladásakor használt naplókat az **Általános** gyorslap **Óra**, **Cikk** és **Költség** mezőjében lehet kiválasztani.  
- A **Termék forrásnyelve** mezőben válassza ki, hogy melyik nyelvet szeretné használni az Eszközkezelés jelentéseiben lévő terméknevekhez. Kiválaszthatja a vállalati számlához beállított nyelvet, vagy a pillanatnyilag bejelentkezett felhasználóhoz beállított nyelvet.  
- Ha automatikusan frissíteni szeretné a feladattípus alapértelmezéseit, a karbantartási terveket és a karbantartási köröket, válassza a **Valós idejű frissítés** váltógomb **Igen** beállítását.
  - Ha a **Nem** beállítást adja meg, a feladattípus alapértelmezései, a karbantartási tervek és a karbantartási körök nem frissülnek automatikusan az Eszközkezelésben.
  - Ha nagy mennyiségű adatot szinkronizál (például sok eszközt vagy munkavégzési helyszínt állított be a karbantartási tervekhez vagy a karbantartási körökhöz), vagy sok karbantartási tervvel vagy karbantartási körrel rendelkezik, válassza a váltógomb **Nem** értékét.  
  - Ha módosítja a feladattípus alapértelmezéseit, a karbantartási terveket vagy a karbantartási köröket, és a **Nem** értéket adta meg a valós idejű frissítéshez, lehetséges, hogy nem jelenik meg figyelmeztetés, ha a módosítások hatással vannak a következőkre:
    - A karbantartási tervekhez vagy körökhöz beállított munkavégzési helyszínek  
    - A karbantartási tervekhez vagy körökhöz beállított objektumok  
    - Karbantartási tervek beállítása  
    - Karbantartási körök beállítása  
- A **Kategória** gyorslapon a munkarendelésekhez tartozó fogyasztásához kapcsolt alapértelmezett kategóriák definiálhatók.  

## <a name="the-work-order-scheduling-tab"></a>A Munkarendelés ütemezése lap

A **Munkarendelés ütemezése** lap az **Általános** gyorslapon a következő beállításokat tartalmazza:

- Az **Időkorlát ütemezése** a munkarendelés várt kezdő dátuma alapján meghatározza azt az időszakot (napokban), amely alatt sor kerül a munkarendelési feladatok tervezésére.  
- Az **Alapterv** a **Szervezeti adminisztráció** modul erőforrásaihoz kapcsolódik. Ha kiválaszt egy alaptervet ebben a mezőben, akkor megtekintheti a munkarendelésekhez társított kapacitásfoglalásokat a **Kapacitásfoglalások** (**Szervezeti adminisztráció** > **Erőforrások** > **Erőforrások** > kiválasztott erőforrás > **Erőforrás** lap > **Kapacitásfoglalások** gomb) részen. Ha üresen hagyja ezt a mezőt, akkor megtekintheti a munkarendelésekkel összekapcsolt kapacitásterhelést a **Kapacitásterhelés** (**Szervezeti adminisztráció** \> **Erőforrások** \> **Erőforrások** \> kiválasztott erőforrás \> **Erőforrás** lap \> **Kapacitásterhelés** gomb) részen.  

>[!NOTE]
>A beállítás, hogy szeretne-e alaptervet használni az **Eszközkezelés** modulban vagy sem, illetve a kapacitásfoglalások és a kapacitásterhelés áttekintésére szolgáló összekapcsolt űrlap a normál telepítés része. Az **Alapterv** mezőben megadott beállítástól függően megtekintheti a kapacitásra vonatkozó adatokat a **Kapacitásfoglalások** vagy a **Kapacitásterhelés** részen a **Szervezeti adminisztráció** modulban. Nem hozható létre olyan beállítás, amelyben a kapacitásfoglalások mindkét nézetben megjelennek.  

Az alábbi listában leírt összes mező a kiszámított értékelési pontszámokhoz kapcsolódik, amelyeket a rendszer a munkarendelések prioritásának a munkarendelések ütemezése során történő kiszámításához használ.

- A **Prioritás** olyan értékelési pontszám, amelyet a rendszer a **Kritikusság** és a **Kezdő dátum** mezőben lévő értékelési pontszámokkal együtt számol ki. A mezőben lévő számot a rendszer elosztja a munkarendelés **Prioritás** mezőjében lévő számmal. Példa: ha az „5,00” értéket adja meg a mezőben, a munkarendelés prioritása pedig „20”, akkor a prioritás értékelési pontszáma 0,25 lesz.  
- A **Kritikusság** olyan értékelési pontszám, amelyet a rendszer a **Prioritás** és a **Kezdő dátum** mezőben lévő értékelési pontszámokkal együtt számol ki. A mezőben lévő számot a rendszer megszorozza a munkarendelés **Kritikusság** mezőjében lévő számmal. Példa: ha a „10,00” értéket adja meg a mezőben, a munkarendelés kritikussága pedig „5”, akkor a kritikusság értékelési pontszáma 50 lesz.  
- A **Kezdő dátum** olyan értékelési pontszám, amelyet a rendszer a **Prioritás** és a **Kritikusság** mezőben lévő értékelési pontszámokkal együtt számol ki. A mezőben a napi pontszám látható negatív értékként; a rendszer összehasonlítja az értéket a munkarendelés **Várható kezdés** mezőjével. Példa: ha a „10,00” értéket adja meg a mezőben, a munkarendelés várható kezdési dátuma pedig három nap múlva van, akkor az értékelés eredménye mínusz 30,00 lesz. A **Prioritás** és a **Kritikusság** mező fenti példákban szereplő 0,25 és 50 értékének hozzáadása után az eredmény 20,25 lesz. A rendszer ezt a számot összehasonlítja a munkarendelés összes értékelési pontszámával a munkarendelés ütemezése alatt, és a legmagasabb értékelési pontszámokat veszi előre a tervezéskor.  
- A **Felelős dolgozó** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozói csoport**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. Ha az „50,00” értéket adja meg a mezőben, és kiválaszt egy felelős dolgozót a munkarendeléshez, a dolgozó 50 pontot kap a dolgozók általános kiszámítása során, a munkarendelés ütemezésekor.  
- A **Felelős dolgozói csoport** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozó**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. Ha az „50,00” értéket adja meg a mezőben, és kiválaszt egy felelős dolgozót a munkarendeléshez, a dolgozó 50 pontot kap a dolgozók általános kiszámítása során, a munkarendelés ütemezésekor.  
- A **Korlátozás a felelősre** ponttal korlátozható a munkarendelés ütemezéséhez elérhető dolgozók száma. Ha attól függetlenül szeretne minden dolgozóhoz pontszámot számítani, hogy felelős dolgozóként vagy felelős dolgozói csoport tagjaként van-e beállítva, adja meg a **Nem** beállítást. Ha minden olyan dolgozóhoz szeretne pontszámot számítani, aki felelős dolgozóként és/vagy felelős dolgozói csoport tagjaként van beállítva a munkarendeléshez, adja meg az **Igen** beállítást.  
- A **Preferált dolgozó** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozó**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. A rendszer kiszámítja és összeadja a négy értékelési pontszámot, és az így kapott pontszámmal állapítja meg, hogy melyik dolgozót melyik munkarendeléshez kell hozzárendelni a munkarendelés ütemezése során. Ha a „10,00” értéket adja meg a mezőben, és kiválaszt egy preferált dolgozót egy munkarendeléshez, a dolgozó 10 pontot kap a dolgozók általános kiszámítása során, a munkarendelés ütemezésekor.  
- A **Preferált dolgozói csoport** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozó**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. Ha a „10,00” értéket adja meg a mezőben, és kiválaszt egy munkarendeléshez kiválasztott preferált dolgozói csoporthoz hozzárendelt dolgozót, a dolgozó 10 pontot kap a dolgozók általános kiszámítása során, a munkarendelés ütemezésekor.  
- A **Korlátozás a preferáltra** ponttal korlátozható a munkarendelés ütemezéséhez elérhető dolgozók száma. Ha attól függetlenül szeretne minden dolgozóhoz pontszámot számítani, hogy preferált dolgozóként vagy preferált dolgozói csoport tagjaként vannak-e beállítva a dolgozók, adja meg a **Nem** beállítást. Ha csak olyan dolgozóhoz szeretne pontszámot számítani, aki preferált dolgozóként és/vagy preferált dolgozói csoport tagjaként van beállítva, adja meg az **Igen** beállítást.  
- A **Hely** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozó**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. Ha a „3000,00” értéket adja meg a mezőben, a dolgozó 3000 pontot kap a számítás során, ha ugyanabban a gyárban vagy létesítményben van, mint az az eszköz, amelyhez ütemezni kell egy feladatot.  
  - Ha a cég használ munkavégzési helyszíneket, a dolgozók teljes pontot kapnak, ha az eszközzel összekapcsolt munkavégzési helyszínen vannak. Ha az eszköz munkavégzési helyszíne rendelkezik fölérendelt eszközzel, az adott munkavégzési helyszínen lévő dolgozók a pontszám felét kapják meg. Ha az a hely is rendelkezik fölérendelt eszközzel, a helyen lévő dolgozók a pontszám harmadát kapják meg. Ha az a hely is rendelkezik fölérendelt eszközzel, a helyen lévő dolgozók a pontszám negyedét kapják meg – stb.  
  - Ha a cég használ helyeket az eszközökhöz (amit nem javaslunk), a rendszer a helyet, a területet és a zónát használja a hely pontszámának kiszámításához. Ha a dolgozó az eszközzel összekapcsolt helyen, területen és zónában van, teljes pontszámot kap. Ha a dolgozó helye csak a hellyel és a területtel egyezik, a dolgozó az értékelési pontszám 2/3-át kapja meg. Ha a dolgozó helye csak a hellyel egyezik, a dolgozó az értékelési pontszám 1/3-át kapja meg.  
- A **Korlátozás a helyszínre** ponttal korlátozható a munkarendelés ütemezéséhez elérhető dolgozók száma. Ha az összes munkavégzési helyszín összes dolgozójához szeretne pontszámot számítani, válassza a **Nem** lehetőséget. Ha csak olyan dolgozókhoz szeretne pontszámot számítani, akik a munkarendelés munkavégzési helyszínéhez vannak társítva, adja meg az **Igen** beállítást.

>[!NOTE]
>A három „Korlátozás...” mezővel korlátozható a dolgozókhoz kiszámított pontszámok száma, így gyorsítható a munkarendelés ütemezése.

**A dolgozó kezdési dátuma** olyan értékelési pontszám, amelyet a rendszer a **Felelős dolgozó**, a **Preferált dolgozó**, a **Preferált dolgozói csoport**, az **Eszköz helye** és a **Kezdő dátum** értékelési pontszámokkal együtt számít ki. A mezőben a napi pontszám látható negatív értékként; a rendszer összehasonlítja az értéket a munkarendelés **Várható kezdés** mezőjével. Példa: ha a „10,00” értéket adja meg a mezőben, a munkarendelés várható kezdési dátuma pedig holnap van, akkor az értékelés eredménye mínusz 10,00.

  - Ha azt feltételezzük, hogy nincs kiválasztva felelős dolgozó és felelős dolgozói csoport az ütemezendő munkarendeléshez, akkor hozzáadja és kivonja a fenti **Preferált dolgozó**, **Preferált dolgozói csoport**, **Eszköz helye** és **Kezdő dátum** mezőkkel kapcsolatos példák értékelési pontszámait, és 3010,00 lesz a végeredmény. Ez magas pontszám az olyan dolgozóknak, akik már preferált dolgozóként lettek kiválasztva, illetve szerepelnek a preferált dolgozói csoportban a munkarendeléshez, illetve akik ugyanabban a létesítményben vannak, mint az eszköz, amelyhez ütemezni kell a feladatot. Ez azt jelenti, hogy a kérdéses dolgozó jó eséllyel lesz kiválasztva a feladatra a munkarendelés ütemezése során.  
  - Ha a fenti nyolc mező egyikébe „0,00” érték kerül, az értékelési pontszámot nem használja a rendszer a munkarendelés ütemezése során.  

## <a name="the-document-types-tab"></a>A Dokumentum típusok lap

Válassza ki azokat a dokumentumtípusokat, amelyeket elérhetővé szeretne tenni a munkarendelési jelentéshez társított mellékletek nyomtatásához. Ehhez válassza a dokumentumtípust a **Rendelkezésre áll** szakaszban, majd az ![előre nyíl.](media/15-setup-for-objects.png) gombot. Ha el szeretné távolítani a kijelölt dokumentumtípust, válassza ki a **Kijelölve** szakaszban, és válassza a ![vissza nyíl](media/16-setup-for-objects.png) gombot.

## <a name="the-number-sequences-tab"></a>A Számsorozatok lap

Válassza ki a szükséges számsorozatot ebben a szakaszban. Az eszközökhöz két számsorozat használható: egy a manuálisan létrehozott eszközökhöz, egy pedig a függőben lévő eszközökkel létrehozottakhoz.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
