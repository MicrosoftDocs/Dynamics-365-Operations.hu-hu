---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a cikk azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Commerce alkalmazásban.
author: josaw1
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 65ef700db5a81c49a962fd388af54e7811c088d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890321"
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
