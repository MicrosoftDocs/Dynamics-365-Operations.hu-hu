---
title: Konfigurációk importálása alkalmazásadatokkal rendelkező dokumentumok létrehozásához
description: 'Az eljárás lépéseit csak akkor lehet végrehajtani, ha előbb a következő eljárást kell végrehajtani: "ER Hozzon létre egy konfigurációs szolgáltatót, és jelölje meg aktívként".'
author: kfend
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccff17ad83b6840b5e8f327e24f8ac8a5e8ff620
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290574"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>Konfigurációk importálása alkalmazásadatokkal rendelkező dokumentumok létrehozásához

[!include [banner](../../includes/banner.md)]

A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését mutatják be. Ebben az eljárásban egy módosított Excel-sablont importálunk az ER-formátum konfigurációkba, amelyeket a Litware, Inc. mintavállalathoz hoztak létrehoz, és ezután elvégezzük az elektronikus dokumentumok létrehozását. Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a DEMF-adathalmazzal hajthatók végre. Mielőtt elkezdené, töltse le és mentse a súgócikkben felsorolt fájlokat: "Elektronikus dokumentumok létrehozása és alkalmazásadatok frissítése az ER-eszközzel" (generate-electronic-documents-update-application-data/). A fájlok a következők: Intrastat (model).xml, Intrastat (mapping).xml és Intrastat (format).xml.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
    * Az eljárás lépései azt mutatják be, hogyan használhatók az ER-funkciók alkalmazásadatok frissítésének végrehajtására, és hogyan hozható létre Intrastat-jelentés. A jelentési folyamat részleteinek archiválása az alkalmazástáblákban történik. Jelenleg, amikor aktiválják az Intrastat-jelentési folyamatot az Intrastat-űrlapról, az archiválás a meglévő forráskódba programozott logika alapján történik. Ebben az eljárásban az alkalmazásadatok hasonló, de egyszerűsített logikáját konfiguráljuk csak az ER-keretrendszer használatával. A forráskód nem módosul.   

## <a name="import-er-configurations"></a>ER-konfigurációk importálása
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
2. Kattintson az Átváltás lehetőségre.
3. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Importálja azt az ER-modellkonfigurációt, amelyt azt az adatmodellt tartalmazza, amelyet arra terveztek, hogy az Intrastat-jelentés létrehozásához adatforrásaként használják. Később ki fogja terjeszteni ezt az adatmodell-definíciót, hogy egy Intrastat jelentési folyamat részleteinek archiválására szolgáló alkalmazás-adatfrissítéshez használhassa.   
    * Kattintson a Tallózás gombra, és válassza ki az Intrastat (modell).xml fájlt.  
4. Kattintson az OK gombra.
5. A fastruktúrában válassza ki az „Instrastat (model)” elemet.
6. Kattintson a Tervező pontra.
7. A fastruktúrában bontsa ki ezt: „'For outgoing document”.
8. A fastruktúrában bontsa ki ezt: „'For outgoing document\Transactions”.
    * Tekintse át az importált adatmodell struktúráját. Vegye figyelembe, hogy a „Kimenő dokumentumhoz” gyökérelem meg van adva az alkalmazástól való adatlekéréshez tartozó adatáramlás megadásához, és az Intrastat-jelentés létrehozásához szükséges adatforrásként való használathoz. A „Tranzakciók (Rekordlista)” képviseli a kötelezően jelentendő Intrastat-tranzakciók listáját. Mivel jelentett vámtarifakódokat fog archiválni, egy adott vámtarifakód egyedi azonosítója – „Árucikk rekordazonosító (Int64)” – szükséges ebben az adatáramlásban.   
9. Zárja be a lapot.
10. Kattintson az Átváltás lehetőségre.
11. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Importálja az ER-hozzárendelési konfigurációt, amely megadja az adatfolyamot az adatok lekéréséhez az alkalmazástól, és ezután a felhasználáshoz az Intrastat-jelentés elkészítéséhez. Később ki fogja terjeszteni ezt a modellhozzárendelés-definíciót, hogy lekérhesse az adatokat egy Intrastat-jelentésből, és egy Intrastat jelentési folyamat részleteinek archiválására szolgáló alkalmazás-adatfrissítéshez használhassa.   
    * Kattintson a Tallózás gombra, és válassza ki az Intrastat (mapping).xml fájlt.  
12. Kattintson az OK gombra.
13. A fastruktúrában bontsa ki az „Instrastat (model)” elemet.
14. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (mapping)”.
15. Kattintson a Tervező pontra.
    * Megjegyzés: az Irány mezőben az aktuális modell-hozzárendelés a 'Modellhez' értéket tartalmazza. Ez azt jelenti, hogy ezt a modell-hozzárendelést az adatok beolvasására tervezték az alkalmazásból, és tárolásukhoz az adatmodellben.  
16. Kattintson a Tervező pontra.
17. A fastruktúrában bontsa ki ezt: „List”.
18. A fában bontsa ki a „Transactions= List” csomópontot.
    * Tekintse át a modell-hozzárendelés struktúráját, amely „A kimenő dokumentumok” gyökérelem alapján szűrt adatmodellt használja. Vegye figyelembe, hogy a hozzáadott „Lista” adatforrás nyújt hozzáférést a szükséges alkalmazásadatokhoz, amely az Intrastat-tábla rekordjainak listája.  
19. Zárja be a lapot.
20. Zárja be a lapot.
21. Kattintson az Átváltás lehetőségre.
22. Kattintson a Betöltés XML-fájlból lehetőségre.
    * Importálja az ER-formátumkonfigurációt, amely meghatározza az Intrastat-jelentés elrendezését, valamint az adatfeltöltés folyamatát a jelentésbe. Később ki fogja terjeszteni ezt a formátumdefiníciót, hogy az adatokat átmozgathassa az Intrastat-jelentésből az adatmodellbe, és az alkalmazás-adatfrissítéshez használhassa az Intrastat-jelentési folyamat részleteinek archiválásához.   
    * Kattintson a Tallózás gombra, és válassza ki az Intrastat (format).xml fájlt.  
23. Kattintson az OK gombra.
24. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (format)”.
25. Kattintson a Tervező pontra.
26. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
27. A fában válassza ki ezt: „File\Declaration”.
28. Kattintson a Hozzárendelés fülre.
29. A fastruktúrában válassza ki ezt: „File”.
    * Tekintse át az Intrastat-jelentés elkészítéséhez használt formátum szerkezetét. Megjegyzés: úgy van tervezve, hogy létrehozzon egy XML-fájlt az adatok feltöltésével az adatmodellből, amelynek az alapja „A kimenő dokumentumok” gyökérelem. Győződjön meg arról, hogy a létrehozott fájl neve meg van-e adva a felhasználói párbeszédpanel űrlapon (erre az „fn” adatforrás szolgál).   
30. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
