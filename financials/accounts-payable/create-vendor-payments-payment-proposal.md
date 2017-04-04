---
title: "Szállítói kifizetések készítése fizetési javaslat segítségével"
description: "Ez a témakör tájékoztatást nyújt a fizetési javaslat beállításairól, és néhány olyan példát is tartalmaz, amely bemutatja a kifizetési javaslatok működésének módját. A kifizetési javaslatok segítségével gyakran szállítói számlát is létrehozhat, mert a lekérdezést a kifizetés szállítói számláinak gyors kiválasztására lehet használni, amely olyan feltételeken alapul, mint a határidő vagy a készpénzfizetési engedmény."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: b46037b9509f329e18f0da69d530f6b1f88c8888
ms.lasthandoff: 03/31/2017


---

# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Szállítói kifizetések készítése fizetési javaslat segítségével

Ez a témakör tájékoztatást nyújt a fizetési javaslat beállításairól, és néhány olyan példát is tartalmaz, amely bemutatja a kifizetési javaslatok működésének módját. A kifizetési javaslatok segítségével gyakran szállítói számlát is létrehozhat, mert a lekérdezést a kifizetés szállítói számláinak gyors kiválasztására lehet használni, amely olyan feltételeken alapul, mint a határidő vagy a készpénzfizetési engedmény. 

A szervezetek gyakran alkalmaznak fizetési javaslatokat a szállítói kifizetések lebonyolítására. A fizetési javaslatos lekérdezés segít a kifizetendő szállítói számlák gyors kiválasztásában a határidő, készpénzfizetési engedmény és egyéb kritériumok alapján. 

A fizetési javaslat lekérdezés különféle lapokat tartalmaz, melyek mindegyike különböző lehetőségeket kínál a befizetendő számlákra. A **paraméter** lap tartalmazza a szervezet többsége leggyakrabban használt beállítások. A a **bejegyzéseket** gyorslapon megadhatja, mely számlákat vagy szállítók fizetési tartományok különböző jellemzők megadásával is. Például ha csak egy bizonyos tartomány szállítók fizetni kíván, meghatározhatja a szállító-tartomány szűrő. Ezt a funkciót gyakran használják a számlák egy adott fizetési mód kiválasztásához. Például, ha a szűrő definiálása adott **fizetési mód** = **ellenőrizze a**, csak azokat a számlákat, amelyek a fizetési mód kiválasztott fizetési, feltéve, hogy azok megfelelnek a lekérdezésben meghatározott egyéb feltételek. A **Speciális paraméterek** lap további beállításokat tartalmaz, melyek egy része nem feltétlenül szükséges az ön szervezete számára. Ezen a lapon például a központosított kifizetésű számlákra vonatkozó lehetőségek szerepelnek.

## <a name="parameters"></a>Paraméterek
-   **Kattintson a számlák által** – számlák által megadott dátumtartományba a **dátumtól** és **dátum** mezők esedékesség, készpénzfizetési engedmény dátuma, vagy mindkettő kattintva választhatja ki. Ha a készpénzfizetési engedmény dátumát, a rendszer először megkeresi, amelyeknél a készpénzfizetési engedmény dátuma közötti számlák a kezdő dátum és a záró dátumot. A rendszer ezután meghatározza, hogy a számla megfelel-e készpénzfizetési engedménynek a lejárati idő alapján, így biztosítva, hogy az engedmény még nem-e járt le.
-   **Dátumtól** és** Dátumig** – Az olyan számlák, melyeknek van lejárati határideje vagy készpénzfizetési engedmény határideje a megadott időintervallumban lesznek fizetésre kiválasztva.
-   **Fizetés dátuma** – Amennyiben konkrét dátumot ad meg, minden kifizetés az adott napra lesz kiírva. A **Minimális kifizetési dátum** mezőt a program figyelmen kívül hagyja.
-   **Minimális kifizetési dátum** – adja meg a minimális kifizetési dátumot. Például a **dátumtól** és **dátum** szeptember 10-én és szeptember 1 közötti tartományban határoznak meg, és ha a minimális kifizetési dátum szeptember 5. Ebben az esetben szeptember 5. szeptember 1-én esedékes összes számlájának van egy kifizetési dátuma szeptember 5. Azonban szeptember 10 a szeptember 5-én esedékes összes számlájának rendelkezik, amely egyenlő a minden egyes számla esedékességi dátuma kifizetési dátum.
-   **Összeghatár** – Adja meg az összes kifizetés maximális összegét.
-   **Minta számla nélküli kifizetések létrehozása** – Ha ez a beállítás értéke **Igen**, fizetések azonnal fog létrejönni a a **fizetési** lap. A **fizetési javaslat** ki lesznek hagyva. Így a kifizetések gyorsabban jönnek létre. A kifizetések továbbra is megváltoztathatóak a **Szállítói kifizetések** oldalon. Másik lehetőségként visszatérhet a **Fizetési javaslat** lapra a **Fizetésre kiválasztott számlák szerkesztése** gombbal.

