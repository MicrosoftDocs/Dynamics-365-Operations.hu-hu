---
title: Kimutatásfeladás funkcionalitás továbbfejlesztései
description: Ez a témakör leírja a kimutatásfeladási funkción végrehajtott javításokat.
author: josaw1
manager: AnnBe
ms.date: 05/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02880edda6c34c24f8dad8cc8cbeafe215f46896
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/14/2019
ms.locfileid: "1541291"
---
# <a name="improvements-to-statement-posting-functionality"></a>Kimutatásfeladás funkcionalitás továbbfejlesztései

[!include[banner](includes/banner.md)]

Ez a témakör leírja a kimutatásfeladási funkción végrehajtott javítások első készletét. Ezek a fejlesztések érhetők el a Microsoft Dynamics 365 for Finance and Operations 7.3.2 verziójában.

## <a name="activation"></a>Aktiválás

Alapértelmezés szerint a Finance and Operations 7.3.2 telepítés során a program be van állítva az örökölt szolgáltatással kivonat feladásához. A továbbfejlesztett kimutatásfeladási funkció engedélyezéséhez engedélyezni kell a konfigurációs kulcsot.

- Ugorjon ide: **Rendszerfelügyelet** \> **Beállítás** \> **Licenckonfiguráció**, a **Kiskereskedelem** csomópont alatt törölje a jelet a **Kiskereskedelmi kimutatások (korábbi verzió)** jelölőnégyzetből, és jelölje be a **Kiskereskedelmi kimutatások** négyzetet.

Ha az új **Kiskereskedelmi kimutatások** konfigurációs kulcs be van kapcsolva, elérhető egy új menüelem, amelynek a neve **Kiskereskedelmi kimutatások**. Ez a menüpont kimutatások kézi létrehozását, számítását és feladását teszi lehetővé. Minden olyan kimutatás, amely a kötegelt feladási folyamat használata esetén hibát okoz, elérhető lesz a menüelem keresztül is. (Ha a **Kiskereskedelmi kimutatások (korábbi verzió)** konfigurációs kulcs be van kapcsolva, a menüelem neve **Nyitott kimutatások**.)

A Finance and Operations a következő ellenőrzéseket tartalmazza, amelyek ezekhez a konfigurációs kulcsokhoz kapcsolódnak:

- Mindkét konfigurációs kulcsot nem lehet egyszerre kell bekapcsolni.
- Ugyanazokat a konfigurációs kulcsokat kell használni az adott kimutatáson az életciklusa során végrehajtott összes művelethez (létrehozás, kiszámítás, törlés, feladás és így tovább). Például nem lehet létrehozni és kiszámítani egy kimutatást, amíg a **Kiskereskedelmi kimutatás (korábbi verzió)** konfigurációs kulcs be van kapcsolva, és aztán megpróbálni feladni ugyanazt az utasítást, amíg a **Kiskereskedelmi kimutatás** konfigurációs kulcs ki van kapcsolva.

> [!NOTE]
> Azt ajánljuk, hogy használja a **Kiskereskedelmi kimutatások** konfigurációs kulcsot a továbbfejlesztett kimutatásfeladási szolgáltatáshoz, kivéve, ha nyomós oka van a **Kiskereskedelmi kimutatások (korábbi verzió)** konfigurációs kulcs használatára helyette. A Microsoft folyamatosan dolgozik az új és továbbfejlesztett feladási funkción, és fontos váltani a legkorábban, hogy ki tudja használni. Az örökölt kimutatásfeladási funkciót kivezetjük 8.0-ás kiadástól.

## <a name="setup"></a>Beállítás

A kimutatásfeladási funkció javításának részeként három új paramétert vittek be a **Kimutatás** gyorslapján a **Feladás** lapján a **Kiskereskedelmi paraméterek** lapon:

