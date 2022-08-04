---
title: A Store Commerce teljesítményproblémáinak elhárítása
description: Ez a témakör leírja, hogyan lehet elhárítani a Store Commerce alkalmazás teljesítményproblémáit Microsoft Dynamics 365 Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2022-05-12
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: fef4eb7063f4acdbca5fab2ad33ec10e0cb603bd
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2022
ms.locfileid: "9169046"
---
# <a name="troubleshoot-store-commerce-performance-issues"></a>A Store Commerce teljesítményproblémáinak elhárítása

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet elhárítani a Store Commerce alkalmazás teljesítményproblémáit Microsoft Dynamics 365 Commerce.

- A Store Commerce rendszer teljesítményproblémáinak elhárítása során kerüli el a távoli bejelentkezést. Ehelyett közvetlenül a Store Commerce eszközbe jelentkezzen be.
- Ha a Store Commerce alkalmazás lassú, a Feladatkezelő vagy az Erőforrás-figyelés segítségével ellenőrizze a MEMÓRIÁt, a hálózatot és a lemezhasználatot. Győződjön meg arról, hogy nincs jelentős eszköz-erőforrás-felhasználás.
- Ellenőrizze a hálózati kapcsolat állapotát, és győződjön meg arról, hogy a HTTPS-kérések és -válaszok nem igényelnek néhány másodpercnél tovább.
