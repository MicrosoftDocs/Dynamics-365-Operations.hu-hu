---
title: Általános napló feldolgozása
description: Ez a témakör a Microsoft Dynamics 365 Finance alkalmazásban szereplő funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve biztosítják a megfelelő adatok tárolását, illetve a belső ellenőrzés megfelelő működését.
author: ShylaThompson
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dbf5f8f2fc3b33077d559ffcef580a5295adb2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815572"
---
# <a name="general-journal-processing"></a>Általános napló feldolgozása

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve biztosítják a megfelelő adatok tárolását, illetve a belső ellenőrzés megfelelő működését.  

## <a name="journal-names"></a>Naplónevek

Az egyik legfontosabb beállítandó terület a naplónév. Érdemes minden célhoz külön naplónevet megadni (pl.: vállalatközi, elhatároláskiigazítás és hibajavítás). A naplónevek személyre szabásával az egyes célokhoz való adatbevitelt egyszerűbbé és biztonságosabbá teheti. 

A **Naplónevek** lapon az alábbi elemeket állíthatja be:

-   **Munkafolyamat-jóváhagyás** – A belső ellenőrzés javítása érdekében olyan napló-munkafolyamatokat határozzon meg, amelyek fontossági határokat szabnak az ellenőrzési és jóváhagyási lépésekhez például a tartozás teljes összege alapján. Az általános naplókhoz a **Főkönyvi munkafolyamatok lapon** állíthat be munkafolyamatokat.
-   **Alapértelmezett értékek** – Válassza ki az alapértelmezett értékeket az ellenszámlákhoz, pénznemhez és pénzügyi dimenziókhoz.
-   **Napló ellenőrzése** – Beállíthat korlátozásokat a vállalatra és a számlatípusra, de akár a szegmensértékekre is. 

**Példák**

A naplónév csak módosításokra használható. Ebben az esetben megadhatja, hogy csak a **Főkönyv** számlatípus legyen érvényes minden vállalat esetében. 

[![Napló-ellenőrzési számlatípusok](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

A naplónév csak egy adott szegmens vagy egy tartomány esetében használható fő számlákhoz. 

[![Naplóellenőrzési szegmens](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

Az **Automatikus sztornírozás** lehetőség elérhető az általános naplók esetében. Tegyük fel például, hogy van egy elhatároláskiigazítása, ahol a tényleges dokumentum feldolgozása még nem történt meg (lásd az alábbi ábrán).
[![Általános napló sztornírozása](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

A Microsoft Excel-bővítmény naplóbejegyzésekhez még nagyobb automatizálást és egyszerűbb adatbevitelt tesz lehetővé. A **Sorok megnyitása az Excelben** művelet elérhető az **Általános napló** és **Naplóbizonylat** oldalakon. 

Az **Időszakos naplók** oldalon beállíthatja az ismétlődő naplókra a naplófeldolgozás automatizálását. 

Bizonylatsorokat bármikor használhat. Az **Általános naplók** oldalon a **Mentés** és **Bizonylatsablon kiválasztása** műveleteket a **Bizonylatsablon** oldalon találja, a bizonylatsorok **Funkciók** lehetősége alatt.

## <a name="related-setup"></a>Kapcsolódó beállítások
A következő beállítások nem csak az általános naplókra vonatkoznak, de biztosítják a helyes és egyszerű adatbevitelt.

### <a name="main-account"></a>Fő számla

A fő számla beállítás számos lehetőséget nyújt az általános napló feldolgozására:

-   **DC/CR követelmény** – Ezt a beállítást akkor használja, ha a fő számla terhelési vagy jóváírási tranzakciókra van korlátozva. A beállítás jóváhagyása a napló ellenőrzése vagy feladása alkalmával történik.

-   **Alapértelmezett ellenszámla**
-   **Felfüggesztett** – Felfüggeszti egy fő számla adatbevitelét minden vállalatnál vagy egy adott vállalatnál/jogi személynél.
-   **Manuális bevitel tiltása** – Megakadályozza, hogy a felhasználók maguk adjanak meg értékeket a számlához a naplókban.
-   **Pénznem alapértelmezése/érvényesítése**
-   **Jogi személy felülbírálása** – Ez a beállítás csak a meghatározott vállalatra vagy jogi személyre vonatkozik:
    -   **Áfa alapértelmezése/érvényesítése**
    -   **Alapértelmezett dimenzió** – **Nem rögzített** vagy **Rögzített érték**. **Rögzített érték** segítségével biztosítható, hogy a feladások mind a fő számlához mindig olyan dimenzióértéket használjanak, amely **Rögzített** beállítású.
-   **Feladás ellenőrzése**
    -   **Felhasználó érvényesítése** – Ez a beállítás szabályozza, hogy mely felhasználók jogosultak olyan a fő számlára való feladásra.
    -   **Feladási típus érvényesítése** – Ez a beállítás szabályozza, hogy mely feladási típusok megengedettek a fő számlához.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Könyvelési szerkezetek és a speciális szabályok szerkezetei

A könyvelési szerkezetek és a speciális szabályok szerkezetei rendkívül fontosak, mert ezekkel biztosítható, hogy a pénzügyi jelentés készítéséhez és teljesítéskövetéséhez szükséges adatok rögzítése megtörténik az általános napló vagy bármilyen dokumentum feldolgozása során. A könyvelési szerkezetek és a speciális szabályok szerkezetei segítségével személyre szabhatja az adatbeviteli élményt. Megszabhatja, hogy csak a helyzethez kapcsolódó pénzügyi dimenziók adatbevitele legyen lehetséges, és kötelezővé teheti azt a feltételt, mely alapján a pontos adat mindig rögzítésre kerül.

További információért tekintse át az alábbi témaköröket:
- [Számlatükör tervezése](plan-chart-of-accounts.md) 
- [Speciális szabályok létrehozása naplók részére](tasks/create-advanced-rules-journals.md)
- [Naplóbejegyzés létrehozása sablon alapján](tasks/create-journal-entry-template.md)
- [Naplók létrehozása és érvényesítése](tasks/create-validate-journals.md)
- [Időszaki naplók feladása](tasks/post-periodic-journals.md)
- [Főkönyvi felosztási napló feldolgozása](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Feladás szimulálása
A **Feladás szimulálása** lehetőséget a legtöbb napló esetében az **Ellenőrzés** menüben találhatja. Amikor érvényesít egy naplót az **Ellenőrzés** funkcióval, a rendszer teszteli a naplót bizonyos hibákat keresve. Ha a **Feladás szimulálása** funkciót használja, akkor a rendszer lefuttatja mindazokat a folyamatokat, amelyek a feladás során végbemennek, anélkül, hogy ténylegesen feladná a naplót. Ezt követően ellenőrizheti a feladással kapcsolatban megjelenő üzeneteket, kijavíthatja az észlelt hibákat, majd megnyithatja a **Feladás** menüt a napló feladásához. 

A **Feladás szimulálása** lehetőség nem áll rendelkezésre a kötegelt feldolgozásnál. Van azonban elérhető kód, amellyel végrehajtható a kötegelt feladás szimulálása, és a fejlesztők kibővíthetik a kódot a funkció hozzáadása érdekében.  

## <a name="journal-unlock"></a>Napló zárolásának feloldása
Egy gomb érhető el a naplóoldal alján az olyan napló zárolásának feloldásához, amelynek a „rendszer által zárolt” állapota Igen. Ezt a feloldást a rendszer egy olyan rendszergazdája hajthatja végre, aki elemezte a végrehajtási kötegelt feladatokat, és megerősítette, hogy ezt a naplót már nem dolgozza fel aktívan a kötegelt feladat. Ezt a gombot a **Szolgáltatások kezelése** lap **Napló feloldása gomb** funkciója engedélyezi. 

## <a name="workflow-recall"></a>Munkafolyamat visszahívása 
A „javíthatatlan” állapotú munkafolyamatok naplójának visszahívása a napló **Munkafolyamat** gombján és a **Munkafolyamat-előzmények** lapon érhető el. Ezt a funkciót a **Funkciókezelés** lapon a **Naplók munkafolyamat-állapotának alaphelyzetbe állítása** funkció engedélyezi.

## <a name="delete-journal-lines"></a>Naplósorok törlése
Az összes naplósor gyors törlésének lehetőség engedélyezve van egy naplóban a **Funkciók** > **Naplósorok törlése**. A funkció engedélyezéséhez kattintson a **Szolgáltatások kezelése** modul **Napló teljesítményoptimalizálásainak törlése** parancsára.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]