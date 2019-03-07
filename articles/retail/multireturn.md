---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Microsoft Dynamics 365 for Retail alkalmazásban.
author: josaw1
manager: AnnBe
ms.date: 1/08/2019
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
ms.openlocfilehash: d2cf6f92e90ef196827abb599c65c732615ec7bb
ms.sourcegitcommit: e72eae546d48d41d4b07ff78cfc0242c32b793e7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2019
ms.locfileid: "373068"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Több vevői rendelést és számlát érintő visszárucikkek

[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

A Dynamics 365 for Finance and Operations 10.0-s verziójában lehetővé vált a több rendelést és számlát érintő visszáruk végrehajtása, míg a 10.0-s verzió előtti kiadásokban a visszárukat egyszerre egyetlen számlára vonatkozóan lehetett csak elvégezni. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>A Retail konfigurálása annak érdekében, hogy támogassa a több vevői rendelést és számlát érintő visszárukat

1. Lépjen a **Kiskereskedelmi paraméterek \> Vevői rendelések** menüpontra.
1. Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert. 

## <a name="process-returns"></a>Visszáruk feldolgozása

A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.

Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája. A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket. A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.