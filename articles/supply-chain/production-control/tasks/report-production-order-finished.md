---
title: Termelési jelentés készként jelenítése
description: Ez az eljárás bemutatja, hogyan lehet készre jelenteni egy termelési rendelést.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4848093bd4901d3aa801fc09d7ee3e79d65ebb0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204457"
---
# <a name="report-a-production-order-as-finished"></a>Termelési jelentés készként jelenítése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet készre jelenteni egy termelési rendelést. Ez az eljárás az USMF bemutatócéget használja. Ez a hatodik eljárás abból a hétből, amely bemutatja a termelési rendelés életciklusát.


## <a name="report-a-production-order-as-finished"></a>Termelési jelentés készként jelenítése
1. Ugrás a Gyártásvezérlés > Termelési rendelések > Minden termelési rendelésre.
    * Válasszon ki egy Elindítva állapotú termelési rendelést.  
2. A Művelet panelen kattintson a Termelési rendelés elemre.
3. Kattintson a Jelentés készként lehetőségre.
    * Ezen a lapon megerősítheti a készre jelentendő késztermékek mennyiségét.  
4. Kattintson az Általános fülre.
5. Állítsa a Jó mennyiséget a „18” értékre.
6. Állítsa a Hiba mennyiséget a „2” értékre.
7. A Hibaok mezőben válassza az „Anyag” lehetőséget.
8. Válassza ki vagy törölje a Záró feladat jelölőnégyzetet.
9. Válassza ki vagy törölje a Hiba elfogadása jelölőnégyzetet.
10. Kattintson az OK gombra.

## <a name="verify-the-report-as-finished-journal"></a>A Készre jelentés napló ellenőrzése
1. A Művelet panelen kattintson a Nézet elemre.
2. Kattintson a Készre jelentett lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A Készre jelentés napló feladásra kerül. Ha módosítani szeretné a naplót, akkor manuálisan létrehozhat egy új naplót, ahol elvégezheti a módosításokat.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]