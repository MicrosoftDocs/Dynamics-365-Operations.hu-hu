---
title: Adatmodell-definíciók kiválasztása formátumok létrehozásakor
description: A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.
author: kfend
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65b3a74f98282f01940c5d17f8aa893d174883da
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290124"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Adatmodell-definíciók kiválasztása formátumok létrehozásakor

[!include [banner](../../includes/banner.md)]

A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit. 

Ez az eljárás bemutatja, hogyan jelölhető ki egy modell gyökérelem adatmodell-definíciókét olyan elektronikus jelentési (ER) formátumkonfiguráció beszúrásához, amelyet elektronikus dokumentumok létrehozására terveztek. Ebben az eljárásban új ER-formátumkonfigurációt adunk hozzá a Litware, Inc. mintavállalat számára. 

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült. A lépések bármely adathalmazzal végrehajthatók.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.

## <a name="add-a-new-er-data-model-configuration"></a>Új ER-adatmodellkonfiguráció hozzáadása
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
    * Hozzáadunk egy új ER-modellkonfigurációt, amely egy olyan adatmodellt tartalmaz, amelyet arra terveztek, hogy az Intrastat-jelentés létrehozásához adatforrásaként használják.  
2. A Név mezőben írja be a 'Fizetési modell (fiktív)' szöveget.
    * Fizetési modell (fiktív)  
3. Kattintson a Konfiguráció létrehozása lehetőségre.
4. Kattintson a Tervező pontra.
    * Nyissa meg az ER-tervezőt a konfiguráció adatmodell-szerkezetének megadásához.  
    * Tegyük fel, hogy a kifizetések üzleti tartomány adatmodelljét két fizetési mód (átutalás és beszedési megbízás) támogatásával tervezzük.  
5. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A Név mezőbe írja be a „Kifizetések – jóváírás átvitele” szöveget.
    * Kifizetések – jóváírás átvitele  
7. Kattintson a Hozzáadás gombra.
8. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
9. Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.
10. A Név mezőbe írja be a „Kifizetések – beszedési megbízás” szöveget.
    * Kifizetések – beszedési megbízás  
11. Kattintson a Hozzáadás gombra.
12. Kattintson a Mentés gombra.
13. Zárja be a lapot.
14. Kattintson az Állapot módosítása elemre.
    * Töltse ki a modell piszkozatverzióját, hogy elérhetővé tehesse az új modell-hozzárendelésekben és formátumokban.  
15. Kattintson a Befejezés gombra.
16. Kattintson az OK gombra.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Új ER-formátumkonfiguráció bevitelének elindítása
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az Új mezőbe írja be a „Fizetési modell (fiktív) adatmodellen alapuló formátum” kifejezést.
3. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
    * Ne feledje, hogy jelenleg a kijelölt adatmodell összes gyökéreleme elérhető kijelölésre adatmodell-meghatározásként. Tovább folytathatja a formátum tervezését, és felhasználhatja az adatmodell bármelyik szükséges gyökérelemét. A kijelölt gyökérelem hiányzó modell-hozzárendelése nem akadályozza meg a folytatást.  
4. Zárja be a lapot.

## <a name="add-a-new-er-model-mapping-configuration"></a>Új ER-modellhozzárendeléskonfiguráció hozzáadása
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az Új mezőbe írja be a „Fizetési modell (fiktív) adatmodellen alapuló modell-hozzárendelés” kifejezést.
3. A Név mezőben írja be a 'Fizetési modell-hozzárendelés (fiktív)' szöveget.
    * Fizetésimodell-hozzárendelések (fiktív)  
4. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-er-model-mappings"></a>ER-modellhozzárendelések tervezése
1. Kattintson a Tervező pontra.
    * Az ER-tervező segítségével adja meg a modell-hozzárendeléseket a szükséges gyökérelemekhez.  
2. Kattintson a Tervező pontra.
    * A kiválasztott modell-hozzárendelésnek a kiválasztott modell gyökéreleméhez való beállításának szimulálása.  
3. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.
4. Kattintson a Gyökér hozzáadása gombra.
5. A Név mezőbe írja be ezt: 'Főkönyv'.
6. Írja be a Tábla mezőbe a „LedgerJournalTrans” szöveget.
    * LedgerJournalTrans  
7. Kattintson az OK gombra.
8. Kattintson a Mentés gombra.
9. Zárja be a lapot.
10. Zárja be a lapot.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Egy másik új ER-formátumkonfiguráció bevitelének elindítása
1. A fastruktúrában válassza ki a „Payment model (fictitious)” lehetőséget.
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. Az Új mezőbe írja be a „Fizetési modell (fiktív) adatmodellen alapuló formátum” kifejezést.
4. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
    * Vegye figyelembe, hogy mostantól csak egy gyökérelem érhető el az alkalmazás adatforrásaihoz való hozzárendelésre. Amikor van legalább egy modell-hozzárendelés, csak a modell alkalmazás-adatforrásokhoz hozzárendelt gyökérelemei választhatók ki modelldefinícióként az ER-formátum hozzáadása közben.   
5. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
