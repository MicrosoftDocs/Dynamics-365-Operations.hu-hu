--- 
title: "Konfigurációk tervezése a bejövő dokumentumok elemzéséhez az alkalmazásadat-frissítések céljából (ER)"
description: "Ez az eljárás egy bejövő elektronikus dokumentumot elemző elektronikus jelentési (ER) konfigurációk megtervezését mutatja be."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: 96c9397c6a83d61b679492f66f4aa6661f1f8621
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="design-configurations-to-parse-incoming-documents-for-application-data-updates-er"></a>Konfigurációk tervezése a bejövő dokumentumok elemzéséhez az alkalmazásadat-frissítések céljából (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás egy bejövő elektronikus dokumentumot elemző elektronikus jelentési (ER) konfigurációk megtervezését mutatja be. Ebben az eljárásban egy módosított Excel-sablont importálunk az ER-formátum konfigurációkba, amelyeket a Litware, Inc. mintavállalathoz hoztak létre, és ezután elvégezzük az elektronikus dokumentumok elemzését. A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. 

Ezek a lépések bármely adathalmazzal végrehajthatók. Mielőtt elkezdené, töltse le és mentse a „Bejövő dokumentumok elemzése az alkalmazásadatok módosításához” súgótémakörben felsorolt fájlokat (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents). A fájlok a következők: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
    * A következő forgatókönyv használandó az XML-formátumú bejövő elektronikus dokumentumok jellemzői elemzésének megjelenítésére: az ERP alkalmazás (Dynamics 365 for Finance and Operations) adatokat kér a webszolgáltatástól (például http://efsta.org/ EFSTA pénzügyi szolgáltatás), és ennek megfelelően elemzi a válaszokat az alkalmazásadatok frissítése érdekében. A leghatékonyabb elemzési mód érdekében egyetlen ER formátum használatos annak ellenére, hogy a várt beérkező dokumentumok XML formátuma különböző szerkezetű.   

## <a name="import-and-review-er-configurations"></a>ER-konfigurációk importálása és ellenőrzése
Importálja azt az ER modellkonfigurációt, amely tartalmazza a beérkező fájl részleteinek tárolására szolgáló minta adatmodellt.  
1. Kattintson az Átváltás lehetőségre.
2. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Kattintson a Tallózás gombra, és válassza ki az EFSTA modell.xml fájlt.  
3. Kattintson az OK gombra.
4. A fastruktúrában válassza ki az „EFSTA modell” lehetőséget.
5. Kattintson a Tervező pontra.
    * Tekintse át az importált adatmodell struktúráját. Vegye figyelembe, hogy az enumType felsorolás meghatározása a következő szolgáltatási választípusok felismerésére szolgál: visszaigazolás a tranzakció benyújtására vonatkozóan, az utolsó benyújtott tranzakcióval kapcsolatos adatok beolvasása, valamint a nem támogatott választípusok felismerése.   
6. A fastruktúrában bontsa ki ezt: Válasz.
    * Vegye figyelembe, hogy a Válasz gyökérelem meghatározása arra szolgál, hogy milyen adatokat kell kiemelni egy támogatott szolgáltatási válaszból az alkalmazásadatok megfelelő frissítése érdekében.   
7. Zárja be a lapot.
    * Azt az ER-formátumkonfigurációt kell importálni, amely megadja a bejövő dokumentumok elemzési módját az adatok ER adatmodellben történő tárolásához.   
8. Kattintson az Átváltás lehetőségre.
9. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Kattintson a Tallózás gombra, és válassza ki az EFSTA format.xml fájlt.  
10. Kattintson az OK gombra.
11. A fastruktúrában bontsa ki az „EFSTA modell” lehetőséget.
12. A fastruktúrában válassza ki az „EFSTA modell\EFSTA formátum” lehetőséget.
13. Kattintson a Tervező pontra.
14. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
    * Ne feledje, hogy az ESET formátumelem lesz a gyökérszint, és három beágyazott FÁJL elemet tartalmaz, ami azt jelenti, hogy ez a formátum elemzi a különböző formátumú bejövő fájlokat.  
15. A fán jelölje be a „Válaszok\Tranzakció befejezése\TraC” lehetőséget.
    * Ne feledje, hogy az elküldött tranzakcióra vonatkozó válasz a TraC gyökérelemtől indul.   
16. A fán jelölje be a „Válaszok\Legutóbbi tranzakciós kérelem\Tra” lehetőséget.
    * Ne feledje, hogy a legutóbb elküldött tranzakcióra vonatkozó válasz a Tra gyökérelemtől indul.   
17. A fán válassza a „Válaszok\Váratlan válasz\Szöveg” lehetőséget.
    * A rendszer egy harmadik, beágyazott SZÖVEG elemmel ellátott FÁJL elemet adott hozzá, hogy felismerje a fent említettől eltérő típusú válaszokat.   
18. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
    * Ez a modell-leképezés tartalmazza az adatáramlás meghatározását a bejövő elemzett dokumentum részleteinek az adatmodell cikkeinek használatával történő tárolása céljából.  
19. Kattintson a Tervező pontra.
20. A fastruktúrában bontsa ki ezt: „format”.
21. A fán bontsa ki a „Formátum\Válaszok: Eset(válaszok)” lehetőséget.
    * Tekintse át a „formátum” adatforrás struktúráját. Mindhárom választípus külön jelenik meg.   
22. A fán válassza ki a „formátum\Válaszok: Eset(válaszok)\aType” lehetőséget.
    * Az „aType” adatforráscikk hozzá van adva, jelezve a válasz típusát, és a „Típus” adatmodellcikkhez kapcsolódik.  
23. Kattintson az Ellenőrzések fülre.
24. A fán válassza ki a „Type = format.Responses.aType” lehetőséget.
    * Vegye figyelembe, hogy az ER-ellenőrzés úgy van konfigurálva, hogy tájékoztassa a felhasználót, ha a válasz struktúrája nem egyezik meg a tranzakció elküldéséről szóló megerősítéssel vagy a legutóbbi elküldött tranzakcióval kapcsolatos információval (nem támogatott válasz esete).   
25. Zárja be a lapot.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Bejövő fájlok elemzéséhez beállított ER-formátum modell leképezésének futtatása
A létrehozott modell-leképezést tesztelési célokból kell futtatni, hogy megtudhassa, hogyan elemzi a beérkező szolgáltatási válaszokat a konfigurált ER formátum. Ez a lépés különbüző XML-fájlokat használ a különböző típusú webszolgáltatási válaszok szimuláláshoz.   
1. Nyissa meg a Response1.xml fájlt egy XML-olvasóval, például a webböngészővel. Vegye figyelembe, hogy a fájl tartalmazza a befejezett tranzakcióra vonatkozó visszaigazolást (a „TraC” a gyökérelem).   
2. Kattintson a Futtatás elemre.
    * Kattintson a Tallózás gombra, és válassza ki a Response1.xml fájlt.  
3. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Látható, hogy a rendszer a választípust helyesen ismerte fel és elemezte (az ERModelEnumDataSourceHandler#EFSTA model#enumType#C jelentése, hogy a tranzakció befejeződött).   
    * Nyissa meg egy XML-olvasóval a Response2.xml fájlt. Vegye figyelembe, hogy a fájl tartalmazza a legutóbb elküldött tranzakcióra vonatkozó információkat (a „Tra” a gyökérelem).   
4. Kattintson a Futtatás elemre.
    * Kattintson a Tallózás gombra, és válassza ki a Response2.xml fájlt.  
5. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Látható, hogy a rendszer a választípust helyesen ismerte fel és elemezte (az ERModelEnumDataSourceHandler#EFSTA model#enumType#R jelentése, hogy a rendszer újraindul).   
    * Nyissa meg egy XML-olvasóval a Response3.xml fájlt. Ne feledje, hogy a fájl a TraZ gyökérelemből indul és hogy ez a szerkezet nem ER formátum használatával van konfigurálva.   
6. Kattintson a Futtatás elemre.
    * Kattintson a Tallózás gombra, és válassza ki a Response3.xml fájlt.  
7. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Látható, hogy a rendszer a választípust helyesen ismerte fel és nem támogatta (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). A megfelelő üzenet az információs naplóba került (az ER-ellenőrzési beállításnak megfelelően), és az adatmodell legnagyobb része nincs kitöltve.   
    * Nyissa meg egy XML-olvasóval a Response4.xml fájlt. Ne feledje, hogy a fájl felépítése szinte teljesen megegyezik a sikeresen elemzett Response1.xml fájllal, kivéve a „TraC” gyökérelem beágyazott elemeinek sorozatát.   
8. Kattintson a Futtatás elemre.
    * Kattintson a Tallózás gombra, és válassza ki a Response4.xml fájlt.  
9. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Látható, hogy a rendszer a választípust helyesen ismerte fel és nem támogatta (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)). A megfelelő üzenet az információs naplóba került, és az adatmodell legnagyobb része nincs kitöltve. Ennek oka az, hogy az ER-formátum aktuális beállítása a bejövő fájl gyökéreleme beágyazott elemeinek bizonyos sorozatát feltételezi.   
10. Zárja be a lapot.
11. A fán jelölje be a „Válaszok\Tranzakció befejezése\TraC” lehetőséget.
12. A Beágyazott elemek elemzési sorrendje mezőben válassza a Bármelyik lehetőséget.
    * A Beágyazott elemek elemzési sorrendje mezőben válassza a Bármelyik lehetőséget, engedélyezve a beágyazott elemek tetszőleges sorozatát a gyökérszintű XML elemhez.  
13. Kattintson a Mentés gombra.
14. Kattintson a Formátum hozzárendelése modellhez lehetőségre.
15. Kattintson a Futtatás elemre.
    * Kattintson a Tallózás gombra, és válassza ki a Response4.xml fájlt.  
16. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Vegye figyelembe, hogy a választípust a rendszer már megfelelően ismerte fel a Response1.xml fájllal egyenlőként.  


