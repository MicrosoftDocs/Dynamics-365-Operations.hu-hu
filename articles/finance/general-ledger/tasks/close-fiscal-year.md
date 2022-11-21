---
title: A pénzügyi év lezárása
description: Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.
author: aprilolson
ms.date: 11/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d52e6789a96defaf1d0132fe97fc183a05af207
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779812"
---
# <a name="close-the-fiscal-year"></a>A pénzügyi év lezárása

[!include [banner](../../includes/banner.md)]

Ez a folyamat bemutatja az év végi zárás folyamatát, amely az egyenlegeket áthelyezi az új pénzügyi évbe.


## <a name="validate-year-end-close-parameters"></a>Ellenőrizze az év végi zárás paramétereit
1. Válassz a **Navigációs panel >Modulok > Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** lehetőséget.
2. Bontsa ki a **Pénzügyi év zárása** szakaszt.
3. Válassza az Igen vagy a Nem **lehetőséget** az Évzárási tranzakciók törlése az átvitel során beállításnál **.** **·**
    
Ha a pénzügyi év már le van zárva, és újrafuttatják az év végi zárást, ez a beállítás fontos. Ha Igen beállításra **van** állítva, a program törli az előző év végi zárás bizonylatát, és új bizonylatot hoz létre minden kezdő egyenleghez. Ha Nem beállításra **van** beállítva, az előző bizonylat megmarad, és egy új bizonylat csak a legutóbbi év végi zárás után feladott bejegyzések módosítására lesz létrehozva.

4. Válassza az Igen vagy a Nem **lehetőséget a Záró** tranzakciók létrehozása átátvitel során beállításhoz **.** **·**

Igen beállítás esetén **két** tranzakció jön létre. A lezárt pénzügyi évben létrejön egy bizonylat, amely az összes főkönyvi számla egyenlegét nullára állítja, és egy másik bizonylatot hoz létre a következő pénzügyi évben a kezdő egyenlegekhez. Ha a Nem **érték van** beállítva, a következő pénzügyi évben a kezdő egyenlegekhez egyetlen bizonylat jön létre.  

5. Válassza az **Igen** vagy **a Nem** lehetőséget **a Pénzügyi év beállítása véglegesen lezárt állapotúra** beállításhoz.

Ha Igen beállításra **van** állítva, a pénzügyi év állapota **Véglegesen lezárt lesz**. Mivel egy véglegesen lezárt évet nem lehet újra megnyitni, ezért a **beállítást** Nem beállítással ajánlott beállítani.  

6. Az **Igen vagy** **a** Nem **lehetőséget választva a bizonylatszámot ki kell tölteni az év végi zárás beállításában**.

Igen beállítás esetén **az** év végi zárási folyamat során manuálisan kell megadni egy bizonylatszámot. Ennek a bizonylatszámnak a létrehozásához nem használatos számsorozat. Ezt ajánlott Igen beállítással **beállítani**.  

7. Zárja be a lapot.
8. Ugorjon a **Főkönyv > Időszaki lezárás > Év végi lezárás** pontra.
9. Az év végi zárási sablon létrehozásához kattintson az **Új** gombra.

Létrehozható egy sablon azon jogi személyek csoportjához, amelyhez az év zárást futtatni kívánjuk. Ez a sablon újra felhasználható évről évre.  

10. A Csoportnév **mezőbe** írja be az év végi lezáró sablon nevét.
11. A **Pénzügyi naptár** mezőben válassza ki azt az üzleti évet, amelyhez a sablont létre fogja hozna.

Az év végi zárási sablonban csak olyan jogi személyeket lehet csoportosítani, amelyek ugyanazt a pénzügyi évet használják. Ennek oka, hogy az év zárása a pénzügyi év, nem pedig egy dátum kiválasztásával történik.  

12. A **Művelet panelen** kattintson a **Mentés** elemre.
13. A **Jogi személyek** szakaszban kattintson a **Hozzáadás** gombra a sablonhoz tartozó jogi entitások kijelöléséhez.
    
Jogi személyek hozzáadhatók a kívánt jogi személyek vagy vagy szervezeti hierarchia kiválasztásával. Csak az ugyanazt a pénzügyi naptárat használó szervezeti hierarchiába tartozó jogi személyek adhatók hozzá.  

14. Válassza ki a jogi személyeket vagy a szervezeti hierarchiát.
15. Kattintson az **OK** gombra.
16. Válassza az **Igen** vagy a **Nem** lehetőséget **a Mérlegátadás dimenzióban**.

A mérlegszámlák **esetében** ajánlott Igen beállításra állítani ezt a beállítást. Ez megőrzi a feladott tranzakciók pénzügyi dimenzióit a mérlegszámlák nyitó egyenlegének létrehozásánál. Eredményszámlák esetében meg lehet őrizni a pénzügyi dimenziókat (**Az** összes bezárása), amikor az egyenlegek átkerülnek a pénzügyi eredményhez, vagy választhatja azt, hogy a pénzügyi dimenziókat egy másik dimenzióértékre váltsa (**Egyetlen** lezárás). Ha a Kis értékű **lezárás** lehetőséget választja, minden dimenzióhoz meghatározhat egy meghatározott dimenzióértéket, vagy akár üresen is hagyhatja.  

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
