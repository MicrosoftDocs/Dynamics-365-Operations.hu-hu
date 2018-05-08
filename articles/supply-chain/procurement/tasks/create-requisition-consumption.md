--- 
title: "Felhasználási igénylés létrehozása"
description: "Ez az eljárás bemutatja az igénylések létrehozásának a folyamatát."
author: mkirknel
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7d8ca4e7eedea140f32e264c205b243027a06d03
ms.openlocfilehash: d1ea95d0bc283297fcedaee730e1829850f07998
ms.contentlocale: hu-hu
ms.lasthandoff: 11/20/2017

---
# <a name="create-a-requisition-for-consumption"></a>Felhasználási igénylés létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az igénylések létrehozásának a folyamatát. Megmutatja, hogy milyen különböző módokon tudja keresni a termékeket a beszerzési katalógusban, illetve hogyan tud hozzáadni egy olyan terméket, amely nem szerepel a katalógusban. Az eljárás megkezdése előtt rendelkeznie kell egy beszerzési irányelvvel, amelyet az igénylés alapértelmezett típusaként kell beállítania. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. Az eljárás csak olyan felhasználói profil által hajtható végre, amely dolgozóként van beállítva.  Ezt a feladatot általában egy alkalmazott végzi el. Az alkalmazott által alkalmazott biztonsági szerepkör teszi lehetővé a feladatok elvégzését, vagy ha USMF-et használ, jelentkezzen be ezen a néven: Alíz.


## <a name="create-a-new-requisition"></a>Új igénylés létrehozása
1. Ugrás a Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva elemre.
2. Kattintson az Új lehetőségre.
3. A Név mezőbe írja be az igénylés nevét.
4. Adja meg a dátumot az Igényelt dátum mezőben.
    * Alapértelmezés szerint a kért dátumot és a könyvelési dátumot a rendszer a beszerzési igénylés soraiba másolja. A dátumok megváltoztathatók a sorok szintjén. A kért dátum a kért szállítási dátum.  
5. Adja meg a dátumot a Könyvelés dátuma mezőben.
    * A könyvelési dátum a főkönyvbe felvett könyvelési bejegyzés rögzítéséhez használható, valamint annak ellenőrzéséhez, hogy rendelkezésre állnak-e a költségvetési alapok.  
6. Kattintson az OK gombra.
7. Az Ok mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * A választott indok alapértelmezés szerint megjelenik a beszerzési igénylési sorokban, de a sor szintjén módosíthatja azt.    
8. Keresse meg és jelölje ki a kívánt rekordot a listán.
9. Válasszon ki egy okot
10. A részletek mezőben adja meg az igénylést leíró részleteket

## <a name="add-a-line-to-the-requisition"></a>Sor hozzáadása az igényléshez
1. Kattintson az Új sor hozzáadása lehetőségre.
    * A sorok hozzáadásának a beszerzési igényléshez két módja van. Ha a termékszámot ismeri, vagy már tudja, hogy olyan terméket kér, amely nem szerepel a termékkatalógusban, hozzáadhatja a sort közvetlenül a „Sor hozzáadása” paranccsal. A másik lehetőség a „Termékek hozzáadása” lehetőség, amellyel a keresést és a szűrést is használhatja a termékkatalógusban szereplő cikkek kereséséhez.    
2. Kattintson a most létrehozott sorra.
    * A kérelmező az a dolgozó, aki az igénylést kérte.   
    * Alapértelmezés szerint az igénylés előkészítését végző személy az a dolgozó, aki azt kérte. Jogosultsággal kell rendelkeznie ahhoz, ha egy másik dolgozó nevében Igényléssort szeretne készíteni. Ha ilyen engedélyek birtokában van, a többi dolgozó megjelenik a keresésben.  
3. A cikkmezőbe írjon egy értéket.
    * A választható elemek korlátozva vannak a kategória-hozzáférési irányelv alapján, illetve a vásárló jogi személybeszerzési katalógusa alapján.   
4. Adjon meg egy számot a Mennyiség mezőben.

## <a name="add-more-products-to-the-requisition"></a>További termékek felvétele az igényléshez
1. Kattintson a Termékek hozzáadása elemre.
    * Ezzel a beállítással kereshet a termékkatalógusban szereplő termékek között.    
2. A beszerzési kategória csomópontjának keresése mezőjébe írja be a keresett kategória nevének első részét, és kattintson az Enter billentyűre.
    * Például írja be a comput szöveget.  
3. Használja az InvokeDefaultButton billentyűparancsot.
4. A választott kategóriában használja a Szűrés lehetőséget a termékek listájának szűréséhez.
5. Válassza ki azt a termékkártyát, amelyet hozzá szeretné adni az igényléshez.
6. Kattintson a Hozzáadás a sorokhoz elemre.
7. Adjon meg egy számot a Mennyiség mezőben.
8. A beszerzési kategória csomópontjának keresése mezőjébe írja be a keresett kategória nevének első részét, és kattintson az Enter billentyűre.
    * Írja be például a High (kiemelők) szöveget.  
9. Használja az InvokeDefaultButton billentyűparancsot.
10. Kattintson a Fel nem sorolt termék hozzáadása a sorokhoz elemre, ha olyan terméket szeretne hozzáadni, amely nem szerepel a beszerzési katalógusban.
11. Írjon be egy értéket a Terméknév mezőbe.
12. Írjon be egy értéket a Mértékegység mezőbe.
13. Kattintson az OK gombra.
14. A Cikk leírása mezőbe írja be a termék leírását.
15. Adjon meg egy számot a Mennyiség mezőben.
16. Adjon meg egy számot az Egységár mezőben.
    * Ha tudja az adott szállító árát (amit a szállítói számla mezőben választott ki), akkor ezt az árat is megadhatja   
17. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az ebben a mezőben rendelkezésre álló szállítók a beszerzési irányelvektől és attól az állapottól függnek, amellyel a szállító rendelkezik az aktuális beszerzési kategóriára vonatkozóan. Ahelyett, hogy itt kiválasztja a szállítót, rákattinthat a Szállítói javaslat gombra is.    
18. A listából válassza ki a használni kívánt szállítót.
19. A Külső cikkszám mezőbe írjon egy értéket.
    * Ez annak a terméknek a hivatkozási száma, amelyet a szállító által ismer. Ez lehet például lehet a szállító saját katalógusban szereplő termék cikkszáma.  
20. Kattintson az OK gombra.

## <a name="distribute-amounts"></a>Összegek felosztása
1. Kattintson a Pénzügyre.
2. Kattintson az Összegek felosztása elemre.
    * Ez a folyamat bemutatja, hogyan tudja az első sor költségét 2 számla között felosztani. Ezt később is megteheti, az igénylés ellenőrzésekor.  
3. Ha új elosztási sort szeretne létrehozni, Kattintson a Szétválasztás elemre.
4. A Főkönyvi számla mezőben válassza ki azt az első költséghelyet, amelyet a költség részévé akar tenni.
5. Válassza ki a másik felosztási sort.
6. A Főkönyvi számla mezőben adja meg a költséghelyet.
7. Kattintson az Egyenlő kiosztás elemre.
8. Zárja be a lapot.

## <a name="view-line-details"></a>A sor részleteinek megjelenítése
1. Bontsa ki a Sorok részletei részt.

## <a name="submit-the-requisition"></a>Az igénylés elküldése
1. A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Kattintson a Küldés hivatkozásra.
3. Zárja be a lapot.
4. A Megjegyzés mezőbe írjon be egy megjegyzést az igénylés jóváhagyójának.
5. Kattintson a Küldés hivatkozásra.
6. Zárja be a lapot.
7. Frissítse a lapot..


