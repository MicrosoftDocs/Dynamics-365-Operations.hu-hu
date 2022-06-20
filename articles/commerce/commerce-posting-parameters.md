---
title: Commerce feladási paraméterek
description: Ez a témakör a pénzügyi és fizikai tranzakciók feladására vonatkozó paramétereket írja le Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 10ea650b7c5c0cad7e1a3d7556c073aecef06036
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887114"
---
# <a name="commerce-posting-parameters"></a>Commerce feladási paraméterek

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a pénzügyi és fizikai tranzakciók feladására vonatkozó paramétereket írja le Microsoft Dynamics 365 Commerce. A Commerce rendszer feladási paraméterei a Commerce Headquarters **retail és Commerce \> Headquarters beállítási paramétereinek \>\> Feladási paramétereiben találhatók \>**.

## <a name="periodic-discount-parameters"></a>Időszaki kedvezmény paraméterei

Az alábbi táblázat felsorolja azokat az időszaki engedményparamétereket, amelyek a pénzügyi és fizikai tranzakciók feladására vonatkoznak.

| Paraméter | Leírás |
|-----------|-------------|
| Időszaki kedvezmény feladása | Ez a beállítás határozza meg, hogy az időszakos ajánlatok fel vannak-e adva a főkönyvi számlákra. Az időszakos engedmények közé többek között a kombinációs, a mennyiségi és az engedményes ajánlatok tartoznak. Ha ez a paraméter engedélyezve van, az **Időszakos engedmények szakaszban további mezőket lehet** beállítani. |
| Főkönyvi számla típusa | <p>Az időszaki engedmények felad használt számlatípusának kiválasztása:</p><ul><li>**Normál** – a rendszer nem használja az ezen a lapon található engedményhez kapcsolódó mezőket. Ehelyett a **Commerce** Headquarters feladási lapján (**Készletkezelés beállítása \>\>\> – Feladás feladása képernyők) megadott számlákat használja**.</li><li>**Időszakos** – a rendszer az ezen a lapon található engedményekkel kapcsolatos mezőkben megadott Commerce engedményszámlákat használja. Ha ezt a lehetőséget választja, minden egyes ajánlattípushoz (engedmény, kombinációs kedvezmény, mennyiség és küszöbérték) meg kell adnia a főkönyvi számlát. Az egyes engedmények beállításakor meg lehet határozni egy számlát. Ha az engedményszámla feladási funkcióját használja az engedménybeállítási lapon, egy további tartozik bejegyzés és jóváírási bejegyzés készül az engedmény Commerce engedmény főkönyvi számláról az engedmény főkönyvi számlájáról történő átsorolására. A további tudnivalókat lásd a kiskereskedelmi [engedményekkel kapcsolatban](retail-discounts-overview.md).</li></ul> |
| Infókód engedményének postai irányítószáma | Ez a beállítás már nem használatos a szabványos Commerce-megoldásban, ezért elavult lesz. |
| Időszaki engedmény feladása rendelésekhez | Ez a beállítás azt szabályozza, hogy a kiskereskedelmi időszaki kedvezményeket feladja-e a rendszer a főkönyvbe a vevői rendelések és a hívásközponti rendelések esetében. |

## <a name="inventory-update-parameters"></a>Készletfrissítési paraméterek

Az alábbi táblázat felsorolja a készletfrissítések paramétereit, amelyek a pénzügyi és tényleges tranzakciók feladására vonatkoznak.

| Paraméter | Leírás |
|-----------|-------------|
| Alapértelmezett kötegazonosító használata, ha nem találhatók a kötegszámok. | Ez a beállítás határozza meg, hogy az alapértelmezett kötegazonosítót használja-e a program kötegre alkalmas cikkekhez, ha nem találhatók kötegszámok, és engedélyezve van a negatív készlet. |
| Alapértelmezett kötegazonosító | Ezt a kötegszámot kell használni, ha **a** cikkek kötegszámai nem találhatók, és engedélyezve van az Alapértelmezett kötegazonosító használata olyankor, amikor nem találhatók a kötegszámok. |

