---
title: Miért nem lehet sztornírozni ezt a tranzakciót?
description: Ez a témakör különböző okokat ismertet, amelyek miatt a tranzakciókat nem lehet sztornírozni. A probléma megoldásait is felsorolja.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e18caf1dbdf8191713c17b1793f5da44cf2f182b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724529"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Miért nem lehet sztornírozni ezt a tranzakciót?

[!include [banner](../includes/banner.md)]

Ez a témakör különböző okokat ismertet, amelyek miatt a tranzakciókat nem lehet sztornírozni. A probléma megoldásait is felsorolja.

## <a name="symptom"></a>Tünet

A szervezetek olyan helyzetben lehetnek, amikor sztornírozniuk kell egy feladott tranzakciót. Esetenként a rendszer megakadályozza, hogy a tranzakciókat sztornírozza. Ez a viselkedés két kérdést vethet fel:

- Miért nem lehet sztornírozni ezt a tranzakciót?
- Hogyan befolyásolja ezt a viselkedést a Tömeges sztornírozás funkció?

## <a name="resolution"></a>Megoldás

Csak akkor lehet sztornírozni a tranzakciókat, ha teljesülnek bizonyos feltételek. A témakör további részei az egyes modulokra vonatkozó ellenőrzést biztosítják. Bár ez a témakör a Microsoft Dynamics 365 Pénzügy tranzakcióira fókuszál, néhány fogalom és ellenőrzés más alkalmazásokra, például az alkalmazásokra is alkalmazható Dynamics 365 Supply Chain Management.

Ezenkívül a tranzakció sztornírozásának helye is befolyásolhatja, hogy visszafordítható-e a tranzakció. Például egy csekként feladott szállítói kifizetést csak a bankszámlák tranzakciós lapján található **Csekkek** szakaszból lehet sztornírozni. Nem sztornírozható a főkönyv **Bizonylattranzakciók** lapján.

Ha a **Funkciókezelés** munkaterületén be van kapcsolva a **Tömeges sztornírozás több dokumentumhoz** funkció (más néven Tömeges sztornírozó funkció), akkor ez befolyásolja, hogy hány tranzakciót lehet sztornírozni, és hol lehet őket sztornírozni. Ez a funkció bekapcsolva két előnnyel jár:

- Bizonyos típusú tranzakcióknál egyszerre több tranzakció is kiválasztható és sztornírozható abból a naplóból, amelyből fel lett adva, illetve a **Bizonylattranzakciók** lapon. A funkció bekapcsolása előtt azonban az egyes tranzakcióknak sztornírozhatóknak kell lenniük. A funkció bevezetése előtt a tranzakciókat egyesével kellett sztornírozni.
- *Egyes* analitikus tranzakciók sztornírozhatóak a naplóból (általános napló) vagy a **Bizonylattranzakciók** lapról. Ezeket nem kell sztornírozni a Részfőkönyv lapról. Például egy szállítói számlanaplót előzőleg csak a **Szállítói tranzakciók** lapról lehetett sztornírozni. Most viszont a Főkönyv oldaláról is sztornírozható a naplóból vagy a **Bizonylattranzakciók** lapról. A témakör egyes részei bemutatják, hogy milyen típusú tranzakciókra nem alkalmazható ez az előny.

A Tömeges sztornírozás funkció **nem** teszi lehetővé több tranzakciótípus sztornírozát. Ha egy tranzakciótípust korábban nem lehetett sztornírozni, a funkció bekapcsolása után sem lehet sztornírozni. Például a beszerzési rendelés szállítói számláit nem lehet sztornírozni, függetlenül attól, hogy be van-e kapcsolva a Tömeges sztornírozás funkció.

A Tömeges sztornírozás funkcióval kapcsolatos további tudnivalókat lásd: [Naplófeladás sztornírozása](reverse-journal-posting.md).

## <a name="general-ledger"></a>Főkönyv

A főkönyvi helyesbítések bevitele csak főkönyvi számlákkal történik. Emiatt csak a főkönyvet frissítik.

Ha a Tömeges sztornírozás funkció ki van kapcsolva, a legtöbb főkönyvi kiigazítás egyenként is sztornírozható a főkönyv **Tranzakciók a \<main account\>-hoz** lapjáról (**LedgerTransAccount**). (A lap pontos címe a kiválasztott fő számlától függően eltérő.) A lapon a fő számlára feladott összes tranzakció látható. Általában a **Főkönyvi kivonatok listája** lapról, vagy a **Tranzakciók** lapnak a **Bizonylattranzakciók** lapon való kiválasztásával nyitható meg.

