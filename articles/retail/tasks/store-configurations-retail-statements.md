--- 
title: " Konfigurációk tárolása kiskereskedelmi kimutatásokhoz"
description: "Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 441ba692f559f9966f3e2512c7760ad2f732b768
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="store-configurations-for-retail-statements"></a> Konfigurációk tárolása kiskereskedelmi kimutatásokhoz

[!include [task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi-üzlet konfigurációkat mutatja be. A Kiskereskedelmi üzletekkel kapcsolatos pénzügyi dimenziókat egy másik eljárás mutatja be. Ez az eljárás az USRT bemutatócéget használja.

1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A Kimutatás/zárás szakasz beállításai hatással vannak a kimutatások létrehozására, ellenőrzésére és az üzlet részére történő feladására.  Nyissa meg a Kimutatás/zárás szakaszt.  
    * Válassza ki a kimutatássorok csoportosításához használni kívánt módszert.  
    * Válassza az "Igen" lehetőséget, ha csak napi egy kimutatást szeretne létrehozni amikor a kimutatás létrehozása kötegelt feladat segítségével hoz létre kimutatásokat.  
    * A fizetőeszköz-elszámolás számítási mező határozza meg, hogy a rendszer összeadja-e a fizetőeszköz-elszámolásokat, vagy az utolsó elemet használja.  
    * Állítsa be, hogy a kerekítési különbségek a főkönyvi számlába kerüljenek feladásra.  
    * A Kerekítés maximális összege mezőben megadhatja a maximálisan megengedett kerekítési összeget.  
    * A Feladás mezőben megadhatja egy adott kimutatás esetén engedélyezett maximális teljes feladási eltérést.  
    * A Műszak mezőben megadhatja egy adott műszak esetén engedélyezett maximális teljes eltérést.  
    * A Tranzakció mezőben megadhatja egy adott kimutatás sorban engedélyezett maximális teljes eltérést.  
    * A Zárási mód mezőben meghatározhatja, hogy a kimutatásban csak lezárt műszak részét képező tranzakciók szerepelhessenek-e, vagy bekerülhessen bármilyen, az adott dátum/idősávba eső tranzakció.  
    * A Munkanap vége mezőben tud megadni megfelelő időpontot, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra.  
    * Válassza az „Igen” lehetőséget, ha azt szeretné, hogy az éjfél utáni tranzakciók az előző napra vonatkozóan kerüljenek feladásra  
    * Válassza az „Igen” lehetőséget, ha szeretné, hogy a rendszer hozzon létre kimutatást minden megjelölt kimutatásmódszer segítségével. Ez akkor lehet hasznos, ha a feladás teljesítményét javítani szükséges a magas tranzakciószámmal működő üzletek esetében, így ugyanis a rendszer több kisebb, párhuzamosan feldolgozható kimutatást hoz létre.  
    * Az Alapértelmezett vevő mezőben tudja kiválasztani az utcáról betérő vevőkhöz használni kívánt vevőszámlát.  


