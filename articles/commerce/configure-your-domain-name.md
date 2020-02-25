---
title: A tartománynév konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
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
ms.openlocfilehash: 4db774783dba4b1cea9552da3cff29a9528bd496
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002174"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="dbf04-103">A tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="dbf04-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="dbf04-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni a tartománynevet egy Microsoft Dynamics 365 e-kereskedelmi webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="dbf04-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="dbf04-105">Tartományok hozzáadása az e-kereskedelem inicializálásakor</span><span class="sxs-lookup"><span data-stu-id="dbf04-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="dbf04-106">Ha e-kereskedelmi környezethez szeretné társítani a tartományokat, akkor az [Új e-commerce webhely telepítése](deploy-ecommerce-site.md) részben leírtaknak megfelelően végezze el az e-kereskedelem inicializálását.</span><span class="sxs-lookup"><span data-stu-id="dbf04-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="dbf04-107">Inicializáláskor a program megkéri, hogy az e-kereskedelmi környezet létrehozásához szükséges adatokat adja meg.</span><span class="sxs-lookup"><span data-stu-id="dbf04-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="dbf04-108">A **Támogatott állomásnevek** mezőbe vegye fel az összes olyan tartományt, amelyet ezzel a környezettel használni szándékozik.</span><span class="sxs-lookup"><span data-stu-id="dbf04-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="dbf04-109">Több tartományt kell elkülöníteni pontosvesszővel.</span><span class="sxs-lookup"><span data-stu-id="dbf04-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="dbf04-110">Ily módon a tartományok konfigurálása az összes szükséges e-kereskedelem összetevőben megtörténik, és a program készen áll arra, hogy a tartalomkézbesítési hálózatból (CDN) vagy webkiszolgálóról érkező forgalmat váltson át, és azt az e-kereskedelmi frontendre irányítja.</span><span class="sxs-lookup"><span data-stu-id="dbf04-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="dbf04-111">Tartományok hozzáadása az e-kereskedelem inicializálása után</span><span class="sxs-lookup"><span data-stu-id="dbf04-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="dbf04-112">Ha az e-kereskedelem inicializálását követően az e-kereskedelmi környezethez szeretné társítani az új tartományokat, akkor szolgáltatási kérelmet kell elküldenie.</span><span class="sxs-lookup"><span data-stu-id="dbf04-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dbf04-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="dbf04-113">Additional resources</span></span>

[<span data-ttu-id="dbf04-114">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="dbf04-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="dbf04-115">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="dbf04-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="dbf04-116">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="dbf04-116">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="dbf04-117">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="dbf04-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="dbf04-118">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="dbf04-118">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="dbf04-119">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="dbf04-119">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="dbf04-120">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="dbf04-120">Enable location-based store detection</span></span>](enable-store-detection.md)