## <a name="advanced-options"></a>Speciális beállítások
-   **Szállítói egyenleg ellenőrzése** – Amennyiben a beállított opció **Igen**, a rendszer ellenőrzi, hogy a szállító rendelkezik-e tartozással, még mielőtt a számla kifizetésre kerülne. Ha a szállító tartozik egyenleg, nincs kifizetés jön létre. Például a szállító lehet jóváírások vagy kifizetések könyvelése, de még nem rendezték. Ilyen esetekben a szállítót nem kell kifizetni. Először rendezni kell a jóváírást vagy az elmaradt befizetést.
-   **Negatív kifizetések törlése** – Ez a beállítás attól függően változik, hogy egy vagy több a kritériumoknak megfelelő számlát kívánunk kifizetni. Ezt a működést a kifizetés módja határozza meg.
-   **Számlák egyenkénti kifizetése** – Amennyiben a **Negatív kifizetések törlése** beállítás **Igen** opciója van bejelölve, és van nem kiegyenlített számla és fizetés egy szállító számára, csak a számla kerül kifizetésre. A kifizetés nem rendezhető a számlával szemben. Ha a **Negatív kifizetések törlése** beállítás **Nem** opcióra van állítva, valamint a számla és a kifizetés nincsenek rendezve, mind a számla és mind a fizetés kifizetése megtörténik. Létrejön egy kifizetés a fizetés részére és egy a visszatérítés (negatív kifizetés) részére.
-   **Több összegű számlák kifizetése** – Ha a **Negatív kifizetések törlése** beállítás **Igen** opcióra van állítva, és létezik rendezetlen számla, illetve kifizetés, mind a rendezetlen számla és a kifizetés is kiválasztásra kerül, az összegük pedig összeadódik, így megadva az összesen kifizetendő összeget. Kivétel akkor fordulhat csak elő amennyiben a kifizetés, visszatérítéssel végződik. Ebben az esetben sem a számla, sem pedig a fizetés nincsenek kiválasztva. Ha a ** negatív kifizetések törlése ** beállítás **nem**, és nem kiegyenlített számla és kifizetés, a számla és a kifizetés fizetéshez kijelölt és összegek kerülnek a kifizetés teljes összege együttesen létrehozásához.
-   **Csak a jelentés nyomtatása** – Állítsa ezt a beállítást **Igen** opcióra, hogy megtekinthesse a fizetési javaslat eredményeit a kifizetések végrehajtása nélkül.
-   **Más jogi személyektől származó szállítói számlák tartalmazása** – Amennyiben az ön szervezete központosított kifizetési rendszert alkalmaz és a kifizetési javaslatnak tartalmaznia kell más jogi személyektől származó, valamint a kritériumoknak megfelelő számlákat is, állítsa be az **Igen** opciót.
-   **Javasoljon jogi személyenként eltérő szállítói kifizetést** – Ha ezt a beállítást **Igen** opcióra állítja, szállítónként minden jogi személyhez külön kifizetés jön létre. A kifizetésen szereplő szállító megegyezik az egyes jogi személyek számláin szereplő szállítóval. Amennyiben ez a beállítás a **Nem** opcióra van állítva és ugyanaz a szállító tartozik több jogi személyhez, egy kifizetés készül a kiválasztott számlák teljes összegével. A kifizetésen szereplő szállító megegyezik a jelenlegi jogi személy szállítójával. Amennyiben a szállító számla nem létezik jogi személyként, abban az esetben az első számlán szereplő szállító számlát kell alkalmazni.
-   **Kifizetés pénznem** – a mező határozza meg a pénznem kifizetésekről készült. Ha a pénznem nincs definiálva, minden számlát a számla pénznemében fizetik ki.
-   **Fizetésnap** – Adja meg a hét azon napján, amelyen a kifizetésre sor kerül. Ez a mező csak akkor kitöltendő ha a kifizetés módja az összes számla kifizetését a hét egy adott napjára adja meg.
-   **Ellenszámla típusa** és **ellenszámla** – állítsa be ezeket a mezőket egy adott számla típusának megadása (például a **főkönyvi** vagy **Bank**) és az Ellenszámla (például egy adott bankszámlát). A számlához tartozó fizetési mód határozza meg az alapértelmezett ellenszámlatípus és az ellenszámla, de ezek a mezők segítségével felülírják az alapértelmezett értékeket.
-   **További szűrők** – a a **bejegyzéseket** gyorslapon meghatározhatja kritériumok további tartományokat. Például ha ki szeretne egyenlíteni a szállítók széles körét, meghatározhatja a szállító-tartomány szűrő. Ezt a funkciót gyakran használják a számlák egy adott fizetési mód kiválasztásához. Például, ha a szűrő definiálása adott **fizetési mód** = **ellenőrizze a**, csak azokat a számlákat, amelyek a fizetési mód kiválasztott fizetési, feltéve, hogy azok megfelelnek a lekérdezésben meghatározott egyéb feltételek.

## <a name="scenarios"></a>Esetek
| Szállító | Számla | Számla dátuma | Számla összege | Fiz. határidő | Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | Június 15.      | 500,00         | Július 15.  | június 29.            | 10,00                |
| 3050   | 1002    | Június 20.      | 600,00         | Július 20.  | Július 4.             | 12,00                |
| 3075   | 1003    | Június 15.      | 250,00         | Június 29.  |                    | 0,00                 |
| 3100   | 1004    | Június 17.      | 100,00         | Július 17.  | Július 1.             | 1,00                 |

Július 1-jén April fizeti ki a szállítókat. April fizetési javaslatot alkalmaz munkája megkönnyítése érdekében.

### <a name="option-1-by-cash-discount"></a>Első opció: Készpénzfizetési engedmény

April a **készpénzfizetési engedmény** opciót választja ki, mint a javaslat típusát. Ő lép egy dátum tartomány, június 26. július 10. A javaslat tartalmazza a következő számlákat:

-   1002, mivel az engedmény dátuma (július 4.) szerepel a fizetési dátumok között.
-   1004, mivel az engedmény dátuma (július 1.) szerepel a fizetési dátumok között.

A következő számlák nem szerepelnek a javaslatban:

-   1001, az engedmény dátuma (június 29) már nem érvényes, így a számla már nem jogosult készpénzfizetési engedményre.
-   1003, mert ez a számla nem rendelkezik engedménydátummal.

### <a name="option-2-by-due-date"></a>Második opció: Határidő alapján

April a **Határidő alapján** opciót választja ki, mint a javaslat típusát. Ő lép egy dátum tartomány, június 26. július 10. A javaslat tartalmazza a következő számlákat:

