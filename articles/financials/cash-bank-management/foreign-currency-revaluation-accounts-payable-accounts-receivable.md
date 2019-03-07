---
title: A kötelezettségek és Kinnlevőségek árfolyam-korrekció
description: Az árfolyamok ingadozásai a devizában megadott nyitott tranzakciók elméleti értékét (könyv szerinti értéke) az idők során megváltoztatják. Ez a cikk tájékoztatást nyújt arról a devizaátértékelési folyamatról, amely a Kötelezettségek és Kinnlevőségek nyitott tranzakciók értékének frissítését elvégzik.
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da1aee4c678cb4786d52abc81b787edceaa5aa38
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "341327"
---
# <a name="foreign-currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>A kötelezettségek és Kinnlevőségek árfolyam-korrekció

[!include [banner](../includes/banner.md)]

Az árfolyamok ingadozásai a devizában megadott nyitott tranzakciók elméleti értékét (könyv szerinti értéke) az idők során megváltoztatják. Ez a cikk tájékoztatást nyújt arról a devizaátértékelési folyamatról, amely a Kötelezettségek és Kinnlevőségek nyitott tranzakciók értékének frissítését elvégzik. 

A nyitott szállítói tranzakciók devizában megadott elméleti értéke (könyv szerinti értéke) az idők során az árfolyam ingadozásának megfelelően változik. A kötelezettségek és Kinnlevőségek nyitott tranzakciók értékét frissítik, futtassa a deviza-átértékelési folyamat. A kötelezettségek és Kinnlevőségek árfolyam-korrekció. A folyamat átértékelni a nyitott összeg az új árfolyam használatával, vagy a Kiegyenlítetlen összegek, a megadott dátumon. Az eredetileg feladott összegek és az újraszámított összegek közötti különbségek azt eredményezik, hogy nem realizált nyereség vagy veszteség keletkezik minden nyitott tranzakciónál. A Kötelezettségek és Kinnlevőségek részkönyvszámlák ezután a nem realizált nyereséget vagy veszteséget tükrözve frissülnek, és egy könyvelési tétel kerül feladásra a főkönyvbe.

## <a name="simulate-a-foreign-currency-revaluation"></a>Devizaátértékelés szimulálása
Előtt meg idegen pénznemösszegek átértékelése nyitott tranzakciókra vonatkozó, futtathatja az árfolyam-korrekció dátuma és a metódus szimulációs jelentés. Az a szimulációs jelentés futtatásához a **Árfolyam-korrekció** lap a **Szimulációs** gombra. A jelentés tartalmazza a nem realizált nyereség vagy veszteség összegét, a szimuláció meghatározott paraméterek alapján előnézete.

## <a name="process-a-foreign-currency-revaluation"></a>Főkönyvi devizaátértékelés feldolgozása
Használja a **Devizaátértékelés** oldalt az **Időszakos feladatok** részben a nyitott tranzakciók átértékeléséhez. A folyamatot futtathatja valós időben, vagy köteg segítségével ütemezheti is. Az átértékelési folyamat beállításainak definiálásakor mindenképpen győződjön meg róla, hogy szeretne-e az eredményekről kinyomtatni egy jelentést. Az átértékelési jelentést a folyamat befejezése után nem lehet újra kinyomtatni. A deviza-átértékelési jelentés generál, ha jelenik különböző a vevő vagy szállító egyenlegeket és a pénznem:

-   A vevőre vagy szállítóra vonatkozik, amelyeknél az idegen pénznemű tranzakciókhoz van már újraértékelt egyenlegei. A következő egyenlegek kell meghatározni:
    -   Eredeti egyenlege a külföldi pénznemben.
    -   A devizaátértékelés összege a könyvelési pénznemben.
    -   A devizaátértékelés összege a könyvelési pénznemben.
    -   Az aktuális és az előző árrés közötti különbség. Ez a különbség a további nem realizált nyereség vagy veszteség.
-   Teljes nem realizált nyereség vagy veszteség minden egyes pénznemhez.

