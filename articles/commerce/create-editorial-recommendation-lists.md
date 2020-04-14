---
title: Válogatott ajánlások manuális létrehozása
description: Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuálisan terméklistákat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b00c83355850f6249068749096b011f805b37e3c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154318"
---
# <a name="manually-create-curated-recommendations"></a>Válogatott ajánlások manuális létrehozása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuálisan termékajánlásokat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.

A válogatott listák egyéni tartalmak olyan gyűjteményei, amelyet emberek hoztak létre és válogattak.  

## <a name="create-a-new-list"></a>Új lista létrehozása

Válogatott termékajánlási lista létrehozásához kövesse az alábbi lépéseket.

1. Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási listák** elemet.
1. Válassza az **Új** lehetőséget.
1. A **Listaazonosító** mezőben adjon meg egy értéket.
1. A **Listanév** mezőben adjon meg egy értéket.
    - A **Listanév** a lista címe, amely megjelenik majd a **Termékgyűjtési** modul válogatott listák szakaszában.
1. Ha termékeket szeretne hozzáadni a listához, válassza a **Termékek hozzáadása** lehetőséget.
1. Ha módosítani szeretné a listán szereplő termékek sorrendjét, írjon be egy értéket a **Megjelenítési sorrend** oszlopában.
    - Ha két terméknél ugyanaz megjelenítési sorrend értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.
1. A lista mentéséhez válassza a **Mentés** parancsot.

## <a name="example-list"></a>Példa listára

![Példa – Válogatott lista a háttérirodában](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[ADLS engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Termékajánlatok engedélyezése](enable-product-recommendations.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakció képernyőjéhez](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)