- **Kimutatás tartalmának törlése letiltása** – Ez a beállítás csak az örökölt kimutatás feladási funkcióra alkalmazható. Azt ajánljuk, hogy a lehetőség beállítása legyen **Nem** megakadályozandó, hogy a felhasználók töröljék a félig feladott állapotú kimutatásokat. A félig feladott állapotú kimutatások törlésekor az adatok megsérülnek. Ezt a lehetőséget is ajánlott **Igen** értékre csak kivételes esetekben állítani.
- **Elérhető készlet lefoglalása a számítás során** – Ajánlott, hogy a **Készlet feladása** kötegelt feladatot használja a készletfoglalásre, és hogy ezen lehetőség beállítása **Nem** legyen. Ha a beállítás értéke **Nem**, a továbbfejlesztett kimutatás eladási funkció nem próbálja meg a számítás időpontjában a foglalási tétel készletnaplósorok létrehozását (ha a bejegyzések nem hozta létre már a **Készlet feladása** kötegelt feladat). Ehelyett a szolgáltatást csak a feladás időpontjában hoz létre készletfoglalási tételeket. Ez a megoldás tervezési döntés eredménye, és az az oka, hogy a számítási folyamat és a feladási folyamat között az időablak mérete általában kicsi. Ha a számítás időpontjában készlet lefoglalása a szándéka, beállíthatja ezt a lehetőséget **Igen** értékre.

    Az örökölt kimutatásfeladási szolgáltatás mindig elvégzi a készletfoglalást a kimutatás számítása során (ha a foglalást még nem tette meg a **Készlet feladása** kötegelt feladat), függetlenül a lehetőség beállításától.

- **Számlálás letiltása szükséges** – Ha ez a beállítás **Igen**, a kimutatás feladására használt eljárás tovább folytatódik akkor is, ha a kimutatáson a számolt összeg és a tranzakciós összeg közötti különbség túl van azon a küszöbértéken, amely meg van határozva a kiskereskedelmi áruházak **Kimutatás** gyorslapján.

Ezenkívül a következő paraméterek kerültek be a **Kötegelt feldolgozás** gyorslapra a **Feladás lapra** a **Kiskereskedelmi paraméterek** oldalon: 

- **Párhuzamos kimutatásfeladááok maximális száma** -Ez a mező a kötegelt feladatok számát határozza meg, amelyek több nyilatkozat feladása esetén használatosak. 
- **Szálak maximális száma a rendelésfeladáshoz kimutatásonként** – Ez a mező a kimutatás feladására szolgáló kötegelt feladat által az egyes kimutatások értékesítési rendeléseinek létrehozásához és számlázásához használt szálak maximális számát jelzi. A kimutatásfeladási folyamat által használt szálak teljes számát a program úgy számítja ki, hogy ezen paraméter értékét megszorozza a **Párhuzamos kivonatfeladások maximális száma** értékével. A paraméter értékének beállítása túl magasra negatív hatással lehet a kimutatásfeladási folyamatának teljesítményére.
- **Összesítésben szereplő maximális tranzakciós sorok** – Ez a mező azt határozza meg, hogy hány tranzakciós sor fog szerepelni egy összesített tranzakcióban, mielőtt újat hoz létre. Az összesített tranzakciók a különböző összesítési feltételek, például a vevő, az üzleti dátum vagy a pénzügyi dimenziók alapján jönnek létre. Fontos megjegyezni, hogy az egyetlen kiskereskedelmi tranzakció sorait a rendszer nem osztja szét különböző összesített tranzakciók között. Ez azt jelenti, hogy egy összesített tranzakció sorainak száma valamivel több vagy kevesebb lehet olyan tényezők alapján mint egyedi termékek.
- **Üzleti tranzakciók ellenőrzéséhez szükséges szálak maximális száma** A szálak maximális száma, amelyek kiskereskedelmi tranzakció ellenőrzéséhez fel lesznek használva. A kiskereskedelmi tranzakciók érvényesítése olyan szükséges lépés, amelyet el kell végezni azelőtt, hogy a tranzakciókat be lehessen húzni a kimutatásba. Emellett szükség van egy **Ajándékutalvány-termék** meghatározására az **Ajándékutalvány** gyorslapján a **Feladás** lapnak a **Kiskereskedelmi paraméterek** lapon. Ezt definiálni kell akkor is, ha a szervezet nem használ ajándékutalványokat.

