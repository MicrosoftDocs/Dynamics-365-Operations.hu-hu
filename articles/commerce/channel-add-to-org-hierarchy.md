---
title: Csatorna hozzáadása a szervezeti hierarchiához
description: Ez a témakör azt mutatja be, hogyan lehet egy csatornát hozzáadni egy szervezeti hierarchiához a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4212797d2959c4f8b0d60e6b45de76ffc3ee0dc2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216752"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Csatorna hozzáadása a szervezeti hierarchiához


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy csatornát hozzáadni egy szervezeti hierarchiához a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A csatornáknak egy vagy több szervezeti hierarchiához kell tartozniuk. A csatornák létrehozása előtt győződjön meg arról, hogy be van állítva a szervezeti hierarchiák.  

Lásd: [Szervezeti hierarchiák](channels-org-hierarchies.md) a szervezeti hierarchiák létrehozásával kapcsolatos további információkért.

## <a name="select-a-hierarchy"></a>Hierarchia kiválasztása

Hierarchia kiválasztásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Szervezeti hierarchiák** részhez.
1. A listából válassza ki azt a szervezeti hierarchiát, amelyhez a csatornáját hozzá szeretné adni.
1. A művelet ablaktáblán a hierarchia részleteinek megtekintéséhez kattintson a **nézet** parancsra.

A következő kép a szervezeti hierarchia részletes adatait jeleníti meg a kiválasztott hierarchiában.

![Szervezeti hierarchia részletes adatai a kiválasztott hierarchiában](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Csatorna hozzáadása egy hierarchia-csomóponthoz

Csatorna hozzáadásához egy hierarchia-csomóponthoz tegye a következőket.

1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Válassza ki azt a hierachia-csomópontot, amelyhez hozzá szeretné adni a csatornát, majd a **Beszúrás** legördülő listából válassza a **Kiskereskedelmi csatorna** elemet. 
1. Válassza ki a hozzáadni kívánt csatornát, majd kattintson az **OK** gombra.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A művelet ablaktáblán válassza a **közzététel** lehetőséget, és adjon meg egy **Érvényességi dátumot** a múltban, hogy ez a művelet azonnal érvénybe lépjen.

A következő képen látható a hierarchia-csomóponthoz hozzáadni kívánt csatorna kiválasztása.

![Csatorna kiválasztása a hierarchia-csomóponthoz való hozzáadásra](media/channel-add-to-org-hierarchy-2.png)

A következő kép egy olyan hierarchiát mutat, amelyben különböző csatornák kerültek hozzáadásra.

![Hierarchia különböző hozzáadott csatornákkal](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>További erőforrások

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Szervezetek és szervezeti hierarchiák áttekintése](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchia megtervezése](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Szervezeti hierarchiák](channels-org-hierarchies.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
    
[Online csatorna beállítása](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]