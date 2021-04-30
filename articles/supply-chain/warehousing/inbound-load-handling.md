---
title: Beszerzési rendelések bejövő rakományának kezelése a raktárban
description: Ez a témakör a beszerzési rendelések bejövő rakományának raktárkezelési folyamatát írja le.
author: omulvad
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 62317f7e42c5392dce32a667f05f22e5c970abc7
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910015"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Beszerzési rendelések bejövő rakományának kezelése a raktárban

Ez a témakör a beszerzési rendelések bejövő rakományának raktárkezelési folyamatát írja le.

Minden bejövő rakományhoz a rendszernek már tartalmaznia kell egy kapcsolódó értékesítési rendelést, és tartalmazhatja a kapcsolódó rakományspecifikációkat és/vagy szállítási tervet is. A bejövő terhelések létrehozásával és kezelésével kapcsolatos további tudnivalókat lásd: [Üzleti folyamat: bejövő rakományok szállítási tervezése](/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Áttekintés: Bejövő rakományok létrehozása, regisztrálása és fogadása

A következő ábra a beszerzésirendelési-mennyiséggel rendelkező bejövő rakományok kezelésének jellemző folyamatát mutatja, amikor azok a raktárba érkeznek.

![A bejövő rakományok kezelési folyamata](media/inbound-process.png "A bejövő rakományok kezelési folyamata")

1. **A szállító megerősíti a beszerzési rendelést.**

    A folyamat akkor indul el, amikor egy beszerzési rendelést bevittek a rendszerbe, majd kiszállították egy szállítónak, aki megerősíti a rendelést. A beszerzési rendelésnek léteznie kell a bejövő rakomány rekordjának létrehozása előtt. A bejövő rakományt azonban akkor is létre lehet hozni, ha a rendelés még nincs visszaigazolva. További tájékoztatás: [Beszerzési rendelések jóváhagyása és megerősítése](../procurement/purchase-order-approval-confirmation.md).

1. **A bejövő rakomány rekordja az érkezés és annak tartalma megtervezéséhez jön létre.**

    A bejövő rakományrekord egy vagy több beszerzési rendelés szállítói szállítmányát jelöli. A rakomány várhatóan egy fizikai szállítási egységként (például teherautónyi) fog érkezni a raktárba. A bejövő rakományrekordot tervezési célokra használja a program, és lehetővé teszi, hogy a logisztikai koordinátor nyomon kövesse a haladását a szállítótól. A rendszer a rendelési sorok mennyiségeinek regisztrálására, valamint az előrehaladás raktári műveletekkel, például az bevételezés és az elraktározási munka történő kezelésére használja. A rakományokat automatikusan vagy manuálisan is létre lehet hozni, és egy beszerzési rendelésen vagy egy előzetes szállítási értesítőn (ASN) is alapulhatnak. További tájékoztatás: [Bejövő rakomány létrehozása és módosítása](/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **A szállító visszaigazolja a rakomány kiszállítását.**

    Amikor a szállító feladja a rakományt, a fogadó raktár logisztikai koordinátora megerősíti a rakomány szállítását. Ha a fogadó vállalat a **Szállításkezelés** modult használja, akkor a bejövő szállítmány visszaigazolása kiváltja a bejövő rakományokhoz társított egyéb rakományelosztási folyamatokat. További tájékoztatás: [Rakomány jóváhagyása szállításra](/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **A rakomány megérkezik a raktárba, és a dolgozók regisztrálják a mennyiségeket.**

    Amikor egy teherautónyi rakomány megérkezik a raktárba, a raktári dolgozók regisztrálják a rakomány mennyiségét. A **Raktárkezelés** modul használata esetén a dolgozók a mobileszközök segítségével végzik a regisztrációt. A további tudnivalókat lásd a [Termékbevételezés összevetése a beszerzési rendelésekkel – a regisztráció](../procurement/product-receipt-against-purchase-orders.md#registration) és [Egy bejövő rakománnyal érkező mennyiségek regisztrálása](#register-item-quantities-arriving) szakaszokat.

1. **A regisztrált rakományok feladása a beszerzési rendelésekkel szemben történik.**

    Miután a rakománymennyiségek regisztrálva lettek, ezeknek a mennyiségeket termékként kell bevételezni vagy feladni, hogy bekerüljenek a vállalat készletfőkönyvébe a fizikai készlet növekedésének rögzítéséhez. A további tudnivalókat lásd [Termékbevételezés összevetése a beszerzési rendelésekkel – termékbevételezés](../procurement/product-receipt-against-purchase-orders.md#product-receipt) és [Regisztrált termékmennyiségek feladása beszerzési rendelésekkel szemben](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Bejövő rakománnyal érkező cikkmennyiség regisztrálása

A Microsoft Dynamics 365 Supply Chain Management számos operatív megközelítést támogat a megrendelt termékek érkezésének regisztrálásához. Így a rendszer beállítható úgy, hogy megfeleljen a specifikus üzleti követelményeknek. Ez a szakasz bemutatja, hogyan regisztrálhatók a bejövő cikkmennyiség egy mobileszköz használatával, amikor a speciális raktárkezelés be van kapcsolva a rendszerben. Azonban van egy alternatív folyamat, amely a mobileszköz helyett a cikkérkezési-napló használatán alapul. Ezen folyamattal kapcsolatos további információért lásd: [Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával](tasks/register-items-advanced-warehousing.md).

Amikor egy bejövő rakomány először megérkezik a raktárba, a raktári dolgozóknak regisztrálniuk kell a szállítmányban szereplő cikkmennyiségeket. Általában kézi olvasókat használnak. Ez a munkafolyamat csak akkor érhető el, ha a rendszerben a következő cikkek elérhetők:

- **Olyan bejövő rakományrekord, amely leírja a szállítmányban várható mennyiséget**

    A szállító általában megerősíti a bejövő rakomány rekordját, mielőtt a szállítmány megérkezne a raktárba. Ennek megfelelően a rakomány állapota _Szállítva_. A raktári dolgozók azonban a _Nyitott_ vagy _Bevételezett_ állapotú rakományokhoz is regisztrálhatnak cikkmennyiségeket.

- **A mobileszköz betöltést támogató menüje**

    A [Raktárkezelés mobilalkalmazás](../warehousing/install-configure-warehouse-management-app.md) mobileszközökhöz a következő munkalétrehozási folyamatokat támogatja:

    - Rakomány – cikk bevételezése
    - Rakomány – cikk bevételezése és eltárolása
    - Vegyes azonosítótábla fogadás, amelyen a mobileszköz menüelemének **Forrásdokumentum-sor azonosítási módja** mezője _Rakomány – cikk bevételezése_. A további tudnivalókat lásd: [Vegyes azonosítótábla fogadás](mixed-license-plate-receiving.md).
    - Vegyes azonosítótábla fogadás és betárolás, ahol a mobileszköz menüelemének **Forrásdokumentum-sor azonosítási módja** mezője _Rakomány – cikk bevételezése_. A további tudnivalókat lásd: [Vegyes azonosítótábla fogadás](mixed-license-plate-receiving.md).

    > [!NOTE]
    > A folyamattól függetlenül a rendszer olyan munkát hoz létre hoz létre, amelyek a bevételezési helyen regisztrált mennyiségeket a szokásos tárolási helyre helyezi. Amikor a _Rakomány – cikk bevételezése és eltárolása_ vagy _Vegyes azonosítótábla bevételezése és eltárolása_ folyamatot használja a program, a rakományt regisztráló dolgozó is utasítást kap az eszköztől, hogy az elraktározási munkát a regisztrációs feladat részeként végezze el. Ezzel szemben a _Rakomány – cikk bevételezése_ és _Vegyes azonosítótábla fogadása_ folyamatok esetében a feltételezés az, hogy az elraktározási munka a regisztrációs feladattól elkülönítve fog történni.

- **Olyan munkasablon, amely meghatározza a kitárolási és betárolási munkát a bejövő rakományokhoz**

    Ez a cikk a korábbi cikkekhez kapcsolódik. Legalább egy munkasablonnal kell rendelkeznie a _Beszerzési rendelés_ munkarendelés típushoz és tartalmaznia kell kitárolási/betárolási munkatípusokat.

A mobileszköz átvezeti a rakomány mennyiségi regisztrálásához szükséges folyamaton a raktár fogadó adminisztrátorát. A folyamatnak legalább a következő lépéseket kell végrehajtania az egyes rakományazonosítók esetében:

1. Adja meg a rakomány azonosítóját.
2. Adja meg a bevételezett cikk cikkszámát.
3. Adja meg a bevételezett cikkszám mennyiségét.
4. Az azonosítótábla számának megadása a cikkek kezdeti helyén, ha a rendszer nincs beállítva, hogy automatikusan létrehozza ezt a számot.
5. Koppintson az **OK** gombra.

Miután a dolgozó befejezte ezeket a lépéseket, a rendszer a megfelelő entitásokon végrehajtja a következő frissítéseket, feltéve, hogy a beszerzési rendelési sor mennyisége egy rakományhoz érkezett, és az összes rakománymennyiség regisztrálva van:

| Entitás | Frissítések | Jegyzet |
|---|---|---|
| Betöltés | A program frissíti a **Munka létrehozva mennyiség** mezőjét a rakománysoron a regisztrált mennyiség megjelenítéséhez. | A **Rakomány állapota** értéke továbbra is _Leszállított_ vagy _Nyitott_ , ha a rakományhoz nem állítottak be szállítási visszaigazolást. Ha legalább egy elraktározási munka elindult, akkor az _folyamatban_ állapotra módosul. |
| Olyan beszerzési rendeléshez tartozó készlettranzakció, amelyhez kapcsolódó rakomány-mennyiségek vannak regisztrálva |<p>Az alábbi mezőket frissíti a program:</p><ul><li>A <b>Bevételezés</b> mező be van állítva <i>Regisztrált</i> értékre.</li><li>A <b>Hely</b> mezőt a program a bevételezési tároló helykódjával frissíti. (Ez a kód az egyes raktárak <b>Alapértelmezett bevételezési hely</b> mezőjében van megadva.)</li><li>Az <b>Azonosítótábla</b> mező a regisztráció során megadott vagy létrehozott azonosítótábla-számmal frissül.</li><li>A <b>Rakományazonosító</b> mező értéke annak a rakománynak a számával lesz frissítve, amelyhez a mennyiség regisztrálva van. (Lásd a megjegyzést.)</li></ul> | A beszerzési rendelési készlettranzakciók és a rakománnyal szemben regisztrált mennyiségek közötti kapcsolatot a 10.0.9 verzióban vezették be opcionális funkcióként, amelynek neve _Beszerzésirendelés-készlettranzakciók társítása egy rakománnyal_. Ez a funkció különösen olyan folyamatok esetében hasznos, ha a beszerzett áruk egyetlen rendelését több rakományként szállítják, vagy ha a rakomány több beszerzési rendeléshez tartalmaz mennyiségeket. |
| Raktári elraktározás | A munka egy munkasablon alapján jön létre, és utasítja a dolgozót, hogy helyezze át a regisztrált mennyiségeket a bevételezési helyről egy szabályos tárolási helyre. | A tárolóhely választását az Elraktározási helyutasítás vezérli. Ha nincs meghatározva helyutasítás, akkor a munka elraktározási helye üres. |

Ne felejtse el, hogy a raktári dolgozók egy vagy több társított rakománnyal regisztrálhatnak egy beszerzési rendelést a _Rakomány – cikk bevételezése_ folyamat használata nélkül. A következő módszerek állnak rendelkezésre:

- **A mobileszközön:** Használja a _Beszerzésirendelés-sor bevételezése_ és _Beszerzésirendelés-sor bevételezése és betárolása_ folyamatokat. (Ha egynél több rakomány van a beszerzésirendelés-sor mennyiségéhez, a dolgozó nem használhatja a _Beszerzésirendelés-sor bevételezése_ folyamatot. Helyette a dolgozó utasítást kap arra, hogy a _Rakomány – cikk bevételezése_ folyamathoz társított eszközműveletet használja.)
- **Az ügyfélen:** A cikkek érkeztetési naplója használható.
- **Az ügyfélen:** A beszerzési rendelés sorából elérhető **Regisztráció** művelet használható.

> [!NOTE]
> Ha a beszerzési rendelés bevételezését az előző módszerek bármelyikével regisztrálják, akkor a beszerzési rendelés készlettranzakciók és a rakomány között nem jön létre társítás, még akkor sem, ha be van kapcsolva a _Beszerzésirendelés-készlettranzakciók társítása egy rakománnyal_ funkció. Ennek a szabálynak az egyik kivétele a **Beszerzésirendelés-sor bevételezése** lehetőség, és csak egy rakománynak van a _Bevételezett_ állapottól eltérő állapota a rendelési sorhoz.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Eltérések kezelése a bejövő rakománymennyiségek regisztrálásakor

A raktári dolgozók részleges rakománymennyiség-bevételezés regisztrációt végezhetnek. A részlegesen betöltött mennyiségek egy része egy külön készlettranzakciót hoz létre, ahol a bevételezés állapota _Regisztrált_ a regisztrált mennyiséghez, és az adagazonosító a származó beszerzésirendelés-sorra hivatkozik.

#### <a name="load-under-receiving"></a>Kisebb mennyiségű rakomány bevételezése

Amikor egy rakomány érkezik, ha a cikkmennyiség kisebb, mint a rakományrekordban szereplő mennyiség, a raktári befogadó személyzet közvetlenül az ügyfélen is képes feldolgozni, nyugtázva ezt az eltérést úgy, hogy a terhelési sor mennyiségét csökkenti, hogy az megfeleljen a beérkezett és regisztrált tényleges mennyiségnek.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Nagyobb mennyiségű rakomány bevételezése

Túlbevételezésre akkor kerül sor, amikor a rakomány megérkezik, és a cikkmennyiség túllépi a várt terhelésisor-mennyiséget. Megadhatja, hogy a rakomány regisztrálásakor milyen mértékű túlbevételezést engedélyez a program, ha egyáltalán engedélyezi.

A megfelelő mobileszköz menüelemek **Terhelés túlbevételezése** mezője segítségével szabályozhatja, hogy mi történjen, ha a raktári dolgozó megpróbál egy túlszállítást regisztrálni. Ez a mező olyan mobileszköz-menüelemekhez érhető el, amelyek a következő munkalétrehozási folyamatokat használják:

- Rakomány – cikk bevételezése
- Rakomány – cikk bevételezése és eltárolása
- Vegyes azonosítótábla fogadás (amikor a mobileszköz menüelemének **Forrásdokumentum-sor azonosítási módja** mezője _Rakomány – cikk bevételezése_)
- Vegyes azonosítótábla fogadás és betárolás (amikor a mobileszköz menüelemének **Forrásdokumentum-sor azonosítási módja** mezője _Rakomány – cikk bevételezése_)

Az alábbi táblázatban a **Terhelés túlbevételezése** mezőhöz rendelkezésre álló beállítások magyarázata látható.

| Érték | Leírás |
|---|---|
| Engedélyezés | A dolgozók regisztrálhatják azokat a mennyiségeket, amelyek meghaladják a fennmaradó nem regisztrált mennyiséget a kiválasztott rakományhoz, de csak akkor, ha a teljes regisztrált mennyiség nem haladja meg a rakományhoz társított beszerzésirendelés-sor mennyiségét (a túlszállítás százalék módosítását követően). |
| Zárolás | <p>A dolgozók nem regisztrálhatják az olyan mennyiségek bevételezését, amelyek meghaladják a kiválasztott rakomány fennmaradó nem regisztrált mennyiségét (a túlszállítási százalékhoz igazítás után). Az a dolgozó, aki megpróbálja regisztrálni a beérkezőket hibaüzenetet kap, és mindaddig nem fog tudni folytatni, amíg nem jegyez be olyan mennyiséget, amely nem egyezik meg vagy nem kevesebb a fennmaradó nem regisztrált rakomány mennyiségénél.</p><p>Alapértelmezés szerint a program átmásolja a terhelési sor túlszállítási százalékértékét a kapcsolódó beszerzési rendelési sorból. Amikor a <b>Terhelés túlbevételezése</b> mező értéke <i>Zárolás</i>, a rendszer a túlszállítás százalékos értéke alapján számítja ki a terhelési sorhoz regisztrálható teljes mennyiséget. Ez az érték azonban a szükség esetén felülírható az egyes rakományokhoz. Ez a viselkedés akkor válik hasznossá, amikor olyan folyamatokat kap, amelyekben túlzott mennyiség, amely megfelel a túlszállítás százalékának aránytalanul van elosztva több rakomány között. Egy példaforgatókönyv:</p><ul><li>Több rakomány van egy beszerzésirendelés-sorhoz.</li><li>A beszerzési rendelés sorának túlszállítási százaléka több, mint 0 (nulla).</li><li>Mennyiségek lettek már regisztrálva van egy vagy több rakománnyal szemben a túlszállítási százalék figyelembe vétele nélkül.</li><li>A túlszállítási mennyiség a legutóbbi rakományhoz érkezik.</li></ul><p>Ebben a helyzetben egy mobileszköz csak akkor használható, ha az utolsó rakományhoz tartozó túlmennyiség regisztrálásához ha a raktári felügyelő a megfelelő terhelési sorhoz az alapértelmezett értékről olyan értékre növeli a túlszállítási százalékot, amely elég nagy ahhoz, hogy a teljes túlszállítás regisztrálható legyen a végső rakományhoz.</p> |
| Zárolás csak a lezárt rakományokhoz | A dolgozók túlfogadhatják a nyitott rakományokhoz tartozó rakománysor mennyiségeket, de olyan terhelésekhez nem, amelyek állapota _Fogadott_. |

> [!NOTE]
> A **Terhelés túlbevételezése** mező alapértelmezett értéke _Engedélyezés_. Ha ez az érték van használatban, akkor a viselkedés megfelel a szokásos működésnek, amely a 10.0.11 verzióban a _Rakomány mennyiségek túlbevételezése_ funkció bevezetése előtt állt rendelkezésre.

### <a name="put-away-the-registered-quantities"></a>A regisztrált mennyiségek elraktározása

Amikor a regisztráció befejeződött a mobileszközön, a _Mennyiség bevételezésének regisztrációja_ művelet frissíti a készlet-és raktári rekordokat, hogy a mennyiségek most a fogadó raktárban legyenek, és elérhetők a foglalásra. A vállalatok raktári műveletei azonban általában megkövetelik, hogy a mennyiségek a fogadó dokkból a szokásos raktári tárhelyre legyenek áthelyezve, hogy a későbbi kitárolási folyamatok megtörténhessenek. Az elraktározással kapcsolatos utasítások rögzítése az elraktározási munkafolyamatban történik, amely automatikusan létrejön, amikor a bejövő rakomány regisztrálva van beérkezettként.

Amikor a raktári dolgozó befejezte az elraktározási munkát, a rendszer rögzíti és nyomon követi az eredményeket számos entitás frissítésével, ahogyan azt a következő táblázat összefoglalja.

| Entitás | Frissítések | Jegyzet |
|---|---|---|
| Betöltés | <p>Az alábbi mezőket frissíti a program:</p><ul><li>A <b>Rakományállapot</b> értéke <i>Folyamatban</i> állapotúra módosul.</li><li>A <b>Munka állapota</b> értéke <i>A munka 100,00%-ban befejezve</i> értékre módosul.</li></ul> | A **Rakományállapot** értéke _Folyamatban_ állapotúra módosul, amikor a dolgozó legalább egy elraktározási munkasorhoz elindítja az elraktározási feladatot. |
| Azon munkafolyamatok készlettranzakciói, amelyekhez a társított mennyiségek eltárolásra kerülnek | A program frissíti a **Bevételezés** és a **Hely** és más kapcsolódó mezőket és, hogy azok bevételezési helyről a tárolóhelyre irányuló mozgást tükrözzék. | A beszerzési rendelés készlettranzakció **Bevételezési állapot** értéke továbbra is _Regisztrálva_ értéken marad. |
| Raktári elraktározás | A **Munk állapota** értéke _Lezárt_ értékre módosul. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>A regisztrált termékmennyiségek feladása a beszerzési rendelésekkel szemben

Miután a bejövő termékmennyiség regisztrálva van a rendszerben, elérhetővé válik az értékesítési és egyéb kimenő és belső műveletekkel kapcsolatos foglalások számára. A rendszer azonban még nem frissíti a készlet- (ideiglenes) számlákat. Ez a frissítés csak akkor történhet meg, ha a műveleti csoport feladja a regisztrált termékbevételezéseket.

Egy olyan lap megnyitásához, ahol feladhatják a termékbevételezést, a műveleti csoport tagja a következő lépések _egyikét_ követheti:

- Nyissa meg a megfelelő terhelési rekordot, majd válassza ki a **Termékbevételezés** műveletet.
- Nyissa meg a **Raktárkezelés \> Ismétlődő feladatok \> Termékbevételezések frissítése** menüt majd a **Rakomány azonosítója** mezőben adja meg a feladni kívánt rakományt.
- Nyissa meg a kapcsolódó beszerzési rendelést, majd válassza ki a **Termékbevételezés** műveletet.
- Ugorjon a következőre: **Beszerzés és forrás \> Beszerzési rendelések \> Termékek bevételezése \> Termékbevételezési munka feladása**.

A **Termékbevételezés** művelet, amely elérhető a **Rakomány** lapon (és a frissítési feladat megfelelő lapján, a **Termékbevételezések frissítése** oldalon) a termékbevételezési mennyiségeket csak olyan beszerzésirendelés-mennyiségekhez frissítheti, amelyek állapota _Regisztrált_. Ugyanakkor a **Beszerzési rendelés** lapon elérhető **Termékbevételezés** művelet tartalmazhatja mindkét feldolgozási állapotú mennyiségeket (_Megrendelve_ és _Regisztrált_). Ezenkívül a termék bevételezési feladása hatókörét további paraméterekkel is szabályozhatja, például a _Most Bevételezett mennyiség_ és _Regisztrált mennyiség és szolgáltatások_.

Csak a _Visszaigazolva_ állapotú rendelések lehetnek termékbevételezéssel feladva. Nem visszaigazolt beszerzési rendelések esetén a **Termékbevételezés** művelet nem érhető el.

### <a name="post-registered-quantities-from-the-load-page"></a>Regisztrált mennyiségek feladása a Rakomány oldalról

A regisztrált mennyiségek termékbevételezés-feladásához a **Terhelés** lapról a következő előfeltételeknek kell teljesülniük:

- A rakománynak legalább egy _Regisztrált_ állapotú mennyiségi egységgel kell rendelkeznie.
- A rakomány állapota _Szállítva_ kell legyen.
- A rakományhoz társított beszerzési rendelésnek _Visszaigazolt_ állapotúnak kell lennie.

> [!NOTE]
> Ha a rakomány állapota nem a _Szállított_ értékre van állítva, akkor a rendszer automatikusan megerősíti a rakományt, mielőtt futtatja a termékbevételezés frissítését. (A terhelés állapota akkor van _Szállítva_ értékre állítva , amikor a felhasználó regisztrálja a rakomány bejövő szállítmányát.)

A kiválasztott rakományhoz kapcsolódó érkezési regisztrációk termékbevételezés-feladásához a dolgozó kiválasztja a szállítólevél **Termékbevételezés** műveletet a **Rakomány** oldalon. A megnyitott lap a következő fontos részletekkel rendelkezik:

- A **Mennyiség** mező a **Paraméterek** szakaszban a **Beállítások** lapon a _Regisztrált mennyiséget_ jeleníti meg. Itt nem érhetők el egyéb lehetőségek.
- Az **Áttekintés** gyorslap rácsa felsorolja a kiválasztott rakományhoz tartozó összes beszerzési rendelést.
- A **Sorok** gyorslap rácsa felsorolja azokat a rendelési sorokat, amelyekhez regisztrált mennyiség tartozik.

> [!NOTE]
> A **Sor** lapon megjelenő rendelési sorok mennyiségét a program eltérően számítja ki attól függően, hogy a _Több termékbevételezés engedélyezése terhelésenként_ funkció be van-e a kapcsolva az Ön Supply Chain Management verziójában.
>
> | Verzió | Számítás |
> |---|---|
> | A 10.0.10 verzióelőtti verziók, valamint az olyan újabb verziók esetében ahol a _Több termékbevételezés engedélyezése terhelésenként_ funkció nincs bekapcsolva | A sor mennyisége az _adott beszerzésirendelés-sor_ összes regisztrált mennyisége, függetlenül attól, hogy a regisztráció több rakományon, a rakománytól függetlenül, egy mobileszközről vagy az ügyfélről történt-e. |
> | A 10.0.10 verzió és újabb verziók esetében ahol a _Több termékbevételezés engedélyezése terhelésenként_ funkció be van kapcsolva | A sor mennyisége az összes olyan regisztrált mennyiség összege _rakományrekordhoz_, amelyről a **Termékbevételezés feladása** műveletet kezdeményezték. |

Amikor a felhasználó az **OK** gombra kattint a bevételezés feladásának jóváhagyásához, a rendszer a megfelelő entitások esetében a következő kulcsfontosságú frissítéseket végzi.

| Entitás | Frissítések |
|---|---|
| Annak a beszerzési rendelésnek a készlettranzakciója, amelybe a sorban szereplő mennyiségek belekerültek a feladási hatókörben | <p>A program frissíti a következő mezőket (de több más frissítést is történik):</p><ul><li>A <b>Bevételezés</b> mező be van állítva <i>Fogadott</i> értékre.</li><li>A <b>Tényleges dátum</b> mező a feladás dátumával frissül.</li></ul> |
| Az a rakomány, amelyről a felhasználó a termékbevételezést feladta | A terhelések frissítései a használt verziótól és a **Több termékbevételezés engedélyezése terhelésenként** mező beállításától függenek. A szabályok leírása a szakasz későbbi részében látható táblázatban található. |

A **Több termékbevételezés engedélyezése rakományonként** lehetővé teszi a vállalatoknak bejövő rakományok bevételezési szabályzatának kiválasztását. A vállalatok működési folyamataitól függően dönthetnek úgy, hogy engedélyezik vagy tiltják több termékbevételezés feladását ugyanarról a rakományról. Azt ajánljuk, hogy a logisztikai vezető a következő értékek egyikére állítsa be a **Több termékbevételezés engedélyezése terhelésenként** mezőt:

- **Nem** – Akkor válassza ezt az értéket, ha a raktárban lévő adminisztrátorok mindig az összes olyan rendelési mennyiséget rögzítik, amelyek az egyes rakományhoz érkeznek egy megadott időkereten belül. Ha a rakománymennyiségek nincsenek regisztrálva, akkor a rendszer azt feltételezi, hogy nem érkeztek meg vagy nem voltak a rakományban, ezért nem kell azokat a rakomány részének tekinteni. A rakományból futtatott termékbevételezés-feladás ugyanezt a feltételezést alkalmazza. A termékbevételezés azon túl, hogy az összes regisztrált mennyiséget frissíti (ez a fő funkciója) – késznek nyilvánítja a rakományt és lezárja további feldolgozásra. Ebben az esetben a terhelési sorok mennyiségei automatikusan frissülnek a regisztrált mennyiségekre, a regisztrált mennyiség nélküli terhelési sorok törlődnek, és a rakomány állapota _Beérkezett_ állapotra módosul.
- **Igen** – Akkor válassza ezt az értéket, ha a raktári fogadó adminisztrátoroknak több időre van szükségük a beérkezett rakomány összes mennyiségének regisztrálásához, de időközben szükséges a már regisztrált mennyiségek termékbevételezés-feladása. Ebben az esetben a logisztikai vezető a termékbevételezés-feladási feladatának futtatása után is nyitva szeretné hagyni a rakományt, hogy a fennmaradó rakomány-mennyiségek folyamatos regisztrálása és a termékbevételezés-feladása megtörténhessen a főkönyvbe.
- **Rákérdezés** – Akkor válassza ezt az értéket, ha a fogadási eljárások vegyesek, és a termékbevételezés feladásakor döntés szükséges.

A következő táblázat összefoglalja, hogy milyen hatásai vannak a **Több termékbevételezés engedélyezése rakományonként** beállításnak.

| Több termékbevételezés engedélyezése rakományonként | Rakománymennyiség | Rakomány állapota | Jegyzet |
|---|---|---|---|
| Ha ez a mező nem érhető el (10.0.10 előtti verziók) | <p>A rakomány mennyisége úgy van beállítva, hogy az a regisztrált mennyiséggel egyenlő.</p><p>Ha a rakomány mennyisége 0 (nulla), ami azt jelenti, hogy nem történt regisztráció, akkor a program törli a rakománysort.</p><p>Ha nincs rakománysor a rakományhoz, akkor a rendszer törli a rakományt.</p> | _Bevételezve_ | Ha a rendelési sor regisztrált mennyiségéhez több rakomány is tartozik, akkor a rendszer csak annak a rakománynak az állapotát jeleníti meg, amelynek a feladása megtörtént és állapota _Fogadott_ értékre lett frissítve. |
| Nincs | <p>A rakomány mennyisége úgy van megadva, hogy az megegyezzen azzal a mennyiséggel, amely társítva van a rakományazonosítóhoz.</p><p>Ha nincs megadva rakományazonosító készlettranzakcióhoz esetében, a viselkedés megfelel a 10.0.10. verzió előtti verziók viselkedésének.</p> | _Bevételezve_ | |
| Igen | Nincs frissítés | _Beérkezett_, ha a teljes regisztrált rakománymennyiség nagyobb vagy egyenlő, mint a rakomány mennyisége | |
| Igen | Nincs frissítés | _Szállítva_ vagy _Folyamatban_, ha a teljes regisztrált rakománymennyiség kisebb, mint a rakomány mennyisége | |

Miután a **Rakomány állapota** mező be van állítva _Fogadott_ értékre, nem hajtható végre több termékbevételezés-feladás ahhoz a rakományhoz. A dolgozó azonban a következő feltételek teljesülése esetén regisztrálhat a fennmaradó rendelési mennyiséget a fogadott rakománnyal szemben. (A további tudnivalókat lásd: [Rakományok túlbevételezése](#load-over-receiving) a témakör korábbi részében.)

- A Supply Chain Management verziója régebbi a 10.0.11 verziónál.
- A _Rakomány mennyiségek túlbevételezése_ funkció be van kapcsolva, és a **Rakománysor túlbevételezése** mező a mobileszköz menüjében a rakománycikk bevételezési műveletéhez _Engedélyezve_ értékre van állítva.

További regisztrált rakománymennyiségek termékbevételezés-feladásához egy _Fogadott_ állapotú rakományhoz a felhasználónak a társított beszerzési rendelésből kell futtatnia a feladási műveletet.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Regisztrált mennyiségek feladása a Beszerzési rendelés oldalról

Regisztrált mennyiségek termékbevételezés-feladásához a **Beszerzési rendelés** oldalról a felhasználó a következő feladatokat hajtja végre, mielőtt kiválasztja a **Termékbevételezés** műveletet:

- A **Mennyiség** mezőt a **Paraméterek** szakaszban a **Beállítások** lapon _Regisztrált mennyiség_ értékre állítja.
- A **Termékbevételezés** mezőbe beírja a feladás során szerepeltetett beszerzési rendelések számát.

> [!NOTE]
> A sormennyiség, amely szerepeltetve lesz a feladás hatókörében a rendelési sor teljes regisztrált mennyisége, függetlenül attól, hogy a regisztráció több rakományon, a rakománytól függetlenül, egy mobileszközről vagy az ügyfélről történt-e. Ugyanezt a szabályt kell alkalmazni, ha a termékbevételezés feladása rakományból van végrehajtva, ha az olyankor történik meg, amikor a **Több termékbevételezés engedélyezése rakományonként** mező nem érhető el, vagy nincs engedélyezve.

Amikor a felhasználó az **OK** gombra kattint a bevételezés feladásának jóváhagyásához, a rendszer a megfelelő entitások esetében a következő kulcsfontosságú frissítéseket végzi.

| Entitás | Frissítések |
|---|---|
| Annak a beszerzési rendelésnek a készlettranzakciója, amelybe a sorban szereplő mennyiségek belekerültek a feladási hatókörben | <p>A program frissíti a következő mezőket (de több más frissítést is történik):</p><ul><li>A <b>Bevételezés</b> mező be van állítva <i>Fogadott</i> értékre.</li><li>A <b>Tényleges dátum</b> mező a termékbevételezés feladása művelet dátumával frissül.</li></ul> |
| Betöltés | A rakományok frissítései attól függenek , hogy elérhetők-e és engedélyezve van-e a **Több termékbevételezés engedélyezése rakományonként** mező. A szabályok leírása a következő táblázatban található. |

A következő táblázat összefoglalja, hogy milyen hatásai vannak a **Több termékbevételezés engedélyezése rakományonként** beállításnak.

| Több termékbevételezés engedélyezése rakományonként | Rakománymennyiség | Rakomány állapota | Jegyzet |
|---|---|---|---|
| Ha ez a mező le van tiltva vagy nem érhető el (10.0.10 előtti verziókban) | Nincs frissítés | Nem történik frissítés. ( Az állapot _Nyitott_, _Szállítva_ vagy _Folyamatban_ marad.) | Mivel a termékbevételezés feladása a beszerzési rendelésből történik, a frissítési logikának nincs információja a hatályában lévő regisztrált mennyiségektől és a rakományokról, amelyekkel szemben regisztrálva lett. Ezért az állapot frissítéséhez nem tudja kiválasztani a rakományt. |
| Engedélyezett | Nincs frissítés | <p>Az alábbi műveletek egyike történik:</p><ul><li>Az állapot <i>Fogadott</i> értékre módosul, ha a beszerzési rendelés készlettranzakciók teljes fogadott és a beszerzett mennyisége nagyobb vagy egyenlő a hozzá társított rakomány mennyiségénél.</li><li>Az állapot <i>Nyitott</i>, <i>Szállítva</i> vagy <i>Folyamatban</i> marad, ha az előző feltétel nem teljesül a rakomány minden sorához.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Válassza ki a megfelelő termékbevételezés-feladás beállítást a logisztikai műveleteihez

A korábban leírt módon a rendszer két termékbevételezés-feladási lehetőséget ajánl. A lehetőségek a következő helyekről érhetők el:

- A **Rakomány** oldalról vagy a **Raktárkezelés \> Időszakos feladatok** menüből frissítési feladatként
- A **Beszerzési rendelés** lapon, illetve a **Beszerzés és forrás \> Beszerzési rendelések \> Termékek bevételezése** menüből feladatként

Azoknak a vállalatoknak, amelyek a bejövő rendelések szállítmányozásának és raktározásának tervezésére és kezelésére raományokat alkalmaznak, a következő funkciók használatát ajánljuk, amelyek a rakományok kezelésére szolgálnak:

- **Rakomány – cikk bevételezése** műveletek a raktár mobileszközein a rakománnyal szemben a beérkezett termék mennyiségének regisztrálásához
- **Termékbevételezés feladása** a rakományból kezdeményezett műveletek a készletfőkönyv frissítéséhez

> [!NOTE]
> A többi mennyiségi regisztrációra és a termékbevételezés feladására szolgáló funkció a kapcsolódó bejövő üzemeltetési folyamatok támogatására használható. Ha azonban ezeket a dedikált rakományorientált funkciókkal felváltva használja, akkor veszélyeztetheti a rakomány rekordjainak pontosságát, és így a rakományelosztási folyamatok zökkenőmentes kezelését.

## <a name="example-scenarios"></a>Példaforgatókönyvek

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>A rendszer előkészítése a mintaforgatókönyvek futtatására

Az ebben a szakaszban ismertetett minta-forgatókönyvekkel történő munkához először győződjön meg róla, hogy minden szükséges funkció be van kapcsolva a rendszerében. A szükséges demóadatoknak is elérhetőnek kell lennie a rendszerben.

#### <a name="turn-on-the-required-features"></a>A szükséges szolgáltatások bekapcsolása

A forgatókönyvek előfeltétele, hogy a _Több termékbevételezés feladása rakományonként_ funkció és ennek előfeltételét képező funkció be legyen kapcsolva. Az adminisztrátorok ezeket a funkciókat a következő lépések végrehajtásával kapcsolhatók be.

1. Nyissa meg a **Funkciókezelés** munkaterületet. (A munkaterület megtalálásával és használatával kapcsolatos részletes tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)

1. Kapcsolja be a _Beszerzésirendelés-készlettranzakciók társítása egy rakománnyal_ funkciót, amely a következő módon van listázva:

    - **Modul:** _Raktárkezelés_
    - **Funkció neve:** _Beszerzésirendelés-készlettranzakciók társítása egy rakománnyal_

1. Kapcsolja be a _Több termékbevételezés feladása rakományonként_ a következő módon:

    - **Modul:** _Raktárkezelés_
    - **Funkció neve:** _Több termékbevételezés feladása rakományonként_

#### <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ha ezeket a forgatókönyveket a megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos demóadatok telepítve vannak. Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Adjon hozzá egy menüelemet a rakománycikkek fogadásához, amikor mobileszköz van használva

Mielőtt a raktári fogadó adminisztrátorok egy mobileszköz segítségével regisztrálhatnak egy rakományhoz kapcsolódó bejövő készletet, egy mobileszköz-menüelemet kell létrehozni erre a célra.

Ebben a szakaszban egy mobileszköz menüelemet hoz létre, és hozzáadja azt egy meglévő menühöz. A raktári dolgozó ezt követően kiválaszthatja a menüelemet a Raktárkezelés mobilalkalmazásban.

1. Nyissa meg a **Raktárkezelés \> Beállítások \> Mobileszköz \> Mobileszköz menüelemei** lehetőséget és győződjön meg arról, hogy a mobileszköz menüje tartalmaz egy olyan menüelemet, amelynek beállításai a következők:

    - **Mód:** _Munka_
    - **Munka-létrehozásifolyamat:** _Rakománycikk fogadása_
    - **Azonosítótábla létrehozása:** _Igen_

    Az összes többi beállítást az alapértelmezett értéken hagyhatja.

    ![Mobileszköz menüelem-beállításai](media/inbound-mobile-menu-items.png "Mobileszköz menüelem-beállításai")

    A mobileszköz-menüelemek beállításával kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).

2. Miután befejezte a menüelem beállítását válassza a **Raktárkezelés \> Beállítások \> Mobileszköz \> Mobileszköz menüelemei** lehetőséget és adja hozzá a mobileszközei menüstruktúrájához.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>1. példaforgatókönyv: Egy olyan rakomány regisztrálása, ahol egyes cikkek hiányoznak

Ez a példa azt mutatja be, hogyan lehet bejegyezni a mennyiségeket egy olyan bejövő rakományhoz, amelynél nem szerepel a teljes várható mennyiség. Ezt követően bemutatja, hogy hogyan kell feladni a termékbevételezést a beszerzési rendeléshez.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Rakomány létrehozása a beszerzési rendelés fogadásának megtervezéséhez

Ebben az eljárásban manuálisan létrehoz egy beszerzési rendelést és egy kapcsolódó rakományt. Ezt követően frissíti a rakományt, hogy szimulálja, hogy az le lett szállítva a szállítótól (ami frissíti a rakomány állapotát). A raktári tervezők a rakományok ezután a **Rakomány állapota** szerinti szűrésével képesek a bejövő rakományok megkeresésére.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. A **Beszerzési rendeléslétrehozása** párbeszédpanelen a **Szállítói számla** mezőt állítsa _1001_ értékre.
1. Válassza az **OK** gombot a párbeszédpanel bezárásához és a beszerzési rendelés létrehozásához.
1. Az új beszerzési rendelés már tartalmaz egy sort a **Beszerzésirendelés-sorok** alatt. A következő értékeket állítsa be ehhez a sorhoz:

    - **Cikkszám:** _A0001_
    - **Raktár:** _24_
    - **Mennyiség:** _10_

1. A **Beszerzés lap** műveleti ablaktáblájában kattintson a **Műveletek \> Megerősítés** pontra. A rendelés állapota most _Visszaigazolt_.
1. A **Raktár** műveleti ablaktáblájában kattintson a **Műveletek \> Rakománytervező munkaterület** pontra.
1. A **Rakománytervezés munkaterület** oldalon, a műveleti ablaktáblán, a **Kínálat és kereslet** lapon válassza a **Hozzáadás \> Az új rakományhoz** lehetőséget.
1. A **Rakománysablon hozzárendelése** párbeszédpanelen állítsa be a **Rakománysablon azonosítója** mezőt _20 lábas konténer_ értékre.
1. Válassza az **OK** gombot a párbeszédpanel bezárásához és a visszatéréshez a munkaterületre.
1. A **Rakományok** szakaszban válassza ki a **Rakományazonosítót**, hogy megnyíljon az újonnan létrehozott rakomány.
1. Tekintse át a rakomány fejlécének és sorainak adatait, és figyelje meg a következő pontokat:

    - A **Rakomány** gyorslapon a **Rakomány állapota** mező _Nyitott_ értékre van állítva.
    - A **Rakománysorok** szakaszban egyetlen olyan sor van, amelyben a **Mennyiség** mező értéke _10_, és a **Munka létrehozva mennyiség** mező értéke _0_ (nulla).

    ![Rakomány részletei](media/inbound-load-details.png "Rakomány részletei")

1. A műveleti ablaktábla **Szállítás és fogadás** lapján válassz a **Megerősítés \> Bejövő szállítmány** lehetőséget. Figyelje meg, hogy a **Rakomány állapota** _Szállított_ értékre változott.
1. Jegyezze fel a **Rakományazonosító** értékét, hogy a következő eljárásban használhassa.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Regisztrálja a rakományban érkezett mennyiségek fogadását

Amikor a rakomány megérkezik a raktárba, a fogadó adminisztrátor regisztrálja a rakomány mennyiségeit egy mobileszközön.

1. A mobileszköz használatával lehet a 24. raktárba bejelentkezni. (A normál demóadatokban _24_-es felhasználó azonosító és az _1_ jelszó használatával jelentkezzen be.)
1. Válassza ki az ehhez az esethez létrehozott _Rakomány – cikk bevételezése_ menüelemet.
1. A következő értékek megadásához kövesse a képernyőn megjelenő adatokat. (A sorrend az éppen használt mobileszköz vagy emulátor típusától függően eltérhet.)

    - **Rakomány** – Adja meg az előző eljárásban létrehozott rakományazonosítót.
    - **Cikk** – adja meg az _A0001_, értéket, amely a rakományhoz várt cikk.
    - **Mennyiség** – A _9_ értéket adja meg a rakomány aktuális tényleges mennyiségeként. Ne feledje, hogy ez a mennyiség kisebb, mint a várt mennyiség.

1. Folytassa tovább a munkafolyamatot, hagyja üresen az összes többi mezőt, vagy állítsa be az alapértelmezett értékeket, amíg az eszköz tájékoztat arról, hogy a munka be van fejezve.

A rakomány fogadása feladat befejeződött, és a fogadó adminisztrátor a következő feladatára léphet tovább. A raktári befogadó személyzet azonban egy idő után felülvizsgálja a rakomány rekordját, és látni fogja, hogy a bevételezett mennyiség kisebb, mint a várt mennyiség. Ezután a következő eljárást fogják végrehajtani a webes ügyfélprogrammal.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A listában keresse meg az imént fogadott rakományt. (Előfordulhat, hogy be kell jelölnie a **Lezártak megjelenítése** jelölőnégyzetet, hogy a _Szállítva_ állapotú bejövő rakományok is szerepeljenek.) Ezt követően a rakomány megnyitásához válassza ki a hivatkozást a **Rakomány azonosítója** oszlopban.
1. A rakomány rekordjában figyelje meg, hogy a **Rakomány állapota** értéke továbbra is _Szállított_, de a rakománysorban szereplő **Munka létrehozott mennyisége** értéke _9_-re változott.
1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. A listán keresse meg az éppen beérkezett beszerzést, majd válassza ki a hivatkozást a **Beszerzési rendelés** oszlopban a rendelés megnyitásához.
\
1. Válassza a **Beszerzésirendelés-sorok** gyorslapon a **Készlet \> Nézet \> Tranzakciók** lehetőséget.
1. A két beszerzési rendelési tranzakció adatait tekintse át. (Előfordulhat, hogy a **Készlettranzakciók** lapot kell testre kell szabnia, hogy a **Rakományazonostó** mezőt a rácsban láthassa.) Két tranzakciónak kell megjelennie:

    - A _Regisztrált_ állapotban szereplő nyugtával rendelkező tranzakció a _9_-es regisztrációs mennyiséget jelenti, amelyet egy adott rakománnyal szemben futtattak a mobileszköz segítségével. A **Rakományazonosító** a szóban forgó tranzakcióhoz van társítva.
    - A _Megrendelt_ állapotban nyugtával rendelkező tranzakciója a fennmaradó, nem regisztrált rendelési sor _1_ mennyiségét jelenti.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>A regisztrált terhelések fogadás-feladása a beszerzési rendelésekkel szemben

Ebben az eljárásban fogadja-feladja a készletet, amit a rakományhoz regisztrált. Ennek eredményeképpen a kapott készlet és a kapcsolódó költségek a vállalat főkönyvébe kerülnek.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. A listában keresse meg a fogadott rakományt. (Előfordulhat, hogy be kell jelölnie a **Lezártak megjelenítése** jelölőnégyzetet, hogy a _Szállítva_ állapotú bejövő rakományok is szerepeljenek.) Ezt követően a rakomány megnyitásához válassza ki a hivatkozást a **Rakomány azonosítója** oszlopban.
1. A műveleti ablaktábla **Szállítás és fogadás** lapján válassz a **Bevételezés \> Termékbevételezés** lehetőséget. Kattintson az **Igen** gombra, ha a rendszer a művelet megerősítését kéri.
1. A **Termékbevételezés feladása** párbeszédpanelen a **Sorok** gyorslapján vizsgálja meg a rácsot. Látnia kell azt a beszerzésirendelés-sort, amelyhez a mennyiséget regisztrálták a kiválasztott rakománnyal szemben.

    > [!NOTE]
    > Azokban a verziókban, ahol a __Több termékbevételezés feladása rakományonként_ funkció nem érhető el, vagy nincs engedélyezve, a **Rakománysorok** rácsban megjelenő alapértelmezett mennyiség a beszerzésirendelés-sorhoz regisztrált összes rakomány teljes mennyisége lesz.

1. Az **Áttekintés** gyorslapon a **Termékbevételezés** mezőt vizsgálja meg a rácson. Figyelje meg, hogy olyan számra van beállítva, amely tartalmazza a kiválasztott rakomány azonosítóját.
1. A termékbevételezés feladásához és a **Termékbevételezés feladása** párbeszédpanel bezárásához kattintson az **OK** gombra.
1. Visszatért a rakomány részleteibe. Figyelje meg a következő pontokat:

    - A **Rakomány állapota** mező immár _Beérkezett_ értékre van állítva.
    - A rakománysorban a rakomány **Mennyiségi** értéke _10_ db-ról _9_ db-ra módosult, hogy megfeleljen a regisztrált mennyiségnek , de a **Munka létrehozott mennyisége** _9_ marad.

Ha a beszerzési csoport nem várja meg, hogy a szállító a fennmaradó 1 rendelési mennyiséget szállítsa, akkor a sor szállítási maradékának _0-ra_ történő frissítésével lezárhatja a rendelést. Ha azonban, ha hamarosan kiderül, hogy a hiányzó darab érkezett az eredeti rakományhoz, akkor a raktári személyzet a következő műveletek egyikét hajthatja végre:

- A mennyiség regisztrálása ugyanazzal a rakománnyal szemben. Ebben az esetben a **Rakomány állapota** mezőt a program visszaállítja a _Leszállított_ értékre, és a **Létrehozott munka mennyisége** értéke _10_-re lesz frissítve. Ez a választás csak a következő helyzetekben érhető el:

    - A _Rakománymennyiségek túlbevételezése_ funkció nem érhető el, vagy nincs engedélyezve.
    - A _Rakománymennyiségek túlbevételezése_ funkció elérhető és engedélyezve van, és a **Rakománysor túlbevételezése** mező beállítása _Engedélyezve_.

- Adja hozzá a mennyiséget egy új vagy meglévő rakományhoz, és dolgozza fel a szokásos módon.
- A mennyiség regisztrálása és/vagy fogadása olyan módon, amely nem jár együtt a rakomány kezelésével.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>2. példaforgatókönyv: Azon mennyiségek regisztrálása, amelyek több olyan bejövő rakományhoz érkeznek, ahol hiányoznak egyes cikkek

Ebben a helyzetben egy beszerzési rendelési sorhoz kapcsolódó bejövő szállítmány két részre lesz bontva. Előfordulhat például, hogy egy beszerzésirendelés-sor a súly és/vagy térfogat tényleges terhelési korlátai miatt több rakományra van osztva.

Ez a forgatókönyv azt is megmutatja, hogyan lehet több, ugyanarra a rakományra vonatkozó termékbevételezés feladását feldolgozni. A program olyan mennyiségeket rögzít, amelyek több bejövő rakománnyal érkeznek, de a mennyiségek nem felelnek meg a várható mennyiségeknek. Ugyanezen rakományhoz többször történik a bevételezés feladása során jelentkező költség-frissítések végrehajtása.

#### <a name="set-up-load-receiving-policies"></a>Rakományfogadó házirendek beállítása

Ebben az eljárásban több termékbevételezés-feladás is engedélyezhető ugyanabból a rakományból.

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Rakományok** lapon állítsa a **Több termékbevételezés engedélyezése rakományonként** mezőt _Igen_ értékre.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Két rakomány létrehozása a beszerzési rendelés fogadásának megtervezéséhez

Ebben az eljárásban manuálisan létrehoz egy beszerzési rendelést és két rakományt. Ezt követően manuálisan frissíti a rakományt, hogy szimulálja, hogy az le lett szállítva a szállító által (ami frissíti a rakomány állapotát). A raktári tervezők a rakományok ezután a **Rakomány állapota** szerinti szűrésével képesek a bejövő rakományok megkeresésére.

Azt is megtanulja, hogy hogyan lehet a beszerzésirendelés-sort úgy beállítani, hogy 20 százalékkal nagyobb mennyiséget tudjon fogadni a sorhoz megadott mennyiségnél.

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. A **Szállító** gyorslapján állítsa a **Szállítói számla** mezőt _1001_ értékre, majd kattintson az **OK** gombra.
1. A program megnyitja az új beszerzési rendelést, és az egy üres sort tartalmaz a **Beszerzésirendelés -sorok** rácsában. A következő értékeket állítsa be ehhez a rendeléssorhoz:

    - **Cikkszám:** _A0001_
    - **Raktár:** _24_
    - **Mennyiség:** _10_

1. A **Sor részletei** gyorslap **Szállítás** lapján állítsa be a **Túlszállítás** mezőt _20_ értékre.
1. A **Beszerzés lap** műveleti ablaktáblájában kattintson a **Műveletek \> Megerősítés** pontra. A rendelés állapota most _Visszaigazolt_.
1. A **Raktár** műveleti ablaktáblájában kattintson a **Műveletek \> Rakománytervező munkaterület** pontra.
1. A **Rakománytervezés munkaterület** oldalon, a műveleti ablaktáblán, a **Kínálat és kereslet** lapon válassza a **Hozzáadás \> Az új rakományhoz** lehetőséget.
1. A **Rakománysablon hozzárendelése** párbeszédpanelen állítsa be a **Rakománysablon azonosítója** mezőt _20 lábas konténer_ értékre. A **Részletek** lapon módosítsa a **Mennyiséget** _10_ helyett _5_ értékre a beszerzésirendelés-sor mennyiségének részleges hozzáadásához.
1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt.
1. A második rakomány létrehozásához ismételje meg a 8–10. lépést. Ez alkalommal a **Mennyiség** mező már _5_ értékre kell legyen állítva.
1. A **Rakománytervezési munkaterület** oldalon a **Rakományok** rácsban válassza ki a **Rakományazonosító** az első rakományhoz, amit létrehozott. Megjelenik a **Rakomány részletei** lap, és a kiválasztott rakomány látható. Tegye a következők egyikét:

    1. A műveleti ablaktábla **Szállítás és fogadás** lapján válassz a **Megerősítés \> Bejövő szállítmány** lehetőséget.
    1. Figyelje meg, hogy a **Rakomány állapota** értéke _Szállított_ értékre változott.
    1. A Bezárás gombra kattintva térjen vissza a **Rakománytervezés munkaterület** lapra.

1. Ismételje meg az előző lépést a létrehozott második rakományhoz.
1. Jegyezze fel a **Rakományok** rácsban megjelenő két **Rakományazonosító** értékét.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Az első rakományhoz érkezett mennyiségek részleges bevételezése, és a regisztrált rakománymennyiségek feladása

Amikor a rakományok megérkeznek a raktárba, a fogadó adminisztrátor regisztrálja a rakomány mennyiségeit egy mobileszközön. A rakományhoz kapcsolódó regisztrált készletet ezt követően a rendszer a vállalat főkönyvében költségfrissíti a beszerzési rendelés termékbevételezésének a rakomány alapján történő feladásával.

Ez az eljárás azt mutatja be, hogyan regisztrálhat egy fogadó adminisztrátor rakománymennyiégeket egy mobileszközön.

1. A mobileszköz használatával lehet a 24. raktárba bejelentkezni. (A normál demóadatokban _24_-es felhasználó azonosító és az _1_ jelszó használatával jelentkezzen be.)
1. Válassza ki az ehhez az esethez létrehozott _Rakomány – cikk bevételezése_ menüelemet.
1. A következő értékek megadásához kövesse a képernyőn megjelenő adatokat. (A sorrend az éppen használt mobileszköz vagy emulátor típusától függően eltérhet.)

    - **Rakomány** – Adja meg az előző eljárásban létrehozott első rakományazonosítót.
    - **Cikk** – adja meg az _A0001_, értéket, amely a rakományhoz várt cikk.
    - **Mennyiség** – adja meg a _3_ értéket. Ne feledje, hogy ez a mennyiség kisebb, mint a várt mennyiség. Ehhez a helyzethez képzelje el, hogy a befogadó adminisztrátornak nincs ideje a rakomány összes mennyiségének regisztrálására. Az eljárás során később ezt a lépést megismételve rögzítheti a fennmaradó darabokat, és a **Mennyiség** mezőt _2_ értékre állítja.

1. Folytassa tovább a munkafolyamatot, hagyja üresen az összes többi mezőt, vagy állítsa be az alapértelmezett értékeket, amíg az eszköz tájékoztat arról, hogy a munka be van fejezve.
1. A webes ügyfélben lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Keresse meg az imént beérkezett rakományt a listán, majd válassza ki a **Rakományazonosítót** a rakomány megnyitásához. Figyelje meg, hogy a **Rakomány állapota** értéke továbbra is _Szállított_, de a rakománysorban szereplő **Munka létrehozott mennyisége** értéke _3_-ra változott.
1. A műveleti ablaktábla **Szállítás és fogadás** lapján válassz a **Bevételezés \> Termékbevételezés** lehetőséget. Kattintson az **Igen** gombra, ha a rendszer a művelet megerősítését kéri.
1. A **Termékbevételezés feladása** párbeszédpanelen tekintse át, de ne módosítsa a megjelenített értékeket, majd kattintson az **OK** gombra.
1. A kiválasztott rakományhoz tartozó **Rakomány részletei** lapra érkezett vissza. Figyelje meg a következő pontokat:

    - A **Rakomány állapota** mező immár _Szállítva_ értékre van állítva.
    - A rakománysorban a rakományhoz tartozó **Mennyiség** érték _5_ darab, ez az eredeti rakomány mennyisége, és a **Létrehozott munka** értéke _3_ marad.

1. Ennek az eljárásnak a megismétlésével végezze el a rakomány maradék mennyiségének regisztrálását. Azonban a 3. lépésben azonban állítsa a **Mennyiség** mezőt _2_ értékre.

Befejezte az első rakomány fogadási feladatát. Két termékbevételezési napló lett létrehozva, egy-egy az egyes futtatott termékbevételezés-frissítésekhez.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>A második rakományhoz és számlához érkezett túlszállított mennyiség bevételezésének regisztrálása

Ennél a forgatókönyvél a bevételezési ügyintéző bejövő mennyiséget regisztrál, amely meghaladja a rakománynál létező mennyiséget. A túlbevételezés engedélyezve lesz, mivel a rendszer úgy van beállítva, hogy a túlszállítást engedélyezze.

1. A mobileszköz használatával lehet a 24. raktárba bejelentkezni. (A normál demóadatokban _24_-es felhasználó azonosító és az _1_ jelszó használatával jelentkezzen be.)
1. Válassza ki az ehhez az esethez létrehozott _Rakomány – cikk bevételezése_ menüelemet.
1. A következő értékek megadásához kövesse a képernyőn megjelenő adatokat. (A sorrend az éppen használt mobileszköz vagy emulátor típusától függően eltérhet.)

    - **Rakomány** – Adja meg a korábban létrehozott második, rakományazonosítót.
    - **Cikk** – adja meg az _A0001_, értéket, amely a rakományhoz várt cikk.
    - **Mennyiség** – Adja meg a _7_ mennyiséget, vagyis azt a fennmaradó mennyiséget, amelyet a szállító jogosult szállítania teljes 12 db-os beszerzési mennyiség részeként (ahol 10 az eredeti rendelési mennyiség és 2 az engedélyezett túlszállítási mennyiség, ami 20%). Ne feledje, hogy 5 db már regisztrálva van az első rakományhoz.

A második rakomány 7 darabbal frisítve lett mennyiséggel frissítette, és a termék bevételezhető-frissíthető ezen mennyiség alapján.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]