> [!NOTE]
> Minden beállítás és paraméter, amely kapcsolódik a kimutatásfeladásokhoz, és meg van határozva a kiskereskedelmi áruházak és a **Kiskereskedelmi paraméterek** oldalon, alkalmazható a továbbfejlesztett kimutatásfeladási funkcióra.

## <a name="processing"></a>Feldolgozás

A kimutatások kiszámíthatók és feladhatók kötegelve a **Kimutatások kötegelt kiszámítása** és a **Kimutatások feladása kötegben** menüpontban. Másik lehetőségként a kimutatások manuálisan kiszámíthatók és feladhatók a **Kiskereskedelmi kimutatások** menüelemmel, amelyet a továbbfejlesztett kimutatásfeladási funkció lehetővé tesz.

A kimutatások kötegelt számítása és feladása folyamat lépései ugyanazok, mint az örökölt kimutatásfeladási funkciónál használtak. Azonban jelentős javítások történtek a kimutatások alapvető háttér-feldolgozása során. Ezek a fejlesztések rugalmasabbá tették a folyamatot, és az állapot- és hibainformációk jobb láthatósággal rendelkeznek. Ezért a felhasználók megoldhatják a hibák kiváltó okát, és folytathatják a feladási folyamatot anélkül, hogy ez adatsérüléshez vezethetne, és anélkül, hogy az adatokat javítani kellene.

Az alábbi szakaszok leírják a kimutatásfeladási funkció fő javításait, amelyek a feladott kimutatások és a kiskereskedelmi kimutatások felhasználói felületén jelennek meg.

### <a name="status-details"></a>Állapotadatok

Új állapotmodellt vezettek be a kimutatásfeladási funkciónál, a számítási és könyvelési folyamatokban.

A következő táblázat leírja a különféle állapotait és azt, hogy milyen sorrendben vannak a számítási folyamat során.

| Állapotok sorrendje | Állapot      | Leírás |
|-------------|------------|-------------|
| 1           | Elindítva    | A kimutatás létrejött, és készen áll a kiszámításra. |
| 2           | Megjelölve     | A tranzakciók, amelyek a hatókörben vannak a kimutatásnál, a kimutatás paraméterei alapján vannak azonosítva, és a kimutatás azonosítójával vannak megjelölve. |
| 3           | Számított | A kimutatássorok kiszámítódnak és megjelennek. |

A következő táblázat leírja a különféle állapotait és azt, hogy milyen sorrendben vannak a feladási folyamat során.

| Állapotok sorrendje | Állapot                   | Leírás |
|-------------|-------------------------|-------------|
| 1           | Ellenőrizve                 | Több ellenőrzés történik a kapcsolódó paramétereken (például intézkedési költség), valamint a kimutatásokon és a kivonatsorokon (például a leszámolt összeg és a tranzakció összege közötti eltérés). |
| 2           | Összesített              | A névvel ellátott és a névtelen vevőkhöz tartozó értékesítési tranzakciók a konfiguráció alapján vannak összesítve. Minden összesített tranzakció értékesítési rendeléssé alakul át végső soron. |
| 3           | Vevősorrend létrehozva  | Az összesített tranzakción alapján értékesítési rendelések jönnek létre a rendszerben. |
| 4           | Számlázott vevői rendelés | Kiszámlázott értékesítési rendelések. |
| 5           | Engedmények feladva        | Az időszaki kedvezménynaplók feladása a konfigurációja alapján történik. |
| 6           | Bevétel/kiadás feladva   | A bevételi/kiadás tranzakciókat bizonylatként adják fel. |
| 7           | Társított bizonylatok         | A kifizetési naplók létrehozása és a megfelelő számlához csatolása történik. |
| 8           | Kifizetések feladva         | A fizetési naplókat feladják. |
| 9           | Ajándékutalványok feladva       | Az ajándékkártya-tranzakciókat bizonylatként adják fel. |
| 10          | Feladva                  | A kimutatás feladottként van megjelölve. |

