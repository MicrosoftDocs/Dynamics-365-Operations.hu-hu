---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004458"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a>Több vevői rendelést és számlát érintő visszárucikkek

[!include [banner](includes/banner.md)]


A visszáruk több rendelést és számlát is érinthetnek. 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a>A Commerce konfigurálása a több vevői rendelést és számlát érintő visszáruk támogatásához

1. Lépjen a **Commerce paraméterek \> Vevői rendelések** menüpontra.
1. Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert. 

## <a name="process-returns"></a>Visszáruk feldolgozása

A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.

Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája. A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket. A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.
