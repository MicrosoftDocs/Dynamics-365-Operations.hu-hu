---
title: Modellek és leképezések módosítása dokumentumoknak alkalmazásadatokkal történő létrehozásához
description: Ez a témakör egy elektronikus dokumentumot létrehozó és alkalmazásadatokat frissítő jelentéskészítési konfigurációk megtervezését mutatja be. (2. rész – Dokumentumok létrehozása).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d7df46bab244d11509b86a27eeed3c2725400b5eb4d0fbf50af1750e7de45d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745888"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Modellek és leképezések módosítása dokumentumoknak alkalmazásadatokkal történő létrehozásához

[!include [banner](../../includes/banner.md)]

Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (2. rész: Dokumentumok létrehozása)” eljárást. 

Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be. Ebben az eljárásban módosítjuk az ER-konfigurációkat, hogy használatba vehessük őket az elektronikus dokumentumok létrehozásához és az alkalmazásadatok frissítéséhez. Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a DEMF-adathalmazzal hajthatók végre.


## <a name="modify-data-model"></a>Az adatmodell módosítása
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza ki az „Instrastat (model)” elemet.
    * Az adatmodell használatát ki fogja terjeszteni. Amellett, hogy adatforrásként használjuk az Intrastat-jelentés létrehozásához, az adatmodellt használjuk az Intrastat-jelentési folyamat adatainak összegyűjtésére. Az adatokat ezután az alkalmazásadatok frissítéséhez használjuk.   
3. Kattintson a Tervező pontra.
4. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
5. Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.
6. A Név mezőbe írja be a következőt: 'Alkalmazásadatok módosításához'.
    * Alkalmazásadatok módosításához  
7. Kattintson a Hozzáadás gombra.
8. A fában válassza ki ezt: „For application data update”.
    * Ezt az új gyökérelemet azért adjuk hozzá, hogy meghatározza az adatáramlást az adatok mozgatásához az Intrastat-jelentésből (adatforrásként használt) az alkalmazástáblákba (frissítési cél). Ne feledje, hogy különböző gyökérelemeket kell használni a kimenő dokumentumba feladott adatok beolvasásához, valamint az adatok beolvasásához abból a dokumentumból, amely az alkalmazásadatok frissítésére szolgál.   
9. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
10. A Név mezőbe írja be az „Archive header” szöveget.
    * Archívumfejléc  
11. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
12. Kattintson a Hozzáadás gombra.
    * Mivel minden egyes létrehozott Intrastat-jelentéshez létrehoz egy rekordot, ehhez létre kell hozni egy új elemet.  
13. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
14. A Név mezőbe írja be a következőt: „Fájlnév”.
    * Fájlnév  
15. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
16. Kattintson a Hozzáadás gombra.
17. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
18. A Név mezőbe írja be a „Sorok száma” szöveget.
    * Sorok száma  
19. A Cikktípus mezőben válassza ki az „Integer” lehetőséget.
20. Kattintson a Hozzáadás gombra.
    * Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók számát jelöli.  
21. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
22. A Név mezőbe írja be a „Archív sorok” szöveget.
    * Archívum sorai  
23. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
24. Kattintson a Hozzáadás gombra.
    * Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók listáját jelöli.  
25. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
26. A Név mezőbe írja be az 'Amount' szöveget.
    * Összeg  
27. A Cikktípus mezőben válassza ki a „Valós” lehetőséget.
28. Kattintson a Hozzáadás gombra.
29. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
30. A Név mezőben írja be az „Árucikk rekordazonosító” szöveget.
    * Árucikk rekordazonosító  
31. A Cikktípus mezőben válassza ki az „Int64” lehetőséget.
32. Kattintson a Hozzáadás gombra.
33. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
34. A Név mezőbe írja be a „Cikkszám” szöveget.
    * Cikkszám  
35. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
36. Kattintson a Hozzáadás gombra.
37. Kattintson a Mentés gombra.
38. Zárja be a lapot.

## <a name="modify-model-mapping"></a>A modell-hozzárendelés módosítása
1. A fastruktúrában bontsa ki az „Instrastat (model)” elemet.
2. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (mapping)”.
    * Módosítsa a meglévő modell-hozzárendelést a használatba vételéhez az alkalmazásadatok frissítésére és az Intrastat-jelentés részleteinek archiválásához.  
3. Kattintson a Tervező pontra.
4. Kattintson az Új lehetőségre.
5. A Név mezőbe írja be a „Archívum frissítése” szöveget.
    * Archívum frissítése  
6. Az Irány mezőben válassza a „Célhoz” lehetőséget.
7. Kattintson a Mentés gombra.
    * Ezt az új hozzárendelés meghatározza az adatáramlást az adatok (Intrastat-jelentés részletei) mozgatásához az adatforrásból az alkalmazástáblákba (frissítési cél). Vegye figyelembe, hogy különböző gyökérelemeket kell használni az adatok beolvasásához az alkalmazásból a jelentési folyamathoz, és ezután az adatmodellből származó adatok használatához az alkalmazásadatok frissítésére.   
8. Kattintson a Tervező pontra.
9. A fastruktúrában válassza ki az „Data model\Data model” lehetőséget.
    * Adja meg a kötelező adatforrást. Ez az adatmodell tartalmazza a jelentett Intrastat-tranzakciók részleteit, amelyeket archiválni kell.  
10. Kattintson a Gyökér hozzáadása gombra.
11. A Név mezőbe írja be ezt: 'model'.
    * modell  
12. A Definíció mezőben adja meg vagy válassza ki az „Alkalmazásadatok frissítéséhez” értékét.
    * Alkalmazásadatok módosításához  
13. Kattintson az OK gombra.
14. A fában bontsa ki a „model” elemet.
15. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
16. A fában válassza ki a „model\Archive header” lehetőséget.
17. Kattintson a Hozzáadás gombra.
    * Mivel fel kell sorolni a jelentett Intrastat-tranzakciókat archiválás céljából, hozzá kell adni a megfelelő adatforrást.  
18. A Név mezőbe írja be a „Felsorolt sorok” szöveget.
    * Felsorolt sorok  
19. Kattintson a Receptúra szerkesztése lehetőségre.
20. A fastruktúrában válassza ki a következőt: „List\ENUMERATE”.
21. Kattintson a Függvény hozzáadása gombra.
22. A fában bontsa ki a „model” elemet.
23. A fában bontsa ki a „model\Archive header” lehetőséget.
24. A fában válassza ki a „model\Archive header\Archive lines” lehetőséget.
25. Kattintson az Adatforrás hozzáadása pontra.
26. A Képlet mezőben adja meg a következőt: 'ENUMERATE(model.'Archive header'.'Archive lines')'.
    * ENUMERATE(model.'Archive header'.'Archive lines')  
27. Kattintson a Mentés gombra.
28. Zárja be a lapot.
29. Kattintson az OK gombra.
30. Kattintson a Cél hozzáadása lehetőségre.
    * Alkalmazástáblák hozzáadása szükséges célként, amely megköveteli a frissítéseket a jelentett Intrastat-tranzakciók archiválásához.  
31. A Név mezőbe írja be a következőt: 'Archiváló'.
    * Archiválás  
32. A Tábla neve mezőbe írja be ezt: 'IntrastatArchiveGeneral'.
    * IntrastatArchiveGeneral  
    * Tartsa meg a „Beszúrás” rekordműveletet, hogy minden egyes Intrastat-jelentési folyamat részletes archiválásakor rekordokat tudjon hozzáadni.  
33. Válassza az Igen lehetőséget a Rekordinformációs napló mezőben.
    * Válassza az Igen lehetőséget az alkalmazásadatok frissítésével kapcsolatos problémákra vonatkozó információk lekéréséhez.  
34. A Rekordművelet ellenőrzésének kihagyása mezőben válassza az Igen beállítást.
    * Válassza az Igen lehetőséget az üres „Intrastat archívum azonosítója” mezőre vonatkozó ellenőrzési hibák figyelmen kívül hagyásához. Ez a rekordok hozzáadását követően történik meg, a táblához a Külkereskedelmi paraméterek űrlapon beállított számsorozat-beállítások alapján.  
35. Kattintson az OK gombra.
    * A hozzáadott adatforrás (a szűrt modell a kijelölt gyökérelem alapján) elemeit kösse össze a hozzáadott cél elemeivel.  
36. A fastruktúrában bontsa ki ezt: „Archive”.
37. A fában bontsa ki az „Archive\<Relations” elemet.
38. A fastruktúrában bontsa ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail”.
39. A fában jelölje ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail\Amount(AmountMST)”.
40. A fában bontsa ki ezt: „model\Archive header\Enumerated lines”.
41. A fában bontsa ki ezt: „model\Archive header\Enumerated lines\Value”.
42. A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Amount”.
43. Kattintson a Kötés gombra.
44. A faszerkezetben válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)”.
45. A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Commodity rec id”.
46. Kattintson a Kötés gombra.
47. A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)”.
48. A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Item number”.
49. Kattintson a Kötés gombra.
50. A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)”.
51. A fában válassza ki ezt: „model\Archive header\Enumerated lines\Number”.
52. Kattintson a Kötés gombra.
53. A fastruktúrában válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail”.
54. A fában válassza ki ezt: „model\Archive header\Enumerated lines”.
55. Kattintson a Kötés gombra.
56. A fastruktúrában válassza ki ezt: „Archive\File name(FileName)”.
57. A fában válassza ki ezt: „model\Archive header\File name”.
58. Kattintson a Kötés gombra.
59. A fában válassza ki ezt: „Archive\Number of lines(NumberOfLines)”.
60. A fában válassza ki ezt: „model\Archive header\Number of lines”.
61. Kattintson a Kötés gombra.
62. A fastruktúrában válassza ki ezt: „Archive”.
63. A fában válassza ki a „model\Archive header” lehetőséget.
64. Kattintson a Kötés gombra.
65. Kattintson a Mentés gombra.
66. Zárja be a lapot.
67. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]