---
title: Rendszergazdai jogosultságok beállítása az életeseményekhez
description: Ez a cikk bemutatja, hogyan kell konfigurálni a rendszergazdai jogokat a Microsoft életeseményéhez Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229986"
---
# <a name="set-administrator-rights-for-life-events"></a>Rendszergazdai jogosultságok beállítása az életeseményekhez

[!include [banner](../includes/preview-banner.md)]

A rendszergazdák a konfigurációs beállításoktól függően frissíthatják az életesemények beállításait. Az Emberi erőforrások **paraméterei** lapon konfigurálhatja olyan paramétereket, amelyek segítségével a rendszergazdák módosíthatják a tervkiválasztásokat. Azt is korlátozhatja, hogy a rendszergazdák ne módosíthatnak.

Az Emberi erőforrások **paraméterei** lapon beállíthatja a visszaigazolt tervekre és az életesemény-beállításokra vonatkozó tervváltozási korlátozásokat.

Ha a **Visszaigazolt terv** beállítás van kiválasztva, csak akkor lehet változtatásokat eszközlni, ha aktív a beléptetési időszak. (A beléptetési időszakokra példák a nyitott beléptetési időszakok, az új felvételi időszakok és az életesemény-beléptetési időszakok.) Ha ez a beállítás nincs bejelölve, bármikor lehet módosításokat tenni.

Ha az Élet **típusú események beállításai** vannak kiválasztva, akkor az élettartam esemény során végrehajtott tervváltozásokat a tervtípushoz megadott életesemény-beállítások korlátozzák. Ha ez a beállítás nincs bejelölve, az élettartam alatt módosíthatók a tervkiválasztások.

## <a name="set-plan-change-restrictions"></a>Tervváltozási korlátozások beállítása

Az Emberi erőforrások **paraméterei** lap **Juttatások kezelése lapján** a következő mezők érhetők el.

| Mező | Leírás |
|-------|-------------|
| Visszaigazolt tervek | Akkor válassza ezt a lehetőséget, ha egy terv csak akkor engedélyezett, ha aktív a beléptetési időszak. Ha ez a beállítás nincs bejelölve, bármikor lehet módosításokat tenni. |
| Életesemény beállításai | Akkor válassza ezt a lehetőséget, ha egy életesemény során a tervtípushoz megadott életesemény-beállítások korlátozzák a terv módosításait. Ha ez a beállítás nincs bejelölve, az élettartam alatt módosíthatók a tervkiválasztások. |
