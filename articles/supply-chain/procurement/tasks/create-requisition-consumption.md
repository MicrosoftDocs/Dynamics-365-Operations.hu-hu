---
title: Felhasználási igénylés létrehozása
description: Ez a témakor az igénylés létrehozásának folyamatát írja le.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acc2cdb9b74cccaefe565b0e2ae8ec4c5f2401c4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429386"
---
# <a name="create-a-requisition-for-consumption"></a>Felhasználási igénylés létrehozása

[!include [banner](../../includes/banner.md)]

Ez a témakor az igénylés létrehozásának folyamatát írja le. Megmutatja, hogy milyen különböző módokon tudja keresni a termékeket a beszerzési katalógusban, illetve hogyan tud hozzáadni egy olyan terméket, amely nem szerepel a katalógusban. Az eljárás megkezdése előtt rendelkeznie kell egy beszerzési irányelvvel, amelyet az igénylés alapértelmezett típusaként kell beállítania. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Az eljárás csak olyan felhasználói profil által hajtható végre, amely dolgozóként van beállítva. Ezt a feladatot általában egy alkalmazott végzi el. Az **Alkalmazott** által alkalmazott biztonsági szerepkör teszi lehetővé a feladatok elvégzését, vagy ha USMF-et használ, jelentkezzen be ezen a néven: **Alíz**.


## <a name="create-a-new-requisition"></a>Új igénylés létrehozása
1. Ugorjon a **Navigációs panel > Modulok >Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva pontra**.
2. Válassza az **Új** lehetőséget.
3. A **Név** mezőbe írja be az igénylés nevét.
4. Adja meg a dátumot az **Igényelt dátum** mezőben. Alapértelmezés szerint a kért dátumot és a könyvelési dátumot a rendszer a beszerzési igénylés soraiba másolja. A dátumok megváltoztathatók a sorok szintjén. A kért dátum a kért szállítási dátum.  
5. Adja meg a dátumot a **Könyvelés dátuma** mezőben. A könyvelési dátum a főkönyvbe felvett könyvelési bejegyzés rögzítéséhez használható, valamint annak ellenőrzéséhez, hogy rendelkezésre állnak-e a költségvetési alapok.  
6. Válassza ki az **OK** lehetőséget.
7. Az **Ok** mezőben válasszon ki egy opciót a legördülő menüben. A választott indok alapértelmezés szerint megjelenik a beszerzési igénylési sorokban, de a sor szintjén módosíthatja azt.  
8. Válasszon ki egy okot.
9. A **részletek** mezőben adja meg az igénylést leíró részleteket

## <a name="add-a-line-to-the-requisition"></a>Sor hozzáadása az igényléshez
1. Válassza a **Sor hozzáadása** lehetőséget. A sorok hozzáadásának a beszerzési igényléshez két módja van. Ha a termékszámot ismeri, vagy már tudja, hogy olyan terméket kér, amely nem szerepel a termékkatalógusban, hozzáadhatja a sort közvetlenül a **Sor hozzáadása** paranccsal. A másik lehetőség a **Termékek hozzáadása** lehetőség, amellyel a keresést és a szűrést is használhatja a termékkatalógusban szereplő cikkek kereséséhez.    
2. Jelölje ki az előbb létrehozott sort.
    - A kérelmező az a dolgozó, aki az igénylést kérte.   
    - Alapértelmezés szerint az igénylés előkészítését végző személy az a dolgozó, aki azt kérte. Jogosultsággal kell rendelkeznie ahhoz, ha egy másik dolgozó nevében Igényléssort szeretne készíteni. Ha ilyen engedélyek birtokában van, a többi dolgozó megjelenik a keresésben.  
3. A **Cikkszám** mezőbe írjon egy értéket. A választható elemek korlátozva vannak a kategória-hozzáférési irányelv alapján, illetve a vásárló jogi személybeszerzési katalógusa alapján.   
4. Adjon meg egy számot a **Mennyiség** mezőben.

