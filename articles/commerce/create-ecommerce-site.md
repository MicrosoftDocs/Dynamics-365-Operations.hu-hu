---
title: E-kereskedelmi webhely létrehozása
description: Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-Commerce webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096774"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="cadb8-103">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="cadb8-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="cadb8-104">Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-Commerce webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.</span><span class="sxs-lookup"><span data-stu-id="cadb8-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="cadb8-105">Az e-kereskedelmi webhelye fejlesztésének megkezdéséhez először létre kell hoznia egy új webhelyet a webhelyépítőben.</span><span class="sxs-lookup"><span data-stu-id="cadb8-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="cadb8-106">Az e-kereskedelmi webhelye fejlesztésének megkezdéséhez először létre kell hoznia egy új webhelyet a webhely-létrehozási környezetben.</span><span class="sxs-lookup"><span data-stu-id="cadb8-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="cadb8-107">Új webhely létrehozása előtt legalább egy online áruházat létre kell hoznia a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="cadb8-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="cadb8-108">A webhely beállítása</span><span class="sxs-lookup"><span data-stu-id="cadb8-108">Set up your site</span></span>

<span data-ttu-id="cadb8-109">A webhelyének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="cadb8-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="cadb8-110">A webhelyépítő környezet megnyitása.</span><span class="sxs-lookup"><span data-stu-id="cadb8-110">Open the site builder environment.</span></span> <span data-ttu-id="cadb8-111">A Microsoft Lifecycle Services (LCS) alkalmazásban találja meg a webhelyépítőt a környezeti funkciók oldalon a Commerce alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="cadb8-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="cadb8-112">A webhely-létrehozási környezet kezdőlapján válassza az **Új webhely** elemet.</span><span class="sxs-lookup"><span data-stu-id="cadb8-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="cadb8-113">Az **Új webhely** párbeszédpanelen adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="cadb8-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="cadb8-114">Mező</span><span class="sxs-lookup"><span data-stu-id="cadb8-114">Field</span></span>                               | <span data-ttu-id="cadb8-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="cadb8-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="cadb8-116">Webhely neve</span><span class="sxs-lookup"><span data-stu-id="cadb8-116">Site name</span></span>                           | <span data-ttu-id="cadb8-117">Adja meg, hogy milyen megjelenítési nevet kell használni a webhely számára a webhely-létrehozási környezetben.</span><span class="sxs-lookup"><span data-stu-id="cadb8-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="cadb8-118">Ez a név csak a szerzői környezetben látható, és nem jelenik meg a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="cadb8-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="cadb8-119">A webhely rendszergazdájának biztonsági csoportja</span><span class="sxs-lookup"><span data-stu-id="cadb8-119">Site administrator's security group</span></span> | <span data-ttu-id="cadb8-120">A webhelyen webhely-rendszergazdai szerepkörrel rendelkező felhasználók kezelésére szolgáló Microsoft Azure Active Directory (Azure AD) biztonsági szerepkört adja meg.</span><span class="sxs-lookup"><span data-stu-id="cadb8-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="cadb8-121">Alapértelmezett csatorna (üzemi egység száma)</span><span class="sxs-lookup"><span data-stu-id="cadb8-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="cadb8-122">Válassza ki azt az online áruházat, amelynek a webhely a webes kirakataként fog szolgálni.</span><span class="sxs-lookup"><span data-stu-id="cadb8-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="cadb8-123">Ha azt szeretné, hogy az e-kereskedelmi webhely több online üzletet támogasson, akkor a webhely beállítása után a **Webhely beállításai** között társítania kell az üzleteket a webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="cadb8-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="cadb8-124">Alapértelmezett nyelv</span><span class="sxs-lookup"><span data-stu-id="cadb8-124">Default language</span></span>                            | <span data-ttu-id="cadb8-125">Adja meg az online áruház és piac alapértelmezett nyelvét.</span><span class="sxs-lookup"><span data-stu-id="cadb8-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="cadb8-126">Az online áruházak több nyelvet is támogathatnak.</span><span class="sxs-lookup"><span data-stu-id="cadb8-126">An online store can support multiple languages.</span></span> <span data-ttu-id="cadb8-127">Ha azt szeretné, hogy a program több nyelvet támogasson ehhez az online áruházhoz vagy egy másik online áruházhoz, akkor a webhely beállítását követően a **Webhely beállításai** között konfigurálhatja ezt a támogatást.</span><span class="sxs-lookup"><span data-stu-id="cadb8-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="cadb8-128">Tartomány</span><span class="sxs-lookup"><span data-stu-id="cadb8-128">Domain</span></span>                              | <span data-ttu-id="cadb8-129">Válassza ki annak a tartománynak a nevét, amely ennek az online áruháznak a tartományaként fog szolgálni.</span><span class="sxs-lookup"><span data-stu-id="cadb8-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="cadb8-130">Ha nem konfigurált tartományokat az LCS-ben, akkor ezt a mezőt üresen hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="cadb8-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="cadb8-131">Miután a tartományt az LCS-ben konfigurálta, hozzá kell adnia az online áruházhoz a **Webhely beállításai** között.</span><span class="sxs-lookup"><span data-stu-id="cadb8-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="cadb8-132">Útvonal</span><span class="sxs-lookup"><span data-stu-id="cadb8-132">Path</span></span>                              | <span data-ttu-id="cadb8-133">Amikor a webhely egynél több nyelvet támogat egy adott tartománynévhez, használja az elérési út mezőt, és hozzon létre egy egyedi webhely-URL-címet ahhoz a tartomány és nyelv kombinációhoz.</span><span class="sxs-lookup"><span data-stu-id="cadb8-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="cadb8-134">Ha az **Alapértelmezett nyelv** mezőben megadott nyelv az egyetlen olyan nyelv, amelyet ebben a tartományban támogatni fog, vagy továbbra is az alapértelmezett nyelv lesz, miután a webhelyet további nyelvekre lokalizálta, azt ajánljuk, hogy hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="cadb8-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="cadb8-135">Miután létrehozta a webhelyet, a **Termékek** lap kiválasztásával ellenőrizheti, hogy az online áruházhoz van-e társítva. Az online áruházhoz rendelt termékek választékát kell látnia.</span><span class="sxs-lookup"><span data-stu-id="cadb8-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="cadb8-136">A lap bal felső részén található legördülő menü segítségével is megnyithatja a hozzárendelt termékeket kategóriánként.</span><span class="sxs-lookup"><span data-stu-id="cadb8-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cadb8-137">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cadb8-137">Additional resources</span></span>

[<span data-ttu-id="cadb8-138">A tartománynevének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="cadb8-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="cadb8-139">Új e-commerce webhely telepítése</span><span class="sxs-lookup"><span data-stu-id="cadb8-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="cadb8-140">Online áruház csatornájának beállítása</span><span class="sxs-lookup"><span data-stu-id="cadb8-140">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="cadb8-141">Online webhely társítása csatornával</span><span class="sxs-lookup"><span data-stu-id="cadb8-141">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="cadb8-142">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="cadb8-142">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="cadb8-143">URL-átirányítások feltöltése ömlesztett formában</span><span class="sxs-lookup"><span data-stu-id="cadb8-143">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="cadb8-144">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="cadb8-144">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="cadb8-145">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="cadb8-145">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="cadb8-146">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="cadb8-146">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="cadb8-147">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="cadb8-147">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="cadb8-148">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="cadb8-148">Enable location-based store detection</span></span>](enable-store-detection.md)
