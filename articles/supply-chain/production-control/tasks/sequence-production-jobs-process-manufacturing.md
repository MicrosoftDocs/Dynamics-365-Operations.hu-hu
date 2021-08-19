---
title: Termelési feladatok sorrendje a folyamatszerű gyártáshoz
description: Ez az eljárásban példaként festék termékeket használ, hogy bemutassa, hogy hogyan lehet a szín és a csomag méretének prioritása szerint a tervezett rendeléseket rendezni.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 880db0852f569c2d091b2906be9e370259c0d7d3fc8c977cf1e240e4b2f34128
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747817"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a>Termelési feladatok sorrendje a folyamatszerű gyártáshoz

[!include [banner](../../includes/banner.md)]

Ez az eljárásban példaként festék termékeket használ, hogy bemutassa, hogy hogyan lehet a szín és a csomag méretének prioritása szerint a tervezett rendeléseket rendezni. Ez az eljárás az USPI bemutatócéget használja. Ezt az eljárást a termeléstervező használja.


## <a name="run-master-planning-for-uspi"></a>Az Alaptervezés futtatása az USPI-re vonatkozóan
1. Ugorjon az Alaptervezés > Alaptervezés > Futtatás > Alaptervezés pontra.
2. Az Alapterv mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * MasterPlan kiválasztása.  
4. Kattintson az OK gombra.
    * Ez indítja el az Alaptervezést a sorozat folyamatával együtt. Ez a folyamat néhány percig is eltarthat.  

## <a name="view-planned-orders-for-the-paint-products"></a>A festék termékek tervezett rendeléseinek megtekintése
1. Ugorjon az Alaptervezés > Alaptervezés > Tervezett rendelések pontra.
2. Bontsa ki a Cikk részletei adatterületet.
3. Bontsa ki az Ütemezés részletei adatterületet.
4. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * MasterPlan kiválasztása.  
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. A Gyorsszűrő használatával szűrjön rá a P300 értékű Cikkszám mezőkre.
    * Oldja fel a jobbra görgetéshez a rendelési dátum és a szállítási dátum megtekintéséhez. Vegye figyelembe, hogy ezek a cikkek egy Mai rendelési dátummal rendelkeznek és a tervezett megrendelések szállítási dátumai nincsenek rendezve a szín és a csomag méret prioritása után, ahogyan ez a termék nevében látható. Egy cikkszám fölé viheti a mutatót a termék nevének és prioritásának megtekintéséhez.  

## <a name="sequence-planned-orders-for-paint"></a>A szekventált tervezett rendelések a festésre vonatkozóan
1. Zárja be a lapot.
2. Ugorjon az Alaptervezési > Alaptervezés > Szekventált tervezett rendelések pontra.
3. Bontsa ki a Cikk részletei adatterületet.
4. Bontsa ki az Ütemezés részletei adatterületet.
    * Megjegyzés: Itt láthatja, hogy a tervezett rendelések kezdő dátumát/idejét a szín és a csomag méretének megfelelően egy 28 napos időszakon belül rendezték. A Kampány mezőben egy számmal határozták meg ezeket az időszakokat. A szekventált tervezett rendelés forma szokásos tervezett rendelési képernyőként működik, és a termeléstervező itt erősheti meg a tervezett rendeléseket.  
5. Az összes sor megjelölése.
6. Kattintson az Elfogadás lehetőségre.
    * Ez az eljárás a tervezett rendeléseket vagy az Elhalasztás vagy az Előleg kijelölt sorozatművelettel frissíti.  

## <a name="verify-the-sequence-of-the-planned-orders"></a>Ellenőrizze a tervezett rendelések sorrendjét
1. Zárja be a lapot.
2. Ugorjon az Alaptervezés > Alaptervezés > Tervezett rendelések pontra.
3. Bontsa ki a Cikk részletei adatterületet.
4. Bontsa ki az Ütemezés részletei adatterületet.
5. A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * MasterPlan kiválasztása.  
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Gyorsszűrő használatával szűrjön rá a P300 értékű Cikkszám mezőkre.
    * Vegye figyelembe, hogy a rendelések rendezése már a szín vagy a méret prioritása szerint megtörtént és a tervezett rendelések a lehető legkorábbi rendelési- és szállítási dátum napján elkezdődtek. Ellenőrizze a Rendelési dátum oszlopát vagy a Kezdő dátumot az Ütemezés részletei FactBoxban.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]