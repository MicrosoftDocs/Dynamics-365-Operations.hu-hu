--- 
title: "Olyan igénylés létrehozása, amely ajánlatkérést használ"
description: "Ez az útmutató bemutatja, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Olyan igénylés létrehozása, amely ajánlatkérést használ

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja, hogy hogyan lehet egy ajánlatkérési folyamat árral és a szállítóval kapcsolatos információit a beszerzési igényléshez hozzáadni. A példában szereplő útmutatót az USMF bemutatócég használhatja, és rendszergazdaként kell bejelentkeznie ahhoz, hogy végrehajthassa az összes lépést. Általában a beszerzési szakemberek hajtják végre a példában szereplő útmutatót.


## <a name="create-a-requisition"></a>Igénylés létrehozása
1. Ugrás a Beszerzés és forrás > Beszerzési igénylések > Beszerzési igénylések általam létrehozva elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. Adja meg a dátumot az Igényelt dátum mezőben.
5. Adja meg a dátumot a Könyvelés dátuma mezőben.
6. Kattintson az OK gombra.
7. A Ok mezőben adjon meg vagy válasszon ki egy értéket.
8. Kattintson az Új sor hozzáadása lehetőségre.
9. Válasszon ki egy kategóriát a Beszerzési kategória mezőben a fa struktúrában, és kattintson az OK gombra.
10. Írjon be egy értéket a Terméknév mezőbe.
11. Adjon meg egy számot a Mennyiség mezőben.
12. Az Egység mezőben adjon meg vagy válasszon ki egy értéket.
13. Kattintson a Mentés gombra.
14. A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.
15. Kattintson a Küldés hivatkozásra.
16. Zárja be a lapot.
17. Kattintson a Küldés hivatkozásra.

## <a name="reassign-a-workflow-task"></a>Munkafolyamat-feladat ismételt hozzárendelése
    * A következő feladat egy Ajánlatkérés létrehozása annak érdekében, hogy ajánlatot kapjon a szállítótól a termékre. Az USMF bemutató adatokban az igénylési munkafolyamat egy olyan szabály szerint van beállítva, hogy ha a szállító nincs bejelölve, vagy az egységár értéke 0 soronként, akkor a rendszer a feladatot hozzárendeli egy adott dolgozóhoz, azért, hogy az létrehozzon egy Ajánlatkérést. Az útmutató folytatásához a feladatot ismét hozzá kell rendelni egy másik felhasználóhoz (saját magához). Csak úgy teheti meg ezt, ha Rendszergazdaként jelentkezik be.  
1. A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Kattintson az Előzmények megtekintése lehetőségre.
3. Frissítse a lapot..
4. Bontsa ki a Nyomkövetési részletek szakaszt.
5. Válassza ki a „Sor munkafolyamata aktiválva” értékkel kezdődő sort a fa struktúrában.
6. Kattintson a Munkafolyamat részleteinek megtekintése lehetőségre.
7. Bontsa ki a Munkatételek szakaszt.
8. Kattintson az Hozzárendelés ismét lehetőségre.
9. Válassza ki a Rendszergazdát a Felhasználó mezőben.
10. Kattintson az Hozzárendelés ismét lehetőségre.
11. Zárja be a lapot.
12. Zárja be a lapot.

## <a name="create-an-rfq"></a>Ajánlatkérés létrehozása
1. Frissítse a lapot..
2. Kattintson az Ajánlatkérés lehetőségre.
3. Válassza ki az USMF lehetőséget a Vevő jogi személy mezőben.
    * Ugyanazt a jogi személyt kell kiválasztania, mint aki az igénylés sorában szerepel.  
4. A listában jelölje meg a kiválasztott sort.
    * Ha a beszerzési igénylésben több sorral rendelkezett, válassza ki az összes olyan sort, amelyet hozzá kíván adni az ajánlatkéréshez.  
5. Kattintson az OK gombra.
6. Frissítse a lapot..
7. Nyissa meg az Adatterület lehetőséget, majd bontsa ki a kapcsolódó dokumentumok szakaszt.
    * Előfordulhat, hogy már megnyitotta az Adatterület lehetőséget. Keresse meg a nyíllal ellátott ikont, a Sorok/Fejléc váltógombok jobb oldalán. Ha jobbra mutat a nyíl, az Adatterület már meg van nyitva. Ha balra mutat a nyíl, kattintson rá, az Adatterület megnyitásához.  
8. Kattintson az Ajánlatkérés mezőben szereplő hivatkozásra az újonnan létrehozott Ajánlatkérés megnyitásához.
9. Kattintson a Fejléc gombra.
10. Kattintson a Hozzáadás gombra.
11. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
12. Kattintson a Hozzáadás gombra.
13. A Szállítószámla mezőben adjon meg vagy válasszon ki egy értéket.
14. Kattintson a Küldés gombra.
15. Kattintson az OK gombra.
16. Kattintson a Válasz beírása gombra.
17. A Művelet panelen kattintson a Válasz elemre.
18. Kattintson az Adatok másolása a válaszba elemre.
    * Ez olyan adatokat másol a válaszhoz az ajánlatkérésből, mint például a mennyiség vagy a dátumok.  
19. Adjon meg egy számot az Egységár mezőben.
    * Ez a szállítótól kapott ár. További információkat is meg kell adnia a szállítóról.  
20. Kattintson az Elfogadás lehetőségre.
21. Kattintson az OK gombra.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Győződjön meg arról, hogy átkerült az ár és a szállító az igényléshez.
1. Zárja be a lapot.
2. Kattintson a Sorok pontra.
3. Kattintson a Kapcsolódó információ lehetőségre.
4. Kattintson a Beszerzési igénylés lehetőségre.
5. Válassza ki azt a sort, amelyet a rendszer átvitt az Ajánlatkéréshez.
    * Győződjön meg arról, hogy átmásolták az árat és a szállítót az igényléshez.  
6. A Munkafolyamat gombra kattintva megnyithatja a legördülő párbeszédablakot.
7. Kattintson a Befejezés gombra.
8. Zárja be a lapot.
9. Kattintson a Befejezés gombra.


