---
title: Váltók beállítása
description: Ez a témakör azt ismerteti, hogy miként lehet beállítani a váltókat.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustBillOfExchangeJour
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cda597b1d99e99ac5c5c396bcfcec9c0712f0eb1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "344708"
---
# <a name="set-up-bills-of-exchange"></a>Váltók beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogy miként lehet beállítani a váltókat.

A váltó olyan írott vagy elektronikus dokumentum, melyet a vevő állít ki arról, hogy egy másik fél – általában egy bank – meghatározott összeget ki fog fizetni a vállalatnak. Ha a szabad szöveges számla vagy értékesítési rendelési számla kiegyenlítésére váltót használnak, akkor a vevő számláján egy követel tétel jelenik meg. A váltó mindaddig biztosítja ezt a követel tételt, amíg a vevő ki nem fizeti a váltót a banknak. A felhasználó (a vállalat) általában a határidő napján egyenlíti ki a számlát a váltóval. Amint a vállalat megkapja a banktól az értesítés, hogy a váltón megadott összeget kifizették, le lehet zárni a váltót. A váltókat a következő időpontokban hívhatja le a bankon keresztül:

-   Az esedékesség napján. Ennek a megközelítésnek a neve beszedés (inkasszó).
-   Az esedékesség ideje előtt, általában a vevőre vonatkozó fizetési feltételekben meghatározott engedmény dátumakor. A tranzakció feladásakor az engedmény összege egy költségszámlára küldhető el. A fennmaradó összeg az Ön kötelezettsége, amíg a bank meg nem kapja a fizetést a vevőtől. Ennek a megközelítésnek a neve engedményes beszedés.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Feladási profilok beállítása váltókhoz

A **Vevő feladási profiljai** oldalon beállíthatja a váltókkal, az óvatolt váltókkal, a beszedésekkel és az engedményes beszedésekkel használandó feladási profilokat. Az **Összegzett számla** mezőben válassza ki azt az összegző számlát, amelyre a váltókat fel kell adni. A számla terhelése vagy jóváírása a váltótranzakció típusától függően történik:
-   Váltók esetén ezen a számlán a váltó feladásakor egy tartozik tétel, a beszedés vagy az engedményes beszedés feladásakor pedig egy követel tétel jelenik meg.
-   Az óvatolt váltók esetén az óvatolt váltó feladásakor ezen a számlán egy tartozik tétel jelenik meg.
-   A beszedések esetén a beszedés feladásakor ezen a számlán egy tartozik tétel jelenik meg.
-   Az engedményes beszedések esetén az engedményes beszedés feladásakor ezen a számlán egy tartozik tétel jelenik meg.

A **Számla kiegyenlítése** mezőben válassza ki azt a készpénzes számlát, amelyre a váltók összegét feladja. A váltók kiegyenlítésekor ezen a számlán egy tartozik tétel jelenik meg. Az **Áfaelőlegek** mezőben válassza ki azt az összegző számlát, amelyre az áfaösszegeket fel kell adni, ha az előlegek kifizetéséhez váltókat használnak. Az engedményes beszedések esetén a **Kötelezettségek az engedményszámlához** mezőben válassza ki azt a számlát, amelyre az engedmény összegét fel szeretné adni. Ezen a számlán az engedményes beszedés feladásakor egy követel tétel jelenik meg.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>A váltók kinnlevőség-paraméterek beállítása

A **Kinnlevőségek paraméterei** oldalon a váltók alapértelmezett feladási profiljait a **Főkönyv és áfa** lapon adhatja meg. A számsorozatok a **Számsorozatok** lapon vannak megadva.

## <a name="set-up-journal-names-for-bills-of-exchange"></a>Váltónaplók neveinek beállítása


A **Naplónevek** lapon a váltókhoz legalább öt naplónevet létre kell hoznia. A naplók típusai a következők:
-   **Vevői váltókiállítás** – Hozzon létre egy nevet a vevői váltókiállítás naplója számára.
-   **Vevői váltóóvatolás** – Hozzon létre egy nevet a vevői váltóóvatolás naplója számára.
-   **Vevői újbóli váltókiállítás** – Hozzon létre egy nevet a vevői újbóli váltókiállítás naplója számára.
-   **Vevői banki átutalás** – Hozzon létre egy naplónevet az átutalási napló számára.
-   **Vevői váltókiegyenlítés** – Hozzon létre egy nevet a vevői váltókiegyenlítés naplója számára.

A váltónaplók megfelelő naplóbizonylati oldalán adja meg a váltóval kapcsolatos adatokat a **Váltó** lapon. Miután feladta a váltó naplósorait, megtekintheti őket a **Váltónapló lekérdezése** oldalon és a **Váltóstatisztika** oldalon.

## <a name="set-up-methods-of-payment-for-bills-of-exchange"></a>Váltók kifizetési módjainak beállítása

A **Fizetési módok** oldalon állítson be legalább egy fizetési módot a váltókhoz. Ha több bankkal is kapcsolatban áll, akkor minden egyes bankhoz állítson be egy olyan kifizetési módot, amely megfelel a bank által megkövetelt váltófizetési formátumnak.

## <a name="set-up-payment-fees-for-bills-of-exchange"></a>Váltók kifizetési díjainak beállítása

A kifizetési díj a kifizetések vevőktől való beszedéséért fizetendő díj. Minden kifizetési díjhoz több kifizetési díjbeállítási sor tartozhat. A beállítási sorokkal határozhatja meg a kifizetési díjak alapértelmezett összegének kiszámítását. Például létrehozhat beállítási sorokat fizetési módokhoz, kifizetési előírásokhoz, pénznemekhez és időszakokhoz. Emellett létrehozhat beállítási sorokat napi intervallumokon alapuló százalékhoz vagy összeghez. Például létrehozhat beállítási sorokat a fizetési módokhoz, fizetési szabályokhoz, pénznemekhez, időszakokhoz és napintervallumokon alapuló százalékhoz vagy összeghez, mint például kamatszázalék a késedelmes fizetési időszak hossza alapján. Ha a bank más-más díjat számít fel a különböző átutalási típusokért, például a **Beszedés** vagy az **Engedmény** típusért, akkor külön kifizetésidíj-sorokat állíthat be mindegyik átutalási típushoz.

## <a name="set-up-remittance-fees-for-bank-remittance-files"></a>Átutalási díjak beállítása banki átutalási fájlokhoz

A **Bankszámlák** oldalon minden generált átutalási fájlhoz külön beállíthatja azokat az átutalási díjakat, amelyeket a banknak kell fizetni az átutalásért. Az átutalási díjak feladása akkor történik meg, amikor a bank visszaigazolta az átutalást, és a díj realizált összege ismertté válik. Az átutalási díjak különböznek a kifizetési díjaktól, amelyek a vevőket terhelik, és a naplósorokhoz kapcsolódnak.

## <a name="set-up-document-layouts-for-bills-of-exchange"></a>Váltódokumentumok elrendezésének beállítása

A **Bankszámlák** oldalon kattintson a **Beállítás** lehetőségre, és adjon meg egy dokumentum-elrendezést minden olyan bankszámlához, amelyekhez nyomtatható váltódokumentumokat fog előállítani.

## <a name="set-up-customers-for-bills-of-exchange"></a>A váltók beállítása a vevőknél

A **Vevők** lapon minden vevőnél, amely megállapodás alapján váltóval fizethet, beállíthat egy váltókhoz tartozó alapértelmezett kifizetési módot a **Fizetési alapértelmezések** lapon.