Ha a Tömeges sztornírozás funkció be van kapcsolva, egy vagy több főkönyvi bizonylat sztornírozható a **Bizonylattranzakciók** lapról, valamint abból a naplóból, amelyből a tranzakció fel lett adva. Kivételt képeznek a főkönyv devizaátértékelési, konszolidációs és év végi zárótranzakciói. Ezeknek a tranzakcióknak a sztornírozása azokból a lapokból történik, amelyekből az év végi zárás lefutott.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Okok, amelyek miatt a tranzakciókat nem lehet sztornírozni

A tranzakciók nem sztornírozhatóak a következő okokból:

- Általános napló:

    - A pénzügyi időszak fel van függve vagy véglegesen le van zárva:

        - Ha a sztornírozó dátum nem nyitott pénzügyi időszakban van, akkor a tranzakció nem sztornírozható.
        - Ha a tranzakció támogatja a sztornírozás dátumának bevitelét, akkor is sztornírozható a sztornírozás dátumának egy nyitott időszakra való módosításával.

    - Az év végi zárási folyamat lefutott:

        - A tranzakció könyvelési dátuma olyan pénzügyi évben van, amely év végi lezáráson ment keresztül. Bár a pénzügyi év egy időszaka még nyitott lehet, a tranzakció nem sztornírozható, ha már lefutott az év végi zárási folyamat a pénzügyi évre vonatkozóan. A pénzügyi év állapota eltér a benne lévő időszakok állapotától.
        - Az év végi lezárás sztornírozható, majd a tranzakció is sztornírozható. Lehet, hogy ez a megközelítés nem lehetséges. A pénzügyi lezárási folyamat állapotától függően egyszerűbb lehet manuálisan megadni a sztornírozó tranzakciót akár a lezárt pénzügyi év, akár a következő pénzügyi év nyitott időszakában. Ha az év végi zárási folyamat során a pénzügyi év egy nyitott időszakára új tranzakciót ad fel, akkor újra le kell futtatni az év végi zárási folyamatot.

    - A tranzakció sztornírozása már folyamatban van:

        - Ha a tranzakció sztornírozása folyamatban van, akkor a folyamatot be kell fejezni. Külön sztornírozási folyamatot nem lehet végezni. 
        - A sztornírozás befejezése után a sztornírozott tranzakció ismét sztornírozható (ez azt jelenti, hogy a sztornírozás sztornírozható).

    - Főkönyvi kiegyenlítés:

        - Ha a tranzakció egy vagy több sorát a **Főkönyvi kiegyenlítések** időszakos feladat (**Főkönyv \> Időszakos feladatok \> Főkönyvi kiegyenlítések**) segítségével egyenlítik ki úgy, hogy a rekord létezik a LedgerTransSettlement táblában, a tranzakciót nem lehet sztornírozni.
        - A főkönyvi kiegyenlítés sztornírozható, majd a bizonylat is sztornírozható.

    - Vállalatközi:

        - Ha a tranzakció vállalatközi tranzakció, akkor nem sztornírozható.
        - A tranzakció **nem** vállalatközi tranzakció, hanem a **Vállalatközi beállítás** lapon megadott "esedékes neki" vagy "esedékes tőle" fő számlára van feladva.

    - Időbeli elhatárolások:

        - Ha az elhatárolt főkönyvi bizonylat sztornírozva van, akkor az elhatárolt bejegyzés és az összes kapcsolódó résztranzakció sztornírozva lesz.
        - Az egyes elhatárolt résztranzakciókat nem lehet sztornírozni.

- Bevétel-megjelenítési napló:

    - A bevétel-megjelenítési tranzakciók nem sztornírozhatók.
    - Ha a bevételt a bevétel-megjelenítési napló elismeri, akkor a bizonylat csak a főkönyvi számlákra lesz feladva. Emiatt a **Bizonylattranzakciók**-hoz hasonló lapokon a tranzakciók úgy jelennek meg, mintha csak főkönyvi bejegyzések lennének.