## <a name="aggregation-parameters"></a>Összesítési paraméterek

Az alábbi táblázat felsorolja azokat az összesítési paramétereket, amelyek a pénzügyi és fizikai tranzakciók feladására vonatkoznak.

| Paraméter | Leírás |
|-----------|-------------|
| Széfes befizetés | Ezzel a paraméterrel összesíthet minden tranzakciót a kimutatás feladása során, és egyetlen sort hozhat létre a naplóban feladásra, nem pedig külön sort az egyes tranzakciókhoz. |
| Banki befizetés | Ezzel a paraméterrel összesíthet minden tranzakciót a kimutatás feladása során, és egyetlen sort hozhat létre a naplóban feladásra, nem pedig külön sort az egyes tranzakciókhoz. |
| Értékesítési tranzakciók | A tranzakció-kimutatás feladási folyamatának részeként ezzel a paraméterrel konszolidálhatja a tranzakciókat. Javasoljuk, hogy engedélyezze ezt a paramétert. Korábban Bizonylattranzakciók névvel **lett ki nevű**. |
| Ne aggregálja a visszárukat | Ha ez a beállítás be van jelölve, minden visszáru-tranzakció külön értékesítési rendelésként lesz feladva a kiskereskedelmi kimutatás feladása során. |

## <a name="batch-processing-parameters"></a>Kötegelt feldolgozás paraméterei

Az alábbi táblázat felsorolja a pénzügyi és fizikai tranzakciók feladására vonatkozó kötegelt feldolgozási paramétereket.

| Paraméter | Leírás |
|-----------|-------------|
| Párhuzamos kivonatok maximális száma | Ez a mező azt határozza meg, hogy hány kötegfeladatot kell egyszerre több kimutatásban elküldeni. |
| Rendelés feldolgozásához használt szálak maximális száma kimutatásonként | Ez a mező azt a szálszámot jelöli, amelyből a kimutatásfeladási kötegelt feladat egyetlen kimutatás értékesítési rendelésének létrehozására és számlázására használ. Az utasításfeladási **folyamat által használt szálak összesített számát úgy számítja ki a program, hogy megszorozza ennek a paraméternek az értékét a maximális párhuzamos kivonatfeladási paraméter értékével**. Ha túl nagy ez a paraméterérték, ez negatívan befolyásolja a kimutatásfeladási folyamat teljesítményét. |
| Egy aggregációban szereplő tranzakciós sorok maximális száma | Ez a mező azt határozza meg, hogy hány tranzakciósor szerepel egyetlen összesített tranzakcióban az új tranzakciók létrehozása előtt. Az összesített tranzakciók létrehozása különböző összesítési feltételek, például a vevő, az üzleti dátum vagy a pénzügyi dimenziók alapján történik. Ne feledje, hogy egyetlen tranzakció sorai nem lesznek felosztva különböző összesített tranzakciók között. Emiatt az összesített tranzakció sorai egy kissé magasabbak vagy alacsonyabbak lehetnek az olyan tényezők alapján, mint az egyedi termékek száma. |
| Üzleti tranzakciók ellenőrzéséhez szükséges szálak maximális száma | Ez a mező a tranzakciók ellenőrzésére használt szálak maximális számát határozza meg. A tranzakciók ellenőrzése kötelező lépés, ahhoz, hogy a tranzakciókat behúzható a kimutatásba. Akkor is meg kell határoznia egy ajándékutalvány-terméket az Ajándékutalvány **gyorslapon** **a Commerce paraméterek** oldalának Feladás lapján, ha a **szervezet** nem használ ajándékutalványt. |

Az alábbi táblázat felsorolja az előző tábla paramétereihez javasolt értékeket. Ezeket az értékeket a telepítés konfigurációja és a rendelkezésre álló infrastruktúra alapján kell tesztelni és testreszedni. A javasolt értékeket meghaladó értékek hátrányosan érinthetik a többi kötegelt feldolgozást is, ezért ellenőrizni kell azt.

