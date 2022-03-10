---
title: Konfigurációk megújítása jelentések készítéséhez Office formátumban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan tervezhetők jelentéskészítési konfigurációk beágyazott képeket tartalmazó elektronikus dokumentumok létrehozására. (1. rész – Paraméterek beállítása).
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f209fcbac310dffb654f7830a4d4b12fa95d7a461b681864b8c9b547f4a4986c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717570"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Konfigurációk megújítása jelentések készítéséhez Office formátumban, beágyazott képekkel

[!include [banner](../../includes/banner.md)]

A lépések végrehajtásához először végre kell hajtani az „ER – Jelentések létrehozása Microsoft Office-formátumokban, beágyazott képekkel (1. rész: Paraméterek beállítása)” feladat-útmutató lépéseit.

Ez az eljárás azt mutatja be, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk Microsoft Excel és Microsoft Word programokban beágyazott képeket tartalmazó elektronikus dokumentumok létrehozására. Ebben a példában áttekintjük a szükséges ER-konfigurációkat a Litware, Inc. mintavállalatra vonatkozóan. 

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználók számára készült. A lépések a USMF-adathalmazzal hajthatók végre.


## <a name="review-the-imported-data-model"></a>Az importált adatmodell ellenőrzése
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza ki ezt: „Model for cheques”.
3. Kattintson a Tervező pontra.
    * Ezt a modellt arra tervezték, hogy a fizetési csekkeket képviselje üzleti szempontból, valamint a modell hozzárendelését az alkalmazás adatforrásaihoz. Tekintse át az ER műveletek készítőjétől származó modellt. Figyelje meg a megjelenő modellelemek attribútumait: szerkezet, név, leírás, adattípus és így tovább.   
4. A fastruktúrában bontsa ki ezt: „root”.
5. A fában válassza ki ezt: „root\cheques”.
6. A fában bontsa ki a „root\cheques” elemet.
7. A fában bontsa ki a „root\cheques\attributes” elemet.
8. A fastruktúrában bontsa ki a „root\payer” csomópontot.
9. A fastruktúrában válassza ki ezt: „root\istestrun”.
10. A fastruktúrában válassza ki a „root\layout” csomópontot.
    * Ennek a modellnek az elrendezés eleme képviseli nyomtatott csekkformátum-elrendezést a kiválasztott bankszámla számára. Emellett két tároló adattípusú csomópont is tartalmaz képek tárolásához.   
11. A fastruktúrában bontsa ki a „root\layout” csomópontot.
12. A fastruktúrában válassza ki ezt: „root\layout\company logo”.
13. A fastruktúrában bontsa ki ezt: „root\layout\company logo”.
14. A fastruktúrában válassza ki ezt: „root\layout\company logo\image”.
15. A fastruktúrában válassza ki ezt: „root\layout\company logo\isprinted”.
16. A fastruktúrában válassza ki ezt: „root\layout\signature”.
17. A fában bontsa ki a „root\layout\signature” elemet.
18. A fastruktúrában válassza ki ezt: „root\layout\signature\image”.
19. A fastruktúrában válassza ki ezt: „root\layout\signature\isprinted”.
    * Megjegyzés: a két kép adatmodellelem a tábláknak azokhoz a mezőihez van kötve, amelyek a vállalati emblémának és a jogosult személy aláírásának a képét tartalmazzák bináris formátumban.  
20. A fában bontsa ki a „root\layout\watermark” elemet.
21. Kattintson a Modell hozzárendelése adatforráshoz gombra.
22. Kattintson a Tervező pontra.
23. A fában bontsa ki a „chequesselected” elemet.
24. A fastruktúrában bontsa ki ezt: „layout”.
25. A fastruktúrában bontsa ki ezt: „layout\company logo”.
26. A fában bontsa ki az „layout\signature” elemet.
27. A fában bontsa ki a „layout\watermark” elemet.
28. Kapcsolja be a Részletek megjelenítése lehetőséget.
    * Megjegyzés: a csekkek adatmodellelem a TmpChequePrintout táblához van kötve, amely futásidőben azoknak a csekkeknek a rekordjait fogja tartalmazni, amelyeket a felhasználó kijelölt a nyomtatáshoz.   
29. Zárja be a lapot.
30. Zárja be a lapot.
31. Zárja be a lapot.

## <a name="review-the-imported-format"></a>Tekintse át az importált formátumot
1. A fastruktúrában bontsa ki ezt: „Model for cheques”.
2. A fában válassza ki ezt: „Model for cheques\Cheques printing format”.
3. Kattintson a Tervező pontra.
4. Kattintson a Mellékletek lehetőségre.
5. Kattintson a Megnyitás gombra.
    * Nyissa meg a csatolt jelentés sablonját az Excel alkalmazásban.  
    * Tekintse át a csatolt jelentés Excel-sablonját, amelyet a rendszer a csekkek nyomtatásához fog használni. A sablon oldalanként két csekket tartalmaz, és a célja az, hogy az előre nyomtatott űrlapra csekkeket nyomtasson. Vegye figyelembe, hogy két üres kép beágyazott. Ezek az üres képek a vállalati emblémának és a kifizetést jóváhagyó személy aláírásának vannak fenntartva. Győződjön meg arról, hogy a képeket neve CompLogo és SignatureImage, az Excel programban.   
6. Zárja be a lapot.
7. A fastruktúrában bontsa ki ezt: „Report”.
8. A fában bontsa ki a „Report\ChequeLines” elemet.
9. A fastruktúrában válassza ki ezt: „Report\ChequeLines\CompLogo”.
10. Kapcsolja be a Részletek megjelenítése lehetőséget.
    * Vegye figyelembe, hogy a ‘CompLogo’ formátum cellaeleme felel meg annak az Excel-elemnek, amelynek a használatával a jelentés feltöltése történik a vállalati embléma képével. Ez a formátumelem ahhoz a képadatmodellhez van kötve, amely futásidőben tartalmazza a vállalati embléma képét bináris formátumban.   
11. Kattintson a Hozzárendelés fülre.
12. Kattintson a Szerkesztés engedélyezve elemre.
    * Vegye figyelembe, hogy a 'CompLogo' formátum cellaelemét nincs engedélyezve beállításra módosíthatja. Ebben az esetben a társított Excel képelem elrejti a létrehozott jelentésben a cég emblémáját. Ha az engedélyezett kifejezés IGAZ értéket ad vissza, és a megadott kötés nem hoz képet, a társított Excel-képelem egy, az Excel-sablonban mentett képet jelenít meg.   
13. Zárja be a lapot.
14. A fában bontsa ki a „labels: Container” elemet.
    * Az előre nyomtatott csekk űrlapon megjelenő néhány címke szerepelni fog a jelentésben, amikor létrehozzák tesztelési célra. Azonban ezeket a címkéket a rendszer nem nyomtatja ki a tényleges nyomtatás közben, mert az előre nyomtatott űrlap már tartalmazza őket.  
15. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]