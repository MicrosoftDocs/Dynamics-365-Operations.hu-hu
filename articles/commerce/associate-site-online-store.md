---
title: Dynamics 365 Commerce webhely társítása online csatornával
description: Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyét egy vagy több online áruházhoz kötni.
author: bicyclingfool
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7ceef55bac11ae8a1f7d9dafbddc45d67b836504
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797305"
---
# <a name="associate-a-dynamics-365-commerce-site-with-an-online-channel"></a><span data-ttu-id="db835-103">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="db835-103">Associate a Dynamics 365 Commerce site with an online channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db835-104">Ez a témakör azt mutatja be, hogyan lehet a Microsoft Dynamics 365 Commerce webhelyét egy vagy több online áruházhoz kötni.</span><span class="sxs-lookup"><span data-stu-id="db835-104">This topic explains how to bind your Microsoft Dynamics 365 Commerce site to one or more online stores.</span></span> 

<span data-ttu-id="db835-105">Miután a Dynamics 365 Commerce e-kereskedelmi környezetet a Microsoft Dynamics Lifecycle Services (LCS) portál segítségével létesítette, készen áll az első e-kereskedelmi webhely létrehozására.</span><span class="sxs-lookup"><span data-stu-id="db835-105">After you've provisioned your Dynamics 365 Commerce e-commerce environment by using the Microsoft Dynamics Lifecycle Services (LCS) portal, you're ready to establish your first e-commerce website.</span></span> <span data-ttu-id="db835-106">A webhely kezdeti létrehozásának részeként a webhelyet a korábban létrehozott online áruházhoz kell társítania.</span><span class="sxs-lookup"><span data-stu-id="db835-106">As part of the initial site creation, you associate the site with an online store that was previously created.</span></span> <span data-ttu-id="db835-107">Ezzel a lépéssel a webhelyet egy online csatornához köti, és ezáltal a webhely képes a navigációs hierarchia, a termékek, kategóriák, árak, szállítási lehetőségek és az online áruházban megadott minden más elem megjelenítésére.</span><span class="sxs-lookup"><span data-stu-id="db835-107">This step binds the site to an online channel and lets the site show the navigation hierarchy, products, categories, prices, shipping options, and everything else that you defined in the online store.</span></span>

<span data-ttu-id="db835-108">Egy új webhely létrehozásához és online áruházhoz társításához az LCS-ben válassza ki a webhely-létrehozási környezet hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="db835-108">To establish a new site and associate an online store with it, in LCS, select the link for the site authoring environment.</span></span> <span data-ttu-id="db835-109">Ezután a webhely-létrehozási környezet oldalán válassza az **Új webhely** elemet.</span><span class="sxs-lookup"><span data-stu-id="db835-109">Then, on the page for the site authoring environment, select **New site**.</span></span> <span data-ttu-id="db835-110">Az **Új webhely** párbeszédpanelen meg kell adnia néhány alapvető információt a webhelyéről.</span><span class="sxs-lookup"><span data-stu-id="db835-110">In the **New site** dialog box, you must provide some basic information about your site.</span></span> <span data-ttu-id="db835-111">A kötelezően megadandő információk teljes magyarázatával kapcsolatban tekintse meg: [Új e-kereskedelmi webhely létrehozása](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="db835-111">For a complete explanation of the information that you must provide, see [Create a new e-commerce site](create-ecommerce-site.md).</span></span>

<span data-ttu-id="db835-112">Miután létrehozta a webhelyet, a **Termékek** lap kiválasztásával ellenőrizheti, hogy az online áruházhoz van-e társítva. Az online áruházhoz rendelt termékek választékát kell látnia.</span><span class="sxs-lookup"><span data-stu-id="db835-112">After your site is created, you can verify that it's associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="db835-113">A lap bal felső részén található legördülő mező segítségével is megnyithatja a termékeket kategóriánként.</span><span class="sxs-lookup"><span data-stu-id="db835-113">You can also use the drop-down field in the upper left of the page to access the products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db835-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="db835-114">Additional resources</span></span>

[<span data-ttu-id="db835-115">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="db835-115">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="db835-116">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="db835-116">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="db835-117">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="db835-117">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="db835-118">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="db835-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="db835-119">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="db835-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="db835-120">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="db835-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="db835-121">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="db835-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="db835-122">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="db835-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="db835-123">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="db835-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="db835-124">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="db835-124">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]