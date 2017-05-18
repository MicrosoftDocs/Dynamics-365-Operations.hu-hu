---
title: "Általános napló feldolgozása"
description: "Ez a cikk a Microsoft Dynamics 365 for Operationsben szereplő funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve garantálják a megfelelő adatok tárolását, a belső ellenőrzés megfelelő működését."
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c020566928cecc15bd7de504164f5adbf34eda44
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="general-journal-processing"></a>Általános napló feldolgozása

[!include[banner](../includes/banner.md)]


Ez a cikk a Microsoft Dynamics 365 for Operationsben szereplő funkciókat mutatja be, amelyek megkönnyítik az általános napló feldolgozását, illetve garantálják a megfelelő adatok tárolását, a belső ellenőrzés megfelelő működését.  

Naplónevek

Az egyik legfontosabb beállítandó terület a naplónév. Érdemes minden célhoz külön naplónevet megadni (pl.: vállalatközi, elhatároláskiigazítás és hibajavítás). A naplónevek személyre szabásával az egyes célokhoz való adatbevitelt egyszerűbbé és biztonságosabbá teheti. 

A **Naplónevek** lapon az alábbi elemeket állíthatja be:

-   **Munkafolyamat-jóváhagyás** – A belső ellenőrzés javítása érdekében olyan napló-munkafolyamatokat határozzon meg, amelyek fontossági határokat szabnak az ellenőrzési és jóváhagyási lépésekhez például a tartozás teljes összege alapján. Az általános naplókhoz a **Főkönyvi munkafolyamatok** lapon állíthat be munkafolyamatokat.
-   **Alapértelmezett értékek** – Válassza ki az alapértelmezett értékeket az ellenszámlákhoz, pénznemhez és pénzügyi dimenziókhoz.
-   **Napló ellenőrzése** – Beállíthat korlátozásokat a vállalatra és a számlatípusra, de akár a szegmensértékekre is. 

**Példák**

A naplónév csak módosításokra használható. Ebben az esetben megadhatja, hogy csak a **Főkönyv** számlatípus legyen érvényes minden vállalat esetében. [![Napló-ellenőrzési számlatípusok](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

A naplónév csak egy adott szegmens vagy egy tartomány esetében használható fő számlákhoz. [![Naplóellenőrzési szegmens](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

Az **Automatikus sztornírozás** lehetőség elérhető az általános naplók esetében. Tegyük fel például, hogy van egy elhatároláskiigazítása, ahol a tényleges dokumentum feldolgozása még nem történt meg (lásd az alábbi ábrán).
[![Általános napló sztornírozása](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

A Microsoft Excel-bővítmény naplóbejegyzésekhez még nagyobb automatizálást és egyszerűbb adatbevitelt tesz lehetővé. A **Sorok megnyitása az Excelben**művelet elérhető az **Általános napló** és **Naplóbizonylat** oldalakon. 

Az **Időszakos naplók** oldalon beállíthatja az ismétlődő naplókra a naplófeldolgozás automatizálását. 

Bizonylatsorokat bármikor használhat. Az **Általános naplók** oldalon a **Mentés** és **Bizonylatsablon kiválasztása** műveleteket a **Bizonylatsablon** oldalon találja, a bizonylatsorok **Funkciók** lehetősége alatt.

## <a name="related-setup"></a>Kapcsolódó beállítások
A következő beállítások nem csak az általános naplókra vonatkoznak, de segítik a helyes és egyszerű adatbevitelt.

### <a name="main-account"></a>Fő számla

A fő számla beállítás számos lehetőséget nyújt az általános napló feldolgozására:

-   **DC/CR követelmény** – Ezt a beállítást akkor használja, ha a fő számla terhelési vagy jóváírási tranzakciókra van korlátozva. A beállítás jóváhagyása a napló ellenőrzése vagy feladása alkalmával történik.
-   **Alapértelmezett ellenszámla**
-   **Felfüggesztett** – Felfüggeszti egy fő számla adatbevitelét minden vállalatnál vagy egy adott vállalatnál/jogi személynél.
-   **Manuális bevitel tiltása** – Megakadályozza, hogy a felhasználók maguk adjanak meg értékeket a számlához a naplókban.
-   **Pénznem alapértelmezése/érvényesítése**
-   **Jogi személy felülbírálása** – Ez a beállítás csak a meghatározott vállalatra vagy jogi személyre vonatkozik:
    -   **Áfa alapértelmezése/érvényesítése**
    -   **Alapértelmezett dimenzió** – **Nem rögzített** vagy **Rögzített érték**. **Rögzített érték** segítségével garantálható, hogy a feladások mind a fő számlához mindig olyan dimenzióértéket használjanak, amely **Rögzített** beállítású.
-   **Feladás ellenőrzése**
    -   **Felhasználó érvényesítése** – Ez a beállítás szabályozza, hogy mely felhasználók jogosultak olyan a fő számlára való feladásra.
    -   **Feladási típus érvényesítése** – Ez a beállítás szabályozza, hogy mely feladási típusok megengedettek a fő számlához.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Könyvelési szerkezetek és a speciális szabályok szerkezetei

A könyvelési szerkezetek és a speciális szabályok szerkezetei rendkívül fontosak, mert ezekkel biztosítható, hogy a pénzügyi jelentés készítéséhez és teljesítéskövetéséhez szükséges adatok rögzítése megtörténik az általános napló vagy bármilyen dokumentum feldolgozása során. A könyvelési szerkezetek és a speciális szabályok szerkezetei segítségével személyre szabhatja az adatbeviteli élményt. Megszabhatja, hogy csak a helyzethez kapcsolódó pénzügyi dimenziók adatbevitele legyen lehetséges, és kötelezővé teheti azt a feltételt, mely alapján a megfelelő adat mindig rögzítésre kerül.

További tudnivalókért lásd: [Tervezés: Számlatükör](plan-chart-of-accounts.md). 