## <a name="add-more-products-to-the-requisition"></a>További termékek felvétele az igényléshez
1. Válassza a **Termékek hozzáadása** lehetőséget. Ezzel a beállítással kereshet a termékkatalógusban szereplő termékek között.    
2. A **Beszerzési kategória csomópontjának keresése** mezőjébe írja be a keresett kategória nevének első részét, és kattintson az **Enter** billentyűre. Például írja be, hogy `comput`.  
3. Használja az **InvokeDefaultButton** billentyűparancsot.
4. A választott kategóriában használja a **Szűrés** lehetőséget a termékek listájának szűréséhez.
5. Válassza ki azt a termékkártyát, amelyet hozzá szeretné adni az igényléshez.
6. Válassza a **Hozzáadás a sorokhoz** lehetőséget.
7. Adjon meg egy számot a **Mennyiség** mezőben.
8. A **Beszerzési kategória csomópontjának keresése** mezőjébe gépelje be a keresett kategória nevének első részét, és kattintson az **Enter** billentyűre. Ennél a példánál adja meg a `High` (kiemelők) nevet.  
9. Használja az **InvokeDefaultButton** billentyűparancsot.
10. Kattintson a **Fel nem sorolt termék hozzáadása a sorokhoz** elemre, ha olyan terméket szeretne hozzáadni, amely nem szerepel a beszerzési katalógusban.
11. Írjon be egy értéket a **Terméknév** mezőbe.
12. Írjon be egy értéket a **Mértékegység** mezőbe.
13. Válassza ki az **OK** lehetőséget.
14. A **Cikk leírása** mezőbe írja be a termék leírását.
15. Adjon meg egy számot a **Mennyiség** mezőben.
16. Adjon meg egy számot az **Egységár** mezőben. Ha tudja az adott szállító árát (amit a szállítói számla mezőben választott ki), akkor ezt az árat is megadhatja.   
17. A **Szállítói számla** mezőben nyissa meg e legördülő listát egy lehetőség kiválasztásához. Az ebben a mezőben rendelkezésre álló szállítók a beszerzési irányelvektől és attól az állapottól függnek, amellyel a szállító rendelkezik az aktuális beszerzési kategóriára vonatkozóan. Ahelyett, hogy itt kiválasztja a szállítót, rákattinthat a **Szállítói javaslat** gombra is.    
18. A listából válassza ki a használni kívánt szállítót.
19. A **Külső cikkszám** mezőbe írjon egy értéket. Ez annak a terméknek a hivatkozási száma, amelyet a szállító által ismer. Ez lehet például lehet a szállító saját katalógusban szereplő termék cikkszáma.  
20. Válassza ki az **OK** lehetőséget.

## <a name="distribute-amounts"></a>Összegek felosztása
1. Válassza a **Pénzügy** lehetőséget.
2. Válassza a **Felosztott összegek** lehetőséget. Ez a folyamat bemutatja, hogyan tudja az első sor költségét 2 számla között felosztani. Ezt később is megteheti, az igénylés ellenőrzésekor.  
3. Ha új elosztási sort szeretne létrehozni, Kattintson a **Szétválasztás** elemre.
4. A **Főkönyvi számla** mezőben válassza ki azt az első költséghelyet, amelyet a költség részévé akar tenni.
5. Válassza ki a másik felosztási sort.
6. A Főkönyvi számla mezőben adja meg a költséghelyet.
7. Válassza az **Egyenlő kiosztás** lehetőséget.
8. Zárja be a lapot.

## <a name="view-line-details"></a>A sor részleteinek megjelenítése
1. Bontsa ki a **Sorok részletei** részt.

## <a name="submit-the-requisition"></a>Az igénylés elküldése
1. A **Munkafolyamat** gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Válassza a **Beküldés** lehetőséget.
3. Zárja be a lapot.
4. A **Megjegyzés** mezőbe írjon be egy megjegyzést az igénylés jóváhagyójának.
5. Válassza a **Beküldés** lehetőséget.
6. Zárja be a lapot.
7. Frissítse a lapot..