-   1003, mivel az engedmény dátuma (június 29.) szerepel a fizetési dátumok között.

A következő számlák nem szerepelnek a javaslatban:

-   1001, mivel az engedmény dátuma (július 15.) nem szerepel a fizetési dátumok között.
-   1002, mivel az engedmény dátuma (július 20.) nem szerepel a fizetési dátumok között.
-   1004, mivel az engedmény dátuma (július 17.) nem szerepel a fizetési dátumok között.

### <a name="option-3-by-due-date-and-cash-discount"></a>Harmadik opció: Határidő és készpénzfizetési engedmény alapján

April a **Határidő és készpénzfizetési engedmény** opciót választja ki, mint a javaslat típusát. Ő lép egy dátum tartomány, június 26. július 10. A javaslat tartalmazza a következő számlákat:

-   1003, mivel az engedmény dátuma (június 29.) szerepel a fizetési dátumok között.
-   1002, mivel az engedmény dátuma (július 4.) szerepel a fizetési dátumok között.
-   1004, mivel az engedmény dátuma (július 1.) szerepel a fizetési dátumok között.

A következő számlák nem szerepelnek a javaslatban:

-   1001, mivel az engedmény dátuma (június 29) már nem érvényes, Így a számla már nem jogosult a készpénzfizetési engedményre, valamint a lejárati határidő (július 15.) is kívül esik a megadott tartományon.

## <a name="country-specific-considerations"></a>Országspecifikus szempontok
### <a name="norway"></a>Norvégia

#### <a name="dimension-control"></a>Dimenzió vezérlőelem

A Dimenzió vezérlőelem lehetővé teszi a fizetési javaslat alapján létrehozott sorok csoportosításának ellenőrzését, valamint az alapértelmezett dimenziók beállítását a kiegyenlített számlák esetében használt pénzügyi dimenziók alapján. Norvégia országfüggő környezetében minden fizetési módhoz tartozik egy pénzügyi dimenzió lap, ahol aktiválhatja a dimenzió ellenőrzését, valamint engedélyezheti az egyes dimenziók csoportosítását. A lehetséges választások:

-   A **Dimenzió vezérlőelem** mező le van tiltva. A fizetési javaslat úgy viselkedik, mint bármely ország esetében.
-   A **Dimenzió vezérlőelem** mező aktiválva van a dimenziók további meghatározása nélkül. A fizetési javaslatot a rendszer a dimenziók figyelmen kívül hagyásával hozza létre. A létrehozott tranzakció nem örököl dimenziókat a kiegyenlített tételből.
-   A **Dimenzió vezérlőelem** mező aktiválva van, és a további dimenziók engedélyezve vannak. Most definiálhatja, hogy másolja át a dimenziókat a program a naplóba. Például: • válassza ki a **részleget** fizetési javaslat készítése üzleti egység a metódus fizetési • jelölje be a jelölőnégyzetet a **CostCenter** jelölőnégyzet bejelölésével a fizetési javaslat létrehozása egy Költséghely mód fizetési

**Megjegyzés:** Ha a harmadik lehetőségnél több dimenziót jelöl ki, a dimenziók kombinációjára vonatkozó fizetési javaslat jön létre.

#### <a name="bank-account-selection"></a>Bankszámla kiválasztása

Beállíthat egy szabványos terhelési fizetési számlát az országfüggő fizetési módtól függetlenül. Ezt a javaslat által létrehozott kifizetési sorokban állíthatja be. A bankszámla funkcióval több, a dimenzió és a pénznem által kezelt terhelési bankszámlát határozhat meg, vagy ezek kombinációját a különböző terhelési bankszámlák használata tekintetében az egyes kombinációktól függően. Beállíthatja ezeket a kombinációk **módok** lap segítségével a **bankszámlák** gomb áll rendelkezésre minden, a fizetési mód **számla típusa Könyvelés** = **Bank**.


