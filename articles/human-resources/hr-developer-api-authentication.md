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
# <a name="authentication"></a>Hitelesítés

Ez a cikk áttekintést nyújt arról, hogyan lehet hitelesítést végrehajtani a Microsoft Dynamics 365 Human Resources adatainak alkalmazásprogramozási felületén (API).

## <a name="overview"></a>Áttekintés

A Human Resources API-ja az OData szolgáltatás megvalósítása. További információ: [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Az alkalmazást engedélyezett hívóként kell hitelesítenie, mielőtt az API kiszolgálná az alkalmazástól érkező kéréseket.

## <a name="fundamentals"></a>Alapelvek

Az adat-API hívásához az alkalmazásának hozzáférési tokent kell beszereznie a Microsoft Identity platformtól. A hozzáférési token az alkalmazásával kapcsolatos információkat tartalmaz, valamint az engedélyt, amellyel rendelkezik a Human Resources szolgáltatás erőforrásainak hívásához.

### <a name="access-token"></a>Hozzáférési jogkivonat

A Microsoft Identity platform által kiadott hozzáférési tokenek base64-kódolású JSON (JavaScript Object Notation) webes tokenek (JWT). Olyan információkat (jogcímeket) tartalmaznak, amelyeket az adat-API (és a Microsoft Identity platform által biztosított egyéb webes API-k) arra használnak, hogy ellenőrizzék a hívót, és meggyőződjenek arról, hogy a hívónak megfelelő engedélyei vannak a kért művelet végrehajtásához. A hívások közben a hozzáférési tokeneket kezelheti titkosítottként. A hozzáférési tokeneket mindig biztonságos csatornán kell továbbítani, például a TLS (Transport Layer Security) és a HTTPS (Hypertext Transfer Protocol Secure) protokollon.

Alább látható egy példa a Microsoft Identity platform által kiadott hozzáférési tokenre.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Az adat-API hívásához a hozzáférési tokent a HTTP-kérelem engedélyezési fejlécéhez kell csatolnia tulajdonosi tokenként. Íme, egy példa.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Új alkalmazás regisztrálása az Azure portál használatával

1. Jelentkezzen be a [Microsoft Azure portálra](https://portal.azure.com) munkahelyi vagy iskolai fiókkal vagy egy személyes Microsoft fiókkal.

2. Ha a fiókja több bérlőhöz is biztosít hozzáférést, válassza ki a fiókját a jobb felső sarokban, és állítsa be a portálos munkamenetet a kívánt Azure Active Directory-bérlőre (Azure AD).

3. A bal oldali ablaktáblában válassza az **Azure Active Directory** szolgáltatást, majd válassza az **Alkalmazásregisztrációk \> Új regisztráció** elemet.

4. Amikor megjelenik az **Alkalmazás regisztrálása** oldal, adja meg az alkalmazás regisztrációs adatait:

    - **Név**: Adjon meg értelemszerű alkalmazásnevet, amely az alkalmazás felhasználóinak fog megjelenni.
    - **Támogatott fióktípusok**: Válassza ki azokat a fióktípusokat, amelyeket az alkalmazásnak támogatnia kell.

        | Támogatott számlatípusok | Leírás |
        |-------------------------|-------------|
        | Csak az ebben a szervezeti címtárban lévő fiókok | Akkor válassza ezt a lehetőséget, ha adott üzletághoz kapcsolódó alkalmazást készít. Ez a beállítás csak akkor érhető el, ha az alkalmazást bejegyzi egy címtárba.<p>Ez a beállítás az **Azure AD – csak egybérlős** beállításhoz van hozzákapcsolva.</p><p>Ez a beállítás az alapértelmezett beállítás, ha az alkalmazást nem címtáron kívül jegyzi be. Utóbbi esetben az alapértelmezett beállítás az **Azure AD – több-bérlős és Microsoft személyes fiók**.</p> |
        | Bármelyik szervezeti címtárban lévő fiókok | Akkor válassza ezt a lehetőséget, ha az összes üzleti és oktatási vevőt meg szeretné célozni.<p>Ez a beállítás az **Azure AD – csak több-bérlős** beállításhoz van hozzákapcsolva.</p><p>Ha az alkalmazást az **Azure AD – csak egybérlős** beállítással jegyezte be, akkor a **Hitelesítés** panelen módosíthatja **Azure AD – csak több-bérlős**, majd vissza **Azure AD – csak egybérlős** beállításúra.</p> |
        | A szervezeti címtárban és a személyes Microsoft-fiókban szereplő fiókok | Válassza ezt a lehetőséget, ha a vevők legszélesebb csoportját szeretné célozni.<p>Ez a beállítás az **Azure AD – több-bérlős és Microsoft személyes fiók** beállításhoz van hozzákapcsolva.</p><p>Ha az alkalmazást az **Azure AD – több-bérlős és Microsoft személyes fiók** beállítással jegyezte be, akkor a felhasználói felületen (UI) nem módosíthatja ezt. Ehelyett az alkalmazásjegyzék-szerkesztőt kell használnia a támogatott fióktípusok módosításához.</p> |

    - **Átirányítási URI (nem kötelező)** – Válassza ki a létrehozott alkalmazás típusát: **Web** vagy **Nyilvános ügyfél (mobil és asztali)**. Ezután adja meg az átirányítási URI-t (vagy a válaszadási URL-t) az alkalmazáshoz.

        - Webalkalmazások esetében az alkalmazás alap URL-címét adja meg. Például a `http://localhost:31544` lehet a helyi számítógépen futó webalkalmazás URL-címe. A felhasználók ezután ezt az URL-címet használhatják a webes ügyfél alkalmazásába való bejelentkezéshez.
        - A nyilvános ügyfelek esetében adja meg azt az URI-t, amelyet az Azure AD a tokenválaszok visszaküldésére használ. Adjon meg az alkalmazásra jellemző értéket, például: `myapp://auth`.

        A webalkalmazásokhoz és a natív alkalmazásokhoz kapcsolódó példákat a [Microsoft Identity platform (korábban Azure Active Directory fejlesztőknek) webhelyén található útmutatók tartalmazzák](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).

5. Az **API-engedélyek** területen válassza az **Engedély hozzáadása** lehetőséget. Ezután a **Szervezet által használt API-k** lapon keresse meg a **Dynamics 365 Human Resources** alkalmazást, majd adja hozzá a **user\_impersonation** engedélyt az alkalmazáshoz. A Human Resources esetében az alkalmazás azonosítója: f9be0c49-aa22-4ec6-911a-c5da515226ff. Ezzel az azonosítóval biztosítható a megfelelő alkalmazás kiválasztása.

6. Válassza a **Regisztrálás** lehetőséget.

   [![Új alkalmazás regisztrálása az Azure portálon](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Az Azure AD egyedi alkalmazásazonosítót (ügyfélazonosítót) rendel hozzá az alkalmazásához, majd megjeleníti az alkalmazás **Áttekintés** lapját. Ha további funkciókat szeretne hozzáadni az alkalmazáshoz, további konfigurációs beállításokat is megadhat, például a márkajelzések, a tanúsítványok és titkos kódok beállításait.

## <a name="retrieving-an-access-token"></a>Hozzáférési token beolvasása

A Human Resources adat-API-jának hívására használt hozzáférési token beolvasásának jellemzői attól függenek, hogy milyen technológiákat használ az ügyfélalkalmazás fejlesztéséhez. Lehetséges például, hogy [külső gyártótól származó eszköz tesztel](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (például a Postman alkalmazást), C# konzolalkalmazást vagy webszolgáltatást fejleszt, vagy JavaScript/TypeScript ügyfelet hoz létre.

Példa C# ügyfélalkalmazásra:
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

Miután beolvasta a hozzáférési tokent, akkor a tokent az engedélyezési fejlécben kell átadnia tulajdonosi tokenként az adat-API számára elküldött minden kérés esetében a fent leírtak szerint.
