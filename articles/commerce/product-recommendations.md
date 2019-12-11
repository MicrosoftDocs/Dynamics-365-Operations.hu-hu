---
title: Termékajánlatok áttekintése
description: Ez a témakör a rendezési termékjavaslatok ismertetését tartalmazza. A termékjavaslatoknak köszönhetően a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és még olyanokat is, amelyek eredetileg nem szándékoznak megvásárolni.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770047"
---
# <a name="product-recommendations-overview"></a>Termékajánlatok áttekintése

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Commerce a termékjavaslatok megjelenítésére használható az e-kereskedelmi webhelyeken és a pénztári (POS) eszközön. A termékjavaslatok olyan cikkek, amelyeket a vevő számára érdekesek lehetnek. Az ajánlások az online és a fizikai áruházakban a más vevők beszerzési trendjein alapulnak.

A termékjavaslatok révén a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és mindeközben jó élményben van részük. A kereszt- és felülértékesítések arra is használhatók, hogy a vásárlók olyan termékeket is találjanak, amelyeket eredetileg nem is szándékoztak megvásárolni. Amikor a termékek felfedezésével kapcsolatos segítséghez használják a javaslatokat, több konverziós lehetőséget is kialakíthatnak, és ezek elősegítik az értékesítési bevételek növelését, valamint javíthatják a vevői elégedettséget és a visszatartást.

A Commerce alkalmazásban a termékjavaslatokat a Microsoft Recommendations gép tanulási technológiái támogatják.


## <a name="scenarios"></a>Esetek

Az alábbi POS-esetekben érhetők el a termékajánlások.

- **Az e-Commerce-ben egy üzlet böngészési vagy érkezőoldalán**: Ha a vevők vagy az üzlet munkatársai meglátogatják a bolt egy oldalát, akkor az ajánlási rendszer az **Új**, **Legkelendőbb**és **Legnépszerűbb** listákban javasolhat termékeket.
- **A Termékrészletek oldalon:** Ha a vevők vagy az üzlet munkatársai felkeresnek egy **Termékrészletek** lapot, akkor az ajánlási motor további, valószínűleg megvásárolni kívánt cikkeket javasol. Ezek a cikkek a **Másoknak ez is tetszett** listán jelennek meg.
- **A tranzakció oldalon vagy a pénztár oldalon:** Az ajánlási motor a kosárban található cikkek teljes listája alapján javasolja a cikkeket. Ezek a cikkek megjelennek a **Gyakran együtt vásárolt** listán.

## <a name="recommendation-service"></a>Ajánlási szolgáltatás

A termékjavaslatoka következő módon használják a Javaslatok gép tanulási technológiákat:

- Az ajánlási szolgáltatásnak megfelelő formátumú adatokat a rendszer kivonja az adatokat a Commerce működési adatbázisából, és elküldi őket az entitástárba.
- Az ajánlási szolgáltatás az adatokat az ajánlási modellek tanításához használja a **Másoknak ez is tetszett**. **Gyakran együtt vásárolt**, **Új**, **Legkelendőbb** és **Legnépszerűbbek** listákhoz.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Válogatott termékek ajánlati listájának létrehozása](create-editorial-recommendation-lists.md)

[AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md)

[Termékjavaslat-listák hozzáadása az oldalakhoz](add-reco-list-to-page.md)
