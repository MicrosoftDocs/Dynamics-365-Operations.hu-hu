---
title: "Információk megtalálása keresések használatával"
description: "A Microsoft Dynamics 365 for Finance and Operations programban számos mező rendelkezik keresőkkel, amelyek révén egyszerűen megtalálhatja a helyes vagy a kívánt értéket. Számos fejlesztést adtak hozzá a keresésekhez, amelyek segítségével ezeket a lehetőségeket könnyebb használni, és segítségükkel a felhasználók hatékonyabbá válnak. Ebben a témakörben megismerheti ezeket az új keresési funkciókat, és néhány hasznos tippet is kap annak érdekében, hogy optimálisan kihasználhassa a rendszer kereséseit."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 9de957490b2ca87949a7cbcecc9acb4e8b98aaaf
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="find-information-by-using-lookups"></a>Információk megtalálása keresések használatával

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations programban számos mező rendelkezik keresőkkel, amelyek révén egyszerűen megtalálhatja a helyes vagy a kívánt értéket. Számos fejlesztést adtak hozzá a keresésekhez, amelyek segítségével ezeket a lehetőségeket könnyebb használni, és segítségükkel a felhasználók hatékonyabbá válnak. Ebben a témakörben megismerheti ezeket az új keresési funkciókat, és néhány hasznos tippet is kap annak érdekében, hogy optimálisan kihasználhassa a rendszer kereséseit.  

<a name="responsive-lookups"></a>Kontextusfüggő keresések
------------------

A Dynamics 365 for Finance and Operations korábbi verzióinál a keresővel való interakció során a felhasználónak konkrét műveletet kellett végrehajtania a legördülő menü megnyitásához. Lehet, hogy csillagot (\*) írt be a keresés jelenlegi érték alapján történő szűrése érdekében, a legördülő gombra leadott kattintással, illetve az **Alt**+**Lefelé nyíl** billentyűkód megadásával. A kereső felülete a következőképpen módosult annak érdekében, hogy jobban igazodjon a internetes gyakorlatokhoz:

-   A Keresés legördülő menüi automatikusan megnyílnak a gépelés során jelentkező kis szünet után, és a legördülő menü tartalmát a kereső vezérlőelemeinek értéke alapján szűri a rendszer.
    -   Kérjük, vegye figyelembe, hogy megszűnt az a régi funkció, hogy a legördülő menü automatikusan megnyílt a csillag (\*) karakter beírását követően.
-   A kereső legördülő menüjének megnyitását követően a következők történnek:
    -   A kurzor a keresőben marad (ahelyett, hogy a fókusz a legördülő menübe kerülne), és Ön továbbra is módosításokat hajthat végre a vezérlő értékénél. Azonban a felhasználó továbbra is használhatja a **Felfelé nyíl** és a **Lefelé nyíl** gombokat a sorok legördülő menüben való módosításához, az Enter billentyűvel pedig kijelölheti az aktuális sort a legördülő menüben.
    -   A legördülő menü tartalma módosul azt követően, hogy módosította a kereső értékét.

Képzelje el például a **Város** keresőmezőt. 

Amikor a fókusz a **Város** mezőn van, elkezdheti keresni a kívánt város megkeresését néhány betű beírásával, például: „bud”.  Miután abbahagyja a gépelést, a kereső automatikusan megnyílik, azokra a városokra szűrve, amelyek a „col” betűkkel kezdődnek. 

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png) 

Ezen a ponton a kurzor még mindig a keresési mezőben van. Ha folytatja a gépelést, és az érték „colum” lesz, akkor a kereső tartalma automatikusan módosul, és ezáltal csak a legújabb érték látható a felületen. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Annak ellenére, hogy a fókusz még mindig a keresőben van, a **Felfelé nyíl** vagy a **Lefelé nyíl** billentyűvel kiemelheti a kijelölni kívánt sort. Ha megnyomja az **Enter** billentyűt, kiválasztásra kerül a kijelölt sor a keresésből, és a vezérlő értéke frissül. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Az azonosítón túli adatok beírása
Adatok bevitele esetén természetes, hogy a felhasználók egy entitást (például ügyfelet vagy szállítót) a neve, és nem az entitásra jellemző azonosító alapján azonosítanak. A Dynamics 365 for Finance and Operations jelenlegi verziójában számos (de nem az összes) keresés mostantól a kontextus szerinti adatbevitelt is lehetővé teszi. Ez a nagyszerű funkció lehetővé teszi a felhasználó számára, hogy az azonosítót vagy a megfelelő nevet beírja a keresőbe. 

Érdemes például fontolóra vennie a **Vevői számla** mező használatát egy értékesítési rendelés létrehozásakor. Ez a mező mutatja a vevő **számlaazonosítóját**, de a felhasználók általában inkább **számlanevet** írnak be **számlaazonosító** helyett ennél a mezőnél, amikor létrehoznak egy értékesítési rendelést, mint például „Tip-Top Nagyker” a „HU-003” helyett.

Ha a felhasználó elkezdett beírni egy **számlaazonosítót** a keresőbe, akkor a legördülő menü automatikusan megnyílik, ahogyan az előző szakaszban látható, és a keresés a felhasználó számára az alábbiak szerint jelenik meg.

[![Környezetfüggő keresés a vevő számlaazonosítójának megadásakor](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

A felhasználó immár azonban megadhatja egy **Számlanév** kezdetét is. Ennek észlelése esetén a felhasználó a következő keresőt láthatja. Fedezze fel, hogyan helyeződik át a **Név** oszlop a keresés első oszlopává, és hogyan történik meg a keresés rendezése és szűrése a **Név** oszlop alapján.

[![A Vevőnév bevitelekor környezetfüggő keresés](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Rács oszlopfejlécek használata speciális szűrésre és rendezésre
Az előző két szakaszban tárgyalt keresési fejlesztések nagy mértékben javítják a felhasználók azon képességét, hogy navigáljanak a keresés soraiban az „ezzel kezdődik” keresésekkel, a keresés **Azonosító** vagy **Név** mezőjében. Vannak azonban olyan helyzetek, amelyekben speciálisabb szűrés (vagy rendezés) szükséges a megfelelő sor kikereséséhez. Ezekben a helyzetekben a felhasználónak szüksége van a szűrési és rendezési lehetőségekre a keresésen belül található rács oszlopfejléceinél. Például képzelje el, hogy egy alkalmazott belép egy értékesítési rendelésbe, és meg kell találnia a megfelelő „kábelt” termékként. Ha a „kábel” lehetőséget írja be a **Cikkszám** mezőbe, az nem segít, mert nincsenek olyan terméknevek, amelyek a „kábel” szöveggel kezdődnek. 

![emptyitemlookup](./media/emptyitemlookup.png) 

Ehelyett a felhasználónak törölnie kell a keresési vezérlő értékét, nyissa meg a keresési legördülő menüt, és szűrje le a legördülő menüt a rács oszlopfejléc segítségével, az alábbiak szerint. Az egeret (vagy érintéses vezérlőt) használók egyszerűen rákattinthatnak (vagy megérinthetik) bármelyik oszlopfejlécre az adott oszlop szűrési és rendezési lehetőségeinek eléréséhez. A billentyűzetet használóknak egyszerűen meg kell nyomniuk az **Alt**+**Lefelé** **nyíl** kombinációt másodjára a fókusz legördülő menübe való áthelyezését követően, és ezt követően a felhasználó átválthat a megfelelő oszlopra, majd megnyomhatja a **Ctrl**+**G** billentyűkombinációt a rácsos oszlopfejléc legördülő menüjének megnyitásához. 

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png) 

A szűrő alkalmazása után (lásd az alábbi képet) a felhasználó a szokásos módon találhatja meg és választhatja ki a sort. 

![filtereditemlookup](./media/filtereditemlookup.png)




