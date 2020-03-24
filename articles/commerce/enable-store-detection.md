---
title: Helyalapú áruházészlelés engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66ffe56f9d969c9d62ed4ff49f0848fab7e58a56
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096869"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="45107-103">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="45107-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="45107-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.</span><span class="sxs-lookup"><span data-stu-id="45107-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="45107-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="45107-105">Overview</span></span>

<span data-ttu-id="45107-106">A Commerce szolgáltatás helyalapú áruházészlelés funkciója segítségével az ügyfeleknek a helyük alapján biztosíthat releváns webhelytartalmat.</span><span class="sxs-lookup"><span data-stu-id="45107-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="45107-107">Ha a helyalapú áruházészlelés be van kapcsolva, a Commerce megjelenítési szolgáltatása a vevő webböngészőjének IP-címéből származó ország-/régiókódot használja, hogy a vevőt a legjobb földrajzi webhely-konfigurációhoz irányítsa.</span><span class="sxs-lookup"><span data-stu-id="45107-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="45107-108">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="45107-108">Privacy notice</span></span>

<span data-ttu-id="45107-109">Ha bekapcsolja a helyalapú áruházészlelés funkciót, akkor a program elküldi a vevő böngészőjének adatait a Microsoft helyszolgáltatásának.</span><span class="sxs-lookup"><span data-stu-id="45107-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="45107-110">Ezt az információt arra használja a program, ha a vevőnek a saját helyéhez releváns tartalmat nyújtsa.</span><span class="sxs-lookup"><span data-stu-id="45107-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="45107-111">Mind a vevő böngészőjéből küldött információ, mind a vevőnek visszaküldött helyalapú információ az adatvédelmi és cookie-kkal kapcsolatos megfelelési irányelvek hatálya alá tartozik.</span><span class="sxs-lookup"><span data-stu-id="45107-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="45107-112">Helyalapú áruházészlelés bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="45107-112">Turn on location-based store detection</span></span>

<span data-ttu-id="45107-113">Ha be szeretné kapcsolni a helyalapú áruházészlelést a Commerce szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="45107-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="45107-114">A szerkesztési eszközben nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="45107-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="45107-115">A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45107-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="45107-116">Válassza az **Webhelybeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45107-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="45107-117">Állítsa a **Helyalapú áruházészlelés engedélyezése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="45107-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45107-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="45107-118">Additional resources</span></span>

[<span data-ttu-id="45107-119">A tartománynevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="45107-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="45107-120">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="45107-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="45107-121">Online áruház csatornájának beállítása</span><span class="sxs-lookup"><span data-stu-id="45107-121">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="45107-122">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="45107-122">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="45107-123">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="45107-123">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="45107-124">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="45107-124">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="45107-125">URL-átirányítások feltöltése ömlesztett formában</span><span class="sxs-lookup"><span data-stu-id="45107-125">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="45107-126">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="45107-126">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="45107-127">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="45107-127">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="45107-128">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="45107-128">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="45107-129">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="45107-129">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
