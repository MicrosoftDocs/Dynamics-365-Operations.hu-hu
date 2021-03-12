---
title: Ajánlatok hozzáadása a tranzakciós képernyőhöz
description: Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 Commerce képernyő-elrendezés tervezőjének használatával.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2e1ef6506833b35e61351600553a3bc29c20d5b2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980232"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Ajánlatok hozzáadása a tranzakciós képernyőhöz

[!include [banner](includes/banner.md)]


Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 Commerce képernyő-elrendezés tervezőjének használatával. A termék ajánlásaival kapcsolatos további tudnivalók: [Termékajánlások a POS-dokumentációban](product.md).


A Commerce használata esetén megjeleníthet termékajánlásokat a pénztáreszközön. Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével. 

## <a name="open-layout-designer"></a>Az Elrendezéstervező megnyitása

1. Lépjen a **Kiskereskedelem és kereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.
2. A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt. Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre az **F2CP16:9M** érték használatával.
3. Keresse meg és jelölje ki a kívánt rekordot a listán. Például válassza a **Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M** lehetőséget.
4. Kattintson az **Elrendezéstervező** elemre.
5. Kövesse az utasításokat az elrendezéstervező elindításához. Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.
6. A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg. Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.


    [![Elrendezéstervező](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Válasszon ki egy megjelenítési beállítást

Két konfigurációs lehetőség áll rendelkezlésre. Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez. A két lehetőség:

- Ajánlások mindig láthatók.
- Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.

### <a name="make-recommendations-always-visible"></a>Az ajánlások mindig láthatóvá tétele


1. Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.


    [![A tranzakciós sorok részletezési területének magassága csökkentve](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé. Méretezze át a vezérlőt, hogy elférjen.

    [![Javaslatok vezérlő az elrendezéshez adva](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
4. A Commerce-ben ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra.
5. Válassza az **1090, Pénztárgépek** elemet.
6. Kattintson a **Futtatás most** elemre.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Egy Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz

1. Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.

2. Kattintson a **Testreszabás** lehetőségre.

    [![Testreszabás – Lapvezérlő párbeszédpanel](./media/pic-5.png)](./media/pic-5.png)

3. Kattintson az **Új lap** elemre.
4. Keresse meg a most felvett új lapot. Ehhez lehet, hogy le kell görgetnie.
5. A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet.

    [![Javasolt termékek kiválasztása a Tartalmak mezőben](./media/pic-6.png)](./media/pic-6.png)

6. A **Címke** mezőben adjon meg egy nevet a javaslatok lapnak Például „Javasolt termékek”.
7. A **Kép** mezőben válassza ki a lapon megjelenítendő képet.
8. Kattintson az **OK** gombra. Az új lap megjelenik a gombrácsban.
9. Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
10. A Commerce-ben ugorjon a **Kiskereskedelem és kereskedelem** &gt; **Kiskereskedelem és kereskedelem informatika** &gt; **Elosztási ütemezés** pontra.
11. Válassza az **1090, Pénztárgépek** elemet.
12. Kattintson a **Futtatás most** elemre.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)
