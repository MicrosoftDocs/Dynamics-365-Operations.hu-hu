---
title: Helyalapú áruházészlelés engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 304d8d2f05916295b9c6320561d6a25ff40df955
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003096"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="7e3d8-103">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7e3d8-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7e3d8-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a hely alapú üzletészlelést a Dynamics 365 Commerce-webhely számára.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="7e3d8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7e3d8-105">Overview</span></span>

<span data-ttu-id="7e3d8-106">A Commerce szolgáltatás helyalapú áruházészlelés funkciója segítségével az ügyfeleknek a helyük alapján biztosíthat releváns webhelytartalmat.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="7e3d8-107">Ha a helyalapú áruházészlelés be van kapcsolva, a Commerce megjelenítési szolgáltatása a vevő webböngészőjének IP-címéből származó ország-/régiókódot használja, hogy a vevőt a legjobb földrajzi webhely-konfigurációhoz irányítsa.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="7e3d8-108">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="7e3d8-108">Privacy notice</span></span>

<span data-ttu-id="7e3d8-109">Ha bekapcsolja a helyalapú áruházészlelés funkciót, akkor a program elküldi a vevő böngészőjének adatait a Microsoft helyszolgáltatásának.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="7e3d8-110">Ezt az információt arra használja a program, ha a vevőnek a saját helyéhez releváns tartalmat nyújtsa.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="7e3d8-111">Mind a vevő böngészőjéből küldött információ, mind a vevőnek visszaküldött helyalapú információ az adatvédelmi és cookie-kkal kapcsolatos megfelelési irányelvek hatálya alá tartozik.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="7e3d8-112">Helyalapú áruházészlelés bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="7e3d8-112">Turn on location-based store detection</span></span>

<span data-ttu-id="7e3d8-113">Ha be szeretné kapcsolni a helyalapú áruházészlelést a Commerce szolgáltatásban, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7e3d8-114">A szerkesztési eszközben nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="7e3d8-115">A bal oldali navigációs ablakban válassza ki a **Webhelykezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="7e3d8-116">Válassza az **Webhelybeállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="7e3d8-117">Állítsa a **Helyalapú áruházészlelés engedélyezése** beállítást **Be** értékre.</span><span class="sxs-lookup"><span data-stu-id="7e3d8-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7e3d8-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7e3d8-118">Additional resources</span></span>

[<span data-ttu-id="7e3d8-119">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7e3d8-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="7e3d8-120">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="7e3d8-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="7e3d8-121">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="7e3d8-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="7e3d8-122">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="7e3d8-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="7e3d8-123">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="7e3d8-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="7e3d8-124">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="7e3d8-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="7e3d8-125">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7e3d8-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)
