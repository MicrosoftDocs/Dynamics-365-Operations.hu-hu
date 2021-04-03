---
title: Értékesítési ajánlatok tömeges létrehozása
description: Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7aaa4e1fee12092be0389f0641e64712e869e6a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260359"
---
# <a name="mass-create-sales-quotations"></a>Értékesítési ajánlatok tömeges létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet hatékonyan árajánlatokat létrehozni termékek és szolgáltatásokat ajánlva, amelyek több vevőnek lesznek elküldve. Ez a tömeges árajánlatlétrehozás árajánlatsablonokon alapul. Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.


## <a name="create-a-quotation-template"></a>Árajánlatsablon létrehozása
1. Lépjen az Értékesítés és marketing > Beállítás > Árajánlatok > sabloncsoportok menüpontba.
2. Kattintson az Új lehetőségre.
3. A Csoportazonosító mezőben adjon meg egy tetszés szerinti azonosítót.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.
7. Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.
8. Kattintson az Új lehetőségre.
9. A Számla típusa mezőben válassza a Vevő lehetőséget.
10. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az OK gombra.
    * Ahhoz, hogy egy árajánlatból sablon legyen, el kell végezni bizonyos lépéseket az árajánlat fejlécében. Ezt az árajánlati sorok hozzáadása előtt kell elvégezni.   
12. A Művelet ablaktáblában kattintson a Beállítások elemre.
13. Kattintson a Nézetváltás elemre.
14. Kattintson a Fejlécnézet gombra.
15. Bontsa ki a Beállítások szakaszt.
16. A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.
17. Írjon be egy értéket a Sablonnév mezőbe.
18. Válassza ki az Igen lehetőséget az Aktív mezőben.
    * Csak aktív sablonok használható, amikor egy sablont alkalmaz egy új értékesítési árajánlatra.  
19. A Művelet ablaktáblában kattintson a Beállítások elemre.
20. Kattintson a Nézetváltás elemre.
21. Kattintson a Sor nézetre.
22. A Cikk mezőben adjon meg vagy válasszon ki egy értéket.
23. Írjon be egy értéket a Cikk mezőbe.
24. Zárja be a lapot.
25. Adjon meg egy számot az Engedményszázalék mezőben.
26. Kattintson az Új sor hozzáadására.
27. A Cikk mezőben adjon meg vagy válasszon ki egy értéket.
28. Írjon be egy értéket a Cikk mezőbe.
29. Zárja be a lapot.
30. Az Egységár mezőben adjon meg egy új árat, vagy módosítsa az aktuálisat.
31. Kattintson az Új sor hozzáadására.
32. A Cikk mezőben adjon meg vagy válasszon ki egy értéket.
33. Írjon be egy értéket a Cikk mezőbe.
34. Zárja be a lapot.
35. Adjon meg egy számot a Mennyiség mezőben.
36. Adjon meg egy számot az Engedmény mezőben.
37. Kattintson a Mentés gombra.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Sablon alkalmazása egyetlen árajánlat létrehozásához
1. Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.
    * Vegye figyelembe, hogy az imént létrehozott ajánlat sablonként van megjelölve.  
2. Kattintson az Új lehetőségre.
3. A Számla típusa mezőben válassza a Vevő lehetőséget.
4. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
5. Bontsa ki a Sablon szakaszt.
6. A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.
7. A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.
8. A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.
9. Kattintson az OK gombra.
    * Az új ajánlat létrehozása megtörtént, a sablon adatai és feltételei alapján.  
10. Zárja be a lapot.
11. Zárja be a lapot.

## <a name="apply-the-template-to-mass-create-quotations"></a>Sablon alkalmazása tömeges árajánlatlétrehozáshoz
1. Lépjen az Értékesítés és marketing > Értékesítési ajánlatok > Árajánlatfrissítés > Ajánlatok tömeges létrehozása menüpontba.
2. A Számla típusa mezőben válassza a Vevő lehetőséget.
3. A Csoportazonosító mezőben adjon meg, vagy válasszon ki egy értéket.
4. A Sablonnév mezőben adjon meg vagy válasszon ki egy értéket.
5. A Számítási mód mezőben válassza ki a „Sablonértékek alapján” lehetőséget.
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Kattintson a Szűrő parancsra.
8. A Feltétel mezőben állítsa a szűrőt úgy, hogy lefedje a vevők azon tartományát, amelyet bele akar foglalni ebbe a tömeges árajánlatlétrehozásba. A következő formátumot használja: "Customer1... CustomerN.
    * Például beállítja a szűrést erre: US-001..US-004  
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.
11. Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.
    * Győződjön meg róla, hogy az a kiválasztott sablonon alapján a tömeges frissítési rutinban megadott minden vevőhöz lett árajánlat létrehozva.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]