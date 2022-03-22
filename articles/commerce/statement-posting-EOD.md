---
title: Kimutatásfeladás funkcionalitás továbbfejlesztései
description: Ez a témakör leírja a kimutatásfeladási funkción végrehajtott javításokat.
author: analpert
ms.date: 01/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: 6ee0cea76be05634aa21643acef5b341f19d75ef
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087603"
---
# <a name="improvements-to-statement-posting-functionality"></a>Kimutatásfeladás funkcionalitás továbbfejlesztései

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör leírja a kimutatásfeladási funkción végrehajtott javítások első készletét. Ezek a fejlesztések érhetők el a Microsoft Dynamics 365 for Finance and Operations 7.3.2 verziójában.

## <a name="activation"></a>Aktiválás

Alapértelmezés szerint a Finance and Operations 7.3.2 telepítés során a program be van állítva az örökölt szolgáltatással kivonat feladásához. A továbbfejlesztett kimutatásfeladási funkció engedélyezéséhez engedélyezni kell a konfigurációs kulcsot.

- Ugorjon ide: **Rendszerfelügyelet** \> **Beállítás** \> **Licenckonfiguráció**, a **Retail és Commerce** csomópont alatt törölje a jelet a **Kimutatások (korábbi verzió)** jelölőnégyzetből, és jelölje be a **Kimutatások** négyzetet.

Ha az új **Kimutatások** konfigurációs kulcs be van kapcsolva, elérhető egy új menüelem, amelynek a neve **Kimutatások**. Ez a menüpont kimutatások kézi létrehozását, számítását és feladását teszi lehetővé. Minden olyan kimutatás, amely a kötegelt feladási folyamat használata esetén hibát okoz, elérhető lesz a menüelem keresztül is. (Ha a **Kimutatások (korábbi verzió)** konfigurációs kulcs be van kapcsolva, a menüelem neve **Nyitott kimutatások**.)

A Commerce a következő ellenőrzéseket tartalmazza, amelyek ezekhez a konfigurációs kulcsokhoz kapcsolódnak:

- Mindkét konfigurációs kulcsot nem lehet egyszerre kell bekapcsolni.
- Ugyanazokat a konfigurációs kulcsokat kell használni az adott kimutatáson az életciklusa során végrehajtott összes művelethez (létrehozás, kiszámítás, törlés, feladás és így tovább). Például nem lehet létrehozni és kiszámítani egy kimutatást, amíg a **Kimutatás (korábbi verzió)** konfigurációs kulcs be van kapcsolva, és aztán megpróbálni feladni ugyanazt az utasítást, amíg a **Kimutatás** konfigurációs kulcs ki van kapcsolva.

> [!NOTE]
> Azt ajánljuk, hogy használja a **Kimutatások** konfigurációs kulcsot a továbbfejlesztett kimutatásfeladási szolgáltatáshoz, kivéve, ha nyomós oka van a **Kimutatások (korábbi verzió)** konfigurációs kulcs használatára helyette. A Microsoft folyamatosan dolgozik az új és továbbfejlesztett feladási funkción, és fontos váltani a legkorábban, hogy ki tudja használni. Az örökölt kimutatásfeladási funkciót kivezetjük 8.0-ás kiadástól.

## <a name="setup"></a>Beállítás

A kimutatásfeladási funkció javításának részeként három új paramétert vittek be a **Kimutatás** gyorslapján a **Feladás** lapján a **Commerce paraméterek** lapon:

- **Kimutatás tartalmának törlése letiltása** – Ez a beállítás csak az örökölt kimutatás feladási funkcióra alkalmazható. Azt ajánljuk, hogy a lehetőség beállítása legyen **Nem** megakadályozandó, hogy a felhasználók töröljék a félig feladott állapotú kimutatásokat. A félig feladott állapotú kimutatások törlésekor az adatok megsérülnek. Ezt a lehetőséget is ajánlott **Igen** értékre csak kivételes esetekben állítani.
- **Elérhető készlet lefoglalása a számítás során** – Ajánlott, hogy a **Készlet feladása** kötegelt feladatot használja a készletfoglalásre, és hogy ezen lehetőség beállítása **Nem** legyen. Ha a beállítás értéke **Nem**, a továbbfejlesztett kimutatás eladási funkció nem próbálja meg a számítás időpontjában a foglalási tétel készletnaplósorok létrehozását (ha a bejegyzések nem hozta létre már a **Készlet feladása** kötegelt feladat). Ehelyett a szolgáltatást csak a feladás időpontjában hoz létre készletfoglalási tételeket. Ez a megoldás tervezési döntés eredménye, és az az oka, hogy a számítási folyamat és a feladási folyamat között az időablak mérete általában kicsi. Ha a számítás időpontjában készlet lefoglalása a szándéka, beállíthatja ezt a lehetőséget **Igen** értékre.

    Az örökölt kimutatásfeladási szolgáltatás mindig elvégzi a készletfoglalást a kimutatás számítása során (ha a foglalást még nem tette meg a **Készlet feladása** kötegelt feladat), függetlenül a lehetőség beállításától.

- **Számlálás letiltása szükséges** – Ha ez a beállítás **Igen**, a kimutatás feladására használt eljárás tovább folytatódik akkor is, ha a kimutatáson a számolt összeg és a tranzakciós összeg közötti különbség túl van azon a küszöbértéken, amely meg van határozva az áruházak **Kimutatás** gyorslapján.

> [!NOTE]
> A Commerce 10.0.14-es verziójának kiadásától kezdve, amikor a **Kiskereskedelmi nyilatkozatok – Csomagolás** funkció engedélyezve van, a **Leltár feladása** A kötegelt munka már nem alkalmazható, és nem futtatható.

Ezenkívül a következő paraméterek kerültek be a **Kötegelt feldolgozás** gyorslapra a **Feladás lapra** a **Commerce paraméterek** oldalon: 

- **Párhuzamos kimutatásfeladások maximális száma** – Ez a mező a kötegelt feladatok számát határozza meg, amelyek több nyilatkozat feladása esetén használatosak. 
- **Szálak maximális száma a rendelésfeladáshoz kimutatásonként** – Ez a mező a kimutatás feladására szolgáló kötegelt feladat által az egyes kimutatások értékesítési rendeléseinek létrehozásához és számlázásához használt szálak maximális számát jelzi. A kimutatásfeladási folyamat által használt szálak teljes számát a program úgy számítja ki, hogy ezen paraméter értékét megszorozza a **Párhuzamos kivonatfeladások maximális száma** értékével. A paraméter értékének beállítása túl magasra negatív hatással lehet a kimutatásfeladási folyamatának teljesítményére.
- **Összesítésben szereplő maximális tranzakciós sorok** – Ez a mező azt határozza meg, hogy hány tranzakciós sor fog szerepelni egy összesített tranzakcióban, mielőtt újat hoz létre. Az összesített tranzakciók a különböző összesítési feltételek, például a vevő, az üzleti dátum vagy a pénzügyi dimenziók alapján jönnek létre. Fontos megjegyezni, hogy az egyetlen tranzakció sorait a rendszer nem osztja szét különböző összesített tranzakciók között. Ez azt jelenti, hogy előfordulhat, hogy egy összesített tranzakcióban a sorok száma valamivel magasabb vagy alacsonyabb olyan tényezők alapján, mint például a különböző termékek száma.
- **Üzleti tranzakciók ellenőrzéséhez szükséges szálak maximális száma** – A szálak maximális száma, amelyek a tranzakció ellenőrzéséhez fel lesznek használva. A tranzakciók érvényesítése olyan szükséges lépés, amelyet el kell végezni azelőtt, hogy a tranzakciókat be lehessen húzni a kimutatásba. Emellett szükség van egy **Ajándékutalvány-termék** meghatározására az **Ajándékutalvány** gyorslapján a **Feladás** lapnak a **Kereskedelmi paraméterek** lapon. Ezt definiálni kell akkor is, ha a szervezet nem használ ajándékutalványokat.

Az alábbi táblázat felsorolja az előző paraméterek ajánlott értékeit. Ezeket az értékeket tesztelni kell, és a telepítési konfigurációhoz és a rendelkezésre álló infrastruktúrához kell igazítani. Az ajánlott értékek bármilyen növelése hátrányosan befolyásolhatja a többi kötegelt feldolgozást, ezért azt érvényesíteni kell.

