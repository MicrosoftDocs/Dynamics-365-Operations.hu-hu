---
title: Cookie-k megfelelősége
description: Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.
author: BrianShook
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2cc2089bc3052c0c59cb0414f8301123a9a30df2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796027"
---
# <a name="cookie-compliance"></a><span data-ttu-id="b61b6-103">Cookie-k megfelelősége</span><span class="sxs-lookup"><span data-stu-id="b61b6-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b61b6-104">Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="b61b6-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b61b6-105">Az adatvédelem fontos tényező, amikor az e-kereskedelmi ügyfelekre hattással lévő nyomkövető technológia kerül használatra.</span><span class="sxs-lookup"><span data-stu-id="b61b6-105">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="b61b6-106">Az adatvédelmi előírások, például az Európai Unió (EU) Általános adatvédelmi rendelete (GDPR) miatt, az elektronikus adatvédelmi irányelveket figyelembe kell venni minden olyan webhelyen, amely jelenleg aktív.</span><span class="sxs-lookup"><span data-stu-id="b61b6-106">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="b61b6-107">Mivel számos e-kereskedelmi webhely alapértelmezésben globálisan elérhető, fontos, hogy ellenőrizze az e-kereskedelmi webhely megfelelési szabványait.</span><span class="sxs-lookup"><span data-stu-id="b61b6-107">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="b61b6-108">Ha többet szeretne megtudni a Microsoft által a cookie-k megfelelősége esetében használt alapelvekről, keresse fel a [Microsoft megbízhatósági központját](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="b61b6-108">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="b61b6-109">Ezen a webhelyen további információkat is kaphat a megfelelőségi és adatvédelmi területekről.</span><span class="sxs-lookup"><span data-stu-id="b61b6-109">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="b61b6-110">A következő táblázat felsorolja a Dynamics 365 Commerce helyek által feladott cookie-k jelenlegi hivatkozási listáját.</span><span class="sxs-lookup"><span data-stu-id="b61b6-110">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="b61b6-111">Cookie neve</span><span class="sxs-lookup"><span data-stu-id="b61b6-111">Cookie name</span></span>                               | <span data-ttu-id="b61b6-112">Használat</span><span class="sxs-lookup"><span data-stu-id="b61b6-112">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="b61b6-113">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="b61b6-113">.AspNet.Cookies</span></span>                             | <span data-ttu-id="b61b6-114">Microsoft Azure Active Directory (Azure AD) hitelesítési cookie-k tárolása egyszeri bejelentkezéshez (SSO).</span><span class="sxs-lookup"><span data-stu-id="b61b6-114">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="b61b6-115">A titkosított felhasználói adatok tárolása (név, vezetéknév, e-mail).</span><span class="sxs-lookup"><span data-stu-id="b61b6-115">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="b61b6-116">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="b61b6-116">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="b61b6-117">A kosárpéldányhoz hozzáadott termékek listájának beszerzésére használt üzletkosár-azonosító.</span><span class="sxs-lookup"><span data-stu-id="b61b6-117">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="b61b6-118">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="b61b6-118">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="b61b6-119">A cookie-k megfelelőségi jóváhagyásának követése.</span><span class="sxs-lookup"><span data-stu-id="b61b6-119">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="b61b6-120">ai_session</span><span class="sxs-lookup"><span data-stu-id="b61b6-120">ai_session</span></span>                                  | <span data-ttu-id="b61b6-121">Azt észleli, hogy a felhasználói tevékenységek számának hány munkafolyamata tartalmazza az alkalmazás bizonyos oldalait és szolgáltatásait.</span><span class="sxs-lookup"><span data-stu-id="b61b6-121">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="b61b6-122">ai_user</span><span class="sxs-lookup"><span data-stu-id="b61b6-122">ai_user</span></span>                                     | <span data-ttu-id="b61b6-123">Észleli, hogy hány ember használta az alkalmazást és annak funkcióit.</span><span class="sxs-lookup"><span data-stu-id="b61b6-123">Detects how many people used the app and its features.</span></span> <span data-ttu-id="b61b6-124">A felhasználókat anonim azonosítók alapján számítja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="b61b6-124">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="b61b6-125">b2cru</span><span class="sxs-lookup"><span data-stu-id="b61b6-125">b2cru</span></span>                                       | <span data-ttu-id="b61b6-126">Dinamikusan tárolja az átirányítási URL-t.</span><span class="sxs-lookup"><span data-stu-id="b61b6-126">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="b61b6-127">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="b61b6-127">JSESSIONID</span></span>                                  | <span data-ttu-id="b61b6-128">Az Adyen fizetési összekötő használja a felhasználói munkamenet tárolásához.</span><span class="sxs-lookup"><span data-stu-id="b61b6-128">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="b61b6-129">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="b61b6-129">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="b61b6-130">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="b61b6-130">Authentication</span></span>                                               |
| <span data-ttu-id="b61b6-131">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="b61b6-131">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="b61b6-132">A kérelem állapotának fenntartására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b61b6-132">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="b61b6-133">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="b61b6-133">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="b61b6-134">A webhelyközi kérések hamisítása (CRSF) jogkivonata, amely a CRSF-től történő védelemhez használatos.</span><span class="sxs-lookup"><span data-stu-id="b61b6-134">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="b61b6-135">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="b61b6-135">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="b61b6-136">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b61b6-136">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="b61b6-137">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="b61b6-137">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="b61b6-138">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b61b6-138">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="b61b6-139">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="b61b6-139">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="b61b6-140">A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b61b6-140">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="b61b6-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="b61b6-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="b61b6-142">Az SSO-munkamenet fenntartására szolgál.</span><span class="sxs-lookup"><span data-stu-id="b61b6-142">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="b61b6-143">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="b61b6-143">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="b61b6-144">A tranzakciók nyomon követésére szolgál (azoknak a nyitott lapoknak a száma, amelyeknek hitelesítése vállalatok közötti (B2C) helyhez történik), az aktuális tranzakciót is beleértve.</span><span class="sxs-lookup"><span data-stu-id="b61b6-144">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="b61b6-145">Webhely felhasználó cookie-hozzájárulása egy e-kereskedelmi weboldalon</span><span class="sxs-lookup"><span data-stu-id="b61b6-145">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="b61b6-146">Ha egy e-kereskedelmi oldal funkciója vagy modulja nem alapvető cookie-t használ, akkor a webhely felhasználójának hozzájárulását a cookie nyomon követése előtt kell beszerezni.</span><span class="sxs-lookup"><span data-stu-id="b61b6-146">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="b61b6-147">Ha engedélyezni szeretné, hogy a webhely felhasználói cookie-hozzájárulást adjanak az e-kereskedelemi webhelyen a webhelyhez tartozó szerzőnek hozzá kell adnia és be kell állítania egy cookie-hozzájárulási modult a lap fejlécmoduljában, hogy a rendszer biztosítsa a jóváhagyás fogadását.</span><span class="sxs-lookup"><span data-stu-id="b61b6-147">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="b61b6-148">A webhely felhasználói hozzájárulását meg kell adni, mielőtt a nem alapvető cookie-t használó funkció vagy modul a webhely oldalán meg lenne jelenítve.</span><span class="sxs-lookup"><span data-stu-id="b61b6-148">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b61b6-149">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b61b6-149">Additional resources</span></span>

[<span data-ttu-id="b61b6-150">Kisegítő funkciók és lehetőségek</span><span class="sxs-lookup"><span data-stu-id="b61b6-150">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="b61b6-151">Megfelelőség áttekintése</span><span class="sxs-lookup"><span data-stu-id="b61b6-151">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="b61b6-152">Adatvédelmi irányelv oldalának hozzáadása</span><span class="sxs-lookup"><span data-stu-id="b61b6-152">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="b61b6-153">Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése</span><span class="sxs-lookup"><span data-stu-id="b61b6-153">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="b61b6-154">Cookie-hozzájárulás modul</span><span class="sxs-lookup"><span data-stu-id="b61b6-154">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="b61b6-155">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="b61b6-155">Header module</span></span>](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
