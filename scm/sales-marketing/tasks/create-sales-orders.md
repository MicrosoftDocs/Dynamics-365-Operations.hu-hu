--- 
title: "Értékesítési rendelések létrehozása"
description: "Ez az eljárás bemutatja, hogyan lehet eladási rendelést létrehozni."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 62276765e1cc76b2328a7b5b57bd18593d93e4ab
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-sales-orders"></a>Értékesítési rendelések létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet eladási rendelést létrehozni. Ezt a folyamatot használhatja az USMF bemutatócéghez. Az Értékesítési rendelést jellemzően értékesítési munkatárs hozza létre. 




## <a name="enter-sales-order-header-details"></a>Adja meg az értékesítési rendelés fejlécének részleteit
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A vevőrekord megkeresése és kijelölése a listán
    * Válassza például a US-004 vevőszámot.  
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az OK gombra.

## <a name="enter-sales-order-line-details"></a>Adja meg az értékesítési rendelés sorainak részleteit
    * Szervezetünk által forgalmazott termékek különböző változatokban kerülhetnek forgalomba, amely termékek között a különbséget jelentheti a konfiguráció, szín és stílus. Továbbá a termékek tárolási dimenzióval rendelkezhetnek, például webhely, raktár, raklap, fejtéses dimenziók (köteg és sorozatszámok). A dimenziók hozzárendelésekor a dimenziókhoz tartozó értékeket ki kell választani a rendelési sorban. A rendelésbevitel hatékonyságának növelése érdekében a rendelési rácshoz rendelje hozzá a megfelelő dimenziókat.  
1. Kattintson az Értékesítésirendelés-sor lehetőségre.
2. Kattintson a Dimenziókra.
    * Ebben az esetben válassza ki a Szín, Webhely és Raktár dimenziókat. Az itt kiválasztott dimenziók az értékesítési rendelés rácson jelennek meg. Ha szeretné, hogy a választások láthatóak maradjanak állítsa a Beállítások mentése lehetőséget Igen-re.   
3. Kattintson az OK gombra.
4. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Ebben a példában válassza ki a T0004 cikkszámot.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ha a cikk része az értékesítési kategóriának a cikk neve automatikusan megjelenik az Eladási kategória mezőben.  
    * Ha a termékdimenzió mezők már rendelkeznek értékkel, akkor az érték a termékrekordból lett átmásolva, ahol alapértelmezett termékdimenzióként lett megadva. Az alapértelmezett értéket bármikor módosíthatja.   
7. A Szín mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A kívánt rekord megkeresése és kijelölése a listán
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Adjon meg egy számot a Mennyiség mezőben.
    * Ha a cikk termelési, tárolási eladási egysége eltér az eladástól, és az eladási mértékegység be van állítva a termékrekordon, akkor ez az egység jelenik meg az Egység mezőben. Az érték bármikor módosítható.   
    * Ha a Webhely mezőnek már van értéke, akkor az érték a termékhez társított rendelés beállításainak fejlécéből került másolásra. Az érték bármikor módosítható. Ha a mező üres válasszon ki egy értéket.   
    * Ha az Egységár már rendelkezik értékkel, akkor az érték az érvényes kereskedelmi megállapodásból vagy a termékrekordból került másolásra. (Az egységár származhat értékesítési szerződésből is, de az értékesítési rendelés létrehozásának folyamata értékesítési szerződés alapján különbözik az alábbiaktól.) Ha a mező üres adjon meg egy értéket.   
    * Az Engedmény mező az engedmény összegét tartalmazva termékegységre vetítve. A sor teljes engedményösszegének kiszámításához az értéket meg kell szorozni a sorban szereplő mennyiséggel.    Ha az Engedmény már rendelkezik értékkel, akkor az érték az érvényes kereskedelmi megállapodásból került másolásra. Ha a mező üres, és szeretne a vevőnek sorkedvezményt adni, akkor adjon meg egy értéket.  
    * Az Engedmény százaléka mező a százalékot tartalmazza, amely a teljes bruttó sorösszegből kerül majd levonásra.  Ha az Engedmény százalék már rendelkezik értékkel, akkor az érvényes kereskedelmi megállapodásból került másolásra. Ha a mező üres, és szeretne a vevőnek sorkedvezményt adni, akkor adjon meg egy értéket.  
    * A Nettó összeg mező azt az értéket tartalmazza amely a sormennyiség és a kedvezményekkel korrigált egységár alapján került számításra.  Átírhatja a számított értéket.  

## <a name="review-the-order-totals"></a>Értékesítési rendelés összegeinek ellenőrzése
1. A Művelet panelen kattintson az Értékesítési rendelés elemre.
2. Kattintson az Összegek lehetőségre.
    * Az Összegek oldalon a teljes rendeléssel kapcsolatos részletek láthatók. Ez magában foglalja a részösszeget, amely a sorok nettó összege az alkalmi sorengedményekhez van igazítva, a teljes számlaösszeget, amely egy részösszeg a alkalmi rendelési-szint engedményhez igazítva, díjakat és az áfát, a vevői hitelkeret helyzetét és továbbiakat.  A számlaösszeg az az érték, amely megjelenik a vevő számladokumentumában.  
3. Kattintson az OK gombra.


