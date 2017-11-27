---
title: "Juttatási program meghatározása és kezelése"
description: "Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a cikk a juttatások beállításával és kezelésével kapcsolatban tartalmaz tájékoztatást."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ecb9b246b0421d2f869c49634714f7cbb35ae3f7
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="define-and-manage-a-benefits-program"></a>Juttatási program meghatározása és kezelése

[!include[banner](includes/banner.md)]


Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a témakör a juttatások beállításával és kezelésével kapcsolatban tartalmaz tájékoztatást.

<a name="benefit-setup"></a>Juttatási beállítás
-------------

Mielőtt a dolgozókhoz juttatásokat rendelhetne, az adott juttatási elemeket létre kell hoznia. Ezek az elemek hasonló juttatási terveket kombinálnak és olyan alapértelmezett beállításokat tartalmaznak, mint a levonási díjak és a könyvelési részletek. Ezen beállítások közül sokat később is módosíthat, ha a dolgozók juttatásban részesülnek. Az egyes juttatási tervekhez egy szervezet több bejegyzési lehetőséget is biztosíthat, vagy a dolgozó is lemondhat egy tervben lévő juttatásról. 

[![Juttatási folyamatábra](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Juttatás elemei
Mielőtt elkezdené a juttatások létrehozását és a dolgozók hozzáadását, meg kell határoznia a juttatás alkotóelemeit: a típusát, a tervet és a beállításokat.

-   **Típus** – egy konkrét juttatásra, például az orvosi ellátásra vagy a parkolásra vonatkozó tervek gyűjteménye.
-   **Terv** – egy adott juttatás egy szerződött szolgáltatótól.
-   **Beállítás** – a fedezeti szint, például csak az alkalmazott vagy az alkalmazott és a házastársa/élettársa is.

Az egyes juttatási típusok, például látszerészeti vagy fogorvosi juttatás esetén a szervezet egy vagy több tervet is ajánlhat dolgozóinak. Az egyes tervekhez a szervezet különböző beállításokat is biztosíthat. A dolgozók például vásárolhatnak kiegészítő életbiztosítási csomagot éves bérük egyszeres, kétszeres vagy háromszoros mértékének megfelelően. A terv és annak minden beállítási kombinációja olyan juttatás lesz, amelyet a dolgozó kiválaszthat. 

[![juttatási kép](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Jogosultság
A munkáltató által ajánlott különböző típusú juttatásokra való megfelelőség számos tényezőtől függ. Ha egy juttatást hoz létre a Microsoft Talent rendszerben, meghatározhatja a megfelelőségi feltételeket az adott juttatáshoz. 

A juttatást elérhetővé teheti minden dolgozó számára. Egyes vállalatok például mellékjuttatásként parkolási bérletet kínálnak dolgozóiknak. A juttatás létrehozásakor a jogosultságot beállíthatja **Minden dolgozó jogosult** beállításra. 

Egyéb juttatások, például letiltások és adókivetések esetében a jogosultság nem érvényes. Ha ilyen típusú juttatást hoz létre, a jogosultságot a **Jogosultság feldolgozásának kihagyása** lehetőségre kell állítania. 

A jogosultság továbbá szabályalapú is lehet. Tegyük fel például, hogy egy vállalat kétféle életbiztosítást ajánl juttatásként a dolgozóinak. A vezetői beosztásban lévő dolgozók az egyik csomagra jogosultak, míg a többi teljes munkaidős dolgozó a másik életbiztosítási csomagra jogosult. A Talent rendszerben létrehozhat egy jogosultsági szabályt, amelybe minden vezető beosztásban lévő dolgozót belevesz, majd egy másikat, amelybe a többi teljes munkaidős dolgozót veszi be, majd hozzárendelheti a megfelelő szabályokat az adott juttatáshoz.

## <a name="enrollment"></a>Bejegyzés
Miután létrehozta a szervezet által kínált juttatásokat és meghatározta azok jogosultságát, már hozzárendelheti a dolgozókat a juttatásokhoz. Egyetlen dolgozót is hozzárendelhet egy juttatáshoz, de egyszerre több dolgozót is hozzáadhat egy vagy több juttatáshoz, egyetlen folyamat során. 

Előfordulhat, hogy egy szervezet visszavonja az egyik juttatását. Ebben az esetben frissítenie kell a juttatást és az abban lévő dolgozókat. A juttatás lejáratának tömeges beállításával egyszerre módosíthatja a juttatás lejárati dátumát, valamint az ahhoz rendelt dolgozókat is. Kiválaszthat például a juttatásban részesülő több dolgozót, és a fedezetük lejárati dátumát egyszerre módosíthatja. 

A juttatások tömeges bővítése funkció hasonlóan működik: ha a tervezetthez képest tovább szeretne egy juttatást biztosítani, egyszerre bővítheti annak lejárati dátumát és módosíthatja az adott juttatásban részesülő dolgozókat.

<a name="see-also"></a>Lásd még
--------

[Juttatásra való jogosultsági irányelvek](benefit-eligibility-policies.md)




