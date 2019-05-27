---
title: Értékesítési szerződések megadása
description: Ez az eljárás bemutatja, hogyan hozhat létre értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 025c9fe2f769f37b63bd79c6c3afedc31a955310
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563913"
---
# <a name="enter-sales-agreements"></a>Értékesítési szerződések megadása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="set-up-sales-agreement-header"></a>Értékesítési szerződés fejléc beállítása
1. Lépjen az Értékesítés és marketing > Értékesítési szerződések > Értékesítési szerződések menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Az Értékesítési szerződés osztályozása mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. Bontsa ki az Általános szakaszt.
9. Az Alapértelmezett kötelezettség mezőben válassza ki a „Termék értékére vonatkozó kötelezettség” lehetőséget.
    * A kötelezettségtípus egy kötelező feltétel, amelyet a megállapodáshoz kell hozzárendelnie, hogy meghatározza, miként teljesítendő a megállapodási szerződés. A négy előre meghatározott típus segítségével beállíthatja a vevő kötelezettségének célját, mennyiségben vagy értékben kifejezve. A mennyiség kötelezettségtípust kizárólag egy adott termékre lehet alkalmazni, de az értékalapú típusok alkalmazhatóak mind meghatározott és nem meghatározott termékek értékesítésére.  
10. A Lejárat dátuma mezőben állítsa be a dátumot egy későbbi dátumra, amikorra szeretné, hogy lejárjon a megállapodás.
11. Kattintson az OK gombra.

## <a name="set-up-product-value-commitment-lines"></a>Termék értékére vonatkozó kötelezettség sorainak beállítása.
1. Kattintson az Új sor hozzáadása lehetőségre.
2. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A megállapodásra kiválasztott kötelezettségvállalás típus hatással van arra, hogy milyen típusú információkat adhat meg a megállapodás soraira. Például egy értékalapú megállapodásra meg kell adnia a teljes nettó összeget (a megállapodás szerinti pénznemben), amelyért a vevő kötelezően vásárol Öntől árukat. Ebben a példában a soron található Mennyiség és Egységár mezők nem érhetők el, mert a vevő számára egy termékből adott értékben történő vásárlásra vonatkozó megállapodást hoz létre.   
5. A Nettó összeg mezőben adja meg azt a pénzösszeget, amely értékben a vevő kötelezettséget vállalt a vásárlásra.
6. Az Engedményszázalék mezőbe írjon be egy százalékos értéket, amely az ehhez a szerződéshez kapcsolt vásárlói értékesítésirendelés-sorokra lesznek érvényesek.
7. Bontsa ki a Soradatok szakaszt.
8. A Maximum betartatása mezőben válassza az Igen lehetőséget.
    * A Maximum betartatása kiválasztása azt jelenti, hogy a kötelezettségvállalás speciális árait, engedményeit és/vagy fizetési feltételeit használó minden értékesítésirendelés-sor teljes összege nem haladhatja meg a kötelezettségvállalásban megadott összeget.  
    * A minimális és maximális kiadási összegek olyan értéktartományt adnak meg, amelyet értékesíteni kell minden, a kiválasztott megállapodást használó értékesítési rendelés esetén.   
9. Bontsa ki az Értékesítési szerződés fejléc részét.
    * Ha a megállapodás állapotára nem Érvényes van beállítva, az értékesítési rendelések nem társíthatók a megállapodáshoz, és ezért nem járulhatnak hozzá a szerződés teljesítéséhez. Az állapot manuálisan módosítható ebben a fázisban. Az állapot azonban normális esetben akkor módosulna, amikor a vevőnek visszaigazolja a megállapodást.  
10. A Művelet panelen kattintson az Értékesítési szerződés elemre.
11. Kattintson a Megerősítés gombra.
    * Győződjön meg arról, hogy a Szerződés megjelölése érvényesként beállítás Igen értékre van állítva.  
12. Válassza az Igen lehetőséget a Jelentés nyomtatása mezőben.
13. Kattintson az OK gombra.
14. Zárja be a lapot.
    * A megállapodás most már érvényes, és elkezdheti a vevői rendelések csatolását a megállapodáshoz, a kötelezettség céljának kiegyenlítéséhez.  

