---
title: "Központosított kifizetések beállítása"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 815282422a6d7b8eef7d0628cf10b715449e1d1d
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-centralized-payments"></a>Központosított kifizetések beállítása



Kövesse az alábbi lépéseket a szervezet más jogi személyek nevében egy jogalany fizetések feldolgozása előkészítésére. Mielőtt elkezdené, a következő beállítást kell elvégezni:

-   Jogi személyek létrehozása.
-   Főkönyvi paraméterek és a számlatükrök beállítása.
-   Kötelezettség paraméterek és Kinnlévőségek paraméterek beállítása (a központosított kifizetéseket használó moduloktól függően).
-   Vállalatközi könyvelés beállítása.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Szervezeti hierarchia felállítása központosított kifizetésekhez
A központosított kifizetésekhez szervezeti hierarchiát kell felállítani. Ugyanaz a szervezeti hierarchia használatos a központosított szállítói kifizetések és a központosított vevői kifizetések feldolgozására. **Megjegyzés:** A központosított kifizetéseknél nincs jelentősége a hierarchia felépítésének. Bármelyik jogi személy a hierarchiában képes lesz kifizetéseket feldolgozni a hierarchiában lévő bármely másik jogi személy nevében. A **Szervezeti hierarchiák** oldalon hozhat létre új szervezeti hierarchiát.

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>A vállalatközi számla beállítása a központosított kifizetések kezelésére
Amikor az aktuális jogi személy kifizetési tranzakcióit más jogi személyekben lévő számlákkal szemben egyenlítik ki, mindegyik jogi személy esetében létrejönnek a megfelelő, a jogi személytől és a jogi személy részére esedékes tranzakciók. Meg kell adnia azt a jogi személyt, ahová bármely alkalmazandó készpénzfizetési engedmény összeg és bármely realizált nyereség vagy veszteség összeg feladása történik. Mielőtt elkezdené, döntse el, melyik jogi személyt fogja használni a szállítói és vásárlói kifizetések feldolgozásához. Ha egy jogi személy a szállítói kifizetéseket dolgozza fel, de egy másik jogi személy a vevői kifizetéseket dolgozza fel, akkor mindegyik jogi személyhez váltani kell. A a **vállalatközi könyvelés** lapon válasszon ki egy vállalatközi kapcsolat bejegyzést egy jogi személy nevében fizetési feldolgozó. A a **kifizetések központi** lapon ki lehet választani e könyvelése készpénzes engedmények, amelyek a kifizetés (vagy egyéb tranzakciót, amely csökkenti a szállítói számla egyenlegének) jogi személy vagy jogi személyt a számla (vagy egyéb tranzakciót, amely növeli a szállítói számla egyenlegének). Ez a választás együtt működik a **Készpénzfizetési engedmény adminisztrációja** mezővel a **Kötelezettségek paraméterei** és **Kinnlevőségek paramétereinek** lapokkal. A túlfizetésekhez és a fillérkülönbözetek tűréséhez a kifizetés szerinti jogi személyben található beállítás kerül felhasználásra. Az alulfizetésekhez és a fillérkülönbözetek tűréséhez a számla szerinti jogi személyben található beállítás kerül felhasználásra.

## <a name="map-vendor-accounts-across-legal-entities"></a>Szállítói számlák leképezése jogi személyek között
Ha az egyik jogi személyből egy szállítónak kifizetéseket teljesít, és az adott szállítóra vonatkozóan szeretne számlákat kiválasztani más jogi személyekben, biztosítania kell, hogy az összes megfelelő szállítói számlák mindegyik jogi személyben ugyanazt a címjegyzék-azonosítót használják. Ha az egy vásárlótól kifizetést fogad, amely több jogi személyben is számlát fizet, biztosítania kell, hogy az összes megfelelő vásárlói számla mindegyik jogi személynél ugyanazt az azonosítót használja a címjegyzékben.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Feladási profilok beállítása a központosított kifizetések kezeléséhez
Amikor olyan kifizetést hoz létre egy jogi személyben, amely más jogi személyekben rögzített számlákat egyenlít ki, a feladási profil azonosítóknak mindkét jogi személyben azonosnak kell lenniük. A kifizetések helyes létrehozásának biztosítása érdekében állítson be minden számla szerinti jogi személyben egy olyan feladási profilt, amely megfelel a kifizetés szerinti jogi személyben használt feladási profiloknak. Váltsunk át az első jogi személy a számla, majd kattintson a **szállítói feladási profilok** lapon létrehozhat új feladási profil, vagy szerkesztheti a már létező feladási profilja. A jogi személynél a számla feladási profil a kiválasztott nem kell megegyeznie a jogi személynél a kifizetés feladási profil beállítása.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Fizetési módok beállítása a központosított kifizetések kezeléséhez
Amikor olyan kifizetést hoz létre egy jogi személyben, amely más jogi személyekben rögzített számlákat egyenlít ki, a fizetési mód azonosítóknak mindkét jogi személyben azonosnak kell lenniük. A kifizetések helyes létrehozásának garantálása érdekében állítson be minden számla szerinti jogi személyben egy olyan fizetési módot, amely megfelel a kifizetés szerinti jogi személyben használt fizetési módoknak. Váltson a számla első jogi személyére, majd a **Fizetési módok **lapon létrehozhat új fizetési módot, vagy szerkeszthet egy meglévő fizetési módot. A számla szerinti jogi személyben lévő fizetési mód esetében kiválasztott beállításoknak nem kell megegyezniük a kifizetés szerinti jogi személyben lévő fizetési mód beállításának módjával.

## <a name="set-up-default-descriptions"></a>Alapértelmezett leírások beállítása
A vállalatközi kiegyenlítési bizonylatokhoz alapértelmezett leírásokat határozhat meg. Az alapértelmezett leírás a vállalattól és a vállalat részére esedékes tranzakcióknál jelenik meg a vállalatközi kiegyenlítési folyamat során. Az **Alapértelmezett leírások** lapon létrehozhat új leírásokat a **Vállalatközi vevői kiegyenlítés **és a **Vállalatközi szállítói kiegyenlítés** számára, a nyelv kiválasztásával, majd szöveg megadásával.


