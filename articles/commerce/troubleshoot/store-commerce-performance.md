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
ms.openlocfilehash: b690e35b2df736f3e277260e6f752ef5240b0938
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870492"
---
# <a name="troubleshoot-store-commerce-performance-issues"></a>A Store Commerce teljesítményproblémáinak elhárítása

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a témakör leírja, hogyan lehet elhárítani a Store Commerce alkalmazás teljesítményproblémáit Microsoft Dynamics 365 Commerce.

- A Store Commerce rendszer teljesítményproblémáinak elhárítása során kerüli el a távoli bejelentkezést. Ehelyett közvetlenül a Store Commerce eszközbe jelentkezzen be.
- Ha a Store Commerce alkalmazás lassú, a Feladatkezelő vagy az Erőforrás-figyelés segítségével ellenőrizze a MEMÓRIÁt, a hálózatot és a lemezhasználatot. Győződjön meg arról, hogy nincs jelentős eszköz-erőforrás-felhasználás.
- Ellenőrizze a hálózati kapcsolat állapotát, és győződjön meg arról, hogy a HTTPS-kérések és -válaszok nem igényelnek néhány másodpercnél tovább.
