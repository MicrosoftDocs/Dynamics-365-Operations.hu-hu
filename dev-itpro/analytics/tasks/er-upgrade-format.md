--- 
title: "A formátum frissítése a formátum új alapverziójának elfogadásával az elektronikus jelentéskészítésben (ER)"
description: "A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tarthatja karban az Elektronikus jelentés (ER) formátumkonfigurációját."
author: NickSelin
manager: AnnBe
ms.date: 02/06/2017
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 8329e14de26dd98c72603018cbd647cb06fb5454
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="upgrade-your-format-by-adopting-of-new-base-version-of-that-format-for-electronic-reporting-er"></a>A formátum frissítése a formátum új alapverziójának elfogadásával az elektronikus jelentéskészítésben (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések bemutatják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tarthatja karban az Elektronikus jelentés (ER) formátumkonfigurációját. Ez az eljárás bemutatja, hogy hogyan lehet létrehozni a formátum egyéni verzióját a konfigurációs szolgáltatóból (CP) a formátum alapján. Azt is bemutatja, hogyan lehet alkalmazni ezen verzió új, alap verzióját.



A lépések végrehajtásához először el kell végezni a „Hozzon létre egy konfigurációs szolgáltatót és állítsa be aktívként aktív” és „A létrehozott formátum segítségével hozza létre a kifizetések elektronikus dokumentumát” eljárásokat. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.


## <a name="select-format-configuration-for-customization"></a>Válassza ki a formátumkonfigurációt a testreszabáshoz
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ebben a példában a Litware, Inc. mintavállalat (http://www.litware.com) konfigurációszolgáltatóként működik, így támogatja az elektronikus kifizetésekre vonatkozó formátumkonfigurációkat egy adott országra vonatkozóan.    A Proseware, Inc. mintavállalat (http://www.proseware.com) a formátumkonfiguráció felhasználójaként működik, amelyet a Litware, Inc. rendszer hozott létre. A Proseware, Inc. az adott ország bizonyos régióiban szereplő formátumokat használja.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. Kattintson a Szűrők megjelenítése pontra.
4. Alkalmazza a következő szűrőket: adja meg a „BACS (UK fiktív)” szűrőértéket a „Név” mezőben az „ezzel kezdődik” szűrési operátor használatával.
    * BACS (UK fiktív)  
    * A Litware, Inc. szolgáltató rendelkezik a BACS (UK fiktív) kiválasztott formátumkonfigurációval.  
5. Kattintson a Szűrők megjelenítése pontra.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * A Befejezett állapotú formátum verzióját használja a Proseware, Inc. rendszer. a testreszabásra vonatkozóan.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Új konfiguráció létrehozása az elektronikus dokumentum egyéni formátumára vonatkozóan
    * A Proseware, Inc. a BACS ( UK fiktív) konfiguráció bevételezett 1.1-es verzióját kapta, amely tartalmazza a kezdeti formátumot az elektronikus kifizetési dokumentumok Litware, Inc. rendszerből történő létrehozására a szolgáltatási előfizetéssel összhangban. A Proseware, Inc. az országa alapjaként kívánja ezt használni, de néhány testreszabás a megadott regionális követelmények támogatását igényli. A Proseware, Inc. továbbra is szeretne rendelkezni kíván az egyéni formátum frissítésének képességével, amint a Litware, Inc. rendszer kiadja az új verzióját (új országspecifikus követelmények támogatására irányuló módosításokkal), és azok a legkisebb költségvetésű frissítését kívánják elvégezni.  Ehhez a Proseware, Inc. rendszernek létre kell hoznia egy olyan konfigurációt, amely a Litware, Inc. rendszer BACS konfigurációját (UK fiktív) alapként használja.  
1. Zárja be a lapot.
2. Válassza ki a Proseware, Inc. rendszert a beállításhoz aktív szolgáltatóként.
3. Kattintson erre: Beállítás aktívként.
4. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
5. A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.
6. A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)”.
    * Válassza ki a BACS (UK fiktív) konfigurációt a Litware, Inc. rendszerből. A Proseware, Inc. az 1.1-es verziót használja alapként az egyéni verzióra vonatkozóan.  
7. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
    * Ez lehetővé teszi Önnek, hogy új konfigurációt hozzon létre az egyéni fizetési formátumra vonatkozóan.  
8. Az Új mezőbe írja be a „Származtatás innen: BACS (UK fiktív), Litware, Inc.” szöveget.
    * Válassza ki a Származtatás lehetőséget alapként a BACS (UK fiktív) használatának megerősítésére az egyéni verzió létrehozásához.  
9. A Név mezőbe írja be a „BACS (UK fiktív egyéni)” szöveget.
    * BACS (UK fiktív egyéni adatok)  
10. A Leírás mezőbe írja be a „BACS szállítói kifizetés (UK fiktív egyéni)” szöveget.
    * BACS szállítói kifizetés (UK fiktív egyéni)  
    * Itt automatikusan megjelenik az aktív konfigurációs szolgáltató (Proseware, Inc.). Ez a szolgáltató tartja majd karban ezt a konfigurációt. Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.  
11. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="customize-your-format-for-the-electronic-document"></a>Az elektronikus dokumentum-formátumának testreszabása
1. Kattintson a Tervező pontra.
2. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
3. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
4. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank”.
5. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A fában válassza ki az XML\Element csomópontot.
7. A Név mezőbe írja be az „IBAN” szöveget.
    * IBAN  
8. Kattintson az OK gombra.
9. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\IBAN”.
10. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
11. A fában válassza ki ezt: „Text\String”.
12. Kattintson az OK gombra.
13. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név\Karakterlánc”.
14. Adja meg a „60” értéket a Maximális hossz mezőben.
15. Kattintson a Hozzárendelés fülre.
16. A fában bontsa ki a „model” elemet.
17. A fában bontsa ki a „model\Payments” elemet.
18. A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.
19. A fában bontsa ki a következőt: „model\Payments\Creditor\Account”.
20. A fastruktúrában válassza ki a „modell\Fizetések\Beszedő\Számla\IBAN” pontot.
21. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk = model.Payments\Szállító\Bank\IBAN\Karakterlánc”.
22. Kattintson a Kötés gombra.
23. Kattintson a Mentés gombra.

## <a name="validate-the-customized-format"></a>A testreszabott formátum érvényesítése
1. Kattintson az Érvényesítés gombra.
    * Annak érdekében, hogy meggyőződjön arról, hogy az összes kötés rendben van, ellenőrizze a testreszabott formátum elrendezését és az adatleképezési módosításokat.  
2. Zárja be a lapot.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Az egyéni formátumkonfiguráció aktuális verziójának állapotmódosítása
    * Módosítsa a tervezett formátumkonfiguráció állapotát Vázlat állapotról Teljesített állapotra annak érdekében, hogy létre lehessen hozni kifizetési dokumentumot.  
1. Kattintson az Állapot módosítása elemre.
    * Ne feledje, hogy a kiválasztott konfiguráció aktuális verziója Vázlat állapotban van.  
2. Kattintson a Befejezés gombra.
3. A Leírás mezőben adjon meg egy értéket.
4. Kattintson az OK gombra.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Fontos, hogy a létrehozott konfiguráció teljesített 1.1.1-es verzióként lesz mentve. Ez azt jelenti, hogy ez az egyéni BACS (UK fiktív egyéni) formátum 1-es verziója, amely a Kifizetések (egyszerűsített modell) adatmodell 1-es verzióján alapuló BACS (UK fiktív) 1-es verzióján alapul.  

## <a name="test-the-customized-format-to-generate-payment-files"></a>A testreszabott formátum tesztelése a Kifizetési fájlok létrehozásához
    * Hajtsa végre a „Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a létrehozott formátum segítségével” eljárásban szereplő lépéseket a párhuzamos Dynamics 365 for Finance and Operations Enterprise kiadás szakaszban. Válassza ki a BACS (Egyesült Királyság fiktív egyéni) formátumát az elektronikus fizetési módszer paramétereiben. Győződjön meg arról, hogy a létrehozott kifizetési fájl tartalmazza a közelmúltban bevezetett XML-csomópontot, amely az IBAN mezőt a regionális követelményeknek megfelelően jeleníti meg.  

## <a name="update-the-existing-country-specific-configuration"></a>A meglévő országspecifikus konfiguráció frissítése
    * A Litware, Inc. rendszernek frissítenie kell a BACS (UK fiktív) konfigurációját, és igazodnia kell az új ország követelményeihez az elektronikus dokumentum formátumának kezelésére vonatkozóan. Később ezen konfiguráció új verziójában tárolva lesz, amelyet felajánlanak a szolgáltatás előfizetői számára, többek között a Proseware, Inc.  
    * A tényleges szolgáltatásnyújtás kapcsolódó folyamataiban a Proseware, Inc. rendszer a BACS (UK fiktív) minden új verzióját importálhatja a Litware, Inc. rendszer konfigurációinak LCS-tárházából. Az eljárás során ezt szimulálja a rendszer a BACS (UK fiktív) a szolgáltató nevében történő frissítésével.  
1. Zárja be a lapot.
2. Válassza ki a Litware, Inc. lehetőséget. szolgáltatót.
3. Kattintson erre: Beállítás aktívként.
4. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
5. A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.
6. A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)”.
    * A vázlatverzióval rendelkező Litware, Inc. szolgáltató BACS (UK fiktív) be van jelölve a módosítások bevezetéséhez az új országspecifikus követelmények támogatására.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Az elektronikus dokumentum alapformátumának honosítása
    * Tegyük fel, hogy az vannak olyan országspecifikus követelmények, amiket a Proseware Inc. rendszernek támogatnia kell: - Minden egyes kifizetéstranzakcióban szereplő hitelezői bank SWIFT- kódja.  - A szállító nevére vonatkozó, maximum 100 karakter hosszú szöveg a fájl létrehozásánál.  
    * Új Ország-specifikus követelmények  
    * Válassza ki a kívánt konfiguráció vázlat verzióját a szükséges módosítások bevezetéséhez.  
1. Kattintson a Tervező pontra.
2. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
3. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
4. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank”.
5. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A fában válassza ki az XML\Element csomópontot.
7. A Név mezőbe írja be a „SWIFT” szöveget.
    * SWIFT  
8. Kattintson az OK gombra.
9. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\SWIFT”.
10. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
11. A fában válassza ki ezt: „Text\String”.
12. Kattintson az OK gombra.
13. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név\Karakterlánc”.
14. Adja meg a „100” értéket a Maximális hossz mezőben.
15. Kattintson a Hozzárendelés fülre.
16. A fában bontsa ki a „model” elemet.
17. A fában bontsa ki a „model\Payments” elemet.
18. A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.
19. A fában bontsa ki a következőt: „model\Payments\Creditor\Agent”.
20. A fastruktúrában válassza ki ezt: „modell\Fizetések\Beszedő\Ügynök\SWIFT”.
21. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk = model.Payments\Szállító\Bank\SWIFT\Karakterlánc”.
22. Kattintson a Kötés gombra.
23. Kattintson a Mentés gombra.

## <a name="validate-the-localized-format"></a>A honosított formátum érvényesítése
1. Kattintson az Érvényesítés gombra.
2. Zárja be a lapot.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Az alapformátum konfigurációjának aktuális verziójának állapotmódosítása
    * Módosítsa a frissített alapformátum konfigurációjának állapotát Vázlat állapotról Befejezett állapotra, hogy elérhető legyen a fizetési bizonylatok létrehozása és az abból származtatott formátumkonfigurációk frissítése.  