- Deviza-átértékelés:

    - A deviza-átértékelési tranzakciók sztornírozhatóak, de csak abból a főkönyvi **Deviza-átértékelés** lapról, amelyről az átértékelést futtatták.
    - A sztornírozás csak akkor fejezhető be, ha azt nyitott pénzügyi időszakba könyvelik.

- Konszolidáció:

    - Konszolidációs tranzakciók sztornírozhatóak, de csak a **Konszolidációs tranzakciók** lapról.
    - A sztornírozás csak akkor fejezhető be, ha azt nyitott pénzügyi időszakba könyvelik.

- Év végi zárás:

    - Az év végi záró tranzakciókat (záró és nyitó tranzakciókat is) a következőképpen lehet sztornírozni:

        - Ha a Főkönyv év végi lezárási fejlesztései funkció ki van kapcsolva, jelölje be az **Előző lezárás visszavonása** beállítást az **Év végi lezárás** párbeszédpanelen.
        - Ha a Főkönyv év végi fejlesztések funkció be van kapcsolva, jelölje ki az év végi záráshoz létrehozott vállalati és pénzügyi év rekordokat az **Év végi lezárás** lapon, majd válassza az **Év végi lezárás sztornírozása** lehetőséget.

    - Ne feledje, hogy az év végi zárás sztornírozása ténylegesen törli a záró és a nyitó tranzakciókat. Sztornírozási bizonylat sosem lesz elküldve.

## <a name="accounts-payable"></a>Kötelezettségek

Több tranzakciótípus frissíti a Kötelezettségek részfőkönyvet. Ilyenek például a szállítói számlák, a szállítói számlanaplók és a költségjelentések.

Ha a Tömeges sztornírozás funkció ki van kapcsolva, a tranzakciók egyenként is sztornírozhatók a **Szállítói tranzakciók** lapon a számlák esetében, vagy a **Bankszámla** lapon a csekkbefizetések esetében.

Ha a Tömeges sztornírozás funkció be van kapcsolva, egy vagy több kötelezettséget is vissza lehet vonni a **Bizonylattranzakciók** lapról, és abból a naplóból, amelyből a tranzakciókat feladták. A szállítói kifizetéseket azonban továbbra is csak a bankszámláról lehet sztornírozni. Ezenkívül a főkönyv **Tranzakciók a \<main account\>-hoz** lapjáról nem lehet szállítói tranzakciókat sztornírozni. Csak a **Bizonylattranzakciók** lapon lehet őket sztornírozni.

Ne feledje, hogy egyes tranzakciókat egyáltalán nem lehet sztornírozni. Ilyenek például a beszerzési rendeléses szállítói számlák és az elektronikus szállítói kifizetések.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Okok, amelyek miatt a tranzakciókat nem lehet sztornírozni

A bizonylatok nem sztornírozhatóak a következő okokból:

- A pénzügyi időszak fel van függesztve vagy le van zárva:

    - Ha a sztornírozó dátum nem nyitott pénzügyi időszakban van, akkor a tranzakció nem sztornírozható.
    - Ha a tranzakció támogatja a sztornírozás dátumának bevitelét, akkor is sztornírozható a sztornírozás dátumának egy nyitott időszakra való módosításával.

- A főkönyvi év végi zárási folyamat lefutott:

    - A tranzakció könyvelési dátuma olyan pénzügyi évre esik, amely a főkönyvben le van zárva. Bár a pénzügyi év egy időszaka még nyitott lehet, a tranzakció nem sztornírozható, ha már lefutott az év végi zárási folyamat a pénzügyi évre vonatkozóan. A pénzügyi év állapota eltér a benne lévő időszakok állapotától.
    - Az év végi lezárás sztornírozható, majd a tranzakció is sztornírozható. Lehet, hogy ez a megközelítés nem lehetséges. A pénzügyi lezárási folyamat állapotától függően egyszerűbb lehet manuálisan megadni a sztornírozó tranzakciót akár a lezárt pénzügyi év, akár a következő pénzügyi év nyitott időszakában. Ha az év végi zárási folyamat során a pénzügyi év egy nyitott időszakára új tranzakciót ad fel, akkor újra le kell futtatni az év végi zárási folyamatot.

