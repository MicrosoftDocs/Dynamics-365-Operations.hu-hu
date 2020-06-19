---
title: Szabadság- és távolléti terv létrehozása
description: A Dynamics 365 Human Resources szolgáltatásban szabadságterveket hozhat létre a különböző típusú szabadságokhoz.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 75a70c5784e7032cfebbe58c1d173923a3023507
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428709"
---
# <a name="create-a-leave-and-absence-plan"></a>Szabadság- és távolléti terv létrehozása

A Dynamics 365 Human Resources szolgáltatásban szabadság- és távolléti terveket definiálhat minden kínált szabadságtípushoz. A szabadság- és távolléti tervek különböző gyakorisággal könyvelhetők, például évente, havonta vagy félhavonta. A tervek meghatározhatók támogatásként is, ahol egyetlen könyvelés történik egy meghatározott dátumon. Létrehozhat például olyan tervet, amely évente mozgatható szabadságolást ad.

A többszintű szabadságtervek lehetővé teszik, hogy az alkalmazottak a szervezetnél eltöltött idő alapján kapjanak juttatásokat. A többszintű tervek lehetővé teszik a további juttatási órák automatikus bejegyzését.

Megadhat maximális átviteli összeget vagy minimális egyenleget annak biztosításához, hogy az alkalmazottak csak a számukra elhatárolt juttatási órákat használják.

Többszintű terv esetében például 80 óra fizetett időt (PTO) adhat meg juttatásként az új alkalmazottak számára. Ezután 120 órát adhat meg 60 havi szolgálathoz.

Beosztás alapú juttatásokat is létrehozhat, például csak vezetőknek járó juttatási órákat.

## <a name="create-a-leave-plan"></a>Szabadságterv létrehozása

1. A **Szabadság- és távolléti tervek** oldalon válassza az **Új terv létrehozása** elemet.

2. A **Részletek**mezőbe írja be a tervre vonatkozó **Név**, **Kezdő dátum**, **Leírás** és **Szabadságtípus** értéket.

Ha a **Több szabadságtípus konfigurálása egyetlen szabadság- és távolléti tervhez** funkció engedélyezve van a szabadságtervek az **Elhatárolási ütemezés** helyen vannak konfigurálva a **Részletek** alatt. A könyvelés ütemezési táblázatában szereplő mindegyik rekordnál megadhatja a szabadság típusát.

 > [!IMPORTANT]
   > Miután engedélyezte, ez a funkció nem kapcsolható ki.

3. Definiálja a könyveléseket a **Könyvelések** lapon. A könyvelés határozza meg, hogy az alkalmazott mikor és milyen gyakran kap szabadságot. Ebben a lépésben definiálhatja azokat az irányelveket, amelyek meghatározzák a könyvelés elvégzését, valamint a juttatások arányosítását.

   1. Válasszon egy értéket a **Könyvelés gyakorisága** legördülő listából:

      - Naponta
      - Heti
      - Kéthetente
      - Félhavonta
      - Havi
      - Negyedéves
      - Félévente
      - Évente
      - Egyik sem

   2. Válasszon egy beállítást a **Könyvelési időszak alapja** legördülő listáról a könyvelési időszakok számításához használandó kezdő dátum meghatározásához:

      | Könyvelési időszak alapja | Leírás |
      | --- | --- |
      | **Terv kezdő dátuma** | A könyvelési időszak kezdő dátuma az a dátum, amikor a terv elérhető. |
      | **Alkalmazotthoz kapcsolódó dátum** | A könyvelési időszak kezdő dátuma az alkalmazott eseményétől függ:</br><ul><li>Egyéni (mindegyik beléptetéshez meg kell adnia a könyvelési dátum alapját)</li><li>Évforduló dátuma</li><li>Eredeti felvételi dátum</li><li>Szolgálati idő dátuma</li><li>A dolgozó módosított kezdési dátuma</li><li>A dolgozó kezdési dátuma</li></ul> |

   3. Válasszon egy beállítást a **Könyvelés megadott dátuma** legördülő listából:

      - **Könyvelési időszak záró dátuma** – Az alkalmazott a megadott időszak utolsó napján kap szabadságot. A helyes összeg könyveléséhez a könyvelési folyamatnak az egész időszakot magában kell foglalnia. Ha például a könyvelési időszak 2020. január 1. és 2020. január 31. között van, akkor a január felvételéhez 2020. február 1-jén kell futtatnia.

      - **Könyvelési időszak záró dátuma** – Az alkalmazott a megadott időszak első napján kap szabadságot.

   4. Válasszon egy beállítást a **Könyvelési irányelv beléptetésnél** legördülő listából. Ez az érték azt határozza meg, hogyan történik a könyvelés kiszámítása, amikor egy alkalmazott egy könyvelési időszak közepén kapja a szabadságot.

      - **Arányosított** – A felvétel dátuma és a kezdő dátum közötti dátumtartomány szolgál a különbség meghatározására napokban. Ez a különbség lesz alkalmazva a könyvelések feldolgozása során.

      - **Teljes könyvelés** – A szinten alapuló teljes könyvelési összeg számít az első könyvelési feldolgozás során.

      - **Nincs könyvelés** – Nincs könyvelés a következő könyvelési időszakig.

   5. Válasszon egy beállítást a **Könyvelési irányelv kiléptetésnél** legördülő listából. Ez az érték azt határozza meg, hogyan történik a könyvelés kiszámítása, amikor egy alkalmazott egy könyvelési időszak közepén mond le a szabadságról.

      - **Arányosított** – A felvétel dátuma és a kezdő dátum közötti dátumtartomány szolgála a különbség meghatározására napokban. Ez a különbség lesz alkalmazva a könyvelések feldolgozása során.

      - **Teljes könyvelés** – A teljes könyvelési összeg, a szint alapján oda lesz ítélve az első könyvelési feldolgozás során.

      - **Nincs elhatárolási** – Nincs növekvény alkalmazva a következő könyvelési időszakig.

4. Adja meg a könyvelés ütemezését a **Könyvelés ütemezése** lapon. A könyvelés ütemezése határozza meg a következőket:

   - Az alkalmazott szabadságának könyvelése
   - Az alkalmazott könyvelt összegei
   - Az átvitt összegek

   Létrehozhat szinteket a szabadság különböző szintek alapján történő megadásához.

   Az órabéres alkalmazottak esetében a ledolgozott órák alapján adhat szabadságot a szervezetnél ledolgozott idő helyett. A ledolgozott munkaórák jellemzően a munkaidő-nyilvántartási rendszerben tárolódnak. A munkaidő-nyilvántartási rendszerből importálhatja a ledolgozott normál órákat és túlórákat, és ezek alapján határozhatja meg az alkalmazottak jutalmát.
   
    1. Válasszon egy beállítást a **Könyvelés típusa** legördülő listából:

      - **Munkaviszony hossza hónapokban** – A könyvelés ütemezésének alapja a munkaviszony hónapban mért ideje.

      - **Ledolgozott órák** – A könyvelés ütemezésének alapja a ledolgozott órák száma. A ledolgozott munkaórák könyvelésével kapcsolatos további tudnivalókat lásd: [Szabadság elhatárolása a ledolgozott órák alapján](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Az elhatárolási egyenlegekkel kapcsolatos további tudnivalókat lásd: [Szabadság elhatárolása a ledolgozott órák alapján](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Írja be az értékeket a könyvelési ütemezés táblázatába:

      - **Munkaviszony hossza hónapokban** – Meghatározza a hónapok minimális számát, amióta az alkalmazottak dolgozniuk kell, hogy elhatárolásra legyenek jogosultak. Ha nem igényel minimumot, állítsa 0-ra az értéket.

      - **Ledolgozott órák** – Meghatározza meg az órák minimális számát, amelyet az alkalmazottak le kell dolgozniuk egy könyvelési időszakban, hogy elhatárolásra legyenek jogosultak. Ha nem igényel minimumot, állítsa 0-ra az értéket.

      - **Könyvelési összeg** – Az órák vagy napok száma, amelyet az alkalmazottak összegyűjtenek időszakonként. Az időszak a könyvelés gyakoriságán alapul.

      - **Minimális egyenleg** – Negatív érték használható a minimális egyenleghez, ha az alkalmazottak több szabadságot kérhetnek, mint amennyivel rendelkeznek.

      - **Maximális áthozat** – A könyvelési folyamat kiigazítja azokat az egyenlegeket, amelyek meghaladják a maximális átviteli egyenleget a kezdő dátum évfordulóján.

      - **Megítélés mennyisége** – A kezdeti órák vagy napok száma, amelyet az alkalmazottaknak megítélnek, amikor először belépnek a szabadságtervbe. Összeg a könyvelésinem lesz elhatárolva minden könyvelési időszakhoz.
      
Ha a **Több szabadságtípus konfigurálása egyetlen szabadság- és távolléti tervhez** engedélyezve van, válasszon egy lehetőséget a **Szabadság típusa** alatt. 

   > [!IMPORTANT]
   > Miután engedélyezte, ez a funkció nem kapcsolható ki.

Ha **Teljes munkaidő egyenérték használata** funkció engedélyezve van, akkor a Human Resources szolgáltatás a beosztáshoz meghatározott teljes munkaidő egyenértéket (FTE) használja az alkalmazottak könyvelésének arányosítására. Ha például az FTE 0,5, és a könyvelési összeg 10, akkor az alkalmazottnak 5 könyvelhető. Ez a funkció csak akkor használható, ha engedélyezi a több szabadságtípust.  

5. Válassza a **Mentés** lehetőséget.

## <a name="accrue-time-off-based-on-hours-worked"></a>Elhatárolt szabadság a ledolgozott órák alapján

Az órabéres alkalmazottak esetében a ledolgozott órák alapján adhat szabadságot a szervezetnél ledolgozott idő helyett. A ledolgozott munkaórák adatai jellemzően a munkaidő-nyilvántartási rendszerben tárolódnak. A munkaidő-nyilvántartási rendszerből importálhatja a ledolgozott normál órákat és túlórákat, és ezek alapján határozhatja meg az alkalmazottak jutalmát.

A ledolgozott munkaórák könyvelési típusának kiválasztása esetén kétféle órát számolhat el: normál órát és túlórát. Az óránkénti munkavégzéssel kapcsolatos eredményszemléletű elszámolás az eredményszemlélet gyakoriságát és az elhatárolás időszakát használja az elhatárolható órák meghatározásához.

### <a name="annual-accrual-frequency"></a>Az elhatárolás éves gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/12            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2085                | 144                 |        
| 2018/31/12            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Havi elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 160                  | 12                    | 8/1/2018-8/31/2018   | 184                 | 12                  |        
| 2018/31/8             | 160                  | 3                     | 8/1/2018-8/31/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Félhavi elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 80                   | 6                     | 8/16/2018-8/31/2018  | 81                  | 6                  |        
| 2018/31/8             | 80                   | 6                     | 8/16/2018-8/31/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Heti elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 40                   | 3                     | 8/27/2018-8/31/2018  | 42                  | 3                  |        
| 2018/31/8             | 40                   | 3                     | 8/27/2018-8/31/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Alkalmazotthoz rendelt szabadságtervek

Az alkalmazott hozzárendelt szabadságterveiben a munkaórák számának szintje és típusa látható ledolgozott órás terveknél. Aktív tervek esetén a ténylegesen ledolgozott órák a könyvelési időszakok szerint is megjelennek.

### <a name="loading-data"></a>Adatok betöltése

A tényleges órákat importálhatja a **Ledolgozott szabadság- és távolléti órák** entitással az adatok kezelésénél. A munkaidőnaptárak használata esetén az importálás ellenőrzi, hogy a normál ledolgozott órák száma nem haladja-e meg a naptárban meghatározott ütemezett órák számát. Az importálás azt is ellenőrzi, hogy egy adott napon ledolgozott órák száma nem haladja-e meg a 24 órát. 

A következő adatok szükségesek a ténylegesen ledolgozott munkaórák importálásához, amelyek felhasználhatók a szabadságelhatárolási folyamat során:

- Személyzeti szám 
- Munkában töltött nap
- Típus
- óra

Egy adott dátum csak egy típushoz társítható.

| Személyzeti szám       | Munkában töltött nap           | Típus                  | óra                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 2018/6/8             | Szabályos               | 8                    |       
| 000337                | 2018/7/8             | Szabályos               | 8                    |
| 000337                | 2018/7/8             | Túlóra              | 3                    |
| 000337                | 2018/8/8             | Szabályos               | 8                    |
| 000337                | 2018/7/8             | Szabályos               | 8                    |
| 000337                | 2018/9/8             | Szabályos               | 8                    |

## <a name="enrollments-and-balances"></a>Beléptetések és egyenlegek

### <a name="enrollment-date"></a>Regisztráció dátuma

A beléptetés dátuma határozza meg, hogy egy alkalmazott mikor kezdheti meg az eltávozás elhatárolását. Ha például ha az alkalmazott 2018. június 15-én van felvéve egy szabadságtervbe, nem határolhat el eltávozást 2018. június 15. előtt.

### <a name="current-balance"></a>Aktuális egyenleg

Az aktuális egyenleg a szabadságkérelmekhez rendelkezésre álló szabadságmennyiség. Ez az összeg tartalmazza az elhatárolásokat, jóváhagyott kérelmek és korrekciókat az aktuális dátumig.

### <a name="current-balance-examples"></a>Példa az aktuális egyenlegre

#### <a name="annual-plan"></a>Éves terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/1        | Éves            | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2019. január 1-jén (1/1/2019) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Aktuális egyenleg (160) = Könyvelési összeg (200) – Kérelem összege (40)

#### <a name="semimonthly-plan"></a>Félhavi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2018. május 1-jén (5/1/2018) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Aktuális egyenleg (22) = Könyvelési összeg (5 × 6) – Kérelem összege (8)

#### <a name="monthly-plan"></a>Havi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2018. május 1-jén (5/1/2018) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Igénylés összege | Aktuális egyenleg (1/1/2019 időpontban) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Aktuális egyenleg (7) = Könyvelési összeg (5 × 3) – Kérelem összege (8)

### <a name="forecasted-balance"></a>Előrejelzett egyenleg

Az *Előrejelzett egyenleg* a szabadság mennyisége, amely egy jövőbeni dátumon érhető el. Könyvelések és áthozott helyesbítések addig az időpontig vannak előrejelezve.

A Human Resources szolgáltatás a következő képletet használja:

Hétfő előre jelzett egyenlege = Aktuális egyenleg – Kérelmek + könyvelések – áthozott kiigazítások

### <a name="forecasted-balance-examples"></a>Előre jelzett egyenleg – példák

#### <a name="annual-plan"></a>Éves terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/1        | Éves            | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2019. február 15-én (2/15/2019) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Előrejelzett egyenleg (40) = Könyvelési érték (20) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

#### <a name="semimonthly-plan"></a>Félhavi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2019. február 15-én (2/15/2019) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Előrejelzett egyenleg (35) = Könyvelési érték (5 × 3) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

#### <a name="monthly-plan"></a>Havi terv

**Terv beállítása**

| Terv kezdő dátuma | Regisztráció dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja | Elhatárolás jutalmazásának dátuma    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 2018/1/1        | 2018/1/2        | Félhavonta       | Terv kezdő dátuma      | Könyvelési időszak záró dátuma |

A könyvelések feldolgozása 2019. február 15-én (2/15/2019) történik a teljes időszak beszámításával.

**Eredmények**

| Halmozódás összege | Minimális egyenleg | Maximális áthozat | Aktuális egyenleg | Előrejelzett egyenleg (2/15/2019 időpontban) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Előrejelzett egyenleg (30) = Könyvelési érték (10 × 1) + Aktuális egyenleg (40)– Áthozott kiigazítások (20)

### <a name="proration-balance-examples"></a>Arányosított egyenlegek – példák

#### <a name="prorated-monthly-plan"></a>Arányosított havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3,00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 2,53    |

#### <a name="full-accrual-monthly-plan"></a>Teljes könyvelési havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3,00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Nincs könyvelési havi terv

**Terv beállítása**

| Terv kezdő dátuma | Könyvelés gyakorisága | Könyvelési időszak alapja |
|-----------------|-------------------|----------------------|
| 2018/1/1        | Havi           | Terv kezdő dátuma      |

**Eredmények**

| Alkalmazott            | Munkaviszony hossza hónapokban | Regisztráció dátuma | Kezdés dátuma | Halmozódás összege | Könyvelés feldolgozása | Egyenleg |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 2018/1/6        | 2018/1/6   | 1.00           | 2018/1/9        | 3.00    |
| Jay Norman          | 0,00              | 2018/15/6       | 2018/15/6  | 1.00           | 2018/1/9        | 2.00    |

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)
- [Szabadság- és távolléti tervek elhatárolása](hr-leave-and-absence-accrue.md)