Az előző táblákban minden állapot független természetű, és az állapotok között hierarchikus függőség épül fel. Ez a függés felülről lefelé terjed. Ha a rendszer hibákat észlel az állapot feldolgozása közben, a kimutatás állapota visszatér az előző állapotba. A folyamat minden olyan későbbi ismételt megkísérlése folytatja az állapotból, amelyik nem sikerült, és tovább halad előre. A módszer használata a következő előnyökkel jár:

- A felhasználó rendelkezik a teljes láthatóságával az állapotnak, ahol a hiba történt.
- Adatvesztés elkerülve. Például az örökölt kimutatásfeladási funkciónál voltak példányok, ahol egyes értékesítési rendelések számlázva lettek, de mások nyitva maradtak. Voltak olyan esetek is, ahol bizonyos kifizetési naplókhoz nem tartozott megfelelő kiegyenlítendő számla, mert hiba történt a számla feladásakor.
- A felhasználók megtekinthetik a kimutatás aktuális állapotát a következő segítségével: **Állapotadatok** gomb a **Végrehajtás részletei** csoportjában a kimutatásnak. Az állapotrészletek lap három részből áll:

    - Az első rész a kimutatás aktuális állapotának megjelenítése, ha hiba lépett fel a hibakóddal és a részletes hibaüzenettel.
    - A második rész a számítási folyamat különböző állapotainak megjelenítése. Vizuális figyelmeztetések adja meg a sikeres futtatású állapotokat, a hibák miatt nem futtatott állapotokat és az állapotokat, amelyek még nem futtattak.
    - A harmadik rész a feladási folyamat különböző állapotainak megjelenítése. Vizuális figyelmeztetések adja meg a sikeres futtatású állapotokat, a hibák miatt nem futtatott állapotokat és az állapotokat, amelyek még nem futtattak.

A második és harmadik szakaszok fejléce emellett a megfelelő folyamat általános állapotát mutatja.

### <a name="event-logs"></a>Eseménynaplók

A kimutatás különféle műveleteken megy át (például, létrehozás, számítás, törlés és feladás), és a kimutatás életciklusa során azonos művelet több példánya is meg lehet hívva. Például egy kimutatást a létrehozása és számítása után a felhasználó törölheti és újra kiszámíthatja. Az **Eseménynaplók** gomb a **Végrehajtás részletei** kimutatáscsoportban tartalmaz egy teljes auditnaplót a kimutatáson meghívott különböző műveletekkel kapcsolatban, információkkal együtt a műveletek meghívásának idejéről.

### <a name="aggregated-transactions"></a>Összesített tranzakciók

A feladási folyamat során az értékesítési tranzakciók a konfiguráció alapján vannak összesítve. Az összesített tranzakciókat a rendszer tárolja, és értékesítési rendelések létrehozásához használja. Minden összesített tranzakció egy megfelelő értékesítési rendelést hoz létre a rendszerben. Megtekintheti az összesített tranzakciókat a következő segítségével: **Összesített tranzakciók** gomb a **Végrehajtás részletei** csoportjában a kimutatásnak.

Az **Értékesítési rendelés részletei** összesített tranzakció lap a következő információkat jeleníti meg:

- **Rekordazonosító** – Az összesített tranzakció azonosítója.
- **Kimutatás száma** – A kimutatás, amelyhez az összesített tranzakció tartozik.
- **Dátum** – A dátum, amikor az összesített tranzakciót létrehozták.
- **Értékesítési azonosító** – Értékesítési rendelés létrehozásakor az összesített tranzakcióból, az értékesítési rendelés azonosítója. Ha ez a mező üres, akkor a megfelelő értékesítési rendelés még nem jött létre.
- **Összesített sorok száma** – Az összesített tranzakciónál és az értékesítési rendelésnél a sorok száma összesen.
- **Állapot** – Az összesített tranzakció utolsó állapota.
- **Számlaazonosító** – Az összesített tranzakció az értékesítési rendelésének számlázása esetén az értékesítési számla azonosítója. Ha ez a mező üres, akkor az értékesítési rendelés számláját még nem adták fel.

