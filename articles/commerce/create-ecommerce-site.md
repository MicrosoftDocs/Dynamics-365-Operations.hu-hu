---
title: E-kereskedelmi webhely létrehozása
description: Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf084f90d203d84c91ddf7c0d963780b895ef23d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963035"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="85157-103">E-kereskedelmi webhely létrehozása</span><span class="sxs-lookup"><span data-stu-id="85157-103">Create an e-commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="85157-104">Ez a témakör bemutatja azokat a lépéseket és információkat, amelyek egy új e-kereskedelmi webhely létrehozásához szükségesek Dynamics 365 Commerce webhelyépítőben.</span><span class="sxs-lookup"><span data-stu-id="85157-104">This topic describes the steps and information required to create a new e-commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="85157-105">A Dynamics 365 Commerce e-kereskedelmi lehetőségek licencelése esetén a webhelykészítő a saját webhely alapjaként használható kezdő webhellyel lesz biztosítva.</span><span class="sxs-lookup"><span data-stu-id="85157-105">When you license the Dynamics 365 Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="85157-106">Ha azonban a nulláról szeretné kezdeni, vagy egy második webhelyet szeretne létrehozni, akkor egy új helyet kell létrehoznia a webhelylétrehozási környezetben.</span><span class="sxs-lookup"><span data-stu-id="85157-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="85157-107">A webhely beállítása</span><span class="sxs-lookup"><span data-stu-id="85157-107">Set up your site</span></span>

<span data-ttu-id="85157-108">A webhelyének beállításához tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="85157-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="85157-109">A webhelyépítő környezet megnyitása.</span><span class="sxs-lookup"><span data-stu-id="85157-109">Open the site builder environment.</span></span> <span data-ttu-id="85157-110">A Microsoft Lifecycle Services (LCS) alkalmazásban találja meg a webhelyépítőt a környezeti funkciók oldalon a Commerce alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="85157-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="85157-111">A webhely-létrehozási környezet kezdőlapján válassza az **Új webhely** elemet.</span><span class="sxs-lookup"><span data-stu-id="85157-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="85157-112">Az **Új webhely** párbeszédpanelen adja meg a következő adatokat.</span><span class="sxs-lookup"><span data-stu-id="85157-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="85157-113">Mező</span><span class="sxs-lookup"><span data-stu-id="85157-113">Field</span></span>                               | <span data-ttu-id="85157-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="85157-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="85157-115">Webhely neve</span><span class="sxs-lookup"><span data-stu-id="85157-115">Site name</span></span>                           | <span data-ttu-id="85157-116">Adja meg, hogy milyen megjelenítési nevet kell használni a webhely számára a webhely-létrehozási környezetben.</span><span class="sxs-lookup"><span data-stu-id="85157-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="85157-117">Ez a név csak a szerzői környezetben látható, és nem jelenik meg a vevők számára.</span><span class="sxs-lookup"><span data-stu-id="85157-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="85157-118">A webhely rendszergazdájának biztonsági csoportja</span><span class="sxs-lookup"><span data-stu-id="85157-118">Site administrator's security group</span></span> | <span data-ttu-id="85157-119">A webhelyen webhely-rendszergazdai szerepkörrel rendelkező felhasználók kezelésére szolgáló Microsoft Azure Active Directory (Azure AD) biztonsági szerepkört adja meg.</span><span class="sxs-lookup"><span data-stu-id="85157-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="85157-120">Alapértelmezett csatorna (üzemi egység száma)</span><span class="sxs-lookup"><span data-stu-id="85157-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="85157-121">Válassza ki azt az online áruházat, amelynek a webhely a webes kirakataként fog szolgálni.</span><span class="sxs-lookup"><span data-stu-id="85157-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="85157-122">Ha azt szeretné, hogy az e-kereskedelmi webhely több online üzletet támogasson, akkor a webhely beállítása után a **Webhely beállításai** között társítania kell az üzleteket a webhelyhez.</span><span class="sxs-lookup"><span data-stu-id="85157-122">If you want your e-commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="85157-123">Alapértelmezett nyelv</span><span class="sxs-lookup"><span data-stu-id="85157-123">Default language</span></span>                            | <span data-ttu-id="85157-124">Adja meg az online áruház és piac alapértelmezett nyelvét.</span><span class="sxs-lookup"><span data-stu-id="85157-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="85157-125">Az online áruházak több nyelvet is támogathatnak.</span><span class="sxs-lookup"><span data-stu-id="85157-125">An online store can support multiple languages.</span></span> <span data-ttu-id="85157-126">Ha azt szeretné, hogy a program több nyelvet támogasson ehhez az online áruházhoz vagy egy másik online áruházhoz, akkor a webhely beállítását követően a **Webhely beállításai** között konfigurálhatja ezt a támogatást.</span><span class="sxs-lookup"><span data-stu-id="85157-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="85157-127">Tartomány</span><span class="sxs-lookup"><span data-stu-id="85157-127">Domain</span></span>                              | <span data-ttu-id="85157-128">Válassza ki annak a tartománynak a nevét, amely ennek az online áruháznak a tartományaként fog szolgálni.</span><span class="sxs-lookup"><span data-stu-id="85157-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="85157-129">Ha nem konfigurált tartományokat az LCS-ben, akkor ezt a mezőt üresen hagyhatja.</span><span class="sxs-lookup"><span data-stu-id="85157-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="85157-130">Miután a tartományt az LCS-ben konfigurálta, hozzá kell adnia az online áruházhoz a **Webhely beállításai** között.</span><span class="sxs-lookup"><span data-stu-id="85157-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="85157-131">Útvonal</span><span class="sxs-lookup"><span data-stu-id="85157-131">Path</span></span>                              | <span data-ttu-id="85157-132">Amikor a webhely egynél több nyelvet támogat egy adott tartománynévhez, használja az elérési út mezőt, és hozzon létre egy egyedi webhely-URL-címet ahhoz a tartomány és nyelv kombinációhoz.</span><span class="sxs-lookup"><span data-stu-id="85157-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="85157-133">Ha az **Alapértelmezett nyelv** mezőben megadott nyelv az egyetlen olyan nyelv, amelyet ebben a tartományban támogatni fog, vagy továbbra is az alapértelmezett nyelv lesz, miután a webhelyet további nyelvekre lokalizálta, azt ajánljuk, hogy hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="85157-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="85157-134">Miután létrehozta a webhelyet, a **Termékek** lap kiválasztásával ellenőrizheti, hogy az online áruházhoz van-e társítva. Az online áruházhoz rendelt termékek választékát kell látnia.</span><span class="sxs-lookup"><span data-stu-id="85157-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="85157-135">A lap bal felső részén található legördülő menü segítségével is megnyithatja a hozzárendelt termékeket kategóriánként.</span><span class="sxs-lookup"><span data-stu-id="85157-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85157-136">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="85157-136">Additional resources</span></span>

[<span data-ttu-id="85157-137">Tartománynév konfigurálása</span><span class="sxs-lookup"><span data-stu-id="85157-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="85157-138">Új e-kereskedelmi bérlő telepítése</span><span class="sxs-lookup"><span data-stu-id="85157-138">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="85157-139">Dynamics 365 Commerce webhely társítása online csatornával</span><span class="sxs-lookup"><span data-stu-id="85157-139">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="85157-140">Robots.txt fájlok kezelése</span><span class="sxs-lookup"><span data-stu-id="85157-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="85157-141">URL-átirányítások tömeges feltöltése</span><span class="sxs-lookup"><span data-stu-id="85157-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="85157-142">B2C-bérlő beállítása a Commerce-ben</span><span class="sxs-lookup"><span data-stu-id="85157-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="85157-143">Felhasználói bejelentkezéshez használt egyéni lapok beállítása</span><span class="sxs-lookup"><span data-stu-id="85157-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="85157-144">Több B2C-bérlő konfigurálása egy Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="85157-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="85157-145">Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="85157-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="85157-146">Helyalapú áruházészlelés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="85157-146">Enable location-based store detection</span></span>](enable-store-detection.md)
