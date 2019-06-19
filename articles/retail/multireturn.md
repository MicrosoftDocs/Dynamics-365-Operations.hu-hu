---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Microsoft Dynamics 365 for Retail alkalmazásban.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
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
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565300"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Több vevői rendelést és számlát érintő visszárucikkek

[!include [banner](includes/banner.md)]


A Dynamics 365 for Finance and Operations 10.0-s verziójában lehetővé vált a több rendelést és számlát érintő visszáruk végrehajtása, míg a 10.0-s verzió előtti kiadásokban a visszárukat egyszerre egyetlen számlára vonatkozóan lehetett csak elvégezni. 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a>A Retail konfigurálása annak érdekében, hogy támogassa a több vevői rendelést és számlát érintő visszárukat

1. Lépjen a **Kiskereskedelmi paraméterek \> Vevői rendelések** menüpontra.
1. Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert. 

## <a name="process-returns"></a>Visszáruk feldolgozása

A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.

Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája. A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket. A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.
