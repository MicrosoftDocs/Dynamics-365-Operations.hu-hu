---
title: "Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján"
description: "Ez a témakör ismerteti, hogyan adható hozzá ajánlások vezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Operations képernyő-elrendezés tervezőjének használatával."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Ajánlások vezérlő hozzáadása egy POS-eszköz tranzakció lapján

[!include[banner](includes/banner.md)]


Ez a témakör ismerteti, hogyan adható hozzá ajánlások vezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Operations képernyő-elrendezés tervezőjének használatával.

A Microsoft Dynamics 365 for Operations használata esetén megjeleníthet termékajánlásokat a POS-eszközön. Az *Ajánlások* olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben. Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével.

## <a name="open-layout-designer"></a>Az Elrendezéstervező megnyitása
1.  Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.
2.  A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt. Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre „F2CP16:9M” érték használatával.
3.  Keresse meg és jelölje ki a kívánt rekordot a listán. Például válassza a „Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M” lehetőséget.
4.  Kattintson az **Elrendezéstervező** elemre.
5.  Kövesse az utasításokat az elrendezéstervező elindításához. Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.
6.  A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg. Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Válasszon megjelenítési beállítást
-----------------------

Két konfigurációs lehetőség áll rendelkezlésre. Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez. A két lehetőség:
-   Ajánlások mindig láthatók.
-   Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.

#### <a name="to-make-recommendations-always-visible"></a>Ajánlások mindig láthatóvá tétele

1.  Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé. Méretezze át a vezérlőt, hogy elférjen.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
4.  A Dynamics 365 for Operationsben lépjen a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelmi IT** &gt; **Elosztási ütemezések** elemre.
5.  Válassza az **1090, Pénztárgépek** elemet.
6.  Kattintson a **Futtatás most** elemre.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Az Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz

1.  Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.
2.  Kattintson a **Testreszabás** elemre.[![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Kattintson az **Új lap** elemre.
4.  Keresse meg a most felvett új lapot. Ehhez lehet, hogy le kell görgetnie.
5.  A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet. [![pic-6](./media/pic-6.png)](./media/pic-6.png)
6.  A **Címke** mezőben adjon nemet az ajánlások lapnak. Írja be például: „Ajánlott termékek”.
7.  A **Kép** mezőben válassza ki a lapon megjelenítendő képet.
8.  Kattintson az **OK** gombra. Az új lap megjelenik a gombrácsban.
9.  Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
10. A Dynamics 365 for Operationsben lépjen a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelmi IT** &gt; **Elosztási ütemezések** elemre.
11. Válassza az **1090, Pénztárgépek** elemet.
12. Kattintson a **Futtatás most** elemre.


<a name="see-also"></a>Lásd még
--------

[Személyre szabott termékajánlások áttekintése](personalized-product-recommendations.md)