Árfolyam-korrekció minden futtatásakor mindig egy rekordot. A rekord a a **Idegen pénznemű Készletértékelés** oldalon válassza **Tranzakciók** miatt az átértékelés létrehozott tranzakciók részletes listáját tekintheti meg. Minden egyes bizonylattranzakció az átértékelésre került nyitott tranzakciónak felel meg. Ha egy nyitott tranzakció átértékelésére több mint egy alkalommal került sor, úgy két bejegyzés lesz látható, amely ugyanazt a bizonylatot használja. Egy rekord képviseli a korábbi nem realizált nyereség vagy veszteség visszaírását, a másik rekord pedig az új nem realizált nyereséget vagy veszteséget. Az átértékelési folyamat futtatásához kattintson a **Árfolyam-korrekció** gombra. A következő paraméterek megadása a munkalapsablonhoz:

-   **Módszer** – A kiválasztott devizaátértékelési feladatnál használt módszer:
    -   **Normál** – A Normál beállítás azt jelenti, hogy a deviza-átértékelési feladatok attól függetlenül fel lesznek adva, hogy az eredmény nyereség vagy veszteség.
    -   **Minimum** – A Minimum azt jelenti, hogy a devizaátértékelési feladatok veszteségeredmény esetén lesznek feladva.
    -   **Számla dátuma** – A Számla dátuma azt jelenti, hogy a devizaátértékelési feladatok a tranzakció eredeti árfolyamát használják, amelyeket a könyvelési pénznemben értékel át eredeti értékükre. Minden korábbi devizaátértékelés eredménye érvénytelenítve lesz.
-   **Figyelembe vett dátum** – Az a dátum, amelyiken a rendszer megkeresi az adott napon nyitott (ki nem egyenlített) összegekkel rendelkező összes tranzakciót. Az idegen pénznemben megadott összegeket a rendszer a Pénznemárfolyamok oldalon megadott **Átváltási árfolyamok** alapján értékeli át. Ha idegen pénznemben megadott összegeket a megállapítási dátumon értékelnek át, akkor ez a dátum lesz az átértékelt tranzakciók utolsó devizaátértékelési dátuma. Ha úgy dönt, hogy a már korrigált tranzakciókhoz tartozó legutóbbi korrekció dátumát megelőző devizaátértékelési dátumra vonatkozóan futtat devizaátértékelést, az ismétlődő feladat nem korrigálja azokat a tranzakciókat, amelyek a korábbi megállapítási dátumon nyitva vannak, de újabb legutóbbi devizaátértékelési dátum tartozik hozzájuk.
-   **Árfolyam dátuma** – Az devizaátértékelési tranzakcióban használt árfolyamot meghatározó dátum.
-   **Használt feladási profil a** – a feladási profilt, amely az alapértelmezett fő számlája megadására szolgál a Kinnlevőségek és kötelezettségek a könyvelési tételeket, a devizaátértékelés-tranzakciókra vonatkozó:
    -   **Feladás** – A vevői tranzakció feladási profilját használja a rendszer.
    -   **Választás** – A feladási profilt a **Feladási sablon** mezőben szereplő feladási profil határozza meg.
-   **Használt feladási profil** – Ha a**Használt feladási profil** helye mezőben a **Kiválasztás** érték szerepel, a devizaátértékelési tranzakciók feladási profilját az ebben a mezőben szereplő feladási profil határozza meg.
-   **Pénzügyi dimenziók** – A Tábla opció azt jelenti, hogy a vevőkód pénzügyi dimenziói lesznek feladva a devizaátértékelési tranzakcióra.
    -   **Nincs** – nem pénzügyi dimenziói vannak feladva. Ha szükséges, a pénzügyi dimenziók a számlastruktúrában, az átértékelési folyamat továbbra is fut, és, amelyeknél nincsenek dimenziók könyvelési tételeket hoz létre. Egy figyelmeztető üzenetet kap, úgy, hogy vissza tudja vonni az átértékelés.
    -   **Tábla** – A Tábla opció azt jelenti, hogy a vevőkód pénzügyi dimenziói lesznek feladva a devizaátértékelési tranzakcióra.
    -   **Feladás** – A Feladás opció azt jelenti, hogy az átértékelt tranzakció pénzügyi dimenziói lesznek feladva a devizaátértékelési tranzakcióra. Alapértelmezés szerint a pénzügyi dimenziók az eredeti tranzakció vevői/szállítói főkönyvi számláról az átértékelési tranzakció vevői/szállítói fő számla lesz, és az átértékelési tranzakció nem realizált nyereség/veszteség főszámla használandó pénzügyi dimenziókat az eredeti tranzakció költség/tárgyi eszköz/bevétel főkönyvi számláról.




