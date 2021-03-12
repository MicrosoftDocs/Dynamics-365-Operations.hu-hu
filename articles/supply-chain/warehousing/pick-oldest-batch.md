---
title: A mobileszköz legrégebbi kötegének kitárolása
description: Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja a mobileszköz legrégebbi kötegének kitárolási beállításait.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdf6335bd333569e278ccd9cf3972c0ec57d4e6c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989668"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="0db1b-103">A mobileszköz legrégebbi kötegének kitárolása</span><span class="sxs-lookup"><span data-stu-id="0db1b-103">Pick oldest batch on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0db1b-104">A **Legrégebbi köteg kitárolása** konfigurációjához a mobileszköz menüjén keresztül férhet hozzá, amely lehetővé teszi, hogy kötelezze vagy figyelmeztesse a raktári dolgozókat arra, hogy tárolják ki az aktuális helyük legrégebbi kötegét.</span><span class="sxs-lookup"><span data-stu-id="0db1b-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="0db1b-105">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="0db1b-105">Where it applies</span></span>
<span data-ttu-id="0db1b-106">A Legrégebbi köteg kitárolásának konfigurációja a mobileszköz menüelemeiben történik, és a kitárolási köteg alatti elemere van hatással.</span><span class="sxs-lookup"><span data-stu-id="0db1b-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="0db1b-107">A Legrégebbi köteg kitárolása konfigurációjának beállítása</span><span class="sxs-lookup"><span data-stu-id="0db1b-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="0db1b-108">Folyamatban lévő munkát használó beállítású cikkeknél a **Legrégebbi köteg kitárolása** lehetséges beállításai a **Nincs**, a **Figyelmeztetés** vagy a **Kényszerítés** a mobileszköz menüjében.</span><span class="sxs-lookup"><span data-stu-id="0db1b-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="0db1b-109">**Nincs**: A dolgozók nem kapnak üzeneteket, és bármelyik köteget kitárolhatják az aktuális helyükön.</span><span class="sxs-lookup"><span data-stu-id="0db1b-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="0db1b-110">**Figyelmeztetés** és **Kényszerítés**: Amikor a dolgozó kijelöl egy köteget, a kötegvezérlő fölött egy köteglista jelenik meg, amely a legrégebbi lejárati dátummal tartalmazó kötegeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="0db1b-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="0db1b-111">Az azonosítótáblával szabályozott a hely esetén az azonosítótábla-vezérlő fölött a legrégebbi köteget tartalmazó azonosítótáblák listája jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="0db1b-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="0db1b-112">**Figyelmeztetés**: Ha egy dolgozó olyan azonosítótáblát vagy köteget választ ki, amelyik nem szerepel a listán, a rendszer letiltja a vezérlőt, és egy figyelmeztetés fog megjelenni, hogy létezik egy korábbi kiválasztható köteg.</span><span class="sxs-lookup"><span data-stu-id="0db1b-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="0db1b-113">Ha folytatni szeretné a munkát, a dolgozó újból kiválaszthatja ugyanazt az azonosítótáblát vagy köteget.</span><span class="sxs-lookup"><span data-stu-id="0db1b-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="0db1b-114">**Kényszerítés**: A dolgozók továbbra is megkapják azt az üzenetet, hogy van egy korábbi kitárolandó köteg.</span><span class="sxs-lookup"><span data-stu-id="0db1b-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>
