---
title: Szállítói kifizetések készítése fizetési javaslat segítségével
description: Ez a témakör tájékoztatást nyújt a fizetési javaslat beállításairól, és néhány olyan példát is tartalmaz, amely bemutatja a kifizetési javaslatok működésének módját.
author: abruer
manager: AnnBe
ms.date: 04/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57e8ce38241933b16252f1c918b0f763a8f1be08
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178172"
---
# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Szállítói kifizetések készítése fizetési javaslat segítségével

[!include [banner](../includes/banner.md)]

Ez a témakör tájékoztatást nyújt a fizetési javaslat beállításairól, és néhány olyan példát is tartalmaz, amely bemutatja a kifizetési javaslatok működésének módját. A kifizetési javaslatok segítségével gyakran szállítói számlát is létrehozhat, mert a lekérdezést a kifizetés szállítói számláinak gyors kiválasztására lehet használni, amely olyan feltételeken alapul, mint a határidő vagy a készpénzfizetési engedmény. 

A szervezetek gyakran alkalmaznak fizetési javaslatokat a szállítói kifizetések lebonyolítására. A fizetési javaslatos lekérdezés segít a kifizetendő szállítói számlák gyors kiválasztásában a határidő, készpénzfizetési engedmény és egyéb kritériumok alapján. 

A fizetési javaslat lekérdezés különféle lapokat tartalmaz, melyek mindegyike különböző lehetőségeket kínál a befizetendő számlákra. A **Paraméter** lap a szervezet által legsűrűbben használt lehetőségeket tartalmazza. A **Belefoglalandó rekordok** gyorslapon tisztázhatja különböző szűrők segítségével, hogy melyik számlákat vagy szállítókat kívánja kifizetni. Például ha csak bizonyos szállítókat kíván kifizetni, alkalmazhat szűrőt a szállítói tartományra. Ezt a funkció általában a bizonyos befizetésmódú számlák kiválasztásakor használjuk. Például, ha meghatározott szűrő a **Fizetés módja** = **Csekk**, akkor (amennyiben a lekérdezés egyéb kritériumainak is megfelelnek) csak a csekkes befizetésű számlák jelennek meg kifizetésre. A **Speciális paraméterek** lap további beállításokat tartalmaz, melyek egy része nem feltétlenül szükséges az ön szervezete számára. Ezen a lapon például a központosított kifizetésű számlákra vonatkozó lehetőségek szerepelnek.

## <a name="parameters"></a>Paraméterek
-   **Számlák kiválasztása a következők alapján** – A dátumok alapján beállított számlák a **Dátumtól** és a **Dátumig** mezők segítségével szűrhetőek határidő, készpénzfizetési engedmény dátuma vagy épp mindkettő szerint. Amennyiben a készpénzfizetési engedmény dátuma opciót alkalmazza, a rendszer először azokra a számlákra keres rá, amelyeknél a megadott időintervallumba esik a készpénzfizetési engedmény időpontja. A rendszer ezután meghatározza, hogy a számla megfelel-e készpénzfizetési engedménynek a lejárati idő alapján, így biztosítva, hogy az engedmény még nem-e járt le.
-   **Dátumtól** és **Dátumig** – Az olyan számlák, melyeknek van lejárati határideje vagy készpénzfizetési engedmény határideje a megadott időintervallumban lesznek fizetésre kiválasztva.
-   **Minimális kifizetési dátum** – adja meg a minimális kifizetési dátumot. Tegyük fel, hogy a **Dátumtól** és a **Dátumig** mezőben a szeptember elsejétől szeptember tizedikéig tartó időszakot adja meg, és a minimális kifizetési dátum szeptember ötödike lesz. Ebben az esetben az összes szeptember 1. és 5. között kifizetendő számla kifizetési dátuma szeptember 5. lesz. Azonban minden olyan számlánál, melynek a kifizetési határideje szeptember 5. és 10. közé esik, a számla saját határideje lesz az érvényes kifizetési határidő.
-   **Összeghatár** – Adja meg az összes kifizetés maximális összegét.
-   **Kifizetés számla-előnézet nélkül** – Amennyiben az **Igen** opciót választja ki, a kifizetések helyből a **Szállítói kifizetések** oldalon jönnek létre. A **Fizetési javaslat** oldal így kimarad. Így a kifizetések gyorsabban jönnek létre. A kifizetések továbbra is megváltoztathatóak a **Szállítói kifizetések** oldalon. Másik lehetőségként visszatérhet a **Fizetési javaslat** lapra a **Fizetésre kiválasztott számlák szerkesztése** gombbal.

## <a name="advanced-options"></a>Speciális beállítások
- **Szállítói egyenleg ellenőrzése** – Amennyiben a beállított opció **Igen**, a rendszer ellenőrzi, hogy a szállító rendelkezik-e tartozással, még mielőtt a számla kifizetésre kerülne. Amennyiben egy szállítónak tartozik egyenlege van, a kifizetés nem valósul meg. A szállítónak lehetnek például jóváírásai vagy már feladott, de még nem jóváírt kifizetései. Ilyen esetekben a szállítót nem kell kifizetni. Először rendezni kell a jóváírást vagy az elmaradt befizetést.
- **Negatív kifizetések törlése** – Ez a beállítás attól függően változik, hogy egy vagy több a kritériumoknak megfelelő számlát kívánunk kifizetni. Ezt a működést a kifizetés módja határozza meg.
- **Számlák egyenkénti kifizetése** – Amennyiben a **Negatív kifizetések törlése** beállítás **Igen** opciója van bejelölve, és van nem kiegyenlített számla és fizetés egy szállító számára, csak a számla kerül kifizetésre. A kifizetés nem rendezhető a számlával szemben. Ha a **Negatív kifizetések törlése** beállítás **Nem** opcióra van állítva, valamint a számla és a kifizetés nincsenek rendezve, mind a számla és mind a fizetés kifizetése megtörténik. Létrejön egy kifizetés a fizetés részére és egy a visszatérítés (negatív kifizetés) részére.
- **Több összegű számlák kifizetése** – Ha a **Negatív kifizetések törlése** beállítás **Igen** opcióra van állítva, és létezik rendezetlen számla, illetve kifizetés, mind a rendezetlen számla és a kifizetés is kiválasztásra kerül, az összegük pedig összeadódik, így megadva az összesen kifizetendő összeget. Kivétel akkor fordulhat csak elő amennyiben a kifizetés, visszatérítéssel végződik. Ebben az esetben sem a számla, sem pedig a fizetés nincsenek kiválasztva. Amennyiben a **Negatív kifizetések törlése** beállítás a **Nem** opcióra van állítva, és a számla, valamint a fizetés nincsenek rendezve, mindkettő ki van választva kifizetésre és az összegük összeadódik, így megadva az összesen fizetendő összeget.
- **Csak a jelentés nyomtatása** – Állítsa ezt a beállítást **Igen** opcióra, hogy megtekinthesse a fizetési javaslat eredményeit a kifizetések végrehajtása nélkül.
- **Más jogi személyektől származó szállítói számlák tartalmazása** – Amennyiben az ön szervezete központosított kifizetési rendszert alkalmaz és a kifizetési javaslatnak tartalmaznia kell más jogi személyektől származó, valamint a kritériumoknak megfelelő számlákat is, állítsa be az **Igen** opciót.
- **Javasoljon jogi személyenként eltérő szállítói kifizetést** – Ha ezt a beállítást **Igen** opcióra állítja, szállítónként minden jogi személyhez külön kifizetés jön létre. A kifizetésen szereplő szállító megegyezik az egyes jogi személyek számláin szereplő szállítóval. Amennyiben ez a beállítás a **Nem** opcióra van állítva és ugyanaz a szállító tartozik több jogi személyhez, egy kifizetés készül a kiválasztott számlák teljes összegével. A kifizetésen szereplő szállító megegyezik a jelenlegi jogi személy szállítójával. Amennyiben a szállító számla nem létezik jogi személyként, abban az esetben az első számlán szereplő szállító számlát kell alkalmazni.
- **Kifizetés pénzneme** – Ez a mező határozza meg az összes fizetés pénznemét. Amennyiben a pénznem nincs meghatározva, minden számla kifizetése a számláén megadott pénznemben történik.
- **Fizetésnap** – Adja meg a hét azon napján, amelyen a kifizetésre sor kerül. Ez a mező csak akkor kitöltendő ha a kifizetés módja az összes számla kifizetését a hét egy adott napjára adja meg.
- **Ellenszámla típusa** és **Ellenszámla** – Használja ezeket a mezőket konkrét számlatípus (például **Főkönyv** vagy **Bank**), illetve ellenszámla (specifikus bankszámla) beállítására. A számla kifizetési módja határozza meg az alapértelmezett ellenszámla-, illetve számlatípust, de ezeket a mezőket használhatja a alapértelmezett értékek átírására.
- **Összesített kifizetés dátuma** – Ez csak akkor használatos, amikor az **Időszak** mező értéke a fizetési mód mezőjében **Teljes**. Amennyiben konkrét dátumot ad meg, minden kifizetés az adott napra lesz kiírva. A **Minimális kifizetési dátum** mezőt a program figyelmen kívül hagyja.
- **További szűrők** – a **Belefoglalandó rekordok** gyorslapon, plusz kritériumokat adhat meg. Például ha csak szállítók egy részét szeretné kifizetni, szűrővel megadhatja a kifizetendő szállítókat. Ezt a funkció általában a bizonyos befizetésmódú számlák kiválasztásakor használjuk. Például, ha meghatározott szűrő a **Fizetés módja** = **Csekk**, akkor (amennyiben a lekérdezés egyéb kritériumainak is megfelelnek) csak a csekkes befizetésű számlák jelennek meg kifizetésre.

## <a name="scenarios"></a>Esetek

| Szállító | Számla | Számla dátuma | Számla összege | Fiz. határidő | Készpénzfizetési engedmény dátuma | Készpénzfizetési engedmény összege |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | Június 15.      | 500,00         | Július 15.  | június 29.            | 10,00                |
| 3050   | 1002    | Június 20.      | 600,00         | Július 20.  | Július 4.             | 12,00                |
| 3075   | 1003    | Június 15.      | 250,00         | Június 29.  |                    | 0,00                 |
| 3100   | 1004    | Június 17.      | 100,00         | Július 17.  | Július 1.             | 1,00                 |

Július 1-jén April fizeti ki a szállítókat. April fizetési javaslatot alkalmaz munkája megkönnyítése érdekében.

### <a name="option-1-by-cash-discount"></a>Első opció: Készpénzfizetési engedmény

April a **készpénzfizetési engedmény** opciót választja ki, mint a javaslat típusát. Június 26-tól július 10-ig terjedő időintervallumot ad meg. A következő számlák szerepelnek a javaslatban:

-   1002, mivel az engedmény dátuma (július 4.) szerepel a fizetési dátumok között.
-   1004, mivel az engedmény dátuma (július 1.) szerepel a fizetési dátumok között.

A következő számlák nem szerepelnek a javaslatban:

-   1001, az engedmény dátuma (június 29) már nem érvényes, így a számla már nem jogosult készpénzfizetési engedményre.
-   1003, mert ez a számla nem rendelkezik engedménydátummal.

### <a name="option-2-by-due-date"></a>Második opció: Határidő alapján

April a **Határidő alapján** opciót választja ki, mint a javaslat típusát. Június 26-tól július 10-ig terjedő időintervallumot ad meg. A következő számlák szerepelnek a javaslatban:

-   1003, mivel az engedmény dátuma (június 29.) szerepel a fizetési dátumok között.

A következő számlák nem szerepelnek a javaslatban:

-   1001, mivel az engedmény dátuma (július 15.) nem szerepel a fizetési dátumok között.
-   1002, mivel az engedmény dátuma (július 20.) nem szerepel a fizetési dátumok között.
-   1004, mivel az engedmény dátuma (július 17.) nem szerepel a fizetési dátumok között.

### <a name="option-3-by-due-date-and-cash-discount"></a>Harmadik opció: Határidő és készpénzfizetési engedmény alapján

April a **Határidő és készpénzfizetési engedmény** opciót választja ki, mint a javaslat típusát. Június 26-tól július 10-ig terjedő időintervallumot ad meg. A következő számlák szerepelnek a javaslatban:

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
-   A **Dimenzió vezérlőelem** mező aktiválva van, és a további dimenziók engedélyezve vannak. Most definiálhatja, hogy másolja át a dimenziókat a program a naplóba. Például • Ha az üzleti egység szerinti fizetési javaslatot szeretne létrehozni a fizetési módra vonatkozóan, jelölje be **BusinessUnit** jelölőnégyzetet, • Ha költséghely szerinti fizetési javaslatot szeretne létrehozni a fizetési módra vonatkozóan, jelölje be a **CostCenter** jelölőnégyzetet

> [[!NOTE]
> Ha a harmadik lehetőségnél több dimenziót jelöl ki, a dimenziók kombinációjára vonatkozó fizetési javaslat jön létre.

#### <a name="bank-account-selection"></a>Bankszámla kiválasztása

Beállíthat egy szabványos terhelési fizetési számlát az országfüggő fizetési módtól függetlenül. Ezt a javaslat által létrehozott kifizetési sorokban állíthatja be. A bankszámla funkcióval több, a dimenzió és a pénznem által kezelt terhelési bankszámlát határozhat meg, vagy ezek kombinációját a különböző terhelési bankszámlák használata tekintetében az egyes kombinációktól függően. Ezeket a kombinációkat a **Fizetési módok** lapon a  **Bankszámlák** gomb használatával állíthatja be, amely minden egyes **Feladási számla típusa** = **Bank** fizetési módhoz elérhető.



