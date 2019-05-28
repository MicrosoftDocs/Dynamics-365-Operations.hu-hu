---
title: A minimum-maximum feltöltési folyamat beállítása
description: Ez az eljárás bemutatja, hogy hogyan állíthat be egy új feltöltési folyamatot, amely a minimális/maximális feltöltési stratégiát használja.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, InventItemIdLookupSimple, WMSLocationIdLookup, WHSLocDirTable, InventLocationIdLookup, SysQueryForm, WHSWorkTemplateTable, WHSReplenishmentTemplates, UnitOfMeasureLookup, SysQueryTableLookUp, SysQueryFieldLookUp, SysRecurrence
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5fc03e0cf0ceb27a5cc406860bf5bd877e95460c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546617"
---
# <a name="set-up-a-min-max-replenishment-process"></a>A minimum-maximum feltöltési folyamat beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan állíthat be egy új feltöltési folyamatot, amely a minimális/maximális feltöltési stratégiát használja. Amikor a készlet a minimális szint alá esik, a rendszer a hely feltöltéséhez hozza létre munkát. Az eljárás azt is bemutatja, hogy hogyan lehet a rögzített kitárolási helyek segítségével az újratelepítést engedélyezni, ha a készlet a minimális szint alá esik, és hogyan lehet a feltöltési folyamatot engedélyezni a rendszeres futtatáshoz egy kötegelt feladat használatával. Ezeket a feladatokat jellemzően egy raktári vezető végzi el. A megjegyzések példaértékeinek használatával futtathatja ezt az eljárást az USMF bemutató vállalatnál, vagy a saját adatait vagy futtathatja. Ha a saját adatait használja, győződjön meg arról, hogy egy olyan raktárral rendelkezik, amely engedélyezve van a Raktárkezelési folyamatok számára.


## <a name="create-a-fixed-picking-location"></a>A fix kitárolási helyek létrehozása
1. Ugorjon a Raktárkezelés > Beállítás > Raktár > Rögzített helyek pontra.
    * A minimum-maximum feltöltésre vonatkozóan ez egy választható feladat, de ha a fix kivételi helyeket használja, akkor lehetővé válik a készlet feltöltése még akkor is, ha a minimális szint alá esik, mert a rendszer meghatározhatja, hogy mely termékeket kell feltölteni, még akkor is, ha nincs a készleten.  
2. Kattintson az Új lehetőségre.
3. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a „A0001” cikket.  
4. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a 2-es helyet.  
5. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén kiválaszthatja az 24-es raktárt.  
6. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a CP-003 lehetőséget.  
7. Zárja be a lapot.

## <a name="create-a-replenishment-location-directive"></a>A feltöltési helyutasítás létrehozása
1. Ugrás a Raktárkezelés > Beállítás > Helyutasítások elemre.
    * A Helyutasítások segítségével határozza meg, hogy honnan kell kitárolni a cikkeket a feltöltési folyamat során.  
2. A Munkarendelés típusa mezőben válassza ki a „Feltöltés” lehetőséget.
3. Kattintson az Új lehetőségre.
4. Írjon be egy értéket a Név mezőbe.
5. A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.
6. A Hely mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén választhatja a 2-es helyet.  
7. A Raktár mezőben adjon meg vagy válasszon ki egy értéket.
    * Az USMF használata esetén kiválaszthatja az 24-es raktárt.  
8. Kattintson a Mentés gombra.
9. Kattintson az Új lehetőségre.
10. A listában jelölje meg a kiválasztott sort.
11. Adjon meg egy számot a Célmennyiség mezőben.
    * Például beállíthatja 9999 értékre.  
12. Jelölje be a Felosztás engedélyezése jelölőnégyzetet.
    * Ha ezt a lehetőséget választja, a munka-létrehozási folyamat a munka mennyiségek több helyen történő szétosztását teszi lehetővé.  
13. Kattintson a Mentés gombra.
14. Kattintson az Új lehetőségre.
15. A listában jelölje meg a kiválasztott sort.
16. Írjon be egy értéket a Név mezőbe.
17. Kattintson a Mentés gombra.
18. Kattintson A lekérdezés szerkesztése elemre.
    * Ezt a lekérdezést beállíthatja azon korlátozások hozzáadására, ahonnan ki lehet választani a készletet a feltöltési folyamat során. Például ez lehet az a készlet is, amelyet csak a raktárház raktárából lehet használni.  
19. Kattintson az OK gombra.
20. Zárja be a lapot.

## <a name="create-a-replenishment-work-template"></a>A feltöltési munkasablon létrehozása
1. Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.
    * A munkasablon segítségével adhat utasításokat a rendszernek, hogy miként kell létrehozni a Min./max. feltöltési munkát. Legalább egy kitárolási és betárolási munkasablonnak kell lennie. A munkasablon azt jeleníti meg, hogy ez Érvénytelen addig, amíg az összes szükséges információt ki nem töltötték.  
2. A Munkarendelés típusa mezőben válassza ki a „Feltöltés” lehetőséget.
3. Kattintson az Új lehetőségre.
4. Írjon be egy értéket a Munkasablon mezőbe.
5. Kattintson a Mentés gombra.
6. Kattintson az Új lehetőségre.
7. A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.
8. A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.
    * Ennek a feltöltéshez kapcsolódó munkaosztálynak kell lennie. Ha az USMF-et használ, jelölje be a „Feltöltés” opciót.  
9. Kattintson az Új lehetőségre.
10. A listában jelölje meg a kiválasztott sort.
11. A Munkatípus mezőben válassza a „Betárolás” lehetőséget.
12. A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.
13. Kattintson a Mentés gombra.
14. Zárja be a lapot.

## <a name="create-a-new-replenishment-template"></a>Egy új feltöltési sablon létrehozása
1. Ugorjon a Raktárkezelés > Beállítás > Feltöltés > Feltöltési sablonok pontra.
    * A feltöltési sablon segítségével határozza meg a cikkeket, a mennyiségeket és a feltöltési helyet.  
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Feltöltési sablon mezőbe.
    * Adjon a sablonnak egy nevet, amely azt jelzi, hogy ez minimális vagy maximális feltöltés.  
4. A Leírás mezőben adjon meg egy értéket.
5. Jelölje be a Hullámigény engedélyezése a nem lefoglalt mennyiségek használatához jelölőnégyzetet.
    * Ha ezt a lehetőséget választja, lehetővé válik a hullám igényfeltöltése min./max. feltöltéshez kapcsolódó mennyiségek felhasználására. Ez például akkor lehet hasznos, ha a minimális/maximális feltöltési munka azonnali feldolgozása nem történik meg annak érdekében, hogy a szükségtelen igény feltöltési munka létrehozását megakadályozzák.  
6. Kattintson az Új lehetőségre.
7. Adjon meg egy számot a Sorozatszám mezőben.
8. A Leírás mezőben adjon meg egy értéket.
9. A listában jelölje meg a kiválasztott sort.
10. A Feltöltési egység mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki például a darab lehetőséget. Ez a beállítás kötelező. Lehetővé teszi egy másik mértékegység meghatározását a feltöltési munkára vonatkozóan, amely összes van hasonlítva az ezen sablon minimális és maximális készletszintjére vonatkozóan meghatározott egységgel.  
11. A Munkasablon mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a korábban létrehozott munkasablont.  
12. A Minimális mennyiség mezőben adjon meg egy számot.
    * Jelölje be a minimális mennyiséget, amely elindítja a feltöltést. Állítsa be például 50 értékre. Azt is megteheti, hogy a nulla értékű beállítást nem módosítja, ha feltölti a rögzített helyeket és az Üres rögzített helyek feltöltése lehetőséget Igen értékre állítja. Szintén ajánlott, hogy Csak a rögzített helyek feltöltése lehetőséget választja ki a teljesítményszempontok miatt.  
13. A Maximális mennyiség mezőben adjon meg egy számot.
    * Állítsa be például 100 értékre.  
14. Az Egység mezőben adjon meg vagy válasszon ki egy értéket.
    * Rendelje hozzá az egységet a minimális és maximális mennyiséghez. Állítsa be például darab lehetőségre.  
15. Jelölje be az Üres rögzített helyek feltöltése jelölőnégyzetet.
    * Jelölje be ezt a jelölőnégyzetet a rögzített helyek feltöltéséhez, ha azok üresek. Ellenkező esetben csak azok a helyek lesznek feltöltve, ahol van készleten lévő mennyiség.  
16. Jelölje be a Csak a rögzített helyek feltöltése jelölőnégyzetet.
17. Kattintson a Termékek kijelölése lehetőségre.
    * Ez a hely határozza meg. hogy mely termékeket kell feltölteni. Ha a Rögzített kitárolási helyek lehetőséget választja, akkor is meg kell határoznia a helyeket a lekérdezésben. A változat-specifikus lekérdezések is ugyanúgy elérhetőek, mint a termékspecifikus lekérdezések.  
18. Válassza ki a Cikkek sora lehetőséget.
19. Érték beírása a Feltétel mezőbe.
    * Válassza ki azokat a cikkeket, amelyeket fel kell tölteni a rögzített helyeken. Írja be például A* szöveget az összes A betűvel kezdődő cikkszám kiválasztásához.  
20. Kattintson a Hozzáadás gombra.
    * Adja hozzá a Hely entitást (kivéve, ha már létezik) annak érdekében, hogy lehetővé váljon a Fix kivételi helyekhez történő feltöltési munka korlátozása a raktár meghatározott területén belül.  
21. A listában jelölje meg a kiválasztott sort.
22. Állítsa be a Tábla mezőt a Helyek lehetőségre.
23. Válassza ki a Helyprofil azonosítója értéket a Mező mezőben.
24. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
25. Kattintson az OK gombra.
26. Zárja be a lapot.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>A feltöltési folyamat beállítása a kötegelt feladatként történő futtatáshoz
1. Ugorjon a Raktárkezelés > Feltöltés > Feltöltések pontra.
    * A Feltöltések lap lehetővé teszi, hogy egy kötegelt feladatként futassa a feltöltést vagy azt követeli, hogy manuálisan elindult feltöltésre legyen beállítva.  
2. Kattintson a Szűrő parancsra.
3. A listában jelölje meg a kiválasztott sort.
4. A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.
5. Kattintson az OK gombra.
6. Bontsa ki a Futtatás a háttérben szakaszt.
7. Állítsa be a Kötegelt feldolgozás lehetőséget Igen értékre.
8. Kattintson az Ismétlődésre.
9. Válassza a Nincs záró dátum lehetőséget.
10. Válassza ki az Ismétlődési mintát.
    * Válassza ki a Napok lehetőséget.  
11. Kattintson az OK gombra.
12. Kattintson az OK gombra.

