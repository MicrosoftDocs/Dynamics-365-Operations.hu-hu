---
title: "A Retail pénztár (POS) képernyőelrendezés-tervező telepítése"
description: "Az egy-kattintás tervező segítségével különböző a Retail Modern POS (MPOS) és Felhőalapú POS elrendezéseket hozhat létre Fekvő vagy Álló módban üzletek, pénztárgépek, pénztárosok és menedzserek számára."
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 4c647f49101dcbbe7dd1feac2dd9aad5c6dd5bcc
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="install-the-retail-point-of-sale-pos-layout-designer"></a>A Retail pénztár (POS) képernyőelrendezés-tervező telepítése

[!include [banner](includes/banner.md)]

Az egy-kattintás tervező segítségével különböző a Retail Modern POS (MPOS) és Felhőalapú POS elrendezéseket hozhat létre Fekvő vagy Álló módban üzletek, pénztárgépek, pénztárosok és menedzserek számára.

Az MPOS vagy a Felhőalapú POS grafikus felületét a kasszaelrendezés vezérli. Az elrendezés különféle objektumok pozícióját szabályozza. Példák: összegelrendezés, cikkrácselrendezés, vevőelrendezés, kifizetés elrendezése, valamint a különféle menügombok elrendezése. Az elrendezések a dolgozók számára megjelenő értékesítési felületének általános megjelenítését is meghatározzák.

## <a name="install-the-one-click-designer"></a>Az egy-kattintás tervező telepítése
1.  A Microsoft Dynamics 365 for Retail rendszerben a bal felső menü segítségével navigáljon a **Kiskereskedelem** **és kereskedelem** &gt; **Csatorna beállítása** &gt; **POS telepítése** &gt; **POS** &gt; **Képernyő-elrendezések** pontra.
2.  Válasszon ki egy bármilyen alkalmazástípussal rendelkező elrendezést a **Modern POS for Windows** vagy a **Felhőalapú POS** pontban, és kattintson az **Elrendezéstervező** lehetőségre.
3.  Az Internet Explorer ablakának alján található értesítési sávon kattintson a **Megnyitás** gombra, hogy elindítsa az egy-kattintás tervező telepítését. (Más böngészőkben előfordulhat, hogy eltérő helyen jelenik meg az értesítési sáv.)
4.  A megjelenő **Alkalmazás futtatása - Biztonsági figyelmeztetés** üzenetpanelen kattintson a **Futtatás** lehetőségre a Kiskereskedelem tervező telepítéséhez. Folyamatjelző mutatja a telepítési folyamat előrehaladását.
5.  A telepítés befejezése után a **Bejelentkezés** lapon adja meg a Microsoft Dynamics 365 for Retail rendszerhez tartozó felhasználónevét és jelszavát, majd kattintson a **Bejelentkezés** gombra a tervező indításához.
6.  Miután a belépő adatai hitelesítésre kerültek és a tervező elindul, megkezdheti a saját elrendezés tervezését vagy a már meglevő módosítását. [![Elrendezés az egykattintásos tervezőben](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Az Elrendezéstervező telepítésével kapcsolatos hibaelhárítás
-   Amikor rákattint **Tervező** lehetőségre, nem jelenik meg a telepítő letöltésére (vagy futtatására) vonatkozó kérdés, vagy a jelenlegi biztonsági beállítások nem teszik lehetővé a fájl letöltését. **Megoldások:**
    -   Internet Explorer böngészőben győződjön meg arról, az előugró ablakok nincs engedélyezve ezen a webhelyen. Kattintson a **Beállítások** &gt; **Lehetőségek** &gt; **Adatvédelem** &gt; **Előugró ablakok blokkolása – Keresés** lehetőségre, és szükség szerint módosítsa a beállítást.
    -   Internet Explorer böngészőben adja hozzá a Dynamics 365 for Retail rendszer URL-jét a megbízható helyek listájához. Kattintson a **Beállítások** &gt; **Lehetőségek** &gt; **Biztonság** &gt; **Megbízható helyek** &gt; **Helyek** &gt; **Hozzáadás** lehetőségre.
-   A program nem indul el, és jelzi, hogy lépjen kapcsolatba a szállítóval. **Megoldás:** Internet Explorer böngészőben adja hozzá a Dynamics 365 for Retail rendszer URL-jét a megbízható helyek listájához. Kattintson a **Beállítás** &gt; **Lehetőségek** &gt; **Biztonság** &gt; **Megbízható helyek** &gt; **Helyek** &gt; **Hozzáadás** lehetőségre.

**Ismert probléma:** A tervező nem működik megfelelően a Google Chrome és a Mozilla Firefox böngészőben. Dolgozunk a probléma megoldásán.

<a name="additional-resources"></a>További erőforrások
--------

[A Retail Modern POS konfigurálása, letöltése, telepítése és aktiválása](retail-modern-pos-device-activation.md)




