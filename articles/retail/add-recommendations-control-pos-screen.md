---
title: Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez
description: Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 213b47422a5e31c2cfc2d173b8c7d9efdecc7568
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573372"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a>Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez

[!include [banner](includes/banner.md)]

> [!NOTE]
> A termékajánló szolgáltatás jelenlegi verzióját eltávolítjuk, mivel ezt a funkciót jobb algoritmussal és újabb kiskereskedelmi orientált képességekkel újratervezzük. További információ: [Eltávolított vagy elavult funkciók](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).

Ez a témakör ismerteti, hogyan adható hozzá ajánlásvezérlő a tranzakciós képernyőhöz pénztári (POS) eszközön a Microsoft Dynamics 365 for Retail képernyő-elrendezés tervezőjének használatával.

A Microsoft Dynamics 365 for Retail használata esetén megjeleníthet termékajánlásokat a pénztáreszközön. Az *Ajánlások* olyan elemek, amelyek érdekelhetik a vevőt a vásárlási előzmények alapján, a kívánságlistájukon levő elemek alapján, illetve olyan elemek alapján, amelyeket más felhasználók vásároltak meg online vagy hagyományos üzletekben. Termékajánlások megjelenítéséhez vezérlőt kell hozzáadni a tranzakciós képernyőhöz a képernyő-elrendezés tervezőjének segítségével.

## <a name="open-layout-designer"></a>Az Elrendezéstervező megnyitása

1. Lépjen a **Kiskereskedelem** &gt; **Csatornabeállítás** &gt; **Pénztárbeállítás** &gt; **Pénztár** &gt; **Képernyő-elrendezések** lehetőségre.
2. A vezérlővel bővíteni kívánt képernyő megkereséséhez használja a gyorsszűrőt. Például szűrjön a **Képernyő-elrendezés azonosítója** mezőre „F2CP16:9M” érték használatával.
3. Keresse meg és jelölje ki a kívánt rekordot a listán. Például válassza a „Név: F2CP16:9M Képernyő-elrendezés azonosítója: F2CP16:9M” lehetőséget.
4. Kattintson az **Elrendezéstervező** elemre.
5. Kövesse az utasításokat az elrendezéstervező elindításához. Amikor a rendszer kéri a hitelesítő adatokat, adja meg ugyanazokat a hitelesítő adatokat, amelyekkel az Elrendezéstervezőt a **Képernyő-elrendezések** oldalról elindította.
6. A bejelentkezéstkor az alábbihoz hasonló oldal jelenik meg. Az elrendezés a bolthoz végzett testreszabásoktól függően eltérő lesz.

    [![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Válasszon ki egy megjelenítési beállítást

Két konfigurációs lehetőség áll rendelkezlésre. Válassza azt a lehetőséget, amely a legjobban illik a bolthoz, és kövesse a további utasításokat a vezérlő beállításának befejezéséhez. A két lehetőség:

- Ajánlások mindig láthatók.
- Az **Ajánlások** lap megjelenik a rácsban a képernyő jobb oldalán.

### <a name="make-recommendations-always-visible"></a>Az ajánlások mindig láthatóvá tétele

1. Csökkentse a tranzakciós sorok részletei terület magasságát úgy, hogy a tőle balra eső ügyfélpanellel egyforma magas legyen.

    [![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. A bal oldali menüből húzza az ajánlások vezérlőt a tranzakciós sor részletei terület és a tranzakciós képernyőn lent középen látható gombrács közé. Méretezze át a vezérlőt, hogy elférjen.

    [![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)

3. Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
4. A Dynamics 365 for Retail alkalmazásban lépjen a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.
5. Válassza az  **1090, Pénztárgépek** elemet.
6. Kattintson a **Futtatás most** elemre.

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Egy Ajánlások lap hozzáadása a képernyő jobb oldalán látható gombrácshoz

1. Kattintson a jobb gombbal az oldal jobb oldalán található gombrács utolsó lapja alatti üres területre.
2. Kattintson a **Testreszabás** lehetőségre.

    [![pic-5](./media/pic-5.png)](./media/pic-5.png)

3. Kattintson az **Új lap** elemre.
4. Keresse meg a most felvett új lapot. Ehhez lehet, hogy le kell görgetnie.
5. A **Tartalom** legördülő menüben válassza az **Ajánlott termékek** elemet.

    [![pic-6](./media/pic-6.png)](./media/pic-6.png)

6. A **Címke** mezőben adjon meg egy nevet a javaslatok lapnak Például „Javasolt termékek”.
7. A **Kép** mezőben válassza ki a lapon megjelenítendő képet.
8. Kattintson az **OK** gombra. Az új lap megjelenik a gombrácsban.
9. Az **X** gombra kattintva zárja be az Elrendezéstervezőt.
10. A Dynamics 365 for Retail alkalmazásban lépjen a **Kiskereskedelem** &gt; **Kiskereskedelem IT** &gt; **Elosztási ütemezés** pontra.
11. A listában válassza a **1090, Pénztárgépek** elemet.
12. Kattintson a **Futtatás most** elemre.

## <a name="additional-resources"></a>További erőforrások

[Személyre szabott termékajánlatok áttekintése](personalized-product-recommendations.md)
