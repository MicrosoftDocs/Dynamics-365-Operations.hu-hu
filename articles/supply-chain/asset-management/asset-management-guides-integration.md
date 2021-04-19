---
title: A Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides alkalmazással
description: Ez a témakör azt mutatja be, hogyan lehet integrálni a Microsoft Dynamics 365 Supply Chain Management Eszközkezelő modulját a Dynamics 365 Guides alkalmazással annak érdekében, hogy kihasználhassa a vegyes valóság útmutatókat a mindennapos szolgáltatási és karbantartási feladatokban.
author: kamaybac
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 4af14a66c839ccee02008057ad1de8ef5b9d291b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813917"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>A Dynamics 365 Supply Chain Management (Eszközkezelés) integrálása a Dynamics 365 Guides alkalmazással

Integrálhatja a Microsoft Dynamics 365 Supply Chain Management **Eszközkezelő modulját** a Dynamics 365 Guides alkalmazással annak érdekében, hogy kihasználhassa a vegyes valóság útmutatókat a mindennapos szolgáltatási és karbantartási feladatokban. Ha egy útmutató egy Eszközkezelési munkarendeléshez van társítva, akkor egy dolgozó, aki megnyitja a munkarendelés karbantartási ellenőrzőlistáját a Supply Chain Management (Dynamics 365) alkalmazásban, azt látja, hogy rendelkezésre áll egy útmutató. A dolgozó ezután megkeresheti és megnyithatja az útmutatót a Dynamics 365 Guides HoloLens alkalmazásban.

## <a name="prerequisites"></a>Előfeltételek

Mielőtt útmutatókat csatolhat a Eszközkezelési munkarendelésekhez, ezeket az előfeltételeket kell elvégeznie:

- [A Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) 10.0.9 vagy újabb verziójának beállítása.
- [A kettős írás funkció bekapcsolása a Supply Chain Management alkalmazásokhoz](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Tesztcsomag bekapcsolása](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) az **MRGuidesFeature** funkcióhoz. (Termelési környezetek esetében először egy támogatási jegyet kell elküldenie, hogy a bérlője bekerüljön a tesztelési csoportba.)
- [Kapcsolja be a következő konfigurációs kulcsokat](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) a **Licenckonfiguráció** oldalon:

    - Eszközkezelés \> Eszközkezelés vegyes valóságban
    - Vegyes valóság \> Vegyes valóság útmutató

