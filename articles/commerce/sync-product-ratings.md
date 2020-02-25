---
title: 'A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce'
description: Ez a témakör azt mutatja be, hogyan lehet szinkronizálni a termékminősítéseket a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: '---'
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6757a5a13d16c490dced7118c1da8aa0ea6d8994
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029486"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet szinkronizálni a termékminősítéseket a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A termék minősítések többcsatornán helyen történő felhasználásához, például a pénztárnál (POS) és a hívásközpontokban a minősítési és az értékelés szolgáltatásból származó minősítéseket importálni kell a Commerce csatornaadatbázisába. Amikor a többcsatornás helyeken elérhetővé teszik a termék minősítését, azzal közvetett módon segítik a vásárlókat, hogy kapcsolatba lépjenek az értékesítőkkel.

Ez a témakör a következő feladatok leírását tartalmazza:

1. A **Termék minősítések szinkronizálása** kötegelt feladatként konfigurálható a **Minősítések és vélemények szolgáltatásból származó** termékminősítések szinkronizálására.
1. Annak megerősítése hogy a termékminősítések szinkronizálásának kötegelt feladata sikeres volt.
1. A termék minősítések elérhetővé tétele a pénztárban.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Kötegelt feladat konfigurálása a termékminősítések szinkronizálásához

> [!IMPORTANT]
> Mielőtt hozzáfogna, győződjön meg arról, hogy telepítve van a Dynamics 365 Commerce 10.0.6 vagy újabb verziója.

### <a name="initialize-the-commerce-scheduler"></a>A kereskedelmi tervezés és ütemezés incializálása

A kereskedelmi tervezés és ütemezés inicializálásához kövesse az alábbi lépéseket.

1. Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Kereskedelmi ütemező inicializálása** elemre. Vagy keressen rá a „Kereskedelmi ütemező inicializálása” elemre.
1. Győződjön meg arról, hogy a **Kereskedelmi tervezés és ütemezés inicializálása** párbeszédpanelen a **Meglévő konfiguráció törlése** beállítás **Nem** értékre van állítva, majd válassza az **OK** lehetőséget.

### <a name="verify-the-retailproductrating-subjob"></a>Ellenőrizze a RetailProductRating alfeladatot

Ha ellenőrizni szeretné, hogy létezik-e a **RetailProductRating** alfeladat, és hajtsa végre az alábbi lépéseket.

1. Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Ütemezési alfeladatok** elemre. Másik lehetőségként keressen rá az „Ütemezési alfeladatok” elemre.
1. Az alfeladatok listájában keressen meg vagy keressen rá a **RetailProductRating** alfeladatra.

A következő ábra egy példát mutat be az alfeladat részleteire a Commerce alkalmazásban.

![A RetailProductRating alfeladat részletei](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Ha nem találja a **RetailProductRating** alfeladatot, előfordulhat, hogy már futtatta a **Termékértékelések szinkronizálása** feladatot és az **1040 CDX** feladatot a Kereskedelmi tervezés és ütemezés inicializálásának megkezdése előtt. Ebben az esetben a **Teljes adatszinkronizálási** feladat futtatásához kövesse az alábbi lépéseket.

> 1. Ugrás a **Retail és Commerce \> Headquarters beállítás \> Kereskedelmi ütemező  \>Csatorna-adatbázis** elemre. Vagy keressen rá a „Csatorna-adatbázis” elemre.
> 1. Válassza ki a szinkronizálni kívánt csatorna-adatbázist.
> 1. A műveleti ablakban válassza ki a **Teljes adatszinkronizálás** elemet.
> 1. Válassza ki az **Elosztási ütemezés kiválasztása** legördülő párbeszédpanelan az **1040 – termékek** elemet, majd kattintson az **OK** gombra.
> 1. Az előző eljárás lépéseinek megismétlésével győződjön meg arról, hogy a **RetailProductRating** alfeladat létrejött.

### <a name="import-product-ratings"></a>Termékminősítések importálása

Ha a termékminősítéseket szeretne importálni a Commerce megoldásba a minősítési és az értékelés szolgáltatásból, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Központ beállítása \> Kereskedelmi ütemezés \> Termékminősítés feladatok szinkronizálása** lehetőséget. Vagy keressen rá a „Termékminősítési feladatok importálása” kifejezésre.
1. A **Termékminősítések lekérése** párbeszédpanel **Futtatás a háttérben** gyorslapján az **Ismétlődés** elemet.
1. Az **Ismétlődés definiálása** párbeszédpanelen állítson be egy ismétlődési mintát. (A javasolt érték két óra.) Ne ütemezzen egy óránál rövidebb ismétlődést.
1. Válassza ki az **OK** lehetőséget.
1. Állítsa be a **Kötegelt feldolgozás** lehetőséget **Igen** értékre. Ez a beállítás segít biztosítani azt, hogy a naplók ellenőrizhetők legyenek, és ellenőrizhesse a kötegelt feladatok futásának állapotát.
1. Válassza az **OK** lehetőséget a kötegelt feladat futtatásához.

A következő ábra egy példát mutat be a kötegelt feladatok konfigurálására a Commerce alkalmazásban.

![A termékminősítések konfigurációja kötegelt feladat konfigurálása](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Annak megerősítése hogy a termékminősítések szinkronizálásának kötegelt feladata sikeres volt

Ha ellenőrizni szeretné, hogy a **Termékminősítések szinkronizálása** kötegelt feladat sikeres volt-e, hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce \> Rendszeradminisztrátor \> Lekérdezések \> Kötegelt feladatok** lehetőséget, vagy, ha csak Commerce raktározási egységet (SKU) használ a **Retail és Commerce \> Lekérdezések és jelentések \> Kötegelt feladatok** lehetőséget. Vagy keressen rá a „kötegelt feladatok” elemre.
1. Ha meg szeretné tekinteni a kötegelt feladat részleteit, a kötegelt feladatok listájában a **Feladattípus** oszlopban keressen egy olyan leírást, amely a „Termékminősítések lekérése” kifejezést tartalmazza.
1. Válassza ki a feladat azonosítóját a kötegelt feladat részleteinek, például az ütemezett kezdési dátum/időt és az ismétlődés szövege megtekintéséhez.

A következő ábra egy példát mutat be a kötegelt feladat részleteire a Commerce alkalmazásban amikor a kötegelt feladat két órás időközönkénti futtatásra van ütemezve.

![Termékminősítések szinkronizálása kötegelt feladat részletei](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>A termék minősítések elérhetővé tétele a pénztárban

A minősítések és a értékelések megoldás a Dynamics 365 Commerce alkalmazásban egy többcsatornás megoldás. A termék minősítések azonban alapértelmezésben nem jelennek meg a pénztárnál. Annak érdekében, hogy az áruházak ügyfelei láthassák a minősítéseket és értékeléseket, amikor segítséget kapnak az értékesítési munkatársaktól, be kell kapcsolni a termék minősítéseit a POS-nál.

A termékértékelések bekapcsolásához a pénztárban hajtsa végre az alábbi lépéseket.

1. Menjen a **Retail és Commerce \> Commerce beállítása \> Paraméterek \> Commerce paraméterek** lehetőségre. Vagy keressen rá a „Commerce paraméterek” elemre.
1. Válassza a **Konfigurációs paraméterek** lap **Új** elemét.
1. Írjon be egy nevet, például **RatingsAndReviews.EnableProductRatingsForRetailStores**, és az értéket állítsa be **igaz**értékre.
1. Válassza a **Mentés** lehetőséget.
1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra. Vagy keressen rá az „Elosztási ütemezés” elemre.
1. A feladatok listájában válassza az **1110** (**Globális konfiguráció**) elemét, majd válassza a **Futtatás most** parancsot.
1. Miután sikeresen futtatta a feladatot, győződjön meg arról, hogy a termékminősítések most megjelennek a pénztárnál.

A következő ábra egy példát mutat be a Commerce paraméterek konfigurálására, amellyel a termék minősítéseit lehet lehet bekapcsolni a pénztárban.

![A termék minősítéséhez szükséges Commerce paraméterek konfigurálása a pénztárban](media/rnr-hq-enable-ratings-in-pos.png)

A következő ábrán egy példa látható a termékminősítésekre a pénztárban.

![Termékminősítések a pénztárban](media/rnr-pos-catalog-ratings.png)

A következő ábrán egy példa látható a termékminősítésekre a hívásközponti csatornákban.

![Termékminősítések egy hívásközpont-csatornában](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és ellenőrzések használatának kiválasztása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)