| Paraméter | Ajánlott érték | Részletek |
|-----------|-------------------|---------|
| Párhuzamos kivonatfeladások maximális száma | <p>Állítsa be ezt a paramétert a parancsot futtató kötegelt csoport számára elérhető kötegelt feladatok számára **Nyilatkozat** munka.</p><p>**Általános szabály:** Szorozza meg az Application Object Server (AOS) virtuális kiszolgálók számát az AOS virtuális kiszolgálónként elérhető kötegelt feladatok számával.</p> | Ez a paraméter nem alkalmazható, ha a **Kiskereskedelmi nyilatkozatok – Csomagolás** funkció engedélyezve van. |
| Rendelés feldolgozásához használt szálak maximális száma kimutatásonként | Kezdje el az értékek tesztelését itt **4**. Általában az érték nem haladhatja meg **8**. | Ez a paraméter határozza meg az értékesítési rendelések létrehozásához és feladásához használt szálak számát. Azt jelenti, hogy hány szál áll rendelkezésre nyilatkozatonként. |
| Egy aggregációban szereplő tranzakciós sorok maximális száma | Kezdje el az értékek tesztelését itt **1000**. A központ konfigurációjától függően a kisebb megrendelések előnyösebbek lehetnek a teljesítmény szempontjából. | Ez a paraméter határozza meg, hogy hány sor kerüljön bele az egyes értékesítési rendelésekbe a kimutatás feladása során. Miután elérte ezt a számot, a sorok új sorrendbe kerülnek felosztásra. Bár az értékesítési sorok száma nem lesz pontos, mivel a felosztás az értékesítési rendelés szintjén történik, közel lesz a beállított számhoz. Ez a paraméter értékesítési rendelések generálására szolgál olyan kiskereskedelmi tranzakciókhoz, amelyekhez nem tartozik megnevezett vevő. |
| Üzleti tranzakciók ellenőrzéséhez szükséges szálak maximális száma | Javasoljuk, hogy állítsa be ezt a paramétert **4**, és csak akkor növeli, ha nem ér el elfogadható teljesítményt. A folyamat által használt szálak száma nem haladhatja meg a kötegelt szerver számára elérhető processzorok számát. Ha túl sok szálat rendel hozzá, az befolyásolhatja a többi kötegelt feldolgozást. | Ez a paraméter azt szabályozza, hogy egy adott üzletben hány tranzakciót lehet egyszerre érvényesíteni. |

> [!NOTE]
> Minden beállítás és paraméter, amely kapcsolódik a kimutatásfeladásokhoz, és meg van határozva a kiskereskedelmi áruházak és a **Kereskedelmi paraméterek** oldalon, alkalmazható a továbbfejlesztett kimutatásfeladási funkcióra.

## <a name="processing"></a>Feldolgozás

A kimutatások kiszámíthatók és feladhatók kötegelve a **Kimutatások kötegelt kiszámítása** és a **Kimutatások feladása kötegben** menüpontban. Másik lehetőségként a kimutatások manuálisan kiszámíthatók és feladhatók a **Kimutatások** menüelemmel, amelyet a továbbfejlesztett kimutatásfeladási funkció lehetővé tesz.

A kimutatások kötegelt számítása és feladása folyamat lépései ugyanazok, mint az örökölt kimutatásfeladási funkciónál használtak. Azonban jelentős javítások történtek a kimutatások alapvető háttér-feldolgozása során. Ezek a fejlesztések rugalmasabbá tették a folyamatot, és az állapot- és hibainformációk jobb láthatósággal rendelkeznek. Ezért a felhasználók megoldhatják a hibák kiváltó okát, és folytathatják a feladási folyamatot anélkül, hogy ez adatsérüléshez vezethetne, és anélkül, hogy az adatokat javítani kellene.

Az alábbi szakaszok leírják a kimutatásfeladási funkció fő javításait, amelyek a feladott kimutatások és a kimutatások felhasználói felületén jelennek meg.

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

