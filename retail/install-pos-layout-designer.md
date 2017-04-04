---
title: "Telepítse a Retail POS-képernyő elrendezéstervezőt"
description: "Az egy-kattintás tervező segítségével különböző a Retail Modern POS (MPOS) és Felhőalapú POS elrendezéseket hozhat létre Fekvő vagy Álló módban üzletek, pénztárgépek, pénztárosok és menedzserek számára."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b33cbf67c00b6baea4393e82d19300085781af29
ms.lasthandoff: 03/31/2017


---

# <a name="install-the-retail-pos-layout-designer"></a>Telepítse a Retail POS-képernyő elrendezéstervezőt

Az egy-kattintás tervező segítségével különböző a Retail Modern POS (MPOS) és Felhőalapú POS elrendezéseket hozhat létre Fekvő vagy Álló módban üzletek, pénztárgépek, pénztárosok és menedzserek számára.

Az MPOS vagy a Felhőalapú POS grafikus felületét a kasszaelrendezés vezérli. Az elrendezés különféle objektumok pozícióját szabályozza. Példák: összegelrendezés, cikkrácselrendezés, vevőelrendezés, kifizetés elrendezése, valamint a különféle menügombok elrendezése. Az elrendezések a dolgozók számára megjelenő értékesítési felületének általános megjelenítését is meghatározzák.

## <a name="install-the-oneclick-designer"></a>Telepítse a oneclick-Tervező
1.  A Microsoft Dynamics 365 műveletekhez, a menü segítségével a bal felső sarokban keresse meg **kiskereskedelmi****és kereskedelmi**&gt;**csatorna beállításait**&gt;**POS telepítési**&gt;**POS**&gt;**képernyő elrendezése**.
2.  Válasszon ki egy bármilyen alkalmazástípussal rendelkező elrendezést a **Modern POS for Windows** vagy a **Felhőalapú POS** pontban, és kattintson az **Elrendezéstervező** lehetőségre.
3.  Az Internet Explorer ablakának alján található értesítési sávon kattintson a **Megnyitás** gombra, hogy elindítsa az egy-kattintás tervező telepítését. (Más böngészőkben előfordulhat, hogy eltérő helyen jelenik meg az értesítési sáv.)
4.  A megjelenő **Alkalmazás futtatása - Biztonsági figyelmeztetés** üzenetpanelen kattintson a **Futtatás **lehetőségre a Kiskereskedelem tervező telepítéséhez. Folyamatjelző mutatja a telepítési folyamat előrehaladását.
5.  A telepítés befejezése után a **Bejelentkezés** lapon adja meg a Microsoft Dynamics 365 for Operations rendszerhez tartozó felhasználónevét és jelszavát, majd kattintson a **Bejelentkezés** gombra a tervező indításához.
6.  Miután a belépő adatai hitelesítésre kerültek és a tervező elindul, megkezdheti a saját elrendezés tervezését vagy a már meglevő módosítását. [![Az egyetlen kattintással tervezőben elrendezés](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Az Elrendezéstervező telepítésével kapcsolatos hibaelhárítás
-   Amikor rákattint **Tervező** lehetőségre, nem jelenik meg a telepítő letöltésére (vagy futtatására) vonatkozó kérdés, vagy a jelenlegi biztonsági beállítások nem teszik lehetővé a fájl letöltését. **Megoldások:**
    -   Internet Explorer böngészőben győződjön meg arról, az előugró ablakok nincs engedélyezve ezen a webhelyen. Kattintson a **beállítások**&gt;**beállítások**&gt;**adatvédelmi**&gt;**található előugró ablakok blokkolása szolgáltatás**, és a beállítást, ha változás szükség.
    -   Internet Explorer böngészőben adja hozzá a Dynamics 365 for Operations rendszer URL-jét a megbízható helyek listájához. Kattintson a **beállítások**&gt;**beállítások**&gt;**biztonsági**&gt;**megbízható helyek**&gt;**helyek**&gt;**hozzáadása**.
-   A program nem indul el, és jelzi, hogy lépjen kapcsolatba a szállítóval. **Megoldás:** Internet Explorer böngészőben adja hozzá a Dynamics 365 for Operations rendszer URL-jét a megbízható helyek listájához. Kattintson a **beállítás**&gt;**beállítások**&gt;**biztonsági**&gt;**megbízható helyek**&gt;**helyek**&gt;**hozzáadása**.

**Ismert probléma:** A tervező nem működik megfelelően a Google Chrome és a Mozilla Firefox böngészőben. Dolgozunk a probléma megoldásán.

<a name="see-also"></a>Lásd még
--------

[A Retail Modern POS konfigurálása, letöltése, telepítése és aktiválása](retail-modern-pos-device-activation.md)


