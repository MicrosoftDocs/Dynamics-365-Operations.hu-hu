---
title: Halasztott bevétel elszámolása
description: Ez a témakör a bevétel Bevétel megjelenítése funkcióval történő megjelenítését ismerteti.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ace1d00ec25a57b26b1858369c32d9134a380977
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570356"
---
# <a name="recognize-deferred-revenue"></a>Halasztott bevétel elszámolása

[!include [banner](../includes/banner.md)]

> [!NOTE]
> A „Bevétel elszámolása” funkció nem kapcsolható be a Funkciókezelés helyen. Jelenleg konfigurációs kulcsok használatával kapcsolhatja be.

Ez a témakör a bevételeknek a bevételmegjelenítési ütemezésben történő megjelenítését ismerteti. Amikor felad egy számlát egy értékesítési rendeléshez, a rendszer az értékesítési rendelés összes olyan sorához bevételmegjelenítési ütemezést hoz létre, amelyik rendelkezik bevételütemezéssel. A rendszer a sorban szereplő bevételütemezés alapján határozza meg, hogy el kell-e halasztani a sor bevételét.

## <a name="view-revenue-recognition-schedule-details"></a>A bevételmegjelenítési ütemezés részleteinek megtekintése

A bevételmegjelenítési ütemezés részletes adatait két módon lehet elérni.

- A bevételmegjelenítési ütemezés közvetlenül megnyitható a számlázott értékesítési rendelésekből. Ebben az esetben a program úgy szűri a bevételütemezés adatait, hogy csak a kiválasztott értékesítési rendelés részletei jelenjenek meg. Ez a módszer akkor hasznos, ha egy értékesítési rendelés ütemezésének a részleteit szeretné érvényesíteni.
- A bevételmegjelenítési ütemezés a **Bevételkönyvelés \> Időszakos feladatok** lapon is megnyitható. Ezt a módot általában akkor használják, ha egy időszak végén kerül sor a bevétel megjelenítésére. Az oldal első megnyitásakor nem látható információ. A rács fölötti szűrőkkel adhatja meg az ütemezés megjelenítendő részleteire vonatkozó feltételeket. A számla dátumai szűrhetők: megadhat dátumtartományt, értékesítési rendelést, vevőt, projektazonosítót vagy állapotot.

[![A Bevételek ütemezései oldal](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

A rács alatt lévő **Pénzügyi dimenzió** gyorslapon láthatók az értékesítési rendelés sorának pénzügyi dimenziói. Ezeket a dimenziókat vette figyelembe a rendszer a halasztott bevétel feladásakor. A bevétel megjelenítésekor ugyancsak figyelembe kell venni őket. A használt dimenzióértékek a bevételhez és a halasztott bevétel fő számláihoz rendelt számlastruktúrától függenek.

## <a name="recognize-revenue"></a>Bevétel megjelenítése

A bevétel a **Bevétel megjelenítése** oldal **Napló létrehozása** folyamatának futtatásával jeleníthető meg. Ez az oldal az értékesítési rendelésből és az **Időszakos feladatok** részről egyaránt megnyitható. Ha a folyamatot az értékesítési rendelésből futtatja, akkor a rendszer csak a kiválasztott értékesítési rendeléshez tartozó bevételt jeleníti meg. A folyamatot általában az **Időszakos feladatok** részről szokták futtatni, így a program az összes feladott értékesítési rendelési számla bevételét megjeleníti.

A bevétel kiválasztásához és feladásához használt feltételek megadásához a **Napló létrehozása** lehetőség kiválasztásával nyissa meg a **Napló létrehozása** párbeszédpanelt.

[![Naplólétrehozás paramétereinek megadása](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

A párbeszédpanelen a **Feldolgozás dátuma** mezőcsoport beállításaival adhatja meg a bevétel megjelenítésekor használt feladási dátumot. Ha a **Kiválasztott dátum** beállítást használja, akkor a **Tranzakció dátuma** mezőben megadhatja a feladási dátumot. Ha a **Bevétel ütemezési dátuma** lehetőséget választja, a program nem használja a tranzakció dátumát. A rendszer ehelyett az ütemezés egyes sorainak **Dátum felismerése** mezőjében szereplő értéket használja feladási dátumként.

Ezután az **Adott dátumtól** mezőben adja meg a bevétel megjelenítésének „adott dátumát”. A rendszer az ütemezés olyan sorait jeleníti meg, ahol a megjelenítés dátuma az „adott dátumra” esik vagy előtte van (ha a sorok nincsenek várakoztatva).

Miután megadott minden dátumot, a párbeszédpanel **OK** gombjára kattintva hozhatja létre a naplót. Egy tájékoztató üzenet jelenik meg, amelyből megmutatja, hogy hány tranzakció jött létre, illetve hogy a tranzakciók melyik naplóban jöttek létre. A napló feladása nem történik meg automatikusan. Ennek megfelelően a bevétel megjelenítéséért felelős vezetőnek van elég ideje ellenőrizni, hogy az ütemezés melyik sorainak a megjelenítésére kerül sor.

A folyamat futtatása után az ütemezés naplóba átvitt sorait **Feldolgozva** jelöléssel látja el a rendszer. A **Feldolgozva** jelölés azt mutatja, hogy a sorok átkerültek a naplóba – de feladottak vagy fel nem adottak egyaránt lehetnek. A **Feldolgozva** jelölést a bevételmegjelenítési napló feladása után sem távolítja el a rendszer. Ha viszont törli a bevételmegjelenítési naplót, vagy ha töröl egy sort, akkor a rendszer eltávolítja a **Feldolgozva** jelölést. Ilyenkor a sor akkor jeleníthető meg, ha a **Napló létrehozása** folyamat újra lefut.

[![A Bevételmegjelenítés ütemezései oldal](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Ha meg szeretné tekinteni, hogy milyen részletek megjelenítése van folyamatban, a **Bevételmegjelenítési napló** oldalon (**Bevételmegjelenítés \> Naplóbejegyzések \> Bevételmegjelenítési napló**) nyissa meg a **Sorok** részt. Az ütemezés éppen megjelenített soraihoz még akkor is mindig létrejön egy-egy külön tranzakció, ha az összes sor feladása ugyanazon a dátumon, ugyanazokkal a főkönyvi számlákkal történik.

[![A Naplóbizonylat oldal](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

A **Számla** oszlopban látható a halasztott bevétel főkönyvi számlája. Ez a főkönyvi számla nem szerkeszthető. Ez a korlátozás azt hivatott garantálni, hogy a megfelelő halasztott bevétel főkönyvi számlája legyen mentesítve. Ennek a főkönyvi számlának az érvényesítése nem a számlastruktúra szerint történik, mivel előfordulhat, hogy a főkönyvi számla módosult a bevétel hivatkozott főkönyvi számlájába történő legutóbbi feladása óta.

Az **Ellenszámla** oszlopban látható a bevétel főkönyvi számlája. Alapértelmezés szerint a bevétel főkönyvi számlája a készletfeladási profilokból származik, a pénzügyi dimenziók pedig az értékesítési rendelés sorából származnak. Ezt a főkönyvi számlát az aktuális számlastruktúra szerint ellenőrzi a program. Ha a számlastruktúra módosult és további pénzügyi dimenziókra van szükség hozzá, akkor a főkönyvi számla szerkeszthető.

Az alapértelmezett összeg az ütemezés megfelelő sorából származik, és nem módosítható.

Ha az értékesítési rendelés több pénznemet használ, akkor a program alapértelmezés szerint a számláról származó átváltási árfolyamot állítja be. Így biztosítható, hogy a könyvelési pénznem és a jelentési pénznem összegei teljes mértékben mentesítettek legyenek. A kerekítés miatt előfordulhat, hogy az ütemezés utolsó sorában lévő árfolyam némileg eltér a számlán szereplő árfolyamtól.

A bevételmegjelenítési napló feladása után a bizonylat bekerül az ütemezésbe. Ha az ütemezés valamelyik sorához több bizonylat tartozik, akkor a sorban egy csillag karakter (\*) látható. Az adott sorhoz feladott bizonylatok megtekintéséhez válassza ki a **Bizonylattranzakciók** lehetőséget.

## <a name="modify-the-revenue-recognition-schedule-details"></a>A bevételmegjelenítési ütemezés részleteinek módosítása

A bevételi ütemezés részletei között szereplő adatok többsége nem szerkeszthető. Nem adhatók hozzá új sorok az ütemezéshez, és a meglévő sorok sem törölhetők. A bevételnek az értékesítési rendelés egyes soraihoz tartozó ütemezési részleteit naprakészen kell tartani, hogy biztosítható legyen, hogy a szervezet mindig a halasztott összeggel egyező összeget jelenítse meg.

### <a name="edit-schedule-lines"></a>Az ütemezés sorainak szerkesztése

Az ütemezés sorainak néhány részlete szerkeszthető. A sorok következő mezői módosíthatók:

- **Várakoztatott** – ez a jelölő beállítható vagy törölhető a sor feldolgozása előtt. A jelölő törléséhez jelölje ki a sort, majd válassza a **Várakoztatás eltávolítása** lehetőséget. A várakoztatott sorok bevétele nem jeleníthető meg. Ha a bevétel ütemezését automatikus várakoztatáshoz állítja be, a sorok automatikusan várakoztathatók.

    [![Bevételütemezések – az ütemezés sorainak szerkesztése](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Megjelenítés dátuma** – a megjelenítés dátuma módosítható a sor feldolgozása előtt. Amikor a bevétel megjelenítésére szolgáló naplót létrehozó folyamat lefut, akkor a program felvesz egy dátumot a **Bevétel megjelenítése az adott dátumtól** mezőbe. A program összehasonlítja ezt a dátumot és a **Megjelenítés dátuma** mezőben megadott dátumot, hogy meghatározza a megjelenítendő sorokat.
- **Felszabadítandó összeg** – a felszabadításra kerülő összeg módosítható a sor feldolgozása előtt. A bevétel megjelenített összegét csak csökkentheti; az összeg nem növelhető. Ebben a mezőben a szervezetek megjeleníthetik a bevétel egy részét a megjelenítés dátumán. Ha az összeg módosul, akkor a **Fennmaradó összeg** mezőben szereplő összeg mutatja, hogy mekkora bevételt kell még megjeleníteni.
- **Kiadandó mennyiség** – ha a bevétel ütemezése egy előfordulásra vagy egy hónapra van beállítva, akkor a **Kiadandó mennyiség** mező az értékesítési rendelés sorához tartozó mennyiséget jeleníti meg. Ez a mező szerkeszthető, és egy másik módot biztosít a bevétel egy részének a megjelenítésére. Ha a sorban szereplő mennyiség például 5, akkor a mennyiség felülbírálható úgy, hogy kisebb legyen 5-nél. A **Felszabadítandó összeg** mezőben lévő összeg arányosan frissül.

### <a name="update-contract-terms"></a>Szerződési feltételek frissítése

A bevétel ütemezésének részletei a számla feladásakor az értékesítési rendelés sorához rendelt bevételütemezés alapján jönnek létre. Ha az értékesítési rendelés sorában szereplő bevételütemezés helytelen, az adat nem módosítható az értékesítési rendelésen az értékesítési rendelés számlázása után. Ehelyett a **Szerződési feltételek frissítése** gombbal kell módosítani a bevétel ütemezését. A bevétel ütemezése a bevétel megjelenítése előtt és után is módosítható.

Az ütemezés módosításához válassza ki a módosítani kívánt elem valamelyik ütemezési sorát. A következő ábrán a 12 hónapos bevételi ütemezés használatával feladott S0008 elemhez tartozó sor látszik kijelölve. A **Szerződési feltételek frissítése** lehetőség kiválasztásakor megjelenik a szerződés kezdő és záró dátumát, valamint a bevétel ütemezését tartalmazó párbeszédpanel.

[![A szerződés kezdő és záró dátuma](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Módosítsa úgy a szerződés kezdő és záró dátumát, hogy a dátumtartomány megfelelő legyen. A dátumtartomány módosításakor az **Ismétlődések száma** mezőben lévő értéknek meg kell egyeznie egy, a rendszerben megadott bevételi ütemezéssel. Mivel ebben a példában a szerződést 24 hónaposra módosítottuk, 24 hónapos bevételi ütemezést kell beállítani. Mivel létezik 24 hónapos bevételi ütemezés, a rendszer alapértelmezés szerint ezt adja meg, és a szerződés módosítható. Ha nem létezik olyan bevételi ütemezés, amely esetében egyezik az előfordulások száma, akkor a szerződés nem módosítható. Miután igény szerint frissítette a szerződési feltételeket és a bevételi ütemezést, a párbeszédpanel **OK** gombjára kattintva mentheti a módosításokat.

[![Szerződés frissített dátumtartománya](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

A szerződés módosításai a következő hatásokkal vannak a bevételi ütemezés részleteire:

- Ha a termékhez nincs megjelenített bevétel, a program az összes megelőző ütemezési részletet eltávolítja, és az új bevételi ütemezés részleteivel helyettesíti őket. Az S0008 elemhez eredetileg például 12 sor tartozott az ütemezési részletek között. Ezt a 12 sort eltávolítja a program; az új bevételi ütemezés alapján 24 vonalra cseréli őket.
- Ha a termékhez tartozik megjelenített bevétel, akkor néhány bevétel megjelenítése helytelen volt, mert a megjelenítés helytelen bevételi ütemezésen alapult. Ezeket a sorokat vissza kell vonni, és – az új ütemezés alapján – újra meg kell jeleníteni őket. Ebben az esetben olyan új bevételütemezési sorok jönnek létre, amelyek negatív összeggel rendelkeznek az eredeti megjelenítési dátumon. Ezután új sorok jönnek létre az összegek új bevételi ütemezés alapján történő megjelenítéséhez. 2019. augusztus 8-án például Ön megjelenített 10,53 USD bevételt. 2019. szeptember 8-án megjelenített 13,16 USD bevételt. Ennek megfelelően két új sor jön létre ugyanazon a napon. Egy sor -10,53 USD-hez, a másik sor pedig 13,16 USD-hez. Ezt követően huszonnégy új sor jön létre; a teljes halasztott bevételt (160,61 USD) közöttük osztja el a rendszer. A sztornírozási sorok a **Napló létrehozása** folyamat futtatásával adhatók fel.

[![Bevételmegjelenítési ütemezés](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)
