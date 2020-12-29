---
title: Hitelesítés
description: Ez a cikk áttekintést nyújt arról, hogyan lehet hitelesítést végrehajtani a Microsoft Dynamics 365 Human Resources adatainak alkalmazásprogramozási felületén (API).
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a0509ce99205d49d516e180203ffb65a1dc09a7c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418782"
---
# <a name="authentication"></a><span data-ttu-id="7c9f8-103">Hitelesítés</span><span class="sxs-lookup"><span data-stu-id="7c9f8-103">Authentication</span></span>

<span data-ttu-id="7c9f8-104">Ez a cikk áttekintést nyújt arról, hogyan lehet hitelesítést végrehajtani a Microsoft Dynamics 365 Human Resources adatainak alkalmazásprogramozási felületén (API).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="7c9f8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7c9f8-105">Overview</span></span>

<span data-ttu-id="7c9f8-106">A Human Resources API-ja az OData szolgáltatás megvalósítása.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="7c9f8-107">További információ: [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="7c9f8-108">Az alkalmazást engedélyezett hívóként kell hitelesítenie, mielőtt az API kiszolgálná az alkalmazástól érkező kéréseket.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="7c9f8-109">Alapelvek</span><span class="sxs-lookup"><span data-stu-id="7c9f8-109">Fundamentals</span></span>

<span data-ttu-id="7c9f8-110">Az adat-API hívásához az alkalmazásának hozzáférési tokent kell beszereznie a Microsoft Identity platformtól.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="7c9f8-111">A hozzáférési token az alkalmazásával kapcsolatos információkat tartalmaz, valamint az engedélyt, amellyel rendelkezik a Human Resources szolgáltatás erőforrásainak hívásához.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="7c9f8-112">Hozzáférési jogkivonat</span><span class="sxs-lookup"><span data-stu-id="7c9f8-112">Access token</span></span>

<span data-ttu-id="7c9f8-113">A Microsoft Identity platform által kiadott hozzáférési tokenek base64-kódolású JSON (JavaScript Object Notation) webes tokenek (JWT).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="7c9f8-114">Olyan információkat (jogcímeket) tartalmaznak, amelyeket az adat-API (és a Microsoft Identity platform által biztosított egyéb webes API-k) arra használnak, hogy ellenőrizzék a hívót, és meggyőződjenek arról, hogy a hívónak megfelelő engedélyei vannak a kért művelet végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="7c9f8-115">A hívások közben a hozzáférési tokeneket kezelheti titkosítottként.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="7c9f8-116">A hozzáférési tokeneket mindig biztonságos csatornán kell továbbítani, például a TLS (Transport Layer Security) és a HTTPS (Hypertext Transfer Protocol Secure) protokollon.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="7c9f8-117">Alább látható egy példa a Microsoft Identity platform által kiadott hozzáférési tokenre.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="7c9f8-118">Az adat-API hívásához a hozzáférési tokent a HTTP-kérelem engedélyezési fejlécéhez kell csatolnia tulajdonosi tokenként.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="7c9f8-119">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="7c9f8-120">Új alkalmazás regisztrálása az Azure portál használatával</span><span class="sxs-lookup"><span data-stu-id="7c9f8-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="7c9f8-121">Jelentkezzen be a [Microsoft Azure portálra](https://portal.azure.com) munkahelyi vagy iskolai fiókkal vagy egy személyes Microsoft fiókkal.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="7c9f8-122">Ha a fiókja több bérlőhöz is biztosít hozzáférést, válassza ki a fiókját a jobb felső sarokban, és állítsa be a portálos munkamenetet a kívánt Azure Active Directory-bérlőre (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="7c9f8-123">A bal oldali ablaktáblában válassza az **Azure Active Directory** szolgáltatást, majd válassza az **Alkalmazásregisztrációk \> Új regisztráció** elemet.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="7c9f8-124">Amikor megjelenik az **Alkalmazás regisztrálása** oldal, adja meg az alkalmazás regisztrációs adatait:</span><span class="sxs-lookup"><span data-stu-id="7c9f8-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="7c9f8-125">**Név**: Adjon meg értelemszerű alkalmazásnevet, amely az alkalmazás felhasználóinak fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="7c9f8-126">**Támogatott fióktípusok**: Válassza ki azokat a fióktípusokat, amelyeket az alkalmazásnak támogatnia kell.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="7c9f8-127">Támogatott számlatípusok</span><span class="sxs-lookup"><span data-stu-id="7c9f8-127">Supported account types</span></span> | <span data-ttu-id="7c9f8-128">Leírás</span><span class="sxs-lookup"><span data-stu-id="7c9f8-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="7c9f8-129">Csak az ebben a szervezeti címtárban lévő fiókok</span><span class="sxs-lookup"><span data-stu-id="7c9f8-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="7c9f8-130">Akkor válassza ezt a lehetőséget, ha adott üzletághoz kapcsolódó alkalmazást készít.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="7c9f8-131">Ez a beállítás csak akkor érhető el, ha az alkalmazást bejegyzi egy címtárba.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="7c9f8-132">Ez a beállítás az **Azure AD – csak egybérlős** beállításhoz van hozzákapcsolva.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="7c9f8-133">Ez a beállítás az alapértelmezett beállítás, ha az alkalmazást nem címtáron kívül jegyzi be.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="7c9f8-134">Utóbbi esetben az alapértelmezett beállítás az **Azure AD – több-bérlős és Microsoft személyes fiók**.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="7c9f8-135">Bármelyik szervezeti címtárban lévő fiókok</span><span class="sxs-lookup"><span data-stu-id="7c9f8-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="7c9f8-136">Akkor válassza ezt a lehetőséget, ha az összes üzleti és oktatási vevőt meg szeretné célozni.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="7c9f8-137">Ez a beállítás az **Azure AD – csak több-bérlős** beállításhoz van hozzákapcsolva.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="7c9f8-138">Ha az alkalmazást az **Azure AD – csak egybérlős** beállítással jegyezte be, akkor a **Hitelesítés** panelen módosíthatja **Azure AD – csak több-bérlős**, majd vissza **Azure AD – csak egybérlős** beállításúra.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="7c9f8-139">A szervezeti címtárban és a személyes Microsoft-fiókban szereplő fiókok</span><span class="sxs-lookup"><span data-stu-id="7c9f8-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="7c9f8-140">Válassza ezt a lehetőséget, ha a vevők legszélesebb csoportját szeretné célozni.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="7c9f8-141">Ez a beállítás az **Azure AD – több-bérlős és Microsoft személyes fiók** beállításhoz van hozzákapcsolva.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="7c9f8-142">Ha az alkalmazást az **Azure AD – több-bérlős és Microsoft személyes fiók** beállítással jegyezte be, akkor a felhasználói felületen (UI) nem módosíthatja ezt.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="7c9f8-143">Ehelyett az alkalmazásjegyzék-szerkesztőt kell használnia a támogatott fióktípusok módosításához.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="7c9f8-144">**Átirányítási URI (nem kötelező)** – Válassza ki a létrehozott alkalmazás típusát: **Web** vagy **Nyilvános ügyfél (mobil és asztali)**.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="7c9f8-145">Ezután adja meg az átirányítási URI-t (vagy a válaszadási URL-t) az alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="7c9f8-146">Webalkalmazások esetében az alkalmazás alap URL-címét adja meg.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="7c9f8-147">Például a `http://localhost:31544` lehet a helyi számítógépen futó webalkalmazás URL-címe.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="7c9f8-148">A felhasználók ezután ezt az URL-címet használhatják a webes ügyfél alkalmazásába való bejelentkezéshez.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="7c9f8-149">A nyilvános ügyfelek esetében adja meg azt az URI-t, amelyet az Azure AD a tokenválaszok visszaküldésére használ.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="7c9f8-150">Adjon meg az alkalmazásra jellemző értéket, például: `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="7c9f8-151">A webalkalmazásokhoz és a natív alkalmazásokhoz kapcsolódó példákat a [Microsoft Identity platform (korábban Azure Active Directory fejlesztőknek) webhelyén található útmutatók tartalmazzák](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="7c9f8-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="7c9f8-152">Az **API-engedélyek** területen válassza az **Engedély hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="7c9f8-153">Ezután a **Szervezet által használt API-k** lapon keresse meg a **Dynamics 365 Human Resources** alkalmazást, majd adja hozzá a **user\_impersonation** engedélyt az alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="7c9f8-154">A Human Resources esetében az alkalmazás azonosítója: f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="7c9f8-155">Ezzel az azonosítóval biztosítható a megfelelő alkalmazás kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="7c9f8-156">Válassza a **Regisztrálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-156">Select **Register**.</span></span>

   <span data-ttu-id="7c9f8-157">[![Új alkalmazás regisztrálása az Azure portálon](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7c9f8-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="7c9f8-158">Az Azure AD egyedi alkalmazásazonosítót (ügyfélazonosítót) rendel hozzá az alkalmazásához, majd megjeleníti az alkalmazás **Áttekintés** lapját.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="7c9f8-159">Ha további funkciókat szeretne hozzáadni az alkalmazáshoz, további konfigurációs beállításokat is megadhat, például a márkajelzések, a tanúsítványok és titkos kódok beállításait.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="7c9f8-160">Hozzáférési token beolvasása</span><span class="sxs-lookup"><span data-stu-id="7c9f8-160">Retrieving an access token</span></span>

<span data-ttu-id="7c9f8-161">A Human Resources adat-API-jának hívására használt hozzáférési token beolvasásának jellemzői attól függenek, hogy milyen technológiákat használ az ügyfélalkalmazás fejlesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="7c9f8-162">Lehetséges például, hogy [külső gyártótól származó eszköz tesztel](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (például a Postman alkalmazást), C# konzolalkalmazást vagy webszolgáltatást fejleszt, vagy JavaScript/TypeScript ügyfelet hoz létre.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="7c9f8-163">Példa C# ügyfélalkalmazásra:</span><span class="sxs-lookup"><span data-stu-id="7c9f8-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="7c9f8-164">Miután beolvasta a hozzáférési tokent, akkor a tokent az engedélyezési fejlécben kell átadnia tulajdonosi tokenként az adat-API számára elküldött minden kérés esetében a fent leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="7c9f8-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
