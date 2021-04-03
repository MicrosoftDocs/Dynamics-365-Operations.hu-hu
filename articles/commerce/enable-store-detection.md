---
title: Helyalapú áruházészlelés engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b34f156642b23f7b9754dac1ee81c7d0004872d8
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478188"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="e1b31-103">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="e1b31-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e1b31-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.</span><span class="sxs-lookup"><span data-stu-id="e1b31-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="e1b31-105">A Commerce szolgáltatás helyalapú áruházészlelés funkciója segítségével az ügyfeleknek a helyük alapján biztosíthat releváns webhelytartalmat.</span><span class="sxs-lookup"><span data-stu-id="e1b31-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="e1b31-106">Ha a helyalapú áruházészlelés be van kapcsolva, a Commerce megjelenítési szolgáltatása a vevő webböngészőjének IP-címéből származó ország-/régiókódot használja, hogy a vevőt a legjobb földrajzi webhely-konfigurációhoz irányítsa.</span><span class="sxs-lookup"><span data-stu-id="e1b31-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="e1b31-107">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="e1b31-107">Privacy notice</span></span>

<span data-ttu-id="e1b31-108">Ha bekapcsolja a helyalapú áruházészlelés funkciót, akkor a program elküldi a vevő böngészőjének adatait a Microsoft helyszolgáltatásának.</span><span class="sxs-lookup"><span data-stu-id="e1b31-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="e1b31-109">Ezt az információt arra használja a program, ha a vevőnek a saját helyéhez releváns tartalmat nyújtsa.</span><span class="sxs-lookup"><span data-stu-id="e1b31-109">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="e1b31-110">Mind a vevő böngészőjéből küldött információ, mind a vevőnek visszaküldött helyalapú információ az adatvédelmi és cookie-kkal kapcsolatos megfelelési irányelvek hatálya alá tartozik.</span><span class="sxs-lookup"><span data-stu-id="e1b31-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="e1b31-111">Helyalapú áruházészlelés bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="e1b31-111">Turn on location-based store detection</span></span>

<span data-ttu-id="e1b31-112">Ha be szeretné kapcsolni a helyalapú áruházészlelést a Commerce szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e1b31-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e1b31-113">A szerkesztési eszközben nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="e1b31-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="e1b31-114">A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1b31-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="e1b31-115">Válassza az **Webhelybeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e1b31-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="e1b31-116">Állítsa a **Helyalapú áruházészlelés engedélyezése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="e1b31-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1b31-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e1b31-117">Additional resources</span></span>

[<span data-ttu-id="e1b31-118">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e1b31-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="e1b31-119">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="e1b31-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="e1b31-120">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1b31-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e1b31-121">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="e1b31-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e1b31-122">robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="e1b31-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="e1b31-123">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="e1b31-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="e1b31-124">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="e1b31-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="e1b31-125">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="e1b31-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="e1b31-126">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="e1b31-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="e1b31-127">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e1b31-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
