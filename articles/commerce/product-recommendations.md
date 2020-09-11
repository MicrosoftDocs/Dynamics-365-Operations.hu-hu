---
title: Termékajánlatok áttekintése
description: Ez a témakör a rendezési termékjavaslatok ismertetését tartalmazza. A termékjavaslatoknak köszönhetően a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és még olyanokat is, amelyek eredetileg nem szándékoznak megvásárolni.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "3664882"
---
# <a name="product-recommendations-overview"></a>Termékajánlatok áttekintése

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Commerce a termékjavaslatok megjelenítésére használható az e-kereskedelmi webhelyeken és a pénztári (POS) eszközön. A termékjavaslatok olyan cikkek, amelyeket a vevő számára érdekesek lehetnek. Az ajánlások az online és a fizikai áruházakban a más vevők beszerzési trendjein alapulnak.

A termékjavaslatok révén a vevők egyszerűen és gyorsan megtalálják azokat a termékeket, amelyeket szeretnének, és mindeközben jó élményben van részük. A kereszt- és felülértékesítések arra is használhatók, hogy a vásárlók olyan termékeket is találjanak, amelyeket eredetileg nem is szándékoztak megvásárolni. Amikor a termékek felfedezésével kapcsolatos támogatáshoz használják a javaslatokat, több konverziós lehetőséget is kialakíthatnak, és ezek elősegítik az értékesítési bevételek növelését, valamint javíthatják a vevői elégedettséget és a visszatartást.

Az e-kereskedelemben a termékjavaslatokat a Microsoft Recommendations gép tanulási technológiái támogatják.

## <a name="recommendation-service"></a>Ajánlási szolgáltatás

A termékajánlások szolgáltatás mesterséges intelligencia és a gépi tanulás (AI-ML) technológiák felhasználását használja a következő módon:

- Az ajánlási szolgáltatásnak megfelelő formátumú adatokat a rendszer kivonja az adatokat a Commerce működési adatbázisából, és elküldi őket az Azure Data Lake Storage megoldásba vagy az entitástárba.
- Az ajánlási szolgáltatás a tárolt adatokat az ajánlási modellek tanításához használja a **Másoknak ez is tetszett**, **Gyakran együtt vásárolt**, **Új**, **Legkelendőbb** és **Legnépszerűbbek** listákhoz.

## <a name="scenarios"></a>Forgatókönyvek

Az alábbi POS-esetekben érhetők el a termékajánlások.

- **Az e-Commerce-ben egy üzlet böngészési vagy érkezőoldalán**: Ha a vevők vagy az üzlet munkatársai meglátogatják a bolt egy oldalát, akkor az ajánlási rendszer az **Új**, **Legkelendőbb**és **Legnépszerűbb** listákban javasolhat termékeket.
- **A Termékrészletek oldalon:** Ha a vevők vagy az üzlet munkatársai felkeresnek egy **Termékrészletek** lapot, akkor az ajánlási motor további, valószínűleg megvásárolni kívánt cikkeket javasol. Ezek a cikkek a **Másoknak ez is tetszett** listán jelennek meg.
- **A tranzakció oldalon vagy a pénztár oldalon:** Az ajánlási motor a kosárban található cikkek teljes listája alapján javasolja a cikkeket. Ezek a cikkek megjelennek a **Gyakran együtt vásárolt** listán.
- **Személyre szabott ajánlások:**: a kereskedők a bejelentkezett vevők számára személyre szabott **kitárolásokat** adhatnak meg a listán, emellett olyan új funkciókat, amelyek lehetővé teszik a meglévő lista-forgatókönyvek személyre szabását a vevő alapján. További információ: [Személyre szabott ajánlatok engedélyezése.](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Termékajánlatok típusai

A következő táblázat leírja, hogy milyen automatizált termék-javaslatok érhetők el a kiskereskedők számára a Dynamics 365 Commerce megoldás implementálásához a [termékkollekciók modulban](product-collection-module-overview.md). A kereskedők megjeleníthetik a bejelentkezett felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja.

| Termékgyűjtési modul  | Típus | Leírás |
|----------------------------|------|-------------|
| Új                        | Algoritmikus | A modul a csatornákhoz és katalógusokhoz nemrég hozzárendelt legújabb termékek listáját jeleníti meg. |
| Legnépszerűbb               | Algoritmikus | Ez a modul a termék listáját jeleníti meg, amelyek az eladások száma alapján van rendezve. |
| Felkapott                   | Algoritmikus | Ez a modul egy adott időszakra vonatkozóan megjeleníti a legjobban teljesítő termékek listáját a legmagasabb eladások alapján rangsorolva.  |
| Gyakran együtt vásárolt | MI-ML | Ez a modul a leggyakrabban együtt vásárolt termékek listáját ajánlja, a fogyasztók aktuális kosártartalmával együtt. |
| Szintén kedvelt           | MI-ML | Ez a modul termékeket ajánlja fel egy adott megtekintett termékre a fogyasztói beszerzési minták alapján. |
| Önnek ajánljuk              | MI-ML | Ez a modul a termékek személyre szabott listáját ajánlja a bejelentkezett felhasználó beszerzési szokásai alapján. A vendégfelhasználó számára ez a lista összecsukott állapotban lesz. |

## <a name="additional-resources"></a>További erőforrások

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Termékajánlatok hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)
