---
title: Továbbfejlesztett banki egyeztetés importálásának beállítása
description: A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Microsoft Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a cikk ismerteti, hogyan állítható be az importálás az Ön banki kivonataihoz.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22d173f6ced2af3e8023bd40f70ca70728c3a0a7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834980"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Továbbfejlesztett banki egyeztetés importálásának beállítása

[!include [banner](../includes/banner.md)]

A Továbbfejlesztett banki egyeztetés funkció lehetővé teszi Önnek az elektronikus banki kivonatok és az automatikus egyeztetés importálását a Dynamics 365 Finance rendszer banki tranzakcióiba. Ez a cikk ismerteti, hogyan állítható be az importálás az Ön banki kivonataihoz. 

A banki kivonat importálási beállítások az elektronikus banki kivonat formátumától függően változnak. A Finance által támogatott három banki kivonat formátuma: ISO20022, MT940 és BAI2.

## <a name="set-time-zone-preference"></a>Időzóna-preferencia beállítása
A banki kivonatok importálási beállításainak konfigurálásakor fontos, hogy figyelembe vegye a banki kivonat fájljain belül a dátum-idő adatok időzónáját. Alapértelmezett módon feltételezhető, hogy a megadott dátum és időértékek már az Egyezményes világidőt (UTC) követik, így nem kell időzóna-átváltást alkalmazni az adatok importálásakor. 

Lehetőség van az adatok importálásához használni kívánt időzóna meghatározására. Ez a beállítás az egyes **Forrásadat-formátum részletei** oldal **Időzóna-preferencia** mezőjében áll rendelkezésre (**Adatkezelés munkaterület > Adatforrások konfigurálása > Adatformátum kiválasztása > Regionális beállítások** gyorslap). Ez a megadott időzóna-beállítás minden olyan importálásra vonatkozik, amely a forrásadatok formátumát használja. Tetszőleges számú adatforrás-formátumot létre lehet hozni a különböző időzónák adatainak importálásához.  

Előfordulhat, hogy ez az időzóna nem ugyanaz, mint a felhasználó vagy a vállalat időzónája, ezért ügyeljen arra, hogy az időzónát a dátum-és időadatok alapján kell egyértelműsíteni. Javasoljuk, hogy az időzóna-beállítások megadásakor vegye figyelembe a következő szempontokat. 

 - Ez az időzóna-preferencia minden olyan importálásra vonatkozik, amely a forrásadatok formátumát használja. Tetszőleges számú adatforrás-formátumot létre lehet hozni a különböző időzónák adatainak importálásának kezeléséhez. 
 
 - Az időzónabeállításnak meg kell felelnie a helyi időzónának az importált fájl dátum-és időadataiban 
 
 - A dátum-és időadatok időzónája nem biztos, hogy ugyanaz, mint a felhasználó vagy a vállalat időzónája.
 
 - A felhasználók saját időzónájukat a **Felhasználói beállítások** pontban adhatják meg.

Ne felejtse el, hogy a következő műveletek minimalizálni tudják a lehetséges dátum-és időütközéseket a banki kivonatok importálásakor. 

 - Ne módosítsa az időzóna-preferenciákat olyan bankszámlák esetében, amelyeknél már importált kivonatokat. Az időzóna-preferencia módosítása hatással lehet az új kimutatások meglévő kimutatásokhoz viszonyított elrendezésére az időzóna-módosítás miatt. 
 
 - Ellenőrizze az összes olyan importot, amely a kiválasztott adatforrás-formátumot használja. A formátumhoz megadott időzóna-preferencia a formátumot használó összes importálási projektre érvényes lesz. Ellenőrizze, hogy a formátumhoz megadott időzóna-preferencia megfelelő-e a formátumot használó összes importálási projektre.

## <a name="sample-files"></a>Mintafájlok
Mind a három formátumra vonatkozóan rendelkezni kell olyan fájlokkal, amik az elektronikus banki kivonatot lefordítják az eredeti formátumról a Finance által használható formátumra. A szükséges erőforrás fájlokat megtalálhatja az **Erőforrások** fülön, az Application Explorer-ben a Microsoft Visual Studio alkalmazásban. Miután megtalálta a fájlokat, másolja azokat egy ismert helyre, így egyszerűen feltöltheti azokat a telepítési folyamat során.

| Erőforrás neve                                           | Fájlnév                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>A banki kivonat formátumainak és a technikai elrendezések példái
Az alábbiakban a továbbfejlesztett banki egyeztetési importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja: [Importfájl-példák](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Technikai elrendezésdefiníció                             | Banki kivonat példafájl          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| DynamicsAXISO20022Layout                                | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout                                    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Állítsa be a ISO20022 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját ISO20022 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Menjen a **Munkaterületek** &gt; **Adatkezelés** lehetőségre.
2.  Kattintson az **Importálás** gombra.
3.  Adja meg a formátum nevét, például **ISO20022**.
4.  A **Forrás adat formátuma** mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **ISO20022XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** Az átalakítási fájlok szabványos formátumra épülnek. Mivel a bankok gyakran eltérnek ebben a formátumban, lehet, hogy frissíteni kell az átalakító fájlt, hogy leképezze az ön banki kivonat formátumát. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Kattintson az **Új** elemre.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
13. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az ISO20022 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Menjen a **Készpénz és bankkezelés** &gt; **Beállítás** &gt; **Továbbfejlesztett banki egyeztetés beállítása** &gt; **Banki kivonatok formátuma** elemre.
2.  Kattintson az **Új** elemre.
3.  Adja meg a kivonat formátumát, például a **ISO20022**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **ISO20022**.
6.  Jelölje be az **XML file** jelölőnégyzetet.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Nyissa meg a következőt: **Készpénz- és bankkezelés** &gt; **Bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés** lehetőséget **Igen** értékre.
4.  Állítsa be a **Kivonat formátuma** mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Állítsa be a MT940 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját MT940 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Menjen a **Munkaterületek** &gt; **Adatkezelés** lehetőségre.
2.  Kattintson az **Importálás** gombra.
3.  Adja meg a formátum nevét, például **MT940**.
4.  A **Forrás adat formátuma** mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **MT940TXT-to-MT940XML.xslt** fájl, amit már korábban lementett.
11. Kattintson az **Új** elemre.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **MT940XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** Az átalakítási fájlok szabványos formátumra épülnek. Mivel a bankok gyakran eltérnek ebben a formátumban, lehet, hogy frissíteni kell az átalakító fájlt, hogy leképezze az ön banki kivonat formátumát. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Kattintson az **Új** elemre.
14. Az 3-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
15. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az MT940 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Menjen a **Készpénz és bankkezelés** &gt; **Beállítás** &gt; **Továbbfejlesztett banki egyeztetés beállítása** &gt; **Banki kivonatok formátuma** elemre.
2.  Kattintson az **Új** elemre.
3.  Adja meg a kivonat formátumát, például a **MT940**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **MT940**.
6.  Állítsa a **Fájl típus** mezőt **txt** értékre.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Nyissa meg a következőt: **Készpénz- és bankkezelés** &gt; **Bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés** lehetőséget **Igen** értékre.
4.  Amikor felszólítást kap a választás megerősítéséhez, és lehetővé teszi a Speciális banki egyeztetést, kattintson az **OK** lehetőségre.
5.  Állítsa be a **Kivonat formátuma** mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Állítsa be a BAI2 banki kivonatok importálását
Először definiálni kell a banki kivonat formátum feldolgozási csoportját BAI2 banki kivonatokhoz, az adatentitás keretrendszer használatával.

1.  Menjen a **Munkaterületek** &gt; **Adatkezelés** lehetőségre.
2.  Kattintson az **Importálás** gombra.
3.  Adja meg a formátum nevét, például **BAI2**.
4.  A **Forrás adat formátuma** mezőt állítsa **XML-Element** értékre.
5.  Az **Entitás neve** mezőbe írja be **Banki kivonatok**.
6.  Az importálási fájlok feltöltéséhez, kattintson a **Feltöltés** gombra, majd tallózással válassza ki a **SampleBankCompositeEntity.xml** fájlt, amit már korábban lementett.
7.  Miután a banki kimutatások entitás feltöltése és a hozzárendelés elkészült, kattintson a **Térkép megjelenítése** entitáshoz tartozó műveletre.
8.  A banki kimutatások entitás egy összetett entitást, amelyet négy külön entitás alkot. Válassza ki a listából a **BankStatementDocumentEntity** lehetőséget, majd kattintson a **Térkép megjelenítése** műveletre.
9.  Az **Átalakítások** fülön, kattintson az **Új** lehetőségre.
10. Az 1-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **BAI2CSV-to-BAI2XML.xslt** fájl, amit már korábban lementett.
11. Kattintson az **Új** elemre.
12. Az 2-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki az **BAI2XML-Reconciliation.xslt** fájl, amit már korábban lementett. **Megjegyzés:** Az átalakítási fájlok szabványos formátumra épülnek. Mivel a bankok gyakran eltérnek ebben a formátumban, lehet, hogy frissíteni kell az átalakító fájlt, hogy leképezze az ön banki kivonat formátumát. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Kattintson az **Új** elemre.
14. Az 3-es sorozatszámhoz, kattintson a **Fájlfeltöltés** lehetőségre, és válassza ki a **BankReconciliation-to-Composite.xslt** fájl, amit már korábban lementett.
15. Kattintson az **Átalakítások alkalmazása** lehetőségre.

A formátum feldolgozó csoport beállítása után, a következő lépés célja az BAI2 banki kivonatok banki kivonat formátuma szabályainak meghatározása.

1.  Menjen a **Készpénz és bankkezelés** &gt; **Beállítás** &gt; **Továbbfejlesztett banki egyeztetés beállítása** &gt; **Banki kivonatok formátuma** elemre.
2.  Kattintson az **Új** elemre.
3.  Adja meg a kivonat formátumát, például a **BAI2**.
4.  Adja meg a formátum nevét.
5.  Állítsa be a **Feldolgozó csoport** mezőt ahhoz a csoporthoz, amit már korábban definiált, például a **BAI2**.
6.  Állítsa a **Fájl típus** mezőt **txt** értékre.

Az utolsó lépés, a Speciális bankszámla egyeztetés engedélyezése és a kivonat formátumának beállítása a bank számlán.

1.  Nyissa meg a következőt: **Készpénz- és bankkezelés** &gt; **Bankszámlák**.
2.  Válassza ki azt a bankszámlát, és nyissa meg a részletek megtekintéséhez.
3.  Az **Egyeztetés** lapon, állítsa a **Speciális banki egyeztetés** lehetőséget **Igen** értékre.
4.  Amikor felszólítást kap a választás megerősítéséhez, és lehetővé teszi a Speciális banki egyeztetést, kattintson az **OK** lehetőségre.
5.  Állítsa be a **Kivonat formátuma** mezőt ahhoz a formátumhoz, amit már korábban létrehozott, például az **BAI2**.

## <a name="test-the-bank-statement-import"></a>Bankkivonat importálásának tesztelése
Az utolsó lépés a banki kivonatok importálásnak tesztelése.

1.  Nyissa meg a következőt: **Készpénz- és bankkezelés** &gt; **Bankszámlák**.
2.  Válassza ki azt a bankszámlát, amihez a Speciális banki egyeztetés funkció engedélyezve van.
3.  Az **Egyeztetés** fülön, kattintson a **Banki kivonatok** lehetőségre.
4.  A **Banki kivonat** oldalon, kattintson az **Importnyilatkozat** lehetőségre.
5.  Az **Bank számla** mezőt állítsa a kiválasztott a bankszámlára. A **Kivonat formátuma** mező értéke automatikusan lesz beállítva, a bankszámla beállításainak alapján.
6.  Kattintson a **Keresés** lehetőségre, és jelölje ki az ön elektronikus banki kivonat fájlját.
7.  Kattintson a **Feltöltés** hivatkozásra.
8.  Kattintson az **OK** gombra.

Ha az importálás sikeres, egy üzenetet fog kapni, amely arról tájékoztatja, hogy sikeresen importálta az ön kivonatát. Ha az importálás nem sikeres, az **Adatok kezelése** munkaterületen, a **Feladatelőzmények** szakaszban, keresse meg a feladatot. Kattintson a feladathoz tartozó **Végrehajtási részletek** lehetőségre, a **Végrehajtási összefoglalás** lap megnyitásához, majd kattintson a **Végrehajtási napló megtekintése** lehetőségre, az importálási hibák megtekintéséhez.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