- Az analitikus napló bejegyzése nem került átvitelre a főkönyvbe:

    - Ez az ok csak a nem beszerzési rendelések szállítói számláira vonatkozik.
    - A **Még át nem vitt analitikusnapló-bejegyzések** lap használatával lehet átvinni a bejegyzést a főkönyvbe. Ezt követően sztornírozható a nem beszerzési rendelés szállítói számlája a **Szállítói tranzakciók** lapon.

- Kiegyenlítés:

    - A tranzakció (például számla vagy kifizetés) ki van egyenlítve vagy kiegyenlítésre van megjelölve.

        - A **Szállítói tranzakciók** lapon a **Kiegyenlítések megtekintése** vagy a **Kiegyenlítés \> Kiegyenlítési előzmények** lehetőség választásával ellenőrizheti, hogy egy tranzakció ki van-e egyenlítve vagy ki van-e jelölve kiegyenlítésre.
        - Ha valamelyik tranzakciót sztornírozni kell, akkor a kiegyenlítést a **Szállítói tranzakciók** lapról (**Kiegyenlítés \> Kiegyenlítés visszavonása**) is sztornírozhatja.

- A bizonylat több részfőkönyvi tranzakciót tartalmaz, amelyet ugyanazon bizonylatszám használatával jegyeztek (Egy bizonylat funkció problémája).
- A számla nincs jóváhagyva:

    - Ha a számlán nincs bejelölve a **Jóváhagyás** jelölőnégyzet, akkor a számlát nem lehet sztornírozni.

        - Ebben az esetben a jóváhagyás nem a munkafolyamat folyamatának jóváhagyására, hanem a számla **Jóváhagyás** beállítására vonatkozik. Ezzel a beállítással megakadályozhatja egy számla kifizetését. Rendszerint szállítói számlajegyzék-számlákhoz használatos.

- A tranzakció a számlagyűjtőben van:

    - A gyűjtőben található számlákat nem lehet közvetlenül a **Szállítói tranzakciók** lapról sztornírozni. Ehelyett sztornírozni kell az érvénytelenítési folyamaton keresztül a **Számla-jóváhagyási napló** lapon.

- A tranzakcióhoz egy javított szülőszámla is tartozik (indiai honosítás).
- A tranzakció kötelezvényállapota **Átutalt számla**.
- A tranzakciót részleges adóelszámolásra használják.
- A tranzakció szállítói számlát tartalmaz, de az adatok sztornírozása helytelen lapról történik, például a **Tranzakciók a \<main account\>-hoz** lapról:

    - Ahogy ez az ok jelzi, még a Tömeges sztornírozás funkció bekapcsolt állapota esetén is csak bizonyos lapokon lehet sztornírozni bizonyos részfőkönyvi tranzakciókat.

### <a name="types-of-transactions-that-cant-be-reversed"></a>A nem sztornírozható tranzakciók típusai

A következő típusú tranzakciókat nem lehet sztornírozni:

- Deviza-átértékelés:

    - A Főkönyvi devizaátértékeléssel ellentétben a Kinnlévőségek és a Kötelezettségek devizaátértékelései nem sztornírozhatók. Ehelyett újra kell futtatni az átértékelést a számladátum használatával. Ebben az esetben az átértékelés a számla dátumán szereplő árfolyamot használja, és alapvetően nullaként (0) hozza létre a nem realizált nyereséget vagy veszteséget. Emiatt az eredmény hasonlít a korábbi átértékelés eredményéhez. Ne feledje azonban, hogy ugyanaz az összeg nem lesz sztornírozva, ha a számlán módosították az alapértelmezett árfolyamot.

- Beszerzési rendelés, szállítói számla:

    - Jóváírást kell létrehozni a szállítói számla sztornírozásához. A sztornírozó tranzakció létrehozásáról a [Beszerzési visszárurendelés létrehozása](../../supply-chain/procurement/tasks/create-purchase-return-order.md) oldalon található további tájékoztatás.

- Kötelezvény
- Jóváírási exportszállítmány banki levele

## <a name="accounts-receivable"></a>Kinnlevőségek

Számos tranzakciótípus frissíti a Kinnlevőségek részfőkönyvét. Ilyenek például az értékesítési rendelésekből származó vevői számlák, az általános naplón keresztül bevitt vevői számlák, a szabadszöveges számlák, a vevői kifizetések és a leírások.