A könyvelési folyamat során a készpénzes átvételi tranzakciókat a rendszer vásárlónként és termékenként összesíti. Ezért csökken a létrehozott értékesítési rendelések és sorok száma. Az összesített tranzakciókat a rendszer tárolja, és értékesítési rendelések létrehozására szolgál. Minden összesített tranzakció egy megfelelő értékesítési rendelést hoz létre a rendszerben. 

Ha egy kimutatás nincs teljesen feladva, megtekintheti az összesített tranzakciókat a kimutatásban. A Műveleti ablakban a **Nyilatkozat** lapon, a **A végrehajtás részletei** csoport, válassza ki **Összesített tranzakciók**.

![Összesített tranzakciók gomb egy olyan kimutatáshoz, amely nincs teljesen feladva.](media/aggregated-transactions.png)

A feladott kivonatok esetében megtekintheti az összesített tranzakciókat a **Közzétett nyilatkozatok** oldalon. A Műveleti ablakban válassza ki a lehetőséget **Érdeklődések**, majd válassza ki **Összesített tranzakciók**.

![Összesített tranzakciók parancs a feladott kimutatásokhoz.](media/aggregated-transactions-posted-statements.png)

A **Az értékesítési rendelés részletei** Egy összesített tranzakció FastTab a következő információkat jeleníti meg:

- **Rekordazonosító** – Az összesített tranzakció azonosítója.
- **Kimutatás száma** – A kimutatás, amelyhez az összesített tranzakció tartozik.
- **Dátum** – A dátum, amikor az összesített tranzakciót létrehozták.
- **Értékesítési azonosító** – Értékesítési rendelés létrehozásakor az összesített tranzakcióból, az értékesítési rendelés azonosítója. Ha ez a mező üres, akkor a megfelelő értékesítési rendelés még nem jött létre.
- **Összesített sorok száma** – Az összesített tranzakciónál és az értékesítési rendelésnél a sorok száma összesen.
- **Állapot** – Az összesített tranzakció utolsó állapota.
- **Számlaazonosító** – Az összesített tranzakció az értékesítési rendelésének számlázása esetén az értékesítési számla azonosítója. Ha ez a mező üres, akkor az értékesítési rendelés számláját még nem adták fel.
- **Hibakód** – Ez a mező akkor van beállítva, ha az összesítés hibaállapotban van.
- **Hiba üzenet** – Ez a mező akkor van beállítva, ha az összesítés hibaállapotban van. Részleteket mutat be arról, hogy mi okozta a folyamat sikertelenségét. A hibakódban található információk segítségével kijavíthatja a problémát, majd manuálisan indíthatja újra a folyamatot. A feloldás típusától függően előfordulhat, hogy az összesített értékesítéseket törölni kell, és új kimutatáson kell feldolgozni.

![Az összesített tranzakció értékesítési rendelés részletei gyorslapján található mezők.](media/aggregated-transactions-error-message-view.png)

A **Tranzakció részletek** Az összesített tranzakció gyorslapja az összesített tranzakcióba bevont összes tranzakciót mutatja. Az összesített tranzakció összesített sorai megjelenítik a tranzakciók minden összesített rekordját. Az összesített sorok részleteket is megjelenítenek, például cikk, változat, mennyiség, ár, nettó összeg, egység és raktár. Alapvetően egy értékesítésirendelés-sor egy összesített sornak felel meg.

![Tranzakció részletei Összesített tranzakció gyorslapja.](media/aggregated-transactions-sales-details.png)

Egyes helyzetekben előfordulhat, hogy az összesített tranzakciók nem tudják feladni az összevont értékesítési rendelést. Ezekben a helyzetekben egy hibakód lesz társítva az utasítás állapotához. Ha csak a hibás összesített tranzakciókat szeretné megtekinteni, engedélyezheti a **Csak a hibákat jelenítse meg** szűrheti az összesített tranzakciók nézetben a jelölőnégyzet bejelölésével. A szűrő engedélyezésével az eredményeket az összesített tranzakciókra korlátozza, amelyek megoldást igénylő hibákat tartalmaznak. A hibák kijavításával kapcsolatos információkért lásd: [Szerkessze és auditálja az online rendeléseket és az aszinkron ügyfélrendelési tranzakciókat](edit-order-trans.md).