1. Kattintson az Állapot módosítása elemre.
    * Ne feledje, hogy a kiválasztott konfiguráció aktuális verziója Vázlat állapotban van.  
2. Kattintson a Befejezés gombra.
3. A Leírás mezőben adjon meg egy értéket.
4. Kattintson az OK gombra.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Az Alapverzió módosítása az egyéni formátum konfigurációra vonatkozóan
    * A Proseware, Inc. értesítést kap arról, hogy a BACS (UK fiktív) konfiguráció 1.2-es verziójának elérhető az elektronikus kifizetési dokumentumok létrehozására a nemrégiben bejelentett országspecifikus követelményeknek megfelelően. A Proseware, Inc. rendszer alapértelmezettként kívánja ezt használni az országra vonatkozóan.  Ehhez a Proseware, Inc. rendszernek meg kell változtatnia az egyéni konfiguráció (Egyesült Királyság fiktív egyéni) alapkonfigurációjának verzióját. Használja az új 1.2-es verziót a BACS (UK fiktív) 1.1-es verziója helyett.  
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Válassza ki a Proseware, Inc. szolgáltatót az aktívként történő megjelöléshez.
3. Kattintson erre: Beállítás aktívként.
4. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
5. A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.
6. A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)” lehetőséget.
7. A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell\BACS (UK fiktív)\BACS (UK fiktív egyéni)” lehetőséget.
    * Válassza ki a Proseware, Inc. rendszer BACS (Egyesül Királyság fiktív egyéni) konfigurációját  
    * Használja a kiválasztott konfiguráció vázlat verzióját a szükséges módosítások bevezetéséhez.  