| Paraméter | Ajánlott érték | Részletek |
|-----------|-------------------|---------|
| Párhuzamos kivonatfeladások maximális száma | <p>Állítsa be ezt a paramétert **a kimutatási feladatot futtató kötegcsoport számára elérhető kötegelt feladatok számára elérhető kötegelt feladatok számára**.</p><p>**Általános szabály:** Az Application Object Server (AOS) virtuális kiszolgálók számának megszorzása az AOS virtuális kiszolgálónként elérhető kötegelt feladatok számával.</p> | Ez a paraméter nem alkalmazható, ha **engedélyezve van a Retail utasítások – Nagykereskedelem beadagolási** funkció. |
| Rendelés feldolgozásához használt szálak maximális száma kimutatásonként | 4-es tesztértékek **kezdete**. Az érték általában nem haladhatja meg a **8-at**. | Ez a paraméter határozza meg az értékesítési rendelések létrehozásához és feladási szálaihoz használt szálak számát. Azt jelzi, hogy hány szál érhető el kimutatásonkénti feladásra. |
| Egy aggregációban szereplő tranzakciós sorok maximális száma | Az értékek tesztelésének kezdete **1000-től**. A Commerce Headquarters konfigurációjától függően a kisebb rendelések jobban megfelelőek lehetnek a teljesítmény szempontjából. | Ez a paraméter azt határozza meg, hogy a kimutatások feladása során hány sor szerepel az egyes értékesítési rendelésekben. A szám elérése után a sorok egy új rendelésre lesznek felosztva. Az értékesítési sorok száma nem egyez meg pontosan a megadott számmal, mert a felosztás az értékesítési rendelés szintjén történik. A szám azonban közel lesz a beállított számhoz. Ezzel a paraméterrel értékesítési rendeléseket lehet létrehozni olyan kiskereskedelmi tranzakciókhoz, amelyekhez nincs elnevezett vevő. |
| Üzleti tranzakciók ellenőrzéséhez szükséges szálak maximális száma | Javasoljuk, hogy **ezt a paramétert 4-re** állítsa, és csak akkor növelje, ha nem éri el az elfogadható teljesítményt. A folyamat által használt szálak száma nem haladhatja meg a kötegkiszolgáló számára elérhető processzorok számát. Ha túl nagy a szálak száma, ez más kötegelt feldolgozást is befolyásolhatja. | Ez a paraméter szabályozza az egy adott üzlet egyidejűleg érvényesíthető tranzakcióinak számát. |

> [!NOTE]
> Minden beállítás és paraméter, amely kapcsolódik a kimutatásfeladásokhoz, és meg van határozva a kiskereskedelmi áruházak és a **Kereskedelmi paraméterek** oldalon, alkalmazható a továbbfejlesztett kimutatásfeladási funkcióra.

## <a name="invoice-parameters"></a>Számlaparaméterek

Az alábbi táblázat felsorolja azokat a számlaparamétereket, amelyek a pénzügyi és fizikai tranzakciók feladására vonatkoznak.

| Paraméter | Leírás |
|-----------|-------------|
| Napló neve | Az értékesítési rendelés kifizetésére vonatkozó vevői kifizetési naplók létrehozásakor használt kifizetési napló neve. Ez a beállítás vonatkozik minden olyan rendelési kifizetésre, amely a pénztárnál, a hívásközpontban és az e-commerce csatornarendelésekkel lett feladva. |
| Számla neve | A kifizetési számla neve. |
| Dimenziók rangsorolása a fizetési módból | Ha ez a jelző engedélyezve van, a kifizetési naplók az üzlet dimenziói helyett a fizetési mód alapján rangsorolják a dimenziókat. |
| Adószámítási viselkedés | Ez a paraméter meghatározza a kimutatások feladása során létrehozott értékesítési rendelések számlázása során való működést:<ul><li>**Újraszámítás –** az adók újraszámítása.</li><li> **Ne számítsa** újra – a POS-ban kiszámított adóösszegek használata.</li></ul> |
| Napló neve | A visszatérítési vevői kifizetési napló létrehozásakor használt naplónév. Ez a beállítás a POS- és hívásközponti rendelésekhez feladott összes rendelési kifizetésre és az e-commerce csatornarendelésre vonatkozik. |

## <a name="statement-parameters"></a>Kimutatás paraméterei

Az alábbi táblázat felsorolja azokat a kimutatási paramétereket, amelyek a pénzügyi és fizikai tranzakciók feladására vonatkoznak.

| Paraméter | Leírás |
|-----------|-------------|
| Készlet lefoglalása a számítás során | Ha ez a paraméter engedélyezve van, a kimutatás számítása ideiglenesen lefoglalja a készletet, amíg a kimutatást fel nem adva meg nem történik. Ez a paraméter alapértelmezés szerint le van tiltva, mert így javítható a kimutatásszámítás teljesítménye. A frissített készletadatokat a Készletkönyvezés kötegelt feladat segítségével **lehet** kiszámítani. Ne feledje, hogy **a készlet feladása** kötegelt feladat már nem használatos, [ha](trickle-feed.md) engedélyezve van a kiskereskedelmi üzlet tranzakcióihoz kapcsolódó, főként becsatoláson alapuló rendelés létrehozása. |
| Számlálás letiltása szükséges | Ez a jelző letiltja a Leltározást a Commerce Headquarters feladása során. |
| Hiba pénzügyi dimenzióinak újraszámítása | Ha ez a paraméter engedélyezve van, a pénzügyi dimenziók a későbbi kimutatásfeladások során újra kiértékelhetőek, ha a kimutatás feladása sikertelen. |
| Visszáruüzlet pénzügyi dimenzióinak használata | Ha ez a paraméter engedélyezve van, akkor az eredeti tranzakció pénzügyi dimenziói helyett az üzlet pénzügyi dimenzióit használja fel a kapcsolt visszárurendelések. |
| Visszáruk kapcsolatának megszüntetése | Ha ez a paraméter engedélyezve van, a kimutatás eredményként hozhatja létre a fel nem adott értékesítéseket blind returns értékként. Ez a paraméter alapértelmezés szerint le van tiltva, és javasoljuk, hogy ne legyen engedélyezve. |
| Kerekítési különbözet felezésének letiltása | Ez a paraméter letiltja a tranzakciós kifizetés és a bruttó összeg kerekítési különbözetének feladását a kifizetések feldolgozása során. |
| Vevői letétek automatikus kiegyenlítése | Ha ez a paraméter engedélyezve van, a vevői kivonat feladása során feladott vevői betéteket a vevő nyitott tranzakciói egyenlítik ki. |
| Pénztári készpénzkezelési egyeztetés engedélyezése és használata | Ha ez a paraméter engedélyezve van, a készpénzkezelési egyeztetés a POS-terminálon történik, és az értékek átmennek a kiskereskedelmi pénzügyi kimutatás feladására, hogy kimutatássorokat hozzanak létre. |
| Főkönyvi bizonylat részletezési szintje | Ez a paraméter meghatározza a pos rendszerből származó kijelölt tranzakciók főkönyvi bizonylatán szereplő részletességi szintet. A tranzakciótípusok közé tartoznak a bevételek, a kiadások és az engedmények. Engedmények esetén ezt a paramétert csak akkor veszi figyelembe a rendszer, ha egy időszaki kedvezmény számlaszáma és a rendes engedmény számlaszáma nem ugyanaz. Hacsak nem kötelező megadni a részleteket, **akkor ezeknél** a feladásnál az összegzés az ajánlott érték. Amikor meg van adva az összegző szintű feladás, **nem lesz kitöltve a TransactionDiscountTrans.RecID** tábla. A Commerce 10.0.27 verzióverzió kiadásában a jelzőt átnevezték és áthelyezték. Korábban Részletezett szint **nevű volt**, és a **Készlet frissítése szakaszban** volt. |
