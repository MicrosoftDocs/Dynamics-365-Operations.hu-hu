---
title: "Információk kereséséhez használja a keresések"
description: "Microsoft Dynamics 365 műveletekhez sok mező van kereséseket, amelyek segítségével könnyen megtalálják a megfelelő vagy a kívánt értéket. Számos további lehetőségét, amely teheti ezeket a vezérlőket használhatóbbá és a felhasználók hatékonyabb kereséseket hozzá lettek adva. Ez a témakör új keresési szolgáltatások tanulni fogunk, és kap hasznos tippeket megszerezni a keresések ki optimális használatát a rendszer."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Információk kereséséhez használja a keresések

Microsoft Dynamics 365 műveletekhez sok mező van kereséseket, amelyek segítségével könnyen megtalálják a megfelelő vagy a kívánt értéket. Számos további lehetőségét, amely teheti ezeket a vezérlőket használhatóbbá és a felhasználók hatékonyabb kereséseket hozzá lettek adva. Ez a témakör új keresési szolgáltatások tanulni fogunk, és kap hasznos tippeket megszerezni a keresések ki optimális használatát a rendszer.  

<a name="responsive-lookups"></a>Válaszol keresések
------------------

Korábbi verzióiban a Dynamics 365 műveletek esetében a keresési vezérlő tevékenység során a felhasználó kellene explicit műveletet a legördülő menü megnyitása. Ez történt a csillag beírásával (\*) a Keresés a vezérlőelem aktuális értéke alapján szűrni a vezérlőelemet, a legördülő gombra kattintva, és segítségével a **Alt**+**le** billentyűparancsot. Keresési vezérlők web jelenlegi gyakorlatának jobban illeszkedjenek a következőképpen módosult:

-   Keresési legördülő menük most automatikusan megnyíljon enyhe szünetben ír, a legördülő menü tartalmát a keresési vezérlőelem értéke alapján szűrni.
    -   Vegye figyelembe, hogy a csillag karakter beírása után a legördülő lista automatikus megnyitása a régi viselkedés (\*) elavult.
-   Miután a Keresés legördülő menüből nyitotta meg, a következő történik:
    -   A kurzor a keresési vezérlő (a fókusz áthelyezése a legördülő menüben) nem marad így a vezérlőelemben lévő érték módosításával is. Azonban a felhasználó továbbra is használhatja a **fel** és **le** sorok a legördülő menüből, és adja meg a legördülő menüben jelölje ki az aktuális sor.
    -   A legördülő menü tartalmát a keresési vezérlőelem értékének végrehajtott módosításokat követően helyesbíti.

Képzelje el például a keresési mező neve **Város**. 

Ha a fókusz a van a **Város** mezőben kezdheti a város, amelyet beírásával néhány betűt, mint a "col."  Írja be a befejezése után a keresés automatikusan megnyíljon, e városok "oszlop"-val kezdődő szűrt. 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

Ezen a ponton a kurzor még van a keresési mezőben. Ha folytatja, az értéke "oszlop", írja be, a keresési tartalom automatikus megfelelően legkésőbb a vezérlőelemben lévő érték beállítása. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Annak ellenére, hogy a fókusz még a keresési vezérlő van, akkor is használhatja a **fel** vagy **le** jelölje ki a sort, amely a kijelölni kívánt billentyűket. Ha megnyomja a **Enter** a keresésből a kijelölt sor lesz választva, és a vezérlőelem értéke módosul. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Több, mint azonosítók beírása
Adatok bevitele esetén természetes a felhasználóknak, hogy azonosítja az entitásokat, például egy vevő vagy szállító neve helyett egy azonosítóját az entitás szempontjából. Dynamics 365 keresések sok (de nem minden) most lehetővé teszi a helyi adatbevitel műveletekhez aktuális verziójában. Ez nagyszerű szolgáltatása lehetővé teszi, hogy a felhasználó Azonosítóját vagy a megfelelő nevet írja be a keresési vezérlő. 

Tegyük fel, hogy a **vevői számla** mezőben, amikor értékesítési rendelést hoz létre. Ez a mező mutatja a **Fiókazonosító** az a vevő, de a felhasználó általában inkább adja meg egy **fióknév** helyett egy **Fiókazonosító** "Erdő Wholesales" helyett "US-003" például egy eladási rendelés létrehozásakor a mező

Ha a felhasználó adhatja meg az **Fiókazonosító** a keresési vezérlőbe, a legördülő menü automatikusan nyitna az előző szakaszban leírtak szerint, és a felhasználó a keresési lenne látni, ahogy az lent látható.

[![A Vevőkód számla bevitelekor környezetfüggő keresés](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Azonban a felhasználó most is megadhat az elején egy **fiók neve** is. Észlelhető, ha a felhasználó látja a következő keresés. Értesítés a **neve** oszlop átkerül a Keresés az első oszlop, és a keresés rendezni és szűrni hogyan alapján a **neve** oszlop.

[![Környezetfüggő keresés bevitelekor a vevő neve](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Rács oszlopfejlécek segítségével speciális szűrés és rendezés
A keresési fejlesztések nagymértékben az előző két szakaszban tárgyalt javításához keresse meg a sorok alapján a "kezdete" Keresés, keresés képessége, a felhasználó a **ID** vagy **neve** a keresési mezőjében. Azonban vannak olyan helyzetek, amelyekben Speciális szűrés (vagy rendezés) megkereséséhez szükség van a helyes sor. Ebben az esetben a felhasználónak ismernie kell a rács-oszlopazonosítók belül a Keresés a szűrési és rendezési beállítások használata. Képzelje el például egy értékesítésirendelés-sor beírása alkalmazott, aki meg kell találnia "kábel" a termék jobb. Írja be a "kábel" a **cikkszám** vezérlőelem nem hasznos, nem termék neve kezdődik "kábel." 

![emptyitemlookup](./media/emptyitemlookup.png) 

Ehelyett a felhasználónak ismernie kell a keresési vezérlőelem értékét, a Keresés legördülő menü megnyitása és a legördülő menü segítségével a rács oszlopnak a fejlécénél, szűrés, ahogy az lent látható. Egér (vagy touch) felhasználó is egyszerűen kattintson (vagy touch) bármelyik oszlop címsorára a szűrési és rendezési beállítások az adott oszlop eléréséhez. Billentyűzet felhasználó, a felhasználó egyszerűen kell nyomja meg az ENTER **Alt**+**le****nyíl** segítségével mozgathatja a fókuszt a legördülő menüből, amely után a felhasználó lapon a megfelelő oszlopba, és nyomja le még egyszer **Ctrl**+**G** a rács oszlopfejléc legördülő menüjének megnyitása. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

A szűrő van alkalmazva (lásd az alábbi képen), miután a felhasználó keresheti meg és jelölje ki a sort, a szokásos módon. 

![filtereditemlookup](./media/filtereditemlookup.png)


