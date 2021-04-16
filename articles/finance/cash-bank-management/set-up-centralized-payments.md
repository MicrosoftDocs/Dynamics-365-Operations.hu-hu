---
title: Központosított kifizetések beállítása
description: A lépések követésével felkészülhet a kifizetéseknek más jogi személyek nevében egy jogi személyben történő feldolgozására a szervezetben.
author: kweekley
ms.date: 05/09/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: roschlom
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0ff7051611c1253ce8f431e24274fab53cf79b6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834917"
---
# <a name="set-up-centralized-payments"></a>Központosított kifizetések beállítása

[!include [banner](../includes/banner.md)]

A lépések követésével felkészülhet a kifizetéseknek más jogi személyek nevében egy jogi személyben történő feldolgozására a szervezetben. Mielőtt hozzálátna, a következő beállításoknak készen kell lenniük:

-   Jogi személyek létrehozása.
-   Főkönyvi paraméterek és a számlatükrök beállítása.
-   Kötelezettség paraméterek és Kinnlévőségek paraméterek beállítása (a központosított kifizetéseket használó moduloktól függően).
-   Vállalatközi könyvelés beállítása.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Szervezeti hierarchia felállítása központosított kifizetésekhez
A központosított kifizetésekhez szervezeti hierarchiát kell felállítani. Ugyanaz a szervezeti hierarchia használatos a központosított szállítói kifizetések és a központosított vevői kifizetések feldolgozására. **Megjegyzés:** A központosított kifizetéseknél nincs jelentősége a hierarchia felépítésének. Bármelyik jogi személy a hierarchiában képes lesz kifizetéseket feldolgozni a hierarchiában lévő bármely másik jogi személy nevében. A **Szervezeti hierarchiák** oldalon hozhat létre új szervezeti hierarchiát. A **Cél** mezőben a **Központosított kifizetések** lehetőséget kell választania. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>A vállalatközi számla beállítása a központosított kifizetések kezelésére
Amikor az aktuális jogi személy kifizetési tranzakcióit más jogi személyekben lévő számlákkal szemben egyenlítik ki, mindegyik jogi személy esetében létrejönnek a megfelelő, a jogi személytől és a jogi személy részére esedékes tranzakciók. Meg kell adnia azt a jogi személyt, ahová bármely alkalmazandó készpénzfizetési engedmény összeg és bármely realizált nyereség vagy veszteség összeg feladása történik. Mielőtt elkezdené, döntse el, melyik jogi személyt fogja használni a szállítói és vásárlói kifizetések feldolgozásához. Ha egy jogi személy a szállítói kifizetéseket dolgozza fel, de egy másik jogi személy a vevői kifizetéseket dolgozza fel, akkor mindegyik jogi személyhez váltani kell. A **Vállalatközi könyvelés** oldalon kiválaszthatja egy jogi személy vállalatközi kapcsolatának bejegyzését, amely nevében fel fogja dolgozni a kifizetéseket. 

A **Központosított kifizetések** lapon kiválaszthatja, hogy a készpénzfizetési engedményeket a kifizetés (vagy más, a szállítói számla egyenlegét csökkentő tranzakció) szerinti jogi személyhez, vagy a számla (vagy más, a szállítói számla egyenlegét növelő tranzakció) szerinti jogi személyhez szeretné-e feladni. Ez a választás együtt működik a **Készpénzfizetési engedmény adminisztrációja** mezővel a **Kötelezettségek paraméterei** és **Kinnlevőségek paramétereinek** lapokkal. A túlfizetésekhez és a fillérkülönbözetek tűréséhez a kifizetés szerinti jogi személyben található beállítás kerül felhasználásra. Az alulfizetésekhez és a fillérkülönbözetek tűréséhez a számla szerinti jogi személyben található beállítás kerül felhasználásra.

## <a name="map-vendor-accounts-across-legal-entities"></a>Szállítói számlák leképezése jogi személyek között
Ha az egyik jogi személyből egy szállítónak kifizetéseket teljesít, és az adott szállítóra vonatkozóan szeretne számlákat kiválasztani más jogi személyekben, biztosítania kell, hogy az összes megfelelő szállítói számlák mindegyik jogi személyben ugyanazt a címjegyzék-azonosítót használják. Ha az egy vásárlótól kifizetést fogad, amely több jogi személyben is számlát fizet, biztosítania kell, hogy az összes megfelelő vásárlói számla mindegyik jogi személynél ugyanazt az azonosítót használja a címjegyzékben.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Feladási profilok beállítása a központosított kifizetések kezeléséhez
Amikor olyan kifizetést hoz létre egy jogi személyben, amely más jogi személyekben rögzített számlákat egyenlít ki, a feladási profil azonosítóknak mindkét jogi személyben azonosnak kell lenniük. A kifizetések helyes létrehozásának biztosítása érdekében állítson be minden számla szerinti jogi személyben egy olyan feladási profilt, amely megfelel a kifizetés szerinti jogi személyben használt feladási profiloknak. Váltson a számla első jogi személyéhez, majd a **Szállítói feladási profilok** lapon lehet létrehozni új feladási profilt és szerkesztheti a már létező feladási profilt. A számla jogi személyében a feladási profil kiválasztásainak nem kell megfelelniük a fizetés jogi személyének feladási profiljának kiválasztásaihoz.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Fizetési módok beállítása a központosított kifizetések kezeléséhez
Amikor olyan kifizetést hoz létre egy jogi személyben, amely más jogi személyekben rögzített számlákat egyenlít ki, a fizetési mód azonosítóknak mindkét jogi személyben azonosnak kell lenniük. A kifizetések helyes létrehozásának garantálása érdekében állítson be minden számla szerinti jogi személyben egy olyan fizetési módot, amely megfelel a kifizetés szerinti jogi személyben használt fizetési módoknak. Váltson a számla első jogi személyére, majd a **Fizetési módok** lapon létrehozhat új fizetési módot, vagy szerkeszthet egy meglévő fizetési módot. A számla szerinti jogi személyben lévő fizetési mód esetében kiválasztott beállításoknak nem kell megegyezniük a kifizetés szerinti jogi személyben lévő fizetési mód beállításának módjával.

## <a name="set-up-default-descriptions"></a>Alapértelmezett leírások beállítása
A vállalatközi kiegyenlítési bizonylatokhoz alapértelmezett leírásokat határozhat meg. Az alapértelmezett leírás a vállalattól és a vállalat részére esedékes tranzakcióknál jelenik meg a vállalatközi kiegyenlítési folyamat során. Az **Alapértelmezett leírások** lapon létrehozhat új leírásokat a **Vállalatközi vevői kiegyenlítés** és a **Vállalatközi szállítói kiegyenlítés** számára, a nyelv kiválasztásával, majd szöveg megadásával.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]