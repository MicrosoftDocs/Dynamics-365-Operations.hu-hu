---
title: ER-modell leképezés kezelése külön ER-konfigurációkban
description: Ez a témakör azt ismerteti, hogyan kell kezelni az elektronikus jelentési (ER) modellleképezéseket a különböző ER-konfigurációkban.
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
ms.openlocfilehash: 23ac14ba06b6ab535545bacbafe90a4a3c946476
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290244"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>ER modell-leképezés kezelése külön ER-konfigurációkban

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörhöz rendelt felhasználó miként hozhat létre konfigurációszolgáltatót az Elektronikus jelentéshez (ER). Ebben a feladat-útmutatóban létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. A lépések végrehajtásához először a következő feladat-útmutató lépéseit kell végrehajtani: „ER – Konfigurációszolgáltató létrehozása, és megjelölés aktívként”. 

Mivel az ER-konfigurációk meg vannak osztva a vállalatok között, a feladat-útmutatót a tetszése szerint vállalat-adatkészlettel hajthatja végre. A Feladat útmutató a funkcionalitása akkor érhető el, ha telepítette a következő gyorsjavítások valamelyikét: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 a Dynamics AX 7.0-s verzióhoz vagy https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 a Dynamics 365 for Operations verzióhoz.

1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató. Ha nem látja a konfigurációszolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” feladat-útmutatóban szereplő lépéseket.   

## <a name="add-a-new-er-model-configuration"></a>Új ER-modellkonfiguráció hozzáadása
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
    * Új modellkonfiguráció hozzáadása. A névnek egyedinek kell lennie a konfigurációfában.  
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. A Név mezőben írja be a „Minta adatmodell” szöveget.
    * Minta adatmodell  
4. Kattintson a Konfiguráció létrehozása lehetőségre.
5. Kattintson a Tervező pontra.
6. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
7. A Név mezőbe írja be a következőt: „Gyökér”.
    * Gyökér  
8. Kattintson a Hozzáadás gombra.
9. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
10. A Név mezőbe írja be a Vállalat szót.
    * Cég  
11. Kattintson a Hozzáadás gombra.
12. A Leírás mezőben adja meg 'A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben' szöveget. 
    * A jogi személy vagy vállalat leírása, amelybe egy felhasználó bejelentkezett futásidőben.  
13. Kattintson a Gyökérhivatkozás lehetőségre.
14. Kattintson az OK gombra.
15. Kattintson a Mentés gombra.
16. Zárja be a lapot.
17. Kattintson az Állapot módosítása elemre.
18. Kattintson a Befejezés gombra.
19. Kattintson az OK gombra.

## <a name="add-a-new-er-model-mapping-configuration"></a>Új ER-modellhozzárendeléskonfiguráció hozzáadása
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.
3. A Név mezőbe írja be a „Minta hozzárendelés” szöveget.
    * Minta leképezés  
4. Kattintson a Konfiguráció létrehozása lehetőségre.
5. Bontsa ki az Előfeltételek szakaszt.
    * Az Implementációk előfeltételcsoport automatikusan hozzá van adva. A csoport tartalmazza a szülő adatmodell-konfigurációra hivatkozó előfeltétel-ellenőrzési összetevőt, és Implementációként van megjelölve. Ez azt jelenti, hogy ez a Mintahozzárendelés modellhozzárendelési konfiguráció a Minta adatmodell implementációjának minősül. Ezért ez az összetevő arra kényszeríti az ER-t, hogy mindig letöltse egy ER-tárházból a Minta-hozzárendelés modell-hozzárendelési konfigurációt, amikor letölti a Minta adatmodell modellkonfigurációt.   
6. Kattintson a Tervező pontra.
    * A létrehozott modell-hozzárendelési konfiguráció egy új, üres hozzárendelést tartalmaz, amelynek a neve azonos a létrehozott konfiguráció nevével. Ha egy kijelölt szülő modellkonfiguráció modell-hozzárendeléseket tartalmaz, ha azok át lesznek másolva egy új modell-hozzárendelési konfigurációba.   
7. Kattintson a Tervező pontra.
8. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.
9. Kattintson a Gyökér hozzáadása gombra.
10. A Név mezőbe írja be a Vállalat szót.
    * Cég  
11. Írja be a Tábla mezőbe a „CompanyInfo” szöveget.
    * CompanyInfo  
12. Kattintson az OK gombra.
13. A fastruktúrában bontsa ki ezt: „Company”.
14. A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.
15. A fastruktúrában válassza ki ezt: „Company\find()\Name”.
16. Kattintson a Kötés gombra.
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.
19. Zárja be a lapot.
20. Kattintson a Konfigurációk lehetőségre a Művelet Panelen.
21. Kattintson a Felhasználói paraméterek lehetőségre.
22. Válassza az Igen lehetőséget a Beállítások futtatása mezőben.
23. Kattintson az OK gombra.
24. Kattintson a Szerkesztés lehetőségre.
25. Válassza az Igen lehetőséget a Vázlat futtatása mezőben.

## <a name="add-a-new-er-format-configuration"></a>Új ER-formátum hozzáadása
1. A fastruktúrában válassza ki a „Sample data model” elemet.
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló formátum” kifejezést.
4. A Név mezőbe írja be a „Minta formátum” szöveget.
    * Minta formátum  
5. Kattintson a Konfiguráció létrehozása lehetőségre.
6. Kattintson a Tervező pontra.
7. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
8. A fában válassza ki ezt: „Text\String”.
9. Kattintson az OK gombra.
10. Kattintson a Hozzárendelés fülre.
11. A fában bontsa ki a „model” elemet.
12. A fában válassza ki ezt: „model\Company”.
13. Kattintson a Kötés gombra.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
    * A létrehozott formátum piszkozatverziójának futtatása tesztelésre.  
16. Kattintson a Futtatás elemre.
    * A verzió gyorslapon kattintson a Futtatás lehetőségre.  
17. Kattintson az OK gombra.
    * Tekintse át a kimenetet, amely tartalmazza annak a vállalatnak a nevét, amelybe az ezt a formátumkonfigurációt futtató felhasználó be van jelentkezve. A létrehozott modell-hozzárendelési konfigurációt ez a formátumkonfigurációra használja, mivel csak egy konfiguráció érhető el, amely tartalmazza a szükséges modell-hozzárendeléseket.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Alternatív ER-modell leképezés konfigurációjának hozzáadása
1. A fastruktúrában válassza ki a „Sample data model” elemet.
2. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
3. Az Új mezőbe írja be a „Minta adatmodell adatmodellen alapuló modell-hozzárendelés” kifejezést.
4. A név mezőben írja be a „Mintaleképezés (másodlagos)” szöveget.
    * Minta-hozzárendelés (másodlagos)  
5. Kattintson a Konfiguráció létrehozása lehetőségre.
6. Kattintson a Tervező pontra.
7. Kattintson a Tervező pontra.
8. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.
9. Kattintson a Gyökér hozzáadása gombra.
10. A Név mezőbe írja be a Vállalat szót.
    * Cég  
11. Írja be a Tábla mezőbe a „CompanyInfo” szöveget.
    * CompanyInfo  
12. Kattintson az OK gombra.
13. Kattintson a Szerkesztés lehetőségre.
14. A fában válassza ki a 'String\CONCATENATE' lehetőséget.
15. Kattintson a Függvény hozzáadása gombra.
16. A fastruktúrában bontsa ki ezt: „Company”.
17. A fában bontsa ki vagy csukja össze a „Companyfind\()” elemet.
18. A fastruktúrában válassza ki ezt: „Company\find()\Name”.
19. Kattintson az Adatforrás hozzáadása pontra.
20. Írjon be egy értéket a Receptúra mezőbe.
    * CONCATENATE(Company.'find()'.Name, ";",  
21. A fastruktúrában válassza ki ezt: „Company\find()\Company(DataArea)”.
22. Kattintson az Adatforrás hozzáadása pontra.
23. Írjon be egy értéket a Receptúra mezőbe.
    * CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)  
24. Kattintson a Mentés gombra.
25. Zárja be a lapot.
26. Kattintson a Mentés gombra.
27. Zárja be a lapot.
28. Zárja be a lapot.
29. Válassza az Igen lehetőséget a Vázlat futtatása mezőben.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Meglévő ER-modell leképezés konfiguráció használata
1. A fában válassza a „Sample data model\Sample format” lehetőséget.
2. Kattintson a Futtatásra.
    * Az ER-formátumkonfigurációhoz kijelölt piszkozatverzió nem hajtható végre, mert egynél több modell-hozzárendelési konfiguráció áll rendelkezésre a nem definiált adatmodellhez, amely a futó ER-formátum adatforrásaként van kiválasztva.   
    * Ezt követően meg fogja adni, hogy a másodlagos modell-hozzárendelési konfiguráció legyen az, amelynek a modell-hozzárendelései lesznek használva a futó ER-formátum adatforrásaként.   
3. A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.
4. Válassza az Igen lehetőséget a Modell-leképezés alapértelmezett értéke mezőben.
5. A fában válassza a „Sample data model\Sample format” lehetőséget.
6. Kattintson a Futtatásra.
7. Kattintson az OK gombra.
    * Ez a formátumkonfiguráció az alapértelmezett modell-hozzárendelési konfigurációt használja az elektronikus dokumentum létrehozásához (a létrehozott kimenet tartalmazza a vállalatkódot).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
