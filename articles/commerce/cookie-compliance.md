---
title: Cookie-k megfelelősége
description: Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446913"
---
# <a name="cookie-compliance"></a><span data-ttu-id="68ed4-103">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="68ed4-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="68ed4-104">Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="68ed4-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="68ed4-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="68ed4-105">Overview</span></span>

<span data-ttu-id="68ed4-106">Az adatvédelem fontos tényező, amikor az e-kereskedelmi ügyfelekre hattással lévő nyomkövető technológia kerül használatra.</span><span class="sxs-lookup"><span data-stu-id="68ed4-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="68ed4-107">Az adatvédelmi előírások, például az Európai Unió (EU) Általános adatvédelmi rendelete (GDPR) miatt, az elektronikus adatvédelmi irányelveket figyelembe kell venni minden olyan webhelyen, amely jelenleg aktív.</span><span class="sxs-lookup"><span data-stu-id="68ed4-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="68ed4-108">Mivel számos e-kereskedelmi webhely alapértelmezésben globálisan elérhető, fontos, hogy ellenőrizze az e-kereskedelmi webhely megfelelési szabványait.</span><span class="sxs-lookup"><span data-stu-id="68ed4-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="68ed4-109">Ha többet szeretne megtudni a Microsoft által a cookie-k megfelelősége esetében használt alapelvekről, keresse fel a [Microsoft megbízhatósági központját](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="68ed4-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="68ed4-110">Ezen a webhelyen további információkat is kaphat a megfelelőségi és adatvédelmi területekről.</span><span class="sxs-lookup"><span data-stu-id="68ed4-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="68ed4-111">A következő táblázat felsorolja a Dynamics 365 Commerce helyek által feladott cookie-k jelenlegi hivatkozási listáját.</span><span class="sxs-lookup"><span data-stu-id="68ed4-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="68ed4-112">Cookie neve</span><span class="sxs-lookup"><span data-stu-id="68ed4-112">Cookie name</span></span>                               | <span data-ttu-id="68ed4-113">Használat</span><span class="sxs-lookup"><span data-stu-id="68ed4-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="68ed4-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="68ed4-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="68ed4-115">Microsoft Azure Active Directory (Azure AD) hitelesítési cookie-k tárolása egyszeri bejelentkezéshez (SSO).</span><span class="sxs-lookup"><span data-stu-id="68ed4-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="68ed4-116">A titkosított felhasználói adatok tárolása (név, vezetéknév, e-mail).</span><span class="sxs-lookup"><span data-stu-id="68ed4-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="68ed4-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="68ed4-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="68ed4-118">A kosárpéldányhoz hozzáadott termékek listájának beszerzésére használt üzletkosár-azonosító.</span><span class="sxs-lookup"><span data-stu-id="68ed4-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="68ed4-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="68ed4-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="68ed4-120">A cookie-k megfelelőségi jóváhagyásának követése.</span><span class="sxs-lookup"><span data-stu-id="68ed4-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="68ed4-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="68ed4-121">ai_session</span></span>                                  | <span data-ttu-id="68ed4-122">Azt észleli, hogy a felhasználói tevékenységek számának hány munkafolyamata tartalmazza az alkalmazás bizonyos oldalait és szolgáltatásait.</span><span class="sxs-lookup"><span data-stu-id="68ed4-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="68ed4-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="68ed4-123">ai_user</span></span>                                     | <span data-ttu-id="68ed4-124">Észleli, hogy hány ember használta az alkalmazást és annak funkcióit.</span><span class="sxs-lookup"><span data-stu-id="68ed4-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="68ed4-125">A felhasználókat anonim azonosítók alapján számítja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="68ed4-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="68ed4-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="68ed4-126">b2cru</span></span>                                       | <span data-ttu-id="68ed4-127">Dinamikusan tárolja az átirányítási URL-t.</span><span class="sxs-lookup"><span data-stu-id="68ed4-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="68ed4-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="68ed4-128">JSESSIONID</span></span>                                  | <span data-ttu-id="68ed4-129">Az Adyen fizetési összekötő használja a felhasználói munkamenet tárolásához.</span><span class="sxs-lookup"><span data-stu-id="68ed4-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="68ed4-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="68ed4-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="68ed4-131">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="68ed4-131">Authentication</span></span>                                               |
| <span data-ttu-id="68ed4-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="68ed4-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="68ed4-133">A kérelem állapotának fenntartására szolgál.</span><span class="sxs-lookup"><span data-stu-id="68ed4-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="68ed4-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="68ed4-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="68ed4-135">A webhelyközi kérések hamisítása (CRSF) jogkivonata, amely a CRSF-től történő védelemhez használatos.</span><span class="sxs-lookup"><span data-stu-id="68ed4-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="68ed4-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="68ed4-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="68ed4-137">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="68ed4-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="68ed4-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="68ed4-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="68ed4-139">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="68ed4-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="68ed4-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="68ed4-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="68ed4-141">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="68ed4-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="68ed4-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="68ed4-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="68ed4-143">Az SSO-munkamenet fenntartására szolgál.</span><span class="sxs-lookup"><span data-stu-id="68ed4-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="68ed4-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="68ed4-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="68ed4-145">A tranzakciók nyomon követésére szolgál (azoknak a nyitott lapoknak a száma, amelyeknek hitelesítése vállalatok közötti (B2C) helyhez történik), az aktuális tranzakciót is beleértve.</span><span class="sxs-lookup"><span data-stu-id="68ed4-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="68ed4-146">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="68ed4-146">Additional resources</span></span>

[<span data-ttu-id="68ed4-147">Kisegítő funkciók és lehetőségek</span><span class="sxs-lookup"><span data-stu-id="68ed4-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="68ed4-148">Megfelelőség áttekintése</span><span class="sxs-lookup"><span data-stu-id="68ed4-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="68ed4-149">Adatvédelmi irányelv oldalának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="68ed4-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="68ed4-150">Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése</span><span class="sxs-lookup"><span data-stu-id="68ed4-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)
