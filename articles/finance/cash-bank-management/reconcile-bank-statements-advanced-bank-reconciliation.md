---
title: Banki kivonatok egyeztetése továbbfejlesztett banki egyeztetés használatával
description: A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a témakör az egyeztetési folyamatot ismerteti.
author: saraschi2
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationWorksheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98243
ms.assetid: 9df13adf-aa9d-4f6b-bde6-25a214611692
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95c216d59cb5eadb24aa0ca00ab53866d697e6c2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226461"
---
# <a name="reconcile-bank-statements-by-using-advanced-bank-reconciliation"></a>Banki kivonatok egyeztetése továbbfejlesztett banki egyeztetés használatával

[!include [banner](../includes/banner.md)]

A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a témakör az egyeztetési folyamatot ismerteti.  

<a name="import-an-electronic-bank-statement"></a>Az elektronikus banki kivonat importálása
-----------------------------------

A banki kivonatok importálása az **Importnyilatkozat** használatával a **Banki kivonatok** oldalon. A banki kivonaton a bankszámla a bankszámla adatainál beállított értékek kombinációja alapján azonosított. Ezek az értékek magukba foglalják a bank nevét, a bankszámla számot, az útvonalszámot, a Society for Worldwide Interbank Financial Telecommunication (SWIFT) kódot és az International Bank Account Number (IBAN) kódot. 

Feltölthet olyan banki kivonatot, ami egy vagy több számla információt tartalmazza. Több számla esetén a számlák tulajdonosai különböző jogi személyek lehetnek.

-   Egy banki kivonat egy számlához importálásához, állítsa be az **Kivonat importálása több bankszámláról az összes jogi személynél** lehetőséget **Nem** értékre, és válassza ki a kivonathoz tartozó bankszámlát. Kattintson a **Keresés** gombra, hogy kijelölje a kapcsolódó banki kivonat fájlt, majd kattintson a **Feltöltés** gombra.
-   Egy banki kivonat fájl több fiókhoz importálásához, állítsa be a **Kivonat importálása több bankszámláról az összes jogi személynél** lehetőséget **Igen** értékre. Kattintson a **Keresés** gombra, hogy kijelölje a kapcsolódó banki kivonat fájlt, majd kattintson a **Feltöltés** gombra.

Ha az elektronikus fájlban található bármelyik kivonatot nem lehet társítani egy bankszámlához az azonosító mezők használatával, vagy több bankszámlához van társítva, akkor ez a kivonat nem lesz importálva. A fájlban található többi kimutatás importálása azonban megtörténik. A felhasználó ezután kap egy üzenetet, amely arról tájékoztatja, hogy a banki kivonatok importálása a meghatározott bankszámlák esetében sikertelen volt. Ne feledje, hogy a felhasználónak, aki a bankszámlakivonat-fájlt importálja, hozzáféréssel kell rendelkezni a jogi személyhez ahhoz, hogy importálni tudja a jogi személy bankszámlájához tartozó kivonatokat. 

Egy zip-fájl segítségével egyetlen folyamatban több kivonatfájlt tölthet fel a Finance megoldásba. Több kivonat több bankszámlához importálásához, egyesítse az összes banki kivonat fájlt egy zip-fájlba. A **Banki kivonatok importálása** párbeszédpanelen, állítsa a **Kivonat importálása több bankszámláról az összes jogi személynél** lehetőséget **Igen** értékre. Kattintson a **Keresés** gombra, hogy kijelölje a zip fájl, ami a kapcsolódó banki kivonat fájlokat tartalmazza, majd kattintson a **Feltöltés** gombra. Az importálási folyamat felismeri a zip-fájlt, és feltölt minden kimutatást, amelyet tartalmaz, a bankszámla jogi személyétől függetlenül.

Az **Egyeztetés importálás után** lehetőség elérhető. Ha ennek a lehetőségnek az értéke **Igen**, a rendszer automatikusan ellenőrzi a banki kivonatot, létrehoz egy új bank egyeztetést és egy munkalapot, majd futtatja a banki kivonat feltöltésekor Alapértelmezett egyeztetési szabálykészletet. Ez a funkció automatizálja a folyamatot addig a pontig, ahol már a tranzakciókat kézzel kell egymáshoz rendelni.

## <a name="validate-the-bank-statement"></a>Banki kivonat ellenőrzése
Egy nyilatkozat érvényesítéséhez kattintson az **Ellenőrzés** gombra a **Banki kivonatok** oldalon. A Banki kivonatokat ellenőrizni kell, mielőtt egyeztethetőek lehetnének. Ez a lépés automatikusan végrehajtott, ha az **Importálás után egyeztetés** beállítás **Igen** értékre van állítva az importálás időpontjában. 