![A Csak a hibák megjelenítése szűrő jelölőnégyzete az összesített tranzakciók nézetben.](media/aggregated-transactions-failure-view.png)

A **Összesített tranzakciók** oldalon töltheti le az XML-t egy adott összesített tranzakcióhoz, ha kiválasztja **Összesített adatok exportálása**. Bármely XML-formázóban megtekintheti az XML-t, hogy megtekinthesse az értékesítési rendelések létrehozásával és feladásával kapcsolatos tényleges adatok részleteit. Az összesített tranzakciók XML-kódjának letöltése funkció nem használható a feladott kimutatásoknál.

![Összesített adatok exportálása gomb az Összesített tranzakciók oldalon.](media/aggregated-transactions-export.png)

Abban az esetben, ha a hibát nem tudja kijavítani az értékesítési rendelés adatainak vagy az értékesítési rendelést alátámasztó adatoknak a javításával, egy **Ügyfélrendelés törlése** gomb elérhető. Megrendelés törléséhez válassza ki a sikertelen összesített tranzakciót, majd válassza ki **Ügyfélrendelés törlése**. Mind az összesített tranzakció, mind a megfelelő értékesítési rendelés törlődik. Mostantól áttekintheti a tranzakciókat a szerkesztés és ellenőrzés funkció használatával. Alternatív megoldásként újra feldolgozhatók egy új nyilatkozattal. Az összes hiba kijavítása után folytathatja a kivonat feladását a vonatkozó utasításhoz tartozó post utasítás függvény futtatásával.

![Ügyfélrendelés törlése gomb az összesített tranzakciók nézetben.](media/aggregated-transactions-delete-cust-order.png)

Az összesített tranzakciók nézete a következő előnyöket nyújtja:

- A felhasználók rálátást kapnak az értékesítési rendelés létrehozása során nem sikerült összesített tranzakciókhoz, és az értékesítési rendelések sikertelen számlázásaihoz.
- A felhasználók rálátást kapnak, hogy hogyan vannak összesítve a tranzakciók.
- A felhasználó teljes auditnaplóval rendelkezik, a tranzakcióktól az értékesítési rendelésekig és az értékesítési számlákig. Az auditnapló nem áll rendelkezésre az örökölt kimutatásfeladási szolgáltatásban.
- Az összesített XML-fájl megkönnyíti a problémák azonosítását az értékesítési rendelések létrehozása és a számlázás során.

### <a name="journal-vouchers"></a>Naplóbizonylatok

A **Naplóbizonylatok** gomb a **Végrehajtás részletei** csoportjában a kimutatásnak a kimutatáshoz létrehozott összes különböző bizonylatot jeleníti meg, amelyek kapcsolatosak az engedményekkel, a bevétel/kiadás számlákkal, az ajándékutalvány kártyákkal és így tovább.

Jelenleg a program csak a feladott kimutatásokra jeleníti meg ezeket az adatokat.

### <a name="payment-journals"></a>Kifizetési naplók

A **Fizetési naplók** gomb a **Végrehajtás részletei** csoportjában a kimutatás csoportnak a kimutatáshoz létrehozott minden különböző kifizetési napló látható.

Jelenleg a program csak a feladott kimutatásokra jeleníti meg ezeket az adatokat.

## <a name="other-improvements"></a>További fejlesztések

A kimutatásfeladási funkción egyéb, a felasználó által látható, háttérrendszeren végrehajtott javítások történtek. Íme néhány példa:

- Az összesítés nem veszi figyelembe a terminál, személyzet és műszak entitásokat. Mivel kevesebb összesítési paramétert van, kevesebb értékesítésirendelés-sort kell feldolgozni.
- Kölcsönös kizárás az tranzakció táblákon való előfordulása ritkább a további bővítménytáblák bevezetésével, és a tranzakciós táblákon beszúrási műveletek végrehajtásával a frissítési műveletek helyett.
- A futó kötegelt feladatok száma paraméterezett, és korlátozott. Ezért ez a szám finomhangolható kifejezetten a vevői környezethez. Az örökölt kimutatásfeladási funkcióban, korlátlan számú kötegelt feladat jött létre egyszerre. Az eredmény kezelhetetlen terhelés, többletköltségeket, és a kötegkiszolgáló szűk keresztmetszetei volt.
- A kimutatások hatékonyan kerülnek várólistára a feldolgozáshoz: a tranzakciók maximális számával rendelkező kimutatások kapnak prioritást.
- A kötegelt folyamatok, például a **Kimutatások kötegelt kiszámítása** és a **Kivonatok feladása kötegben**, csak kötegelt módban futnak. Az örökölt kimutatásfeladási funkcióban a felhasználók interaktív módban futtathatták a kötegelt folyamatokat, amely egyetlen szálas művelet, ellentétben a kötegelt folyamatokkal, amelyek többszálasak.
- Az örökölt kimutatásfeladási funkcióban a kötegelt művelet hibája a teljes kötegelt feladatot hibaállapotba helyezte. A továbbfejlesztett funkcióban a kötegelt művelet hibái nem helyezik a kötegelt feladatot hibaállapotba, ha más kötegelt műveletek sikeresen befejeződtek. Ajánlott először megvizsgálni a kötegelt végrehajtás futtatásának feladási állapotát a **Kimutatások** lapon, amelyen megtekintheti az esetleges hibák miatt nem feladott kimutatásokat.
- Az örökölt kimutatásfeladási funkcióban az első kimutatáshiba hatására sikertelen lesz a teljes köteg. A fennmaradó kimutatások nincsenek feldolgozva. A továbbfejlesztett funkcióban a kötegelt feldolgozás tovább folytatja minden jelentés feldolgozását akkor is, ha a kimutatások némelyike hibát okoz. Egyik előnye, hogy a felhasználók rálátást kapnak a hibák kimutatások pontos számára. Ezért felhasználók nem kerülnek végtelen körbe, amelyben hibákat javítanak, és addig futtatják a kimutatás feladása folyamatot, amíg meg nem történik az összes kimutatás feladása.

## <a name="general-guidance-about-the-statement-posting-process"></a>A kimutatásfeladási folyamattal kapcsolatos általános útmutatás

- Javasoljuk, hogy a kivonat feladása folyamatot kötegben futtassa, mert a kötegelt futtatás kihasználja a kötegkeretrendszer többszálas teljesítményét. Többszálas végrehajtás szükséges a kimutatásfeladásoknál általában látható nagyon nagy mennyiségű tranzakció kezeléséhez.
- Ajánlott bekapcsolni a cikkmodellcsoport negatív tényleges készletét, hogy a feladás zökkenőmentes legyen. Bizonyos esetekben a negatív kimutatásokat nem lehet feladni, hacsak nincs negatív tényleges készlet. Például elméletben, ha a készleten egy cikkból csak egy egység van, és volt egy értékesítési tranzakció és egy visszáru-tranzakció a cikkhez, a tranzakciónak feladhatónak kell lennie akkor is, ha a negatív készlet nincs bekapcsolva. Mivel azonban a kimutatásfeladási folyamat a vevőre sorrendben kéri le az értékesítési tranzakciót és a visszáru-tranzakciót, nem biztos, hogy az értékesítési sor lesz először feladva, majd a visszárusor követi. Ezért hibák léphetnek fel. Ha a negatív készlet be van kapcsolva ebben az esetben, a tranzakció feladása nem lesz hátrányosan érintett, és a rendszer megfelelően tükrözi a készletet.
- Ajánlott az összesítés használata a kimutatások kiszámítása és feladása során. Emiatt a következő beállítások javasoltak az összesítési paraméterek egy részéhez:

    - Menjen a **Retail és Commerce** \> **Központ beállítása** \> **Paraméterek** \> **Kiskereskedelmi paraméterek** lehetőségre. Ezután a **Feladás** lapon, a **Készletmódosítás** gyorslapon, a **Részletességi szint** mezőben válassza ki az **Összegzés** lehetőséget.
    - Menjen a **Retail és Commerce** \> **Központ beállítása** \> **Paraméterek** \> **Kiskereskedelmi paraméterek** lehetőségre. Ezután a **Feladási** lapon, az **Összesítés** gyorslapon állítsa a **Bizonylattranzakciók** lehetőséget **Igen** beállításra.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
