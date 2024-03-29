---
title: Juttatási program meghatározása és kezelése
description: Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a cikk a juttatások beállításával és kezelésével kapcsolatos tájékoztatást tartalmaz.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 08b80f4f90ce6b4a286120cd6329a45a4ebd3f71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877801"
---
# <a name="define-and-manage-a-benefits-program"></a>Juttatási program meghatározása és kezelése


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Human Resources számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a cikk a juttatások beállításával és kezelésével kapcsolatos tájékoztatást tartalmaz.

## <a name="benefit-setup"></a>Juttatási beállítás

Mielőtt a dolgozókhoz juttatásokat rendelhetne, az adott juttatási elemeket létre kell hoznia. Ezek az elemek hasonló juttatási terveket kombinálnak és olyan alapértelmezett beállításokat tartalmaznak, mint a levonási díjak és a könyvelési részletek. Ezen beállítások közül sokat később is módosíthat, ha a dolgozók juttatásban részesülnek. Az egyes juttatási tervekhez egy szervezet több bejegyzési lehetőséget is biztosíthat, vagy a dolgozó is lemondhat egy tervben lévő juttatásról. 

[![Juttatási folyamatábra.](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Juttatás elemei

Mielőtt elkezdené a juttatások létrehozását és a dolgozók hozzáadását, meg kell határoznia a juttatás alkotóelemeit: a típusát, a tervet és a beállításokat.

-   **Típus** – egy konkrét juttatásra, például az orvosi ellátásra vagy a parkolásra vonatkozó tervek gyűjteménye.
-   **Terv** – egy adott juttatás egy szerződött szolgáltatótól.
-   **Beállítás** – a fedezeti szint, például csak az alkalmazott vagy az alkalmazott és a házastársa/élettársa is.

Az egyes juttatási típusok, például látszerészeti vagy fogorvosi juttatás esetén a szervezet egy vagy több tervet is ajánlhat dolgozóinak. Az egyes tervekhez a szervezet különböző beállításokat is biztosíthat. A dolgozók például vásárolhatnak kiegészítő életbiztosítási csomagot éves bérük egyszeres, kétszeres vagy háromszoros mértékének megfelelően. A terv és annak minden beállítási kombinációja olyan juttatás lesz, amelyet a dolgozó kiválaszthat. 

[![juttatási kép.](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Jogosultság
A munkáltató által ajánlott különböző típusú juttatásokra való megfelelőség számos tényezőtől függ. Ha egy juttatást hoz létre a Dynamics 365 Human Resources rendszerben, meghatározhatja a megfelelőségi feltételeket az adott juttatáshoz. 

A juttatást elérhetővé teheti minden dolgozó számára. Egyes vállalatok például mellékjuttatásként parkolási bérletet kínálnak dolgozóiknak. A juttatás létrehozásakor a jogosultságot beállíthatja **Minden dolgozó jogosult** beállításra. 

Egyéb juttatások, például letiltások és adókivetések esetében a jogosultság nem érvényes. Ha ilyen típusú juttatást hoz létre, a jogosultságot a **Jogosultság feldolgozásának kihagyása** lehetőségre kell állítania. 

A jogosultság továbbá szabályalapú is lehet. Tegyük fel például, hogy egy vállalat kétféle életbiztosítást ajánl juttatásként a dolgozóinak. A vezetői beosztásban lévő dolgozók az egyik csomagra jogosultak, míg a többi teljes munkaidős dolgozó a másik életbiztosítási csomagra jogosult. A Human Resources rendszerben létrehozhat egy jogosultsági szabályt, amelybe minden vezető beosztásban lévő dolgozót belevesz, majd egy másikat, amelybe a többi teljes munkaidős dolgozót veszi be, majd hozzárendelheti a megfelelő szabályokat az adott juttatáshoz.

## <a name="enrollment"></a>Bejegyzés
Miután létrehozta a szervezet által kínált juttatásokat és meghatározta azok jogosultságát, már hozzárendelheti a dolgozókat a juttatásokhoz. Egyetlen dolgozót is hozzárendelhet egy juttatáshoz, de egyszerre több dolgozót is hozzáadhat egy vagy több juttatáshoz, egyetlen folyamat során. 

Előfordulhat, hogy egy szervezet visszavonja az egyik juttatását. Ebben az esetben frissítenie kell a juttatást és az abban lévő dolgozókat. A juttatás lejáratának tömeges beállításával egyszerre módosíthatja a juttatás lejárati dátumát, valamint az ahhoz rendelt dolgozókat is. Kiválaszthat például a juttatásban részesülő több dolgozót, és a fedezetük lejárati dátumát egyszerre módosíthatja. 

A juttatások tömeges bővítése funkció hasonlóan működik: ha a tervezetthez képest tovább szeretne egy juttatást biztosítani, egyszerre bővítheti annak lejárati dátumát és módosíthatja az adott juttatásban részesülő dolgozókat.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