Egy összesített tranzakció **Tranzakció részletei** lapja az összes kiskereskedelmi tranzakciót jeleníti meg, amelyeket behívott a rendszer az összesített tranzakcióba. Az összesített tranzakció összesített sorai megjelenítik a kiskereskedelmi tranzakciók minden összesített rekordját. Az összesített sorok részleteket is megjelenítenek, például cikk, változat, mennyiség, ár, nettó összeg, egység és raktár. Alapvetően egy értékesítésirendelés-sor egy összesített sornak felel meg.

Az **Összesített tranzakciók** lapon letöltheti egy adott összesített tranzakció XML-jét az **Értékesítési rendelés XML exportálása** gomb használatával. Az XML segítségével hibakeresheti a problémákat, amelyek az értékesítési rendelés létrehozására és feladására vonatkoznak. Csak töltse le az XML-fájlt, töltse fel egy tesztkörnyezetbe, és végezze el a hibakeresést a tesztkörnyezetben. Az összesített tranzakciók XML-kódjának letöltése funkció nem használható a feladott kimutatásoknál.

Az összesített tranzakció nézet a következő előnyökkel jár:

- A felhasználók rálátást kapnak az értékesítési rendelés létrehozása során nem sikerült összesített tranzakciókhoz, és az értékesítési rendelések sikertelen számlázásaihoz.
- A felhasználók rálátást kapnak, hogy hogyan vannak összesítve a tranzakciók.
- A felhasználó teljes auditnaplóval rendelkezik, a kiskereskedelmi tranzakcióktól az értékesítési rendelésekig és az értékesítési számlákig. Az auditnapló nem áll rendelkezésre az örökölt kimutatásfeladási szolgáltatásban.
- Az összesített XML-fájl megkönnyíti az értékesítési rendelés létrehozása és számlázása során felmerült problémák azonosítását.

### <a name="journal-vouchers"></a>Naplóbizonylatok

A **Naplóbizonylatok** gomb a **Végrehajtás részletei** csoportjában a kimutatásnak a kimutatáshoz létrehozott összes különböző bizonylatot jeleníti meg, amelyek kapcsolatosak az engedményekkel, a bevétel/kiadás számlákkal, az ajándékutalvány kártyákkal és így tovább.

Jelenleg a program csak a feladott kimutatásokra jeleníti meg ezeket az adatokat.

### <a name="payment-journals"></a>Kifizetési naplók

A **Fizetési naplók** gomb a **Végrehajtás részletei** csoportjában a kimutatás csoportnak a kimutatáshoz létrehozott minden különböző kifizetési napló látható.

Jelenleg a program csak a feladott kimutatásokra jeleníti meg ezeket az adatokat.

## <a name="other-improvements"></a>További fejlesztések

A kimutatásfeladási funkción egyéb, a felasználó által látható, háttérrendszeren végrehajtott javítások történtek. Íme néhány példa:

- Az összesítés nem veszi figyelembe a terminál, személyzet és műszak entitásokat. Mivel kevesebb összesítési paramétert van, kevesebb értékesítésirendelés-sort kell feldolgozni.
- Kölcsönös kizárás az tranzakció táblákon való előfordulása ritkább a további bővítménytáblák bevezetésével, és a kiskereskedelmi tranzakciós táblákon beszúrási műveletek végrehajtásával a frissítési műveletek helyett.
- A futó kötegelt feladatok száma paraméterezett, és korlátozott. Ezért ez a szám finomhangolható kifejezetten a vevői környezethez. Az örökölt kimutatásfeladási funkcióban, korlátlan számú kötegelt feladat jött létre egyszerre. Az eredmény kezelhetetlen terhelés, többletköltségeket, és a kötegkiszolgáló szűk keresztmetszetei volt.
- A kimutatások hatékonyan kerülnek várólistára a feldolgozáshoz: a tranzakciók maximális számával rendelkező kimutatások kapnak prioritást.
- A kötegelt folyamatok, például a **Kimutatások kötegelt kiszámítása** és a **Kivonatok feladása kötegben**, csak kötegelt módban futnak. Az örökölt kimutatásfeladási funkcióban a felhasználók interaktív módban futtathatták a kötegelt folyamatokat, amely egyetlen szálas művelet, ellentétben a kötegelt folyamatokkal, amelyek többszálasak.
- Az örökölt kimutatásfeladási funkcióban a kötegelt művelet hibája a teljes kötegelt feladatot hibaállapotba helyezte. A továbbfejlesztett funkcióban a kötegelt művelet hibái nem helyezik a kötegelt feladatot hibaállapotba, ha más kötegelt műveletek sikeresen befejeződtek. Ajánlott először megvizsgálni a kötegelt végrehajtás futtatásának feladási állapotát a **Kiskereskedelmi kimutatások** lapon, amelyen megtekintheti az esetleges hibák miatt nem feladott kimutatásokat.
- Az örökölt kimutatásfeladási funkcióban az első kimutatáshiba hatására sikertelen lesz a teljes köteg. A fennmaradó kimutatások nincsenek feldolgozva. A továbbfejlesztett funkcióban a kötegelt feldolgozás tovább folytatja minden jelentés feldolgozását akkor is, ha a kimutatások némelyike hibát okoz. Egyik előnye, hogy a felhasználók rálátást kapnak a hibák kimutatások pontos számára. Ezért felhasználók nem kerülnek végtelen körbe, amelyben hibákat javítanak, és addig futtatják a kimutatás feladása folyamatot, amíg meg nem történik az összes kimutatás feladása.

## <a name="general-guidance-about-the-statement-posting-process"></a>A kimutatásfeladási folyamattal kapcsolatos általános útmutatás

- Javasoljuk, hogy a kivonat feladása folyamatot kötegben futtassa, mert a kötegelt futtatás kihasználja a kötegkeretrendszer többszálas teljesítményét. Többszálas végrehajtás szükséges a kimutatásfeladásoknál általában látható nagyon nagy mennyiségű tranzakció kezeléséhez.
- Ajánlott bekapcsolni a cikkmodellcsoport negatív tényleges készletét, hogy a feladás zökkenőmentes legyen. Bizonyos esetekben a negatív kimutatásokat nem lehet feladni, hacsak nincs negatív tényleges készlet. Például elméletben, ha a készleten egy cikkból csak egy egység van, és volt egy értékesítési tranzakció és egy visszáru-tranzakció a cikkhez, a tranzakciónak feladhatónak kell lennie akkor is, ha a negatív készlet nincs bekapcsolva. Mivel azonban a kimutatásfeladási folyamat a vevőre sorrendben kéri le az értékesítési tranzakciót és a visszáru-tranzakciót, nem biztos, hogy az értékesítési sor lesz először feladva, majd a visszárusor követi. Ezért hibák léphetnek fel. Ha a negatív készlet be van kapcsolva ebben az esetben, a tranzakció feladása nem lesz hátrányosan érintett, és a rendszer megfelelően tükrözi a készletet.
- Ajánlott az összesítés használata a kimutatások kiszámítása és feladása során. Emiatt a következő beállítások javasoltak az összesítési paraméterek egy részéhez:

    - Menjen ide: **Kiskereskedelem** \> **Központ beállítása** \> **Paraméterek** \> **Kiskereskedelmi paraméterek**. Ezután a **Feladás** lapon, a **Készletmódosítás** gyorslapon, a **Részletességi szint** mezőben válassza ki az **Összegzés** lehetőséget.
    - Menjen ide: **Kiskereskedelem** \> **Központ beállítása** \> **Paraméterek** \> **Kiskereskedelmi paraméterek**. Ezután a **Feladási** lapon, az **Összesítés** gyorslapon állítsa a **Bizonylattranzakciók** lehetőséget **Igen** beállításra.
