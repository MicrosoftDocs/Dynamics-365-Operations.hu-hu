---
title: "Meghatározása és juttatások programok kezelése"
description: "Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a cikk a juttatások beállításával és kezelésével kapcsolatban tartalmaz tájékoztatást."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Meghatározása és juttatások programok kezelése

Az emberi erőforrások számos olyan eszközt biztosít, amelyek segítségével beállíthatja és karbantarthatja a szervezet által a dolgozóknak biztosított juttatásokat, levonásokat és dolgozói kompenzációs terveket. Ez a témakör egy kezelése ellátások beállításával kapcsolatos információk.

<a name="benefit-setup"></a>Juttatási beállítások
-------------

Mielőtt a dolgozókhoz juttatásokat rendelhetne, az adott juttatási elemeket létre kell hoznia. Ezek az elemek hasonló juttatási terveket kombinálnak és olyan alapértelmezett beállításokat tartalmaznak, mint a levonási díjak és a könyvelési részletek. Ezen beállítások közül sokat később is módosíthat, ha a dolgozók juttatásban részesülnek. Az egyes juttatási tervekhez egy szervezet több bejegyzési lehetőséget is biztosíthat, vagy a dolgozó is lemondhat egy tervben lévő juttatásról. 

[![Juttatás folyamat](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Juttatás elemei
Mielőtt elkezdené a juttatások létrehozását és a dolgozók hozzáadását, meg kell határoznia a juttatás alkotóelemeit: a típusát, a tervet és a beállításokat.

-   **Típus** – egy konkrét juttatásra, például az orvosi ellátásra vagy a parkolásra vonatkozó tervek gyűjteménye.
-   **Terv** – egy adott juttatás egy szerződött szolgáltatótól.
-   **Beállítás** – a fedezeti szint, például csak az alkalmazott vagy az alkalmazott és a házastársa/élettársa is.

Az egyes juttatási típusok, például látszerészeti vagy fogorvosi juttatás esetén a szervezet egy vagy több tervet is ajánlhat dolgozóinak. Az egyes tervekhez a szervezet különböző beállításokat is biztosíthat. A dolgozók például vásárolhatnak kiegészítő életbiztosítási csomagot éves bérük egyszeres, kétszeres vagy háromszoros mértékének megfelelően. A terv és annak minden beállítási kombinációja olyan juttatás lesz, amelyet a dolgozó kiválaszthat. 

[![juttatás pic](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Jogosultság
A munkáltató által ajánlott különböző típusú juttatásokra való megfelelőség számos tényezőtől függ. Juttatás létrehozásakor a Microsoft Dynamics 365 műveletek beállíthatja az adott juttatás érvényes jogosultsági típusát. 

Elérhetővé teheti a juttatás azoknak a munkavállalóknak. Például egyes cégek által kínált parkolási fázisok az alkalmazottak, a mellékjuttatás. A juttatás létrehozásakor a jogosultságot beállíthatja **Minden dolgozó jogosult** beállításra. 

Egyéb juttatások, mint például a garnishments és adó lefölözések, a jogosultság nem alkalmazható. Savó hoz létre az ilyen típusú ellátások, állítja a támogathatósági **való jogosultság folyamatának megkerülése**. 

Végezetül juttatásra való jogosultság szabály alapú is lehet. Például a vállalat kétféle típusú életbiztosítási juttatás alkalmazottak. Végrehajtó alkalmazottak jogosultak egy életbiztosítási terv, mivel az életbiztosítási terv teljes munkaidőben foglalkoztatott munkavállalók jogosultak. Műveletek 365 Dynamics, a juttatásra való jogosultsági szabály minden végrehajtó alkalmazottakat és a teljes munkaidős alkalmazottak megtalálni egy másik szabály létrehozása, és alkalmazhatja ezeket a szabályokat a megfelelő juttatásra.

## <a name="enrollment"></a>Bejegyzés
Miután létrehozta a szervezet által kínált juttatásokat és meghatározta azok jogosultságát, már hozzárendelheti a dolgozókat a juttatásokhoz. Egyetlen dolgozót is hozzárendelhet egy juttatáshoz, de egyszerre több dolgozót is hozzáadhat egy vagy több juttatáshoz, egyetlen folyamat során. 

Előfordulhat, hogy egy szervezet visszavonja az egyik juttatását. Ebben az esetben az ellátás és a munkavállalók, akik feliratkoztak a kell frissítenie. A tömeges juttatásban lejárati ezt az előnyt egyszerre előny és a munkavállaló való belépés lejárati dátum módosítását teszi lehetővé. Kiválaszthat például a juttatásban részesülő több dolgozót, és a fedezetük lejárati dátumát egyszerre módosíthatja. 

A juttatások tömeges bővítése funkció hasonlóan működik: ha a tervezetthez képest tovább szeretne egy juttatást biztosítani, egyszerre bővítheti annak lejárati dátumát és módosíthatja az adott juttatásban részesülő dolgozókat.

<a name="see-also"></a>Lásd még
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