Ha a Tömeges sztornírozás funkció ki van kapcsolva, a tranzakciók egyenként is sztornírozhatók a **Vevői tranzakciók** lapon a számlák esetében, vagy a **Bankszámlák** lapon a letétek esetében. A kifizetések sztornírozásáról lásd a [Készpénz- és bankkezelés](cant-reverse-transctns.md#cash-and-bank-management) című szakaszt a témakör további részében.

Ha a Tömeges sztornírozás funkció be van kapcsolva, egy vagy több kinnlevőséget is sztornírozni lehet a **Bizonylattranzakciók** lapról, és abból a naplóból, amelyből a tranzakciókat feladták. A betéteket azonban továbbra is csak a bankszámláról lehet sztornírozni, a szabadszöveges számlákat pedig csak az eredeti oldalról lehet sztornírozni (ha be van kapcsolva a javításokat lehetővé tévő funkció). Ezenkívül a főkönyv **Tranzakciók a \<main account\>-hoz** lapjáról továbbra sem lehet vevői tranzakciókat sztornírozni. Azoban ezek sztornírozhatók a **Bizonylattranzakciók** lapról.

Ne feledje, hogy egyes tranzakciókat nem lehet sztornírozni. Ilyen lehet például az értékesítési rendelés vevői számlája és a leírás.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Okok, amelyek miatt a tranzakciókat nem lehet sztornírozni

A tranzakciók nem sztornírozhatóak a következő okokból:

- A pénzügyi időszak fel van függve vagy véglegesen le van zárva:

    - Ha a sztornírozó dátum nem nyitott pénzügyi időszakban van, akkor a tranzakció nem sztornírozható.
    - Ha a tranzakció támogatja a sztornírozás dátumának bevitelét, akkor is sztornírozható a sztornírozás dátumának egy nyitott időszakra való módosításával.

- A főkönyvi év végi zárási folyamat lefutott:

    - A tranzakció könyvelési dátuma olyan pénzügyi évben van, amely a főkönyvi év végi lezáráson ment keresztül. Bár a pénzügyi év egy időszaka még nyitott lehet, a tranzakció nem sztornírozható, ha már lefutott az év végi zárási folyamat a pénzügyi évre vonatkozóan. A pénzügyi év állapota eltér a benne lévő időszakok állapotától.
    - Az év végi lezárás sztornírozható, majd a tranzakció is sztornírozható. Lehet, hogy ez a megközelítés nem lehetséges. A pénzügyi lezárási folyamat állapotától függően egyszerűbb lehet manuálisan megadni a sztornírozó tranzakciót akár a lezárt pénzügyi év, akár a következő pénzügyi év nyitott időszakában. Ha az év végi zárási folyamat során a pénzügyi év egy nyitott időszakára új tranzakciót ad fel, akkor újra le kell futtatni az év végi zárási folyamatot.

- Az analitikus napló bejegyzése nem került átvitelre a főkönyvbe:

    - Ez az ok csak a szabadszöveges számlákra vonatkozik.
    - A **Még át nem vitt analitikusnapló-bejegyzések** lap használatával lehet átvinni a bejegyzést a főkönyvbe. A szabadszöveges számla ezután sztornírozható vagy javítható, ha engedélyezve van a javítási funkció.

- Kiegyenlítés:

    - A tranzakció (például számla vagy kifizetés) ki van egyenlítve vagy kiegyenlítésre van megjelölve.

        - A **Vevői tranzakciók** lapon a **Kiegyenlítések megtekintése** vagy a **Kiegyenlítés \> Kiegyenlítési előzmények** lehetőség választásával ellenőrizheti, hogy egy tranzakció ki van-e egyenlítve vagy ki van-e jelölve kiegyenlítésre.
        - Ha valamelyik tranzakciót sztornírozni kell, akkor a kiegyenlítést a **Vevői tranzakciók** lapról (**Kiegyenlítés \> Kiegyenlítés visszavonása**) is sztornírozhatja.

- A tranzakció több részfőkönyvi tranzakciót tartalmaz, amelyet ugyanazon bizonylatszám használatával jegyeztek (Egy bizonylat funkció problémája).
- A számla nincs jóváhagyva:

    - Ha a számlán nincs bejelölve a **Jóváhagyás** jelölőnégyzet, akkor a számlát nem lehet sztornírozni.

        - Ebben az esetben a jóváhagyás nem a munkafolyamat folyamatának jóváhagyására, hanem a bizonylatsorok **Jóváhagyás** beállítására vonatkozik. Ezzel a beállítással megakadályozhatja egy számla kifizetését. Bár ezt a lehetőséget általában a Kötelezettségeknél használják, a Kinnlevőségek között naplókban bevitt számlákhoz is használható.

- A tranzakcióhoz egy javított szülőszámla is tartozik (indiai honosítás).
- A tranzakció vevői számlát tartalmaz, de az adatok sztornírozása helytelen lapról történik, például a **Tranzakciók a \<main account\>-hoz** lapról:

    - Ahogy ez az ok jelzi, még a Tömeges sztornírozás funkció bekapcsolt állapota esetén is csak bizonyos lapokon lehet sztornírozni bizonyos részfőkönyvi tranzakciókat.

### <a name="types-of-transactions-that-cant-be-reversed"></a>A nem sztornírozható tranzakciók típusai

A következő típusú tranzakciókat nem lehet sztornírozni:

- Deviza-átértékelés:

    - A Főkönyvi devizaátértékeléssel ellentétben a Kinnlévőségek és a Kötelezettségek devizaátértékelései nem sztornírozhatók. Ehelyett újra kell futtatni az átértékelést a számladátum használatával. Ebben az esetben az átértékelés a számla dátumán szereplő árfolyamot használja, és alapvetően nullaként (0) hozza létre a nem realizált nyereséget vagy veszteséget. Emiatt az eredmény hasonlít a korábbi átértékelés eredményéhez. Ne feledje azonban, hogy ugyanaz az összeg nem lesz sztornírozva, ha a számlán módosították az alapértelmezett árfolyamot.

- Olyan tranzakció, amely helyesbíti az adóelőleget
- Rendelés – vevői számla:

    - Jóváírást vagy visszatérítést kell létrehozni a tranzakció sztornírozásához. A sztornírozó tranzakció létrehozásával kapcsolatos információkat lásd: [Értékesítési visszáruk](../../supply-chain/warehousing/sales-returns.md).

- Váltó
- Pénztári tranzakció
- Speciális kiigazítás
- Kamatlevél
- Fizetési felszólítás
- Jóváírás banki levele
- Szállítmány exportálása
- Bevétel-megjelenítési napló:

    - Ha a bevételt a bevétel-megjelenítési naplóból ismeri fel, akkor a bizonylatok csak a főkönyvi számlákra lesznek feladva. Emiatt úgy jelennek meg, mintha csak főkönyvi bejegyzések lennének. Ezek a bejegyzések nem sztornírozhatók, mert a bevétel ütemezése nem lesz újra megnyitva a bevétel ismételt megjelenítése érdekében.

## <a name="cash-and-bank-management"></a>Készpénz- és bankkezelés

Számos tranzakciótípus frissíti a Bank részfőkönyvet az általános naplóban. Ilyenek például a szállítói kifizetések, a vevői kifizetések és a banki átutalások.

Ha a Tömeges sztornírozás funkció ki van kapcsolva, a tranzakciók egyenként is sztornírozhatók a **Bankszámlák** lapon a csekkek és betétek esetében, vagy a **Vevői tranzakciók** lapon a vevői kifizetések esetében.

Ha a Tömeges sztornírozás funkció be van kapcsolva, egy vagy több kifizetési tranzakciót is vissza lehet vonni a **Bizonylattranzakciók** lapról, és abból a naplóból, amelyből a tranzakciókat feladták. A betéteket azonban továbbra is csak a bankszámláról lehet sztornírozni. Ezenkívül a főkönyv **Tranzakciók a \<main account\>-hoz** lapjáról továbbra sem lehet banki tranzakciókat sztornírozni. Azoban ezek sztornírozhatók a **Bizonylattranzakciók** lapról.

Ne feledje, hogy egyes tranzakciókat nem lehet sztornírozni. Ilyen például az elektronikus szállítói kifizetés.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Okok, amelyek miatt a tranzakciókat nem lehet sztornírozni

A tranzakciók nem sztornírozhatóak a következő okokból:

- A pénzügyi időszak fel van függve vagy véglegesen le van zárva:

    - Ha a sztornírozó dátum nem nyitott pénzügyi időszakban van, akkor a tranzakció nem sztornírozható.
    - Ha a tranzakció támogatja a sztornírozás dátumának bevitelét, akkor is sztornírozható a sztornírozás dátumának egy nyitott időszakra való módosításával.

- A főkönyvi év végi zárási folyamat lefutott:

    - A tranzakció könyvelési dátuma olyan pénzügyi évben van, amely a főkönyvi év végi lezáráson ment keresztül. Bár a pénzügyi év egy időszaka még nyitott lehet, a tranzakció nem sztornírozható, ha már lefutott az év végi zárási folyamat a pénzügyi évre vonatkozóan. A pénzügyi év állapota eltér a benne lévő időszakok állapotától.
    - Az év végi lezárás sztornírozható, majd a tranzakció is sztornírozható. Lehet, hogy ez a megközelítés nem lehetséges. A pénzügyi lezárási folyamat állapotától függően egyszerűbb lehet manuálisan megadni a sztornírozó tranzakciót akár a lezárt pénzügyi év, akár a következő pénzügyi év nyitott időszakában. Ha az év végi zárási folyamat során a pénzügyi év egy nyitott időszakára új tranzakciót ad fel, akkor újra le kell futtatni az év végi zárási folyamatot.

- Kiegyenlítés:

    - A tranzakció (kifizetés) ki van egyenlítve vagy kiegyenlítésre van megjelölve.

        - A **Szállítói tranzakciók** lapon a **Kiegyenlítések megtekintése** vagy a **Kiegyenlítés \> Kiegyenlítési előzmények**, illetve a **Vevői tranzakciók** lehetőség választásával ellenőrizheti, hogy egy tranzakció ki van-e egyenlítve vagy ki van-e jelölve kiegyenlítésre.
        - Ha valamelyik tranzakciót sztornírozni kell, akkor a kiegyenlítést a **Szállítói tranzakciók** vagy **Vevői tranzakciók** lapról (**Kiegyenlítés \> Kiegyenlítés visszavonása**) is sztornírozhatja.

- A tranzakció több részfőkönyvi tranzakciót tartalmaz, amelyet ugyanazon bizonylatszám használatával jegyeztek (Egy bizonylat funkció problémája).
- Áthidalt tranzakciók:

    - Ha a tranzakció áthidaló kifizetéshez kapcsolódik, akkor nem lehet sztornírozni.
    - Ha az áthidalt kifizetést sztornírozni kell, először le kell venni a kifizetést az áthidaló számláról a bank felé. Ezt követően sztornírozható a kifizetés, feltéve, hogy megfelel az egyéb ellenőrzési feltételeknek.

- A tranzakció tartalmaz egy bankszámlát, de a **Tranzakciók a \<main account\>-hoz** lapról vagy egy helytelen részfőkönyvből, például a Kinnlevőségek vagy a Tartozások lapról sztornírozódik:

    - Ahogy ez az ok jelzi, még a Tömeges sztornírozás funkció bekapcsolt állapota esetén is csak bizonyos lapokon lehet sztornírozni bizonyos részfőkönyvi tranzakciókat.

- Banki deviza-átértékelés:

    - A banki deviza-átértékelés sztornírozható. Ha azonban nem időrendi sorrendben hajtja végre a sztornírozás lépéseit, az megakadályozhatja a sztornírozást. Ha például márciusban és áprilisban futtatja az átértékelést, akkor a márciusi átértékelés csak az áprilisi átértékelés sztornírozása után sztornírozható.

### <a name="types-of-transactions-that-cant-be-reversed"></a>A nem sztornírozható tranzakciók típusai

A következő típusú tranzakciókat nem lehet sztornírozni:

- Elektronikus átutalási tranzakcióként (EFT) teljesített szállítói kifizetések
- Kötelezvények
- Váltók

## <a name="fixed-assets"></a>Tárgyi eszközök

Több tranzakciótípus frissíti a tárgyi eszközök analitikus naplóját. Ilyen például a beszerzés és az értékcsökkenés.

Ha a Tömeges sztornírozás funkció ki van kapcsolva, akkor a tranzakciók sztornírozása a tranzakció típusától függően egyenként a **Szállítói tranzakciók** lapról, a **Tárgyieszköz-tranzakciók** lapról vagy az Eszközlízing lapról történhet.

Ha a Tömeges sztornírozás funkció be van kapcsolva, egy vagy több Tárgyieszköz-tranzakciót is sztornírozni lehet a **Bizonylattranzakciók** lapról abban a naplóban, amelyben a tranzakciókat feladták.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Okok, amelyek miatt a tranzakciókat nem lehet sztornírozni

A tranzakciók nem sztornírozhatóak a következő okokból:

- A pénzügyi időszak fel van függve vagy véglegesen le van zárva:

    - Ha a sztornírozó dátum nem nyitott pénzügyi időszakban van, akkor a tranzakció nem sztornírozható.
    - Ha a tranzakció támogatja a sztornírozás dátumának bevitelét, akkor is sztornírozható a sztornírozás dátumának egy nyitott időszakra való módosításával.

- A főkönyvi év végi zárási folyamat lefutott:

    - A tranzakció könyvelési dátuma olyan pénzügyi évre esik, amely a főkönyvben le van zárva. Bár a pénzügyi év egy időszaka még nyitott lehet, a tranzakció nem sztornírozható, ha már lefutott az év végi zárási folyamat a pénzügyi évre vonatkozóan. A pénzügyi év állapota eltér a benne lévő időszakok állapotától.
    - Az év végi lezárás sztornírozható, majd a tranzakció is sztornírozható. Lehet, hogy ez a megközelítés nem lehetséges. A pénzügyi lezárási folyamat állapotától függően egyszerűbb lehet manuálisan megadni a sztornírozó tranzakciót akár a lezárt pénzügyi év, akár a következő pénzügyi év nyitott időszakában. Ha az év végi zárási folyamat során a pénzügyi év egy nyitott időszakára új tranzakciót ad fel, akkor újra le kell futtatni az év végi zárási folyamatot.

- Beszerzések:

    - Ha a beszerzés beszerzési rendelés szállítói számláján történt, a sztornírozást szállítói jóváírás megadásával kell elvégezni. A sztornírozó tranzakció létrehozásáról a [Beszerzési visszárurendelés létrehozása](../../supply-chain/procurement/tasks/create-purchase-return-order.md) oldalon található tájékoztatás.
    - A beszerzés projekttranzakción történt.
    - A beszerzés nem sztornírozható az eszköz értékcsökkenésének feladása után. A beszerzés sztornírozása előtt sztornírozni kell az értékcsökkenést.
    - Ha egy tárgyi eszköz értékmodelljének vagy értékcsökkenési könyvének állapota nem nyitott, akkor a tranzakció nem sztornírozható.

- Kivezetés:

    - A kivezetés szabadszöveges számlán keresztül történik:

        - A szabadszöveges számla helyesbítése zárolva van, ha az tárgyi eszközt tartalmaz. Ha viszont a tárgyi eszközt naplón keresztül vezeti ki, a szabadszöveges számla sztornírozható a tárgyieszköz-rekordból.

    - Ha egy tárgyi eszköz értékmodelljének vagy értékcsökkenési könyvének állapota nem nyitott, akkor a tranzakció nem sztornírozható.

- Értékcsökkenés:

    - Az értékcsökkenés **sztornírozható**, ha az ezt követő értékcsökkenést is feladják. Azonban figyelmeztetést fog kapni, mert ez a megközelítés nem a legjobb gyakorlat.
    - Ha egy tárgyi eszköz értékmodelljének vagy értékcsökkenési könyvének állapota nem nyitott, akkor a tranzakció nem sztornírozható.

- Egy adott eszközre és eszközkönyvre vonatkozó tranzakciók (vagy sztornírozott tranzakciók) a bizonylat tranzakciódátumán vagy később léteznek.
- A tranzakció tartalmaz egy eszközszámlát, de a **Tranzakciók a \<main account\>-hoz** lapról vagy egy helytelen részfőkönyvből, például a Kinnlevőségek vagy a Tartozások lapról sztornírozódik:

    - Ahogy ez az ok jelzi, még a Tömeges sztornírozás funkció bekapcsolt állapota esetén is csak bizonyos lapokon lehet sztornírozni bizonyos részfőkönyvi tranzakciókat.
    - Ha egy beszerzés nem beszerzési rendelés szállítói számlája vagy szállítói számlanapló alapján történik, akkor csak a Kötelezettségek **Szállítói tranzakciók** lapjáról sztornírozható.
    - Ha egy tárgyi eszközt Eszközlízingből szereznek be, akkor sztornírozható az Eszközlízing **Kötelezettségtranzakciók** lapján.