Banki kivonat érvényesítése a következőket ellenőrzi:

-   A banki kivonat megegyezik-e a kiválasztott bankszámlával.
-   A banki kivonat egyenlege megegyezik-e a kiválasztott bankszámla egyenlegével.
-   A kivonat nyitó egyenlege megegyezik-e az adott bankszámla előző kivonatának záró egyenlegével.
-   A dátum nem fedi-e át egy másik, ugyanahhoz a bankszámlához tartozó banki kivonat dátumát.
-   Nincsenek-e dátumbeli hiányok a kimutatásokban az adott bankszámlában:
-   A kimutatássorok dátumai a banki kivonat kezdő és befejező dátuma között van-e.
-   A nyitó egyenleg és az összesített sor összeg egyenlő-e a záró egyenleggel.

Az ellenőrzés befejezése után, a banki kivonat állapota frissül **Érvényesített** értékre. A banki kivonatot ellenőrizni kell, mielőtt az egyeztethető lehetne.

## <a name="reconcile-the-bank-statement"></a>A banki kivonat egyeztetése
Miután importált és érvényesített egy elektronikus banki a kivonatot a **Banki kivonatok** oldalon, egyeztetheti a banki kivonatot a **Banki egyeztetés** és a **Banki egyeztetési munkalap** lapok használatával. 

A **Banki egyeztetés** lapon, kattintson az **Új** gombra, hogy létre hozzon egy új egyeztetést, majd ezután válassza ki az importált kivonathoz tartozó bankszámlát. Egy bankszámlához csak egy nyitott banki egyeztetés érhető el. A fordulónap dátuma határozza meg, az egyeztetési munkalapon szereplő bankszámlakivonat tranzakciókat és Operations banki tranzakciókat. Alapértelmezés szerint az aktuális rendszerdátum a fordulónap dátuma, de az egyeztetésben a dátum módosítható. A fennmaradó fejléc információ automatikusan származtatott a kivonatból. Ez a lépés automatikusan végrehajtott, ha az **Importálás után egyeztetés** beállítás **Igen** értékre van állítva az importálás időpontjában. 

A **Banki egyeztetés** oldalon, kattintson a **Munkalap** gombra, a **Banki egyeztetési munkalap** oldal megnyitásához. Ha az **Összehangolás importálás után** beállítás **Igen** értékre van beállítva, az Alapértelmezett egyeztetési szabály készlet automatikusan elindul az egyeztetéshez. Egyeztetési szabályok kézi futtatásához kattintson az **Egyeztetési szabályok futtatása** gombra, hogy kijelölje banki tranzakciókra futtatandó szabálykészleteket vagy egyeztetési szabályokat. Ha sok a feldolgozandó tranzakció, kötegelt feladatként is végre hajthatja ezt a lépést. 

A **Banki egyeztetési munkalap** oldal négy rácsot tartalmaz, amik a tranzakciókat tartalmazzák. A két felső rács mutatja a banki kivonatokból és az Operations megoldásból még nem egyeztetett tranzakciókat. A két alsó rács az egyeztetett tranzakciókat jeleníti meg. A **Banki kivonat tranzakció részletei** lap mutatja a felső rácson kiválasztott nem egyeztetett bankszámlakivonat tranzakció részleteit. 

Három mód van a bankszámlakivonat tranzakciók összeillesztésére vagy egyeztetésére:

-   Tranzakciók egyeztetése Operations banki tranzakciókkal.
-   Tranzakciók egyeztetése sztornírozási bankszámlakivonat tranzakcióval.
-   Tranzakciók megjelölése **Új** értékként, így később könyvelhetők, mint banki tranzakció a Finance rendszerben.

Tranzakciók manuális egyeztetéséhez, jelölje ki a tranzakciókat a **Banki kivonat tranzakciók** rácsban, majd válassza ki a megfelelő tranzakciókat az **Operations banki tranzakciók** rácsban, és kattintson **Egyeztetés** gombra. A kijelölt tranzakciók átkerülnek a nem egyeztetett tranzakciókat tartalmazó felső rácsokról a kiegyenlített tranzakciókat tartalmazó alsó rácsokra. Ezenkívül, az egyeztetett és a nem egyeztetett összegezett értékek frissülnek. Lehet egy az egyhez, több az egyhez és több a többhöz tranzakció megegyezés. Az egyeztetéseknek meg kell felelniük az engedélyezett dátum különbségek és tranzakciótípus leképezések szabályainak. Ezek a szabályok a **Pénz és bank menedzsment paraméterek** oldalon vannak megadva .

Fillér eltérések előfordulhatnak az egyeztetés során. Egyeztethet egy banki kivonat tranzakciót és egy Operations banki tranzakciót, amik fillér eltérésekkel rendelkeznek, ha az eltérés a tűréshatárokon belül van, amit a bankszámla **Megengedett fillér eltérés** mezője határoz meg. Az összeg az egyeztetett Operations banki tranzakció banki tranzakció **Korrekciós összeg** mezőben jelenik meg. Ha a banki egyeztetés egyeztetettként van bejelölve, a javítások feladása automatikusan történik, a kapcsolódó banki tranzakciótípusnál definiált fő számla segítségével. A javítások nem támogatottak az **Ellenőrzés** és a **Letét** dokumentumtípusok esetében. 

Banki kivonat tranzakciók sztornírozások az egyeztetés munkalap használatával egyeztethetőek. Két kimutatássor egyeztethető, ha összegeket ellentétesek, és az egyik tranzakció visszaírásra van megjelölve. Beállíthat egy egyeztetési szabályt, a **Sztornírozás kimutatássorok törlése** műveletre.

A sztornírozott Operations banki tranzakciókat egyeztetni kell az **Operations banki tranzakciók** oldal használatával. Egyeztethet két Operations banki tranzakciót, ha a dokumentumokon ugyanaz a bankszámla, a dokumentum típus és fizetési hivatkozás, és ha ellentétes összegeket tartalmaznak. Egyeztethet egyszer visszavont csekket is, hogy megelőzze ezeknek a tranzakcióknak a megjelenését az egyeztetési munkalapon. 

Ha vannak új bank által kezdeményezett tranzakciók, mint például kamatok, díjak és költségek, amelyek még nem szerepelnek a Finance rendszerben, hozzáadhatja őket egy naplóhoz, ami kijelölt banki kivonat egyeztetéséhez van társítva. Jelölje be a bankszámlakivonat tranzakciót a **Bank kivonat tranzakciók** nem kiegyenlített tranzakciók rácsában, és kattintson a **Megjelölés újként** lehetőségre. A tranzakció állapotának értéke **Új**-ra változik, és a tranzakció áthelyeződik a **Banki kivonat tranzakciók** rács egyeztetett tranzakciói közé. Az **Új** értékkel jelölt tranzakciókat a későbbi **Banki kivonat** oldalon fogja könyvelni. 

Helytelenül egyeztetett tranzakciókat szét választhat. Válassza ki az egyeztetett banki kivonat tranzakciót, és kattintson a **Szétválasztás** lehetőségre. Minden kapcsolódó tranzakció visszakerül a felső rácsokra a nem kiegyenlített tranzakciókhoz, és az egyeztetett és a nem egyeztetett összegek frissülnek. 

Az egyeztetési folyamat befejezését követően be kell jelölnie a Banki egyeztetési munkalapot egyeztetettre.  Ez a folyamat automatikusan feladja a javítási összegeket a **Banki tranzakciótípus** oldalon beállított számlák használatával.  A banki egyeztetési kivonat bármikor megjelölhető egyeztetettnek, akkor is, ha vannak még nem egyeztetett banki kivonatsorok.  A nem egyeztetett tranzakciók automatikusan átkerülnek a következő egyeztetési munkalapra mint nem egyeztetett, egyeztetendő banki kivonati tranzakciók.  Ügyeljen, hogy miután egy banki tranzakciós egyeztetést egyeztetettnek jelölt, ezt többé nem lehet visszavonni.  Az egyeztetés többé nem szerkeszthető, és akkor többé nem lehet módosításokat végezni az egyeztetésen.

## <a name="post-new-transactions-that-are-associated-with-the-reconciliation"></a>Új, már egyeztetéssel egyeztetett tranzakciók könyvelése
Az egyeztetés munkalapon **Új** értékkel jelölt Banki kivonat tranzakciók a **Banki kivonat** oldalon könyvelődnek. A **Banki kivonat** oldalon válassza a kivonat azonosítóját, a kivont adatainak megtekintéséhez. A **Könyvelés** menüben, használhatja a **Felosztások megtekintése** és a **Könyvelés megtekintése** lehetőségeket, az új tranzakciók és a hozzájuk tartozó tételek részletes adatainak megtekintéséhez. Válassza ki a **Könyvelés** lehetőséget az **Új** értékkel jelölt banki kivonat sorok főkönyvbe könyveléséhez. Fontos megjegyezni, hogy könyvelés csak egyszer hajtható végre banki kivonatonként.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]