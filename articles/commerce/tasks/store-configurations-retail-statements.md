---
title: " Konfigurációk tárolása kiskereskedelmi kimutatásokhoz"
description: Ez az eljárás a Commerce kimutatások létrehozásának és feladásának módját befolyásoló üzleti konfigurációkat mutatja be.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 57081b9e737373641cd9d884919d03dcf62a2ffe
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140655"
---
# <a name="store-configurations-for-retail-statements"></a> Konfigurációk tárolása kiskereskedelmi kimutatásokhoz

[!include [banner](../includes/banner.md)]

Ez az eljárás a Commerce kimutatások létrehozásának és feladásának módját befolyásoló üzleti konfigurációkat mutatja be. Az üzletekkel kapcsolatos pénzügyi dimenziókat egy másik eljárás mutatja be. Ez az eljárás az USRT bemutatócéget használja.

1. A **Navigációs ablaktáblán** lépjen a **Modulok > Retail és Commerce > Csatornák > Áruházak > Minden áruház** részhez.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a **Szerkesztés** lehetőségre.
5. A **Kimutatás/zárás** gyorslap beállításai hatással vannak a kimutatások létrehozására, ellenőrzésére és az üzlet részére történő feladására. Bontsa ki a **Kimutatás/zárás**gyorslapot.  
6. A **Kimutatás módszere** mezőben válassza ki a kimutatássorok csoportosításához használni kívánt módszert.  
7. Válassza az "Igen" lehetőséget a **Naponta egy kimutatás** pontban, ha csak napi egy kimutatást szeretne létrehozni, amikor a kimutatás létrehozása kötegelt feladat segítségével hoz létre kimutatásokat.  
8. A **Fizetőeszköz-elszámolási számítás** mező határozza meg, hogy a rendszer összeadja-e a fizetőeszköz-elszámolásokat, vagy az utolsó elemet használja.  
9. A **Kerekítés** mezőben válassza ki, hogy a kerekítési különbségek a főkönyvi számlába kerüljenek.  
10. A **Kerekítés maximális összege** mezőben megadhatja a maximálisan megengedett kerekítési összeget.
11. A **Feladás** mezőben megadhatja az adott kimutatás esetén engedélyezett maximális teljes feladási eltérést.
12. A **Műszak** mezőben megadhatja egy adott műszak esetén engedélyezett maximális teljes eltérést.  
13. A **Tranzakció** mezőben megadhatja az adott kimutatássorban engedélyezett maximális teljes eltérést.  
14. A **Zárási mód** mezőben meghatározhatja, hogy a kimutatásban csak lezárt műszak részét képező tranzakciók szerepelhessenek-e, vagy bekerülhessen bármilyen, az adott dátumsávba/idősávba eső tranzakció.  
15. A **Munkanap vége** mezőben tud megadni megfelelő időpontot, ha azt szeretné, hogy az éjfél utáni tranzakciókat az előző napra vonatkozóan adja fel a rendszer.  
16. Válassza az „Igen” lehetőséget a **Feladás munkanapként** pontban, ha azt szeretné, hogy az éjfél utáni tranzakciókat az előző napra vonatkozóan adja fel a rendszer.  
17. Válassza az „Igen” lehetőséget a **Kimutatás szerinti bontás módszere** pontban, ha szeretné, hogy a rendszer hozzon létre kimutatást minden megjelölt kimutatásmódszer segítségével. Ez akkor lehet hasznos, ha a feladás teljesítményét javítani szükséges a magas tranzakciószámmal működő üzletek esetében, így ugyanis a rendszer több kisebb, párhuzamosan feldolgozható kimutatást hoz létre.  
18. Az **Általános** gyorslapon az **Alapértelmezett vevő** mezőben tudja kiválasztani az utcáról betérő vevőkhöz használni kívánt vevőszámlát.  

