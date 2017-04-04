---
title: "Továbbfejlesztett banki egyeztetés importálásának beállítása"
description: "A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 for Operations rendszer banki tranzakcióiba. Ez a cikk ismerteti, hogyan állítható be az importálás az Ön banki kivonataihoz."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: acf7bacf6e95725024ff0a542a059349593d01a0
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Továbbfejlesztett banki egyeztetés importálásának beállítása

A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 for Operations rendszer banki tranzakcióiba. Ez a cikk ismerteti, hogyan állítható be az importálás az Ön banki kivonataihoz. 

A banki kivonat importálási beállítások az elektronikus banki kivonat formátumától függően változnak. Microsoft Dynamics 365 műveletek három banki kivonat formátumokat nem támogatja: ISO20022, MT940 és BAI2.

## <a name="sample-files"></a>Mintafájlok
Három formátum fordítása formátumra Dynamics 365 műveletekhez használt eredeti formátumról elektronikus banki kivonat fájlokat kell rendelkeznie. A szükséges erőforrás fájlokat megtalálhatja az **Erőforrások** fülön, az Application Explorer-ben a Microsoft Visual Studio alkalmazásban. Miután megtalálta a fájlokat, másolja azokat egy ismert helyre, így egyszerűen feltöltheti azokat a telepítési folyamat során.

| Erőforrás neve                                           | Fájlnév                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_,\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_,\_egyeztetés\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_,\_összetett\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_,\_egyeztetés\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_,\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_,\_egyeztetés\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>A banki kivonat formátumainak és a technikai elrendezések példái
Az alábbiakban példák a továbbfejlesztett banki egyeztetés importálási fájl műszaki elrendezés meghatározások és három kapcsolódó banki kivonat például fájlok: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Technikai elrendezésdefiníció                             | Banki kivonat példafájl          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Állítsa be a ISO20022 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját ISO20022 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Ugrás a **munkaterületek**&gt;**adatok kezelése**.
2.  Click **Import**.
3.  Adja meg a formátum nevét, például **ISO20022**.
4.  A **Forrás adat formátuma **mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az** ISO20022XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** 365 Dynamics műveletek átalakító fájlok a szokásos formátum van építve. Bankok gyakran különbözik ebben a formátumban, mert előfordulhat az átalakító fájl leképezése a banki kivonat formátumának módosítása. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Click **New**.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
13. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az ISO20022 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Keresse fel **készpénz-és banki**&gt;**a telepítő**&gt;**banki egyeztetés beállításainak speciális**&gt;**banki kivonat formátuma**.
2.  Click **New**.
3.  Adja meg a kivonat formátumát, például a **ISO20022**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **ISO20022**.
6.  Jelölje be az **XML file** jelölőnégyzetet.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Ugrás a **készpénz-és banki**&gt;**bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés **lehetőséget **Igen** értékre.
4.  Állítsa be a **Kivonat formátuma **mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Állítsa be a MT940 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját MT940 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Ugrás a **munkaterületek**&gt;**adatok kezelése**.
2.  Click **Import**.
3.  Adja meg a formátum nevét, például **MT940**.
4.  A **Forrás adat formátuma** mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **MT940TXT-to-MT940XML.xslt** fájl, amit már korábban lementett.
11. Kattintson az **Új** elemre.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **MT940XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** 365 Dynamics műveletek átalakító fájlok a szokásos formátum van építve. Bankok gyakran különbözik ebben a formátumban, mert előfordulhat az átalakító fájl leképezése a banki kivonat formátumának módosítása. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Click **New**.
14. Az 3-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
15. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az MT940 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Keresse fel **készpénz-és banki**&gt;**a telepítő**&gt;**banki egyeztetés beállításainak speciális**&gt;**banki kivonat formátuma**.
2.  Click **New**.
3.  Adja meg a kivonat formátumát, például a **MT940**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **MT940**.
6.  Állítsa a **Fájl típus** mezőt **txt** értékre.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Ugrás a **készpénz-és banki**&gt;**bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés** lehetőséget **Igen** értékre.
4.  Amikor felszólítást kap a választás megerősítéséhez, és lehetővé teszi a Speciális banki egyeztetést, kattintson az **OK** lehetőségre.
5.  Állítsa be a **Kivonat formátuma** mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Állítsa be a BAI2 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját BAI2 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Ugrás a **munkaterületek**&gt;**adatok kezelése**.
2.  Click **Import**.
3.  Adja meg a formátum nevét, például **BAI2**.
4.  A **Forrás adat formátuma** mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **BAI2CSV-to-BAI2XML.xslt** fájl, amit már korábban lementett.
11. Kattintson az **Új** elemre.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **BAI2XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** 365 Dynamics műveletek átalakító fájlok a szokásos formátum van építve. Mivel a bankok gyakran tónusértékeinek ezt a formátumot, és az átalakító fájl leképezése a banki kivonat formátumának frissítése is. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Click **New**.
14. Az 3-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
15. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az BAI2 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Keresse fel **készpénz-és banki**&gt;**a telepítő**&gt;**banki egyeztetés beállításainak speciális**&gt;**banki kivonat formátuma**.
2.  Click **New**.
3.  Adja meg a kivonat formátumát, például a **BAI2**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **BAI2**.
6.  Állítsa a **Fájl típus** mezőt **txt** értékre.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Ugrás a **készpénz-és banki**&gt;**bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés** lehetőséget **Igen** értékre.
4.  Amikor felszólítást kap a választás megerősítéséhez, és lehetővé teszi a Speciális banki egyeztetést, kattintson az **OK** lehetőségre.
5.  Állítsa be a **Kivonat formátuma** mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **BAI2**.

## <a name="test-the-bank-statement-import"></a>Bankkivonat importálásának tesztelése
Az utolsó lépés a banki kivonatok importálásnak tesztelése.

1.  Ugrás a **készpénz-és banki**&gt;**bankszámlák**.
2.  Válassza ki azt a bankszámlát, amihez a Speciális banki egyeztetés funkció engedélyezve van.
3.  Az **Egyeztetés** fülön, kattintson a **Banki kivonatok** lehetőségre.
4.  A **Banki kivonat** oldalon, kattintson az **Importnyilatkozat** lehetőségre.
5.  Az **Bank számla** mezőt állítsa a kiválasztott a bankszámlára. A **Kivonat formátuma** mező értéke automatikusan lesz beállítva, a bankszámla beállításainak alapján.
6.  Kattintson a **Keresés** lehetőségre, és jelölje ki az ön elektronikus banki kivonat fájlját.
7.  Kattintson a **Feltöltés** hivatkozásra.
8.  Kattintson az **OK** gombra.

Ha az importálás sikeres, egy üzenetet fog kapni, amely arról tájékoztatja, hogy sikeresen importálta az ön kivonatát. Ha az importálás nem sikeres, az **Adatok kezelése** munkaterületen, a **Feladatelőzmények** szakaszban, keresse meg a feladatot. Kattintson a feladathoz tartozó **Végrehajtási részletek** lehetőségre, a **Végrehajtási összefoglalás** lap megnyitásához, majd kattintson a **Végrehajtási napló megtekintése** lehetőségre, az importálási hibák megtekintéséhez.


