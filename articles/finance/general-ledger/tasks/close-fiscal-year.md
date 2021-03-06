---
title: A pénzügyi év lezárása
description: Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.
author: aprilolson
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f17b7fefb9251a28bfba9d0e93b9ad171ef7b9c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815188"
---
# <a name="close-the-fiscal-year"></a>A pénzügyi év lezárása

[!include [banner](../../includes/banner.md)]

Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.


## <a name="validate-year-end-close-parameters"></a>Ellenőrizze az év végi zárás paramétereit
1. Válassz a **Navigációs panel >Modulok > Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** lehetőséget.
2. Bontsa ki a **Pénzügyi év zárása** szakaszt.
3. Válassza az „Igen” vagy „Nem” lehetőséget az **Évzáró tranzakciók törlése átvezetés közben** beállításnál.
    
    Ha a pénzügyi év már le van zárva, és újrafuttatják az év végi zárást, ez a beállítás fontos. Ha Igen értékre van állítva, az előző év végi zárási bizonylat törlésre kerül, és az összes számla nyitóegyenlegéhez új bizonylat jön létre. Ha Nem értékre van állítva, a korábbi bizonylat megmarad, és új bizonylat csak az utolsó évlezárás után könyvelt tételek helyesbítéséhez jön létre.

4. Válassza az „Igen” vagy „Nem” elemet a **Záró tranzakciók létrehozása átvezetés közben** lehetőségnél.

    Ha Igen értékre van állítva, két tranzakció jön létre. Egy bizonylat jön létre a lezárás alatt álló pénzügyi évhez, hogy az eredménykimutatási főkönyvi számlák egyenlegét lenullázza, és egy második bizonylat is létrejön a következő pénzügyi évi nyitó egyenlegekhez. Ha Nem értékre van állítva, egyetlen bizonylat jön létre a következő pénzügyi évi nyitó egyenlegekhez.  

5. Válassza az „Igen” vagy „Nem” elemet a **Pénzügyi év beállítása véglegesen lezárt állapotúra** lehetőségnél.

    Ha Igen értékre van állítva, a pénzügyi év állapota „Véglegesen lezárva” lesz.  Mivel a véglegesen lezárt év nem nyitható meg újra, az ajánlott gyakorlat a beállítás Nem értékre állítása.  

6. Válassza „Igen” vagy „Nem” elemet a **Bizonylatszámot meg kell adni az év végi zárás során** lehetőségnél.

    Ha Igen értékre van állítva, a bizonylatszámot manuálisan kell megadni az év végi zárás során. Ennek a bizonylatszámnak a létrehozásához nem használatos számsorozat. Az ajánlott gyakorlat a beállítás Igen értékre állítása.  

7. Zárja be a lapot.
8. Ugorjon a **Főkönyv > Időszaki lezárás > Év végi lezárás** pontra.
9. Az év végi zárási sablon létrehozásához kattintson az **Új** gombra.

    Létrehozható egy sablon azon jogi személyek csoportjához, amelyhez az év zárást futtatni kívánjuk. Ez a sablon újra felhasználható évről évre.  

10. A **Csoport neve** mezőben adja meg egy év végi zárási sablon nevét.
11. A **Pénzügyi naptár** mezőben válassza ki azt az üzleti évet, amelyhez a sablont létre fogja hozna.

    Az év végi zárási sablonban csak olyan jogi személyeket lehet csoportosítani, amelyek ugyanazt a pénzügyi évet használják. Ennek oka, hogy az év zárása a pénzügyi év, nem pedig egy dátum kiválasztásával történik.  

12. A **Művelet panelen** kattintson a **Mentés** elemre.
13. A **Jogi személyek** szakaszban kattintson a **Hozzáadás** gombra a sablonhoz tartozó jogi entitások kijelöléséhez.
    
    Jogi személyek hozzáadhatók a kívánt jogi személyek vagy vagy szervezeti hierarchia kiválasztásával.  Csak az ugyanazt a pénzügyi naptárat használó szervezeti hierarchiába tartozó jogi személyek adhatók hozzá.  

14. Válassza ki a jogi személyeket vagy a szervezeti hierarchiát.
15. Kattintson az **OK** gombra.
16. Az **Mérlegdimenziók átvitele** helyen válassza az „igen” vagy a „nem” lehetőséget.

    Mérlegszámláknál az ajánlott gyakorlat a beállítás Igen értékre állítása. Ez megőrzi a feladott tranzakciók pénzügyi dimenzióit a mérlegszámlák nyitó egyenlegének létrehozásánál. Eredményszámláknál dönthet úgy, hogy megőrzi a pénzügyi dimenziókat (Az összes lezárása), amikor az egyenlegek átkerülnek a Mérleg szerinti eredménybe, illetve dönthet úgy, hogy a pénzügyi dimenziókat lecseréli egy eltérő dimenzióértékre (Egyetlen lezárása). Ha az Egyetlen lezárása lehetőséget választja, minden egyes dimenzióhoz megadhat egy dimenzióértéket, illetve dönthet úgy is, hogy üresen hagyja a mezőt.  

17. Kattintson a **Mentés** gombra.
18. A **Műveletpanelen** található **Pénzügyi zárás futtatása** kiválasztásával indítsa el az év végi zárást. Az év végi zárás lefut a kijelölt sablonon.  
19. Válassza ki az összes jogi személyt vagy egy részhalmazukat, amelyeken futtatni kívánja az év végi zárást.

    Amikor először futtatnak év végi zárást, a nyitó egyenlegek beszerzéséhez a legtöbb szervezet dönthet úgy, hogy az év végi zárást a sablonon belüli valamennyi jogi személyen lefuttatják. Ha ezután kiigazító tételekre kerül sor, dönthet úgy, hogy az év végi zárást csak azon jogi személyeken futtatja le, amelyeknél kiigazítások történtek.  

20. Kattintson az **OK** gombra.
21. Válassza ki a pénzügyi évet, amelyen futtatni kívánja az év végi zárást.
22. A **Bizonylat mezőben** adjon meg egy értéket. Az ajánlott gyakorlat a pénzügyi év belefoglalása a bizonylatszámba, mivel így könnyebb megtalálni a létrehozott év végi zárási bizonylatot.  
23. Az év végi zárás alapértelmezés szerint kötegelten fut. Az ajánlott gyakorlat a hosszú ideig futó folyamatok futtatását kötegelt módban végezni. Ez általában egyike ezeknek a folyamatoknak, ezért a kötegelt módban történő futtatás az alapértelmezett.  
24. Kattintson az **OK** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]