- [A Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 200.0.0.96 vagy újabb verziójának beállítása.

## <a name="use-dynamics-365-guides-with-asset-management"></a>A Dynamics 365 Guides használata az Eszközkezeléssel

Egy útmutató társításához a Eszközkezelés modulban egy karbantartás ellenőrzőlista sora használható. A társítást karbantartási ellenőrzőlista sablonnal, egy karbantartási feladattípussal vagy egy munkarendeléssel lehet létrehozni, mivel mindhárom tartalmaz karbantartási ellenőrzőlista sorokat. Időt takaríthat meg egy sablon használatával, mert a sablon minden olyan karbantartási feladattípushoz társítható, amely használja azt. Például egy karbantartási feladattípushoz kapcsolódó útmutató automatikusan az összes olyan munkarendeléshez társítva van, amely előírja azt a feladattípust. Másfelől viszont a közvetlenül a munkarendeléshez kapcsolódó útmutató csak ahhoz a munkarendeléshez létezik.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Útmutató társítása karbantartásiellenőrzőlista-sablonhoz

Útmutató társításához egy karbantartásiellenőrzőlista-sablonhoz kövesse az alábbi lépéseket.

1. Hozzon létre egy útmutatót a Dynamics 365 Guides PC és HoloLens alkalmazásokkal. Ha szeretne többet megtudni útmutatók készítéséről, tekintse át az alábbi témaköröket:

    - [A számítógépes alkalmazás használata útmutató létrehozásához](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [A hologramok elhelyezése a HoloLens alkalmazás segítségével](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. Az Supply Chain Management alkalmazásban [hozzon létre egy karbantartásiellenőrzőlista-sablont](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. A létrehozott útmutatót társítsa egy karbantartásiellenőrzőlista-sorhoz az új karbantartásiellenőrzőlista-sablonban:

    1. A **Karbantartásiellenőrzőlista-sorok** gyorslapon válassza ki azt a sort, amelyhez társítani szeretné az útmutatót.
    1. Válassza a **Társított útmutatók** gyorslap **Útmutató hozzáadása** elemét.

        ![Útmutató társítása karbantartásiellenőrzőlista-sorhoz](media/am-guides-integration-add-guide.png "Útmutató társítása karbantartásiellenőrzőlista-sorhoz")

    1. A **Név** mezőben válasszon ki egy segédvonalat, majd válassza a **Mentés** parancsot.

        ![A Név mezőben válasszon egy útmutatót](media/am-guides-integration-select-guide.png "A Név mezőben válasszon egy útmutatót")

1. A karbantartásiellenőrzőlista-sablon társítása egy feladattípushoz:

    1. [Hozzon létre egy karbantartásifeladat-típust](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), vagy válasszon egy meglévő karbantartásifeladat-típust.
    1. A Művelet ablaktáblán válassza a **Karbantartási feladattípus alapértelmezései** lehetőséget.

        ![Karbantartási feladattípus alapértelmezések gomb](media/am-guides-integration-job-defaults.png "Karbantartási feladattípus alapértelmezések gomb")

    1. Hozzon létre egy sort, majd kattintson a **Mentés** lehetőségre.

        ![Egy sor létrehozása](media/am-guides-integration-add-line.png "Egy sor létrehozása")

    1. A Művelet panelen válassza a **Karbantartási ellenőrzőlista** elemet.

        ![Karbantartási ellenőrzőlista gombja](media/am-guides-integration-maintenance-checklist.png "Karbantartási ellenőrzőlista gombja")

    1. A **Karbantartásellenőrzőlista-sorok** gyorslapján vegyen fel egy sort, majd módosítsa a **Típus** mező értékét **Sablon** értékre.

        ![A Típus érték módosítása](media/am-guides-integration-checklist-lines.png "A Típus érték módosítása")

    1. Válassza ki a **Sor részletei** gyorslap **Sablon** mezőjében azt a sablont, amelyhez az útmutatót társította, majd válassza a **Mentés** parancsot.

        ![Sablon kijelölése](media/am-guides-integration-checklist-line-details.png "Sablon kijelölése")

1. [Hozzon létre egy munkarendelést](work-orders/manually-created-workorders.md#create-work-order), majd válassza ki azt a karbantartási feladattípust, amely az útmutatóhoz társított karbantartásiellenőrzőlista-sablont használja. A program automatikusan a munkarendeléshez rendeli az útmutatót.

    ![Válassza ki a karbantartási feladat típusát](media/am-guides-integration-create-work-order.png "Válassza ki a karbantartási feladat típusát")

1. A munkarendeléshez és a dolgozókhoz kapcsolódó útmutató megtekintése:

    1. A munkarendelés eléréséhez nyissa meg az [Eszközkezelési mobil munkaterületet](asset-management-mobile-workspace.md).
    1. Nyissa meg a munkarendeléshez tartozó [Karbantartási ellenőrzőlistát](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job).
    1. Jelöljön ki egy ellenőrzőlista-sort a kapcsolódó útmutató megtekintéséhez.

        ![Az ellenőrzőlista-sorhoz társított útmutató](media/am-guides-integration-show-guide.png "Az ellenőrzőlista-sorhoz társított útmutató")

    1. Nyissa meg az útmutatót a HoloLens eszközön.

        ![Az útmutatót megnyitása a HoloLens eszközön](media/am-guides-integration-hololens-select.png "Nyissa meg az útmutatót a HoloLens eszközön")

> [!NOTE]
> Az útmutatók közvetlenül is társíthatók egy munkarendelés vagy egy feladattípus karbantartási ellenőrzőlistájához.

> [!IMPORTANT]
> Létezik egy ismert probléma, amikor egy karbantartásiellenőrzőlista-sablont egy alapértelmezett karbantartási feladattípushoz társít, a sablonhoz csatolt útmutató nem jelenik meg a **Karbantartási feladattípus alapértelmezései** gyorslapjának **Társított útmutatók** lapján. Az útmutató azonban azt követően megjelenik, hogy a feladattípus egy munkarendelésre lesz alkalmazva a **Társított útmutatók** gyorslapon.

## <a name="see-also"></a>Lásd még

- [Kettős írás – áttekintés](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Eszközkezelés – áttekintés](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]