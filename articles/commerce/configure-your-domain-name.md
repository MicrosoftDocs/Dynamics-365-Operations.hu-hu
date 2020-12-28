---
title: A tartománynév konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517122"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="d04ce-103">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d04ce-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d04ce-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="d04ce-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="d04ce-105">Tartományok hozzáadása az e-kereskedelem inicializálásakor</span><span class="sxs-lookup"><span data-stu-id="d04ce-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="d04ce-106">Ha a Dynamics 365 Commerce e-kereskedelmi környezethez szeretné társítani a tartományokat, akkor az [Új e-kereskedelmi bérlő üzembe helyezése](deploy-ecommerce-site.md) részben leírtaknak megfelelően végezze el az e-kereskedelem inicializálását.</span><span class="sxs-lookup"><span data-stu-id="d04ce-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="d04ce-107">Inicializáláskor a program megkéri, hogy az e-kereskedelmi környezet létrehozásához szükséges adatokat adja meg.</span><span class="sxs-lookup"><span data-stu-id="d04ce-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="d04ce-108">A **Támogatott állomásnevek** mezőbe vegye fel az összes olyan tartományt, amelyet ezzel a környezettel használni szándékozik.</span><span class="sxs-lookup"><span data-stu-id="d04ce-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="d04ce-109">Több tartományt kell elkülöníteni pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="d04ce-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="d04ce-110">Ily módon a tartományok konfigurálása az összes szükséges Kereskedelmi összetevőben megtörténik, és a program készen áll arra, hogy a tartalomkézbesítési hálózatból (CDN) vagy webkiszolgálóról érkező forgalmat váltson át, és azt az e-kereskedelmi frontendre irányítja.</span><span class="sxs-lookup"><span data-stu-id="d04ce-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="d04ce-111">Tartományok hozzáadása az e-kereskedelem inicializálása után</span><span class="sxs-lookup"><span data-stu-id="d04ce-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="d04ce-112">Ha az e-kereskedelem inicializálását követően az e-kereskedelmi környezethez szeretné társítani az új tartományokat, akkor szolgáltatási kérelmet kell elküldenie.</span><span class="sxs-lookup"><span data-stu-id="d04ce-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d04ce-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d04ce-113">Additional resources</span></span>

[<span data-ttu-id="d04ce-114">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="d04ce-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="d04ce-115">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="d04ce-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="d04ce-116">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="d04ce-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="d04ce-117">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="d04ce-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="d04ce-118">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="d04ce-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="d04ce-119">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="d04ce-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="d04ce-120">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="d04ce-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="d04ce-121">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="d04ce-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="d04ce-122">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d04ce-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="d04ce-123">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d04ce-123">Enable location-based store detection</span></span>](enable-store-detection.md)
