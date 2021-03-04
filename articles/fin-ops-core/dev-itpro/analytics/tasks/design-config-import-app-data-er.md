---
title: ER-konfigurációk tervezése bejövő dokumentumok elemzésére
description: Ez az eljárás egy bejövő elektronikus dokumentumot elemző elektronikus jelentési (ER) konfigurációk megtervezését mutatja be.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 446a4676ad00c93d691d3048408c32d7ad373d2d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682093"
---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>ER-konfigurációk tervezése bejövő dokumentumok elemzésére

[!include [banner](../../includes/banner.md)]

Ez az eljárás egy bejövő elektronikus dokumentumot elemző elektronikus jelentési (ER) konfigurációk megtervezését mutatja be. Ebben az eljárásban egy módosított Excel-sablont importálunk az ER-formátum konfigurációkba, amelyeket a Litware, Inc. mintavállalathoz hoztak létre, és ezután elvégezzük az elektronikus dokumentumok elemzését. A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.

Ezek a lépések bármely adathalmazzal végrehajthatók. Mielőtt hozzákezdene, töltse le és mentse a „Bejövő dokumentumok elemzése az alkalmazásadatok frissítéséhez” témakörben tárgyalt fájlokat ([Bejövő dokumentumok elemzése](../parse-incoming-electronic-documents.md)). A fájlok a következők: EFSTA model.xml, EFSTA format.xml, Response1.xml, Response2.xml, Response3.xml, Response4.xml.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.
2. Válassza a Jelentéskészítési konfigurációk elemet.
    * A következő forgatókönyv használandó az XML-formátumú bejövő elektronikus dokumentumok jellemzői elemzésének megjelenítésére: az ERP alkalmazás () adatokat kér a webszolgáltatástól (például [eftsa](http://efsta.org/) pénzügyi szolgáltatás), és ennek megfelelően elemzi a válaszokat az alkalmazásadatok frissítése érdekében. A leghatékonyabb elemzési mód érdekében egyetlen ER formátum használatos annak ellenére, hogy a várt beérkező dokumentumok XML formátuma különböző szerkezetű.

## <a name="import-and-review-er-configurations"></a>ER-konfigurációk importálása és ellenőrzése

Importálja azt az ER modellkonfigurációt, amely tartalmazza a beérkező fájl részleteinek tárolására szolgáló minta adatmodellt.

1. Árfolyam kijelölése.
2. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Válassza a Tallózás gombot, és válassza ki az EFSTA modell.xml fájlt.
3. Válassza ki az OK lehetőséget.
4. A fastruktúrában válassza ki az „EFSTA modell” lehetőséget.
5. Válassza a Tervező lehetőséget.
    * Tekintse át az importált adatmodell struktúráját. Vegye figyelembe, hogy az enumType felsorolás meghatározása a következő szolgáltatási választípusok felismerésére szolgál: visszaigazolás a tranzakció benyújtására vonatkozóan, az utolsó benyújtott tranzakcióval kapcsolatos adatok beolvasása, valamint a nem támogatott választípusok felismerése.
6. A fastruktúrában bontsa ki ezt: Válasz.
    * A „Válasz” gyökérelem meghatározása arra szolgál, hogy milyen adatokat kell kiemelni egy támogatott szolgáltatási válaszból az alkalmazásadatok megfelelő frissítése érdekében.
7. Zárja be a lapot.
    * Azt az ER-formátumkonfigurációt kell importálni, amely megadja a bejövő dokumentumok elemzési módját az adatok ER adatmodellben történő tárolásához.
8. Árfolyam kijelölése.
9. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Válassza a Tallózás gombot, és válassza ki az EFSTA format.xml fájlt.
10. Válassza ki az OK lehetőséget.
11. A fastruktúrában bontsa ki az „EFSTA modell” lehetőséget.
12. A fastruktúrában válassza ki az „EFSTA modell\EFSTA formátum” lehetőséget.
13. Válassza a Tervező lehetőséget.
14. Válassza a Kibontás/összecsukás lehetőséget.
    * Az ESET formátumelem lesz a gyökérszint, és három beágyazott FÁJL elemet tartalmaz, ami azt jelenti, hogy ez a formátum elemzi a különböző formátumú bejövő fájlokat.
15. A fán jelölje be a „Válaszok\Tranzakció befejezése\TraC” lehetőséget.
    * Az elküldött tranzakcióra vonatkozó válasz a „TraC” gyökérelemtől indul.
16. A fán jelölje be a „Válaszok\Legutóbbi tranzakciós kérelem\Tra” lehetőséget.
    * Az elküldött tranzakcióra vonatkozó válasz a „Era” gyökérelemtől indul.
17. A fán válassza a „Válaszok\Váratlan válasz\Szöveg” lehetőséget.
    * A rendszer egy harmadik, beágyazott SZÖVEG elemmel ellátott FÁJL elemet adott hozzá, hogy felismerje a fent említettől eltérő típusú válaszokat.
18. Válassza Formátum hozzárendelése modellhez lehetőséget.
    * Ez a modell-leképezés tartalmazza az adatáramlás meghatározását a bejövő elemzett dokumentum részleteinek az adatmodell cikkeinek használatával történő tárolása céljából.
19. Válassza a Tervező lehetőséget.
20. A fastruktúrában bontsa ki ezt: „format”.
21. A fán bontsa ki a „Formátum\Válaszok: Eset(válaszok)” lehetőséget.
    * Tekintse át a „formátum” adatforrás struktúráját. Mindhárom választípus külön jelenik meg.
22. A fán válassza ki a „formátum\Válaszok: Eset(válaszok)\aType” lehetőséget.
    * Az „aType” adatforráscikk hozzá van adva, jelezve a válasz típusát, és a „Típus” adatmodellcikkhez kapcsolódik.
23. Válassza az Ellenőrzések fület.
24. A fán válassza ki a „Type = format.Responses.aType” lehetőséget.
    * Az ER-ellenőrzés úgy van konfigurálva, hogy tájékoztassa a felhasználót, ha a válasz struktúrája nem egyezik meg a tranzakció elküldéséről szóló megerősítéssel vagy a legutóbbi elküldött tranzakcióval kapcsolatos információval (nem támogatott válasz esete).
25. Zárja be a lapot.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>Bejövő fájlok elemzéséhez beállított ER-formátum modell leképezésének futtatása

A létrehozott modell-leképezést tesztelési célokból kell futtatni, hogy megtudhassa, hogyan elemzi a beérkező szolgáltatási válaszokat a konfigurált ER formátum. Ez a lépés különbüző XML-fájlokat használ a különböző típusú webszolgáltatási válaszok szimuláláshoz.

1. Nyissa meg a Response1.xml fájlt egy XML-olvasóval, például a webböngészővel. Ez a fájl tartalmazza a befejezett tranzakcióra vonatkozó visszaigazolást (a „TraC” a gyökérelem).
2. Válassza a Futtatás parancsot.
    * Válassza a Tallózás gombot, és válassza ki a Response1.xml fájlt.
3. Válassza ki az OK lehetőséget.
    * Tekintse át a létrehozott kimenetet. A választípus helyesen lett felismerve és elemezve (`ERModelEnumDataSourceHandler#EFSTA model#enumType#C` tranzakció-befejezve esetet jelent).
    * Nyissa meg egy XML-olvasóval a Response2.xml fájlt. Ez a fájl tartalmazza a legutóbb elküldött tranzakcióra vonatkozó információkat (a „`Tra`” a gyökérelem).
4. Válassza a Futtatás parancsot.
    * Válassza a Tallózás gombot, és válassza ki a Response2.xml fájlt.
5. Válassza ki az OK lehetőséget.
    * Tekintse át a létrehozott kimenetet. A választípus helyesen lett felismerve és elemezve (`ERModelEnumDataSourceHandler#EFSTA model#enumType#R` rendszer újraindítás esetet jelent).
    * Nyissa meg egy XML-olvasóval a Response3.xml fájlt. Ez a fájl a TraZ gyökérelemből indul és hogy ez a szerkezet nem ER formátum használatával van konfigurálva.
6. Válassza a Futtatás parancsot.
    * Válassza a Tallózás gombot, és válassza ki a Response3.xml fájlt.
7. Válassza ki az OK lehetőséget.
    * Tekintse át a létrehozott kimenetet. A választípus t helyesen nem támogatottként lett felismerve (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`). A megfelelő üzenet az információs naplóba került (az ER-ellenőrzési beállításnak megfelelően), és az adatmodell legnagyobb része nincs kitöltve.
    * Nyissa meg egy XML-olvasóval a Response4.xml fájlt. A fájl felépítése szinte teljesen megegyezik a sikeresen elemzett Response1.xml fájllal, kivéve a „TraC” gyökérelem beágyazott elemeinek sorozatát.
8. Válassza a Futtatás parancsot.
    * Válassza a Tallózás gombot, és válassza ki a Response4.xml fájlt.
9. Válassza ki az OK lehetőséget.
    * Tekintse át a létrehozott kimenetet. A választípus t helyesen nem támogatottként lett felismerve (`ERModelEnumDataSourceHandler#EFSTA model#enumType#U`)). A megfelelő üzenet az információs naplóba került, és az adatmodell legnagyobb része nincs kitöltve. Ennek a viselkedésnek az oka az, hogy az ER-formátum aktuális beállítása a bejövő fájl gyökéreleme beágyazott elemeinek bizonyos sorozatát feltételezi.
10. Zárja be a lapot.
11. A fán jelölje be a „Válaszok\Tranzakció befejezése\TraC” lehetőséget.
12. A Beágyazott elemek elemzési sorrendje mezőben válassza a Bármelyik lehetőséget.
    * A „Beágyazott elemek elemzési sorrendje” mezőben válassza a Bármelyik lehetőséget, engedélyezve a beágyazott elemek tetszőleges sorozatát a gyökérszintű XML elemhez.
13. Válassza a Mentés lehetőséget.
14. Válassza Formátum hozzárendelése modellhez lehetőséget.
15. Válassza a Futtatás parancsot.
    * Válassza a Tallózás gombot, és válassza ki a Response4.xml fájlt.
16. Válassza ki az OK lehetőséget.
    * Tekintse át a létrehozott kimenetet. A választípust a rendszer már megfelelően ismerte fel a Response1.xml fájllal egyenlőként.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]