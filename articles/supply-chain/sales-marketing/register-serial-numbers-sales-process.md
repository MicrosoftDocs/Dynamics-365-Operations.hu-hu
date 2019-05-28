---
title: Sorozatszámok bejegyzése az értékesítési folyamat során
description: Ez a témakör bemutatja, hogy hogyan regisztrálhatja a sorozatszámokat a szállítólevélen vagy a számlákon az értékesítési folyamat során. Ez a funkció akkor hasznos, ha a vállalat szolgáltatási és garanciális célokra akar sorozatszámokat rögzíteni, de nem kell a sorozatszámokat fenntartaniuk a készletben a bevételezéstől a kiadásig.
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e86c2f8d1d5920198db74dc3b64f2393c5e13ff7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555038"
---
# <a name="register-serial-numbers-in-the-sales-process"></a>Sorozatszámok bejegyzése az értékesítési folyamat során

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Ez a témakör bemutatja, hogy hogyan regisztrálhatja a sorozatszámokat a szállítólevélen vagy a számlákon az értékesítési folyamat során. Ez a funkció akkor hasznos, ha a vállalat szolgáltatási és garanciális célokra akar sorozatszámokat rögzíteni, de nem kell a sorozatszámokat fenntartaniuk a készletben a bevételezéstől a kiadásig.

Sok vállalat csak szolgáltatási és garanciális célokra akar sorozatszámot rögzíteni, és nem kell sorozatszámokat fenntartaniuk a készletben a bevételezéstől a kiadásig. Az ilyen esetekben a Microsoft Dynamics 365 for Finance and Operations lehetővé teszi hogy bejegyezze a sorozatszámokat a szállítóleveleken vagy számlákon, amikor a termékek eladásra kerülnek. Ha a termékek később visszatérnek Önhöz, akkor minden termék nyomon követhető egy számlához, hogy meghatározza, hogy Ön adta-e el a terméket és hogy a szerviz és garancia kötelezettségek érvényesek-e.

Engedélyeznie kell a sorozatszámokat az értékesítési folyamathoz az **Értékesítési folyamatban aktív** opció kijelölésével a **Nyomon követési dimenzió csoportok** oldalon. A következő események zajlanak le a Microsoft Dynamics 365 for Finance and Operations rendszerben:
-   A **Sorozatszámok** gyorslapon a **Sorozatszám-ellenőrzés** beállítás be van jelölve. Ha ez a jelölőnégyzet be van jelölve, regisztrálnia kell a csomagjegyzéken vagy a számlán található mindegyik elemhez egy sorozatszámát.
-   A nyomon követési dimenzió csoport összes sorozatszám kijelölése törlődik, kivéve az **Üres kiadás megengedett** opciót. Kiválaszthatja az **Üres kiadás megengedett** opciót hogy felülírja a sorozatszám-ellenőrzést és engedélyezze, hogy a termékeket sorozatszámok nélkül legyenek csomagolva és számlázva.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>Mikor regisztrálom a sorozatszámokat az értékesítési folyamat során?
Egy értékesítési rendeléshez a sorozatszámokat regisztrálhatja a szállítólevélen vagy a számlán. Amikor egy számlát készít elő egy sorozatszámmal ellátott cikkhez, amit egy szállítólevéllel szállítottak le választhat a szállítólevélen és a számlán szereplő sorozatszámok közül. A regisztrált sorozatszámok száma nem haladhatja meg a leszállított cikkek mennyiségét. Részleges számla létrehozásakor, kiválaszthat kevesebb sorozatszámmal ellátott cikket mint amennyi a szállítólevélen regisztrálva lett. Ha a csomagjegyzék vagy számla nyomtatásához a sorozatszámok regisztrált jelennek meg.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>Beírhatom a sorozatszámokat beolvasással, vagy gépelnem kell őket?
Beolvashatja vagy gépelheti is a sorozatszámokat. Beolvasó használata esetén a beolvasási mód határozza meg, hogy a sorozatszámok hozzáadódnak vagy eltávolítódnak a sorozatszámok listájához/listájából a számlán vagy szállítólevélen. Ha szeretne sorozatszámokat beolvasni például egy kézi vonalkód olvasó használatával konfigurálja az olvasót, hogy küldjön egy Enter vagy TAB parancsot a sorozatszám után. Ez a parancs jelzi az adatfolyam végét. Ellenkező esetben meg kell nyomnia az Enter vagy TAB gombot a billentyűzeten minden egyes sorozatszám beolvasása után.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Ha engedélyezem a sorozatszámokat az értékesítési folyamathoz, akkor minden cikkemhez kell sorozatszámot regisztrálnom?
A termékhez rendelt nyomon követési dimenziócsoport beállítása meghatározza, hogy kötelező-e sorozatszámokat regisztrálni minden cikkhez a szállítólevélen vagy számlán. Amikor engedélyezi a sorozatszámokat az értékesítési folyamathoz a **Sorozatszám ellenőrzés** opció automatikusan kiválasztásra kerül. Ezután regisztrálnia kell egy sorozatszámot, vagy regisztrálhat üres regisztrációt egy olvashatatlan számhoz, minden cikkhez a szállítólevélen vagy számlán. Ha nem kíván sorozatszámot igényelni minden termékhez akkor jelölje ki az **Üres kiadás megengedett** opciót abban a nyomon követési dimenziócsoportban, ami a cikkhez van rendelve. Ezután regisztrálhat kevesebb sorozatszámot, mint a leszállított cikkek mennyisége. Ha több sorozatszámot regisztrál, mint a leszállítandó cikkek mennyisége, akkor képtelen lesz feladni a szállítólevelet vagy számlát.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>Regisztrálhatja a sorozatszámok részleges számlák és a részleges szállítmányokat?
Lehetősége van részleges számlák és szállítólevek készítésére az értékesítési megrendelésekhez és csak azokhoz a cikkekhez sorozatszámot regisztrálni, amelyeket ezek a számlák és szállítólevelek tartalmaznak. Ha részleges számlát szeretne készíteni és több mint egy szállítólevele van az értékesítési megrendeléshez akkor lehetősége van hogy több mint egy szállítólevélből belevegyen sorozatszámokat. Azonban csak egy szállítólevél lehet, amely nem tartalmazza az összes sorozatszámot. Például ha három szállítólevele van és mindegyik szállítólevél két sorozatszámmal ellátott cikket tartalmaz, akkor nem tud részleges számlát készíteni egy cikkhez minden szállítólevélből.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>Mi a teendő, amikor egy sorozatszám nem olvasható?
Ha sorozatszámot nem lehet olvasni vagy beolvasni, akkor lehetősége van, hogy üres sort készítsen a cikkhez a **Nem olvasható** a gombra kattintással a **Sorozatszámok** oldalon. Ha a sorozatszám később elérhetővé válik frissítheti a számlát vagy szállítólevelet. További információhoz lásd a következő szakaszban, "Ki tudom javítani vagy meg tudom változtatni a sorozatszámokat, amiket egy értékesítési megrendeléshez regisztráltam?"

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>Ki tudom javítani vagy meg tudom változtatni a sorozatszámokat, amiket egy értékesítési megrendeléshez regisztráltam?
Igen, sorozatszámok helyesbíthetők, ha a következő feltételek teljesülnek:
-   **Számlák** – Módosíthatja a még nem számlázott cikkek sorozatszámát. Ezután a szállítólevél szintén frissítésre kerül. Azonban, ha egy értékesítési rendelés sor helyesbítésre került negatív mennyiség regisztrálásával nem tudja megváltoztatni a sorozatszámokat az értékesítési rendelés sorhoz.
-   **Szállítólevelek** –Nem lehetséges olyan szállítólevél-sor részleges javítása, amely sorozatszámmal ellátott cikkeket tartalmat. A teljes mennyiség, a sor sztornírozni kell. Ha egy szállítólevél érvénytelenítve vagy javítva lett nem kell újra regisztrálnia a megváltozott sorozatszámot amikor új szállítólevelet készít ugyanazokhoz a sorozatszámmal ellátott cikkekhez. A regisztrált fogja használni.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>Megtekinthetem a sorozatszámokat, amelyek közösen lettek leszállítva egy konkrét szállítólevéllel, vagy egy számla tartalmazta őket?
Igen, futtassa a lekérdezést a csomagjegyzék jegy naplósor vagy a számlát tartalmazó naplósor sorszámának a dokumentumban szereplő listáját tekintheti meg.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>Megtekintheti a szerializált cikkekről van készleten?
Nem, nem tekintheti meg a készleten lévő sorozatszámmal ellátott cikkeket, mert a sorozatszámok nincsenek regisztrálva, amíg a cikkek eladásra nem kerülnek.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>Regisztrálhatja a tényleges súllyal rendelkező cikkek sorozatszámait?
Nem, az értékesítési folyamat során nincs lehetősége sorozatszám regisztrálására a tényleges súllyal rendelkező cikkekhez. Továbbá, ha egy termék tényleges súllyal rendelkező cikként van beállítva, akkor nem rendelhető hozzá egy nyomon követő dimenziócsoporthoz, amely úgy van beállítva, hogy csak az értékesítési folyamat során használjon sorozatszámokat.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>Van lehetőségem a kiskereskedelmi POS-nál regisztrálni a sorozatszámokat?

Igen, a kiskereskedelmi pénztár (POS) arra utasítja a felhasználót, hogy adjon meg egy sorozatszámot, amikor a felhasználó elad egy cikket ami egy nyomon követési dimenziócsoporthoz van rendelve, ami úgy van beállítva, hogy használjon sorozatszámokat az értékesítési folyamatban.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Milyen biztonsági szerepkörökre van szükség, hogy sorozatszámokat regisztráljunk az értékesítési folyamat során?
Ez a funkció minden olyan szerep számára elérhető, amely jogosult a szállítólevelek és számlák kezelésére. Az alábbi feladatok engedélyezik a dolgozók számára a sorozatszámok korrekcióját és üres bejegyzések létrehozását az olvashatatlan vagy beolvashatatlan sorozatszámok esetén:
-   Sorozatszámkorrekciók karbantartása
-   Olvashatatlan sorozatszámok regisztrációjának karbantartása





