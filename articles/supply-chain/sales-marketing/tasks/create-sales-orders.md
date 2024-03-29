---
title: Értékesítési rendelések létrehozása
description: Ez az eljárás bemutatja, hogyan lehet eladási rendelést létrehozni.
author: Henrikan
ms.date: 04/06/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462f47ab5d85665ed8132e5bfb6dd945c537c1ef
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551724"
---
# <a name="create-sales-orders"></a>Értékesítési rendelések létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet eladási rendelést létrehozni. Ezt a folyamatot használhatja az USMF bemutatócéghez. Az Értékesítési rendelést jellemzően értékesítési munkatárs hozza létre. 

## <a name="enter-sales-order-header-details"></a>Adja meg az értékesítési rendelés fejlécének részleteit
1. Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.
2. Válassza az **Új** lehetőséget.
3. A **Vevői számla** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A vevőrekord megkeresése és kijelölése a listán
    - Válassza például a US-004 vevőszámot.  
5. Válassza ki az **OK** lehetőséget.

## <a name="enter-sales-order-line-details"></a>Adja meg az értékesítési rendelés sorainak részleteit
    
Szervezetünk által forgalmazott termékek különböző változatokban kerülhetnek forgalomba, amely termékek között a különbséget jelentheti a konfiguráció, szín és stílus. Továbbá a termékek tárolási dimenzióval rendelkezhetnek, például webhely, raktár, raklap, követési dimenziók (köteg és sorozatszámok). A dimenziók hozzárendelésekor a dimenziókhoz tartozó értékeket ki kell választani a rendelési sorban. A rendelésbevitel hatékonyságának növelése érdekében a rendelési rácshoz rendelje hozzá a megfelelő dimenziókat.
    
1. Az **Értékesítésirendelés-sorok** szakaszban válassza ki az **Értékesítésirendelés-sort.**
2. **Dimenziók** kijelölése.
    
    Ebben az esetben válassza ki a Szín, Webhely és Raktár dimenziókat. Az itt kiválasztott dimenziók az értékesítési rendelés rácson jelennek meg. Ha szeretné, hogy a választások láthatók maradjanak, állítsa a **Beállítások mentése** lehetőséget Igen-re.
    
3. Válassza ki az **OK** lehetőséget.
4. A **Cikkszám** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Ebben a példában válassza ki a T0004 cikkszámot.
    - Ha a cikk része az értékesítési kategóriának a cikk neve automatikusan megjelenik az Eladási kategória mezőben.  
    - Ha a termékdimenzió mezők már rendelkeznek értékkel, akkor az érték a termékrekordból lett átmásolva, ahol alapértelmezett termékdimenzióként lett megadva. Az alapértelmezett értéket bármikor módosíthatja.   
6. A **Szín** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. Adjon meg egy számot a **Mennyiség** mezőben.
    - Ha a cikk termelési, tárolási eladási egysége eltér az eladástól, és az eladási mértékegység be van állítva a termékrekordon, akkor ez az egység jelenik meg az **Egység** mezőben. Az érték bármikor módosítható.   
    - Ha a **Webhely** mezőnek már van értéke, akkor az érték a termékhez társított rendelés beállításainak fejlécéből került másolásra. Az érték bármikor módosítható. Ha a mező üres válasszon ki egy értéket.   
    - Ha az **Egységár** már rendelkezik értékkel, akkor az érték az érvényes kereskedelmi megállapodásból vagy a termékrekordból került másolásra. (Az egységár származhat értékesítési szerződésből is, de az értékesítési rendelés létrehozásának folyamata értékesítési szerződés alapján különbözik az alábbiaktól.) Ha a mező üres adjon meg egy értéket.   
    - Az **Engedmény** mező az engedmény összegét tartalmazva termékegységre vetítve. A sor teljes engedményösszegének kiszámításához az értéket meg kell szorozni a sorban szereplő mennyiséggel. Ha az **Engedmény** már rendelkezik értékkel, akkor az érték az érvényes kereskedelmi megállapodásból került másolásra. Ha a mező üres, és szeretne a vevőnek sorkedvezményt adni, akkor adjon meg egy értéket.  
    - Az **Engedmény százaléka** mező a százalékot tartalmazza, amely a teljes bruttó sorösszegből kerül majd levonásra.  Ha az **Engedmény százalék** már rendelkezik értékkel, akkor az érvényes kereskedelmi megállapodásból került másolásra. Ha a mező üres, és szeretne a vevőnek sorkedvezményt adni, akkor adjon meg egy értéket. 
    - A **Nettó** összeg mező azt az értéket tartalmazza amely a sormennyiség és a kedvezményekkel korrigált egységár alapján került számításra.  Átírhatja a számított értéket.  

## <a name="review-the-order-totals"></a>Értékesítési rendelés összegeinek ellenőrzése
1. A **Művelet panelen** kattintson az **Értékesítési rendelés** elemre.
2. Válassza ki az **Összegek** elemet.
    
    Az **Összegek** oldalon a teljes rendeléssel kapcsolatos részletek láthatók. Ez magában foglalja a részösszeget, amely a sorok nettó összege az alkalmi sorengedményekhez van igazítva, a teljes számlaösszeget, amely egy részösszeg a alkalmi rendelési-szint engedményhez igazítva, díjakat és az áfát, a vevői hitelkeret helyzetét és továbbiakat. A számlaösszeg az az érték, amely megjelenik a vevő számladokumentumában.  
    
3. Válassza ki az **OK** lehetőséget.

## <a name="sales-order-creation-performance-enhancement"></a>Értékesítési rendelések létrehozásának teljesítményjavítása
Az alkalmazás 10.0.26-os **verziójában bevezetett új funkció csökkenti a SourceDocumentHeader** **és SourceDocumentLine táblák további rekord-létrehozási többletét**. A teljesítmény csökken, és csökken a tárolási méret, mivel ezek a rekordok nincsenek létrehozva. A forrásdokumentum keretrendszerének ezen alapul szolgáló táblái jelenleg nem használatosak a termék értékesítési rendeléseit használva, és nincsenek ütemezett tervek a termékek alkalmazására. Ennek a funkciónak a engedélyezése biztonságos változásnak számít a jobb teljesítmény érdekében. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
