---
title: Az ER-konfigurációk függőségének meghatározása más összetevőknél
description: Ez a témakör ismerteti, hogyan lehet elektronikus jelentési konfigurációt tervezni, és megadni az egyéb szoftverösszetevőktől való függőségét.
author: NickSelin
ms.date: 07/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 525e9be1655bdf0c0328ec53509ab1966abd7bde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883568"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>Az ER-konfigurációk függőségének meghatározása más összetevőknél

[!include [banner](../../includes/banner.md)]

A lépések végrehajtásához végre kell hajtania a feladat-úmutató lépéseit, az ER model-leképezési konfigurációk kezelését, és hozzáféréssel kell rendelkeznie a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáshoz.

Ez az eljárás bemutatja, hogyan hozhat létre elektronikus jelentési (ER) konfigurációt, és hogyan adhatja meg az egyéb szoftverösszetevőktől való függőségi viszonyt, hogy biztosíthassa, hogy a konfiguráció letöltése megfelelő a Finance and Operations meghatározott verziója esetében. Ebben a példában létrehozzuk a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. 

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként bármely vállalatnál végrehajthatja. 

1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
    * Győződjön meg arról, hogy a konfigurációs fa tartalmazza a Minta adatmodell konfigurációját és az alsóbb szintű cikkeket. Ellenkező esetben hajtsa végre a feladat-útmutató lépéseit, az ER model-leképezési konfigurációk kezelését, majd indítsa újra az útmutatót.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>ER-konfigurációk függőségének meghatározása más összetevők közül
1. A fastruktúrában bontsa ki a „Minta adatmodell” elemet.
2. A fán válassza a következőt: „Sample data model\Sample mapping”.
    * Most a Mintaleképezés „modell-leképezési” konfiguráció vázlatverzióját választottuk ki. Meg kell határoznia a többi szoftverösszetevővel való függőségi viszonyát. Ez a lépés a konfiguráció verziójának ER-tárházból történő letöltésének, valamint a jelen verzió további használatának előfeltétele.   
3. Bontsa ki az Előfeltételek szakaszt.
    * Vegye figyelembe, hogy az Implementációk előfeltételcsoport automatikusan hozzá van adva ebben a szakaszban. Ez a csoport tartalmazza az adatmodell-konfigurációra hivatkozó előfeltétel-ellenőrzési összetevőt, és az Implementáció jelzője be van kapcsolva. Ez a jelző mutatja, hogy a Mintaleképezés leképezési konfiguráció a Minta adatmodell adatmodell végrehajtásának minősül. Ez az összetevő hatására arra kényszeríti az ER-t, hogy mindig letöltse egy ER-tárházból a Mintaleképezés leképezési konfigurációt, amikor letölti a Minta adatmodell modellkonfigurációt.   
4. Kattintson a Szerkesztés lehetőségre.
    * Az összetevő típusának meghatározását használva a szoftverösszetevő aktuális konfigurációjának egyetlen függősége határozható meg, sem az összetevő verziója, sem pedig az összetevőverziók tartománya.  
    * A kívánt függőségek csoportosíthatók. Amikor az „Összes” csoportosítási típus be van jelölve, ezen csoport függőségi állapota teljesültnek minősül, ha a csoport és az alsóbb szintű csoport minden függőségi feltétele teljesül. Amikor az „Egyik” csoportosítási típus be van jelölve, ezen csoport függőségi állapota teljesültnek minősül, ha a csoport legalább egy függőségi feltétele teljesül.   
5. Kattintson az Új lehetőségre.
6. Válassza a Termék előfeltételeként szükséges összetevő lehetőséget.
7. Válassza a Microsoft Dynamics 365 for Operations (1611) lehetőséget.
8. A Verzió mezőbe írja be a következő értéket: [7.1.1541.3036,8).
    * [7.1.1541.3036,8)  
    * A beírt függőségeket a rendszer akkor értékeli ki, amikor ezt a beállítást letölti valamely ER-tárházból. A rendszer ezt a konfigurációs verziót tölti le az ER-tárházból, ha a Minta adatmodell konfiguráció 1-es verziója már fennáll, vagy korábban le volt töltve. Ha előzetesen letölti a rendszer, akkor azt a Pénzügyi és műveletek 7.1.1541.3036 verzióban kell végrehajtani, de nem haladhatja meg a 8-as főverziót.   
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.
11. Kattintson az Állapot módosítása elemre.
12. Kattintson a Befejezés gombra.
13. Kattintson az OK gombra.
14. A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.
15. Kattintson a Szerkesztés lehetőségre.
16. Kattintson az Új lehetőségre.
17. Válassza a Termék előfeltételeként szükséges összetevő lehetőséget.
18. Válassza ki a Microsoft Dynamics AX 7.0 RTW verziót.
19. A Verzió mezőbe írja be a következő értéket: [7.0.1265.3015,7.1).
    * [7.0.1265.3015,7.1)  
    * A függőségeket a rendszer akkor értékeli ki, amikor a beállítást letölti valamely ER-tárházból. A rendszer ezt a konfigurációs verziót tölti le az ER-tárházból, ha a Minta adatmodell konfiguráció 1-es verziója már fennáll, vagy korábban le volt töltve. Amennyiben korábban letöltötték, a kitöltését a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition programban kell elvégezni, amelynek verziója kötelezően 7.0.1265.3015 vagy újabb verzió, de nem haladhatja meg a 1-as alverziót.   
20. Kattintson a Mentés gombra.
21. Zárja be a lapot.
22. Kattintson az Állapot módosítása elemre.
23. Kattintson a Befejezés gombra.
24. Kattintson az OK gombra.

## <a name="configure-the-er-repository"></a>ER-tárház konfigurálása
1. Zárja be a lapot.
2. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Nyissa meg az aktuális ER-szolgáltató, a Litware, Inc. ER-tárházainak listáját.  
3. A listában jelölje meg a kiválasztott sort.
4. Kattintson a Tárházak gombra.
5. Kattintson a Szűrők megjelenítése pontra.
6. Adja meg az LCS szűrőértékét a Típusnév mezőben a „tartalmazza” szűrési operátor használatával.
    * Ha az LCS tárház már regisztrálva van a jelenlegi ER-szolgáltatónál, kihagyhatja a fennmaradó lépéseket ebben az alfeladatban. Ha az LCS tárház még nincs regisztrálva, végezze el a fennmaradó lépéseket.   
7. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
8. A Konfiguráció tárházának típusa mezőbe írja be az „LCS” értéket.
9. Kattintson a Tárház létrehozása lehetőségre.
10. A Projekt mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a kívánt LCS-projektet a Projekt mező keresőjéből.  
11. Kattintson az OK gombra.
12. Zárja be a lapot.

## <a name="upload-configurations-to-lcs"></a>Konfigurációk feltöltése az LCS rendszerbe
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
2. A fastruktúrában válassza ki a „Sample data model” elemet.
3. Válassza ki a jelen konfiguráció teljesített verzióját.
4. Kattintson az Állapot módosítása elemre.
5. Kattintson a Megosztás lehetőségre.
6. Kattintson az OK gombra.
    * A modellkonfiguráció 1-es verziója fel van töltve az LCS szolgáltatásba a korábban konfigurált, ER-tárháznak szánt LCS-projekt segítségével.   
7. A fastruktúrában bontsa ki a „Minta adatmodell” elemet.
8. A fán válassza a következőt: „Sample data model\Sample mapping”.
9. Válassza ki a jelen konfiguráció teljesített verzióját.
10. Kattintson az Állapot módosítása elemre.
11. Kattintson a Megosztás lehetőségre.
12. Kattintson az OK gombra.
    * A modell-leképezés 1.1-es verziója fel van töltve az LCS szolgáltatásba a korábban konfigurált, ER-tárháznak szánt LCS-projekt segítségével.   
13. A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.
14. Válassza ki a jelen konfiguráció teljesített verzióját.
15. Kattintson az Állapot módosítása elemre.
16. Kattintson a Megosztás lehetőségre.
17. Kattintson az OK gombra.
    * A modell-leképezés 1.1-es verziója fel van töltve az LCS szolgáltatásba a korábban konfigurált, ER-tárháznak szánt LCS-projekt segítségével.   

## <a name="evaluate-er-configuration-dependencies"></a>ER konfigurációs függőségek kiértékelése
A rendszer törli a létrehozott konfigurációkat, és visszatölti őket az LCS-tárházból.  
1. A fán válassza a következőt: „Sample data model\Sample mapping”.
2. Kattintson a Törlés gombra.
3. Kattintson az Igen gombra.
4. A fában válassza ki ezt: „Sample data model\Sample mapping (alternative)”.
5. Kattintson a Törlés gombra.
6. Kattintson az Igen gombra.
7. A fában válassza a „Sample data model\Sample format” lehetőséget.
8. Kattintson a Törlés gombra.
9. Kattintson az Igen gombra.
10. A fastruktúrában válassza ki a „Sample data model” elemet.
11. Kattintson a Törlés gombra.
12. Kattintson az Igen gombra.
13. Zárja be a lapot.
    * Nyissa meg az aktuális ER-szolgáltató, a Litware, Inc. ER-tárházainak listáját.  
14. Kattintson a Tárházak gombra.
15. Kattintson a Szűrők megjelenítése pontra.
16. Adja meg az LCS szűrőértékét a Típusnév mezőben a „tartalmazza” szűrési operátor használatával.
17. Kattintson a Megnyitás gombra.
18. A fastruktúrában válassza ki a „Sample data model” elemet.
    * Vegye figyelembe, hogy megtekintheti annak értékelését, hogy teljesültek-e a jelenlegi tárház különböző verzióinak ER-konfigurációira vonatkozó előfeltételek. Az értékelés megtekintéséhez kattintson az Előfeltételek ellenőrzése lehetőségre.   
19. Kattintson az Előfeltételek ellenőrzése lehetőségre.
20. Kattintson az Importálás gombra.
21. Kattintson az Igen gombra.
22. Zárja be a lapot.
23. Zárja be a lapot.
24. Zárja be a lapot.
25. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
26. A fastruktúrában bontsa ki a „Minta adatmodell” elemet.
    * Vegye figyelembe, hogy a Mintaleképezés modell-leképezési konfigurációt a rendszer a kijelölt adatmodell-konfigurációval együtt letöltötte. A két fájl letöltése együtt történik, mivel a Mintaleképezés meghatározása a kiválasztott adatmodell végrehajtása, és mivel az alkalmazásra vonatkozik. A „Mintaleképezés (másodlagos)” konfiguráció még nincs letöltve, mivel nem teljesült a kívánt alkalmazásverzióhoz kapcsolódó feltétel.   
    * Ha bejelentkezik a Pénzügy és műveletek szolgáltatásba, regisztrálja ugyanazt a szolgáltatót, hozzáfér ugyanannak az LCS-projektnek, és letölti ugyanazt az adatmodell-konfigurációt, a "Minta megfeleltetés (alternatív)" konfiguráció lesz letöltve, míg a program kihagyja a "Minta megfeleltetés" konfigurációt.  

## <a name="additional-resources"></a>További erőforrások

[Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése](../general-electronic-reporting-manage-configuration-lifecycle.md)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
