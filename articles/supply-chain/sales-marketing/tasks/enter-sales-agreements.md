---
title: Értékesítési szerződések megadása
description: Ez a témakör bemutatja, hogyan hozhat létre értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe.
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2c1494842c5fd2aa598546ba655c33d6fd3f16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568303"
---
# <a name="enter-sales-agreements"></a>Értékesítési szerződések megadása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan hozhat létre értékesítési szerződést, amely kötelezi valamelyik vevőjét egy termék vásárlására egy egyeztetett összegben adott idő alatt, különleges engedményekért cserébe. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="set-up-sales-agreement-header"></a>Értékesítési szerződés fejléc beállítása
1. A navigációs ablakban ugorjon a **Modulok > Értékesítés és marketing > Értékesítési szerződések > Minden értékesítési szerződés** pontra.
2. Válassza az **Új** lehetőséget.
3. A **Vevői számla** mező legördülő listájából válassza ki a kívánt rekordot.
4. Az **Értékesítési szerződés besorolása** mező legördülő listájából válassza ki a kívánt rekordot.
5. Bontsa ki az **Általános** szakaszt.
6. Az **Alapértelmezett kötelezettség** mezőben válassza ki a **Termék értékére vonatkozó kötelezettség** lehetőséget. A kötelezettségtípus egy kötelező feltétel, amelyet a megállapodáshoz kell hozzárendelnie, hogy meghatározza, miként teljesítendő a megállapodási szerződés. A négy előre meghatározott típus segítségével beállíthatja a vevő kötelezettségének célját, mennyiségben vagy értékben kifejezve. A mennyiség kötelezettségtípust kizárólag egy adott termékre lehet alkalmazni, de az értékalapú típusok alkalmazhatóak mind meghatározott és nem meghatározott termékek értékesítésére.  
7. A **Lejárat dátuma** mezőben állítsa be a dátumot egy későbbi dátumra, amikorra szeretné, hogy lejárjon a megállapodás.
8. Válassza ki az **OK** lehetőséget.

## <a name="set-up-product-value-commitment-lines"></a>Termék értékére vonatkozó kötelezettség sorainak beállítása.
1. Válassza a **Sor hozzáadása** lehetőséget.
2. A **Cikkszám** mezőben válassza ki a kívánt rekordot a legördülő menüből. A megállapodásra kiválasztott kötelezettségvállalás típus hatással van arra, hogy milyen típusú információkat adhat meg a megállapodás soraira. Például egy értékalapú megállapodásra meg kell adnia a teljes nettó összeget (a megállapodás szerinti pénznemben), amelyért a vevő kötelezően vásárol Öntől árukat. Ebben a példában a soron található **Mennyiség** és **Egységár** mezők nem érhetők el, mert a vevő számára egy termékből adott értékben történő vásárlásra vonatkozó megállapodást hoz létre.   
3. A **Nettó összeg** mezőben adja meg azt a pénzösszeget, amely értékben a vevő kötelezettséget vállalt a vásárlásra.
4. Az **Engedményszázalék** mezőbe írjon be egy százalékos értéket, amely az ehhez a szerződéshez kapcsolt vásárlói értékesítésirendelés-sorokra lesznek érvényesek.
5. Bontsa ki a **Sorrészletek** szakaszt.
6. A **Maximum betartatása** mezőben válassza az **Igen** lehetőséget.
    - A **Maximum betartatása** kiválasztása azt jelenti, hogy a kötelezettségvállalás speciális árait, engedményeit és/vagy fizetési feltételeit használó minden értékesítésirendelés-sor teljes összege nem haladhatja meg a kötelezettségvállalásban megadott összeget.  
    - A minimális és maximális kiadási összegek olyan értéktartományt adnak meg, amelyet értékesíteni kell minden, a kiválasztott megállapodást használó értékesítési rendelés esetén.   
7. Bontsa ki az **Értékesítési szerződés fejléc** részét. Ha a megállapodás állapotára nem **Érvényes** van beállítva, az értékesítési rendelések nem társíthatók a megállapodáshoz, és ezért nem járulhatnak hozzá a szerződés teljesítéséhez. Az állapot manuálisan módosítható ebben a fázisban. Az állapot azonban normális esetben akkor módosulna, amikor a vevőnek visszaigazolja a megállapodást.  
8. A Művelet panelen kattintson az **Értékesítési szerződés** elemre.
9. Válassza ki a **Visszaigazolás** lehetőséget. Győződjön meg arról, hogy a **Szerződés megjelölése érvényesként** beállítás **Igen** értékre van állítva.  
10. Válassza az **Igen** lehetőséget a **Jelentés nyomtatása** mezőben.
11. Válassza ki az **OK** lehetőséget.
12. Zárja be a lapot. A szerződés immár hatályos. Elkezdheti a vevői rendelések csatolását a megállapodáshoz, a kötelezettség céljának kiegyenlítéséhez.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]