8. Kattintson az Új alap lehetőségre.
    * Válassza ki az alapkonfiguráció új, 1.2-es verzióját, amit a konfiguráció frissítésére vonatkozóan új alapként kell alkalmazni.  
9. Kattintson az OK gombra.
    * Vegye figyelembe, hogy a rendszer bizonyos ütközéseket észlelt az egyéni verzió és azon új alapverzió között, amely néhány olyan formátum módosítást jelenít meg, amelyet nem lehet automatikusan egyesíteni.  

## <a name="resolve-rebase-conflicts"></a>Az új alappal kapcsolatos ütközések megoldása
1. Kattintson a Tervező pontra.
    * Vegye figyelembe, hogy a szállító nevének szöveghossz-korlátozására vonatkozó módosításokat nem lehet automatikusan nem oldható fel. Ezért ez jelenik meg ütközések listájában. A Frissítés típusú ütközés esetén a következő lehetőségek közül választhat: – Alkalmazás az alapérték előtt (gomb a rács tetején) az előzetes alapverzió érték (ebben az esetben 0) átviteléhez.  - Az alapérték (gomb a rács tetején) alkalmazása az új Alapverzió érték (ebben az esetben 100) átviteléhez.  - Tartsa meg a saját (egyéni) értékét (az esetünkben ez 60).  Kattintson az Alapérték alkalmazása lehetőségre a 100 karakteres országspecifikus határérték alkalmazásához a szállító nevének hosszúságára vonatkozóan.  
    * Ne feledje, hogy a Proseware, Inc. és a Litware, Inc. rendszer kapcsolt összetevős IBAN- és SWIFT-kódokat használó formátum egyéni és helyi verziójával rendelkezik, amelyek automatikusan egyesítettek az irányító formátumban.  
2. Kattintson az Alkalmazás az alapérték előtt lehetőségre.
    * Kattintson az Alapérték alkalmazása lehetőségre a 100 karakteres országspecifikus határérték alkalmazásához a szállítói névre vonatkozóan.  
3. Kattintson a Mentés gombra.
    * Azon formátum mentése, ami eltávolítja a feloldott ütközéseket az ütközések listájából.  
4. Zárja be a lapot.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Az egyéni formátumkonfiguráció új verziójának állapotmódosítása
1. Kattintson az Állapot módosítása elemre.
    * Módosítsa a frissített, egyéni formátum konfiguráció állapotának Vázlat állapotát Befejezett állapotra. Így lehetővé válik, hogy a formátum konfigurációja fizetési bizonylatokat hozzon létre. Ne feledje, hogy a kiválasztott konfiguráció aktuális verziója Vázlat állapotban van.  
2. Kattintson a Befejezés gombra.
3. A Leírás mezőben adjon meg egy értéket.
4. Kattintson az OK gombra.
    * Vegye figyelembe, hogy a rendszer a létrehozott konfigurációt teljesített 1.2.2-es verzióként menti: az alap BACS (UK fiktív egyéni) formátum 2-es verziója, amely a Kifizetések (egyszerűsített modell) adatmodell 1-es verzióján alapuló alap BACS (UK fiktív) formátum 2-es verzióján alapul.  

## <a name="test-the-customized-format-for-payment-files-generation"></a>A testreszabott formátum tesztelése a Kifizetési fájlok létrehozásához
    * Hajtsa végre a „Hozzon létre elektronikus dokumentumokat a kifizetésekre vonatkozóan a létrehozott formátum segítségével” eljárásban szereplő lépéseket egy párhuzamos Dynamics 365 for Finance and Operations Enterprise kiadás szakaszban. Válassza ki a létrehozott BACS (UK fiktív egyéni) formátumát az elektronikus fizetési módszer paramétereiben. Győződjön meg arról, hogy a létrehozott kifizetési fájl tartalmazza a Proseware, Inc. által a közelmúltban bevezetett XML-csomópontot, amely az IBAN-számlakódot a regionális követelményeknek megfelelően jeleníti meg. A fájlnak tartalmaznia kell a közelmúltban a Litware, Inc. által bevezetett XML-csomópontot is, amely a SWIFT-bankkódot az ország előírásainek megfelelően jeleníti meg.  


