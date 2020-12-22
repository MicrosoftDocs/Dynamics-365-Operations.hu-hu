---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Commerce alkalmazásban.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: e95f06ffaaf2d250b02a8458faa2d9e0b5ef5631
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459143"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Több vevői rendelést és számlát érintő visszárucikkek

[!include [banner](includes/banner.md)]


Ez a cikk a több számlán átívelő, vevői rendeléseket érintő visszárukat optimalizálja. 

## <a name="enable-refunds-over-multiple-captures"></a>Visszatérítések engedélyezése többszörös rögzítéseknél

Ez a funkció több, összekapcsolt visszatérítést tesz lehetővé ugyanarra a vevői rendelésre vonatkozóan. 

1. Nyissa meg a **Funkciókezelés** munkaterületet, és keresse meg a következőt: **Visszatérítések engedélyezése többszörös rögzítéseknél**.
2. Válassza ki a **Visszatérítések engedélyezése többszörös rögzítéseknél** lehetőséget, majd kattintson az **Engedélyezés** elemre. 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében

Ez a funkció biztosítja, hogy amikor egy rendelés visszáruja több számla igénybevételével történik, akkor az adók végső soron megegyezzenek az eredetileg felszámolt adó összegével. 

1. Nyissa meg a **Funkciókezelés** munkaterületet, és keresse meg a következőt: **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében**.
2. Válassza az **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében** elemet, és kattintson az **Engedélyezés** lehetőségre. 


## <a name="process-returns"></a>Visszáruk feldolgozása

Ezen funkciók engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.

Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája. A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket. A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.

Ha a rendelést teljes egészében visszaküldték, akkor a vevőnek visszatérített adók összege megegyezik az eredetileg felszámított adó összegével.

