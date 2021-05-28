---
title: E-kereskedelmi webhely áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce e-kereskedelmi webhelyeinek támogatásáról.
author: bicyclingfool
ms.date: 11/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 55c40029082e49c1fbc9d9d5e9361218e5ddc5a0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022472"
---
# <a name="e-commerce-site-overview"></a>E-kereskedelmi webhely áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce e-kereskedelmi webhelyeinek támogatásáról. Információkat tartalmaz arról, hogy az e-kereskedelem online áruházait hogyan inicializálják és kezelik a Dynamics 365 Commerce rendszerben. A témakör az online áruházakkal kapcsolatos további információkra mutató hivatkozásokat is tartalmaz, valamint információt nyújt az e-kereskedelmi webhely beállításáról és konfigurálásáról. Bár ez a témakör számos alapvető tudnivalót tartalmaz, nem terjed ki mindenre, ami egy éles e-kereskedelmi webhely beállításához szükséges. A Dynamics 365 Commerce dokumentációban részletesebb témakörök találhatók.

## <a name="online-store-channel"></a>Online áruház csatornája

Mielőtt új webhely hozna létre a Dynamics 365 Commerce alkalmazásban, létre kell hoznia legalább egy online üzleti csatornát. További információt az [Online csatorna beállítása](channel-setup-online.md) című témakörben talál. 

A Dynamics 365 Commerce alkalmazásban egy online üzlet csatorna használatával alakítja ki a termékeket, az árazást, a nyelveket, a fizetési módokat, a teljesítési műhelyeket, valamint a vásárlók számára kínált online élmény egyéb szempontjait.

Csak egy online üzlet csatornát kell beállítani a Dynamics 365 Commerce használatának megkezdéshez. Egyetlen e-kereskedelmi webhely azonban több online áruház számára is képes biztosítani az online élményt. Ha például több online áruház van beállítva különböző földrajzi régió támogatására, akkor az e-kereskedelmi oldalak egyetlen csoportja használható az egyes üzletek által meghatározott egyedi élmények biztosítására. További információt arról, hogy miként állíthat be egy webhelyet több online áruház támogatásához, az [Online webhely társítása csatornával](associate-site-online-store.md) című témakörben talál.

Miután beállított egy online áruházat, társíthatja azt a Dynamics 365 Commerce webhellyel, amely online kirakatként szolgál majd. További információ az online áruházakról és a beállításuk módjáról az [Online áruházak beállítása](/dynamics365/unified-operations/retail/online-stores) című témakörben található.

## <a name="deploy-a-new-e-commerce-tenant"></a>Új e-kereskedelmi bérlő telepítése

Az e-kereskedelmi webhely inicializálása során a rendszer tartománynevet kér. A Commerce-ben használt tartományokkal kapcsolatos további információkért lásd: [Tartománynév konfigurálása](configure-your-domain-name.md) és [Tartományok a Dynamics 365 Commerce rendszerben](domains-commerce.md). Ha új e-kereskedelmi bérlőt szeretne telepíteni a [Microsoft Dynamics Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide) használatával, kövesse az [Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md) című részben leírt lépéseket. Miután az e-kereskedelmi bérlő be van állítva az LCS-ben, a rendszer egy linket biztosít a Commerce webhelyépítőjéhez. Ezután a Commerce webhelyszerkesztővel inicializálhatja és konfigurálhatja az e-kereskedelmi webhelyeket.

## <a name="initialize-your-e-commerce-site"></a>Az e-kereskedelmi webhely inicializálása

Amikor elindítja a Commerce webhelyszerkesztőt az LCS-ből, megjelenik a **Webhelyek** lap. Ez az oldal két előre konfigurált webhelyet tartalmaz, az **alapértelmezett** elemet és a **fabrikam** elemet, amint az a következő ábrán látható példában látható.

![Webhelyek lap a Commerce webhelyszerkesztőjében](media/e-commerce-site-01.png)

Ha kijelöli az egyik ilyen webhelyet, a rendszer kéri, hogy válasszon ki egy tartománynevet, egy alapértelmezett online áruházi csatornát, a kijelölt csatorna támogatott nyelvét és egy elérési utat. Ha csak egy csatornát használ, üresen hagyhatja az elérési utat. A Commerce webhelyszerkesztőben később további online áruházi csatornák vagy nyelvek is konfigurálhatók. Minden további csatornához vagy nyelvhez egyedi elérési út szükséges. Például két online csatornája van, amelyek egyetlen webhelyhez vannak társítva, és a webhely tartományneve `www.fabrikam.com`. Ebben az esetben az egyik csatorna elérési útja lehet az alapértelmezett érték, amelynek nincs elérési útja (`https://www.fabrikam.com`), és a második csatorna beállítható egy új elérési útra, például a **site2**, amely rendelkezik a következő URL-címmel: `https://www.fabrikam.com/site2`. A következő ábra egy példa a kereskedelmi webhelyszerkesztő webhelyinicializálási párbeszédpanelre.

![Webhely inicializálása párbeszédpanel a Commerce webhelyszerkesztőben](media/e-commerce-site-02.png)

A **Webhelyek** lapon egy **Új webhely** gomb is szerepel. A gomb kiválasztásakor megjelenő párbeszédpanel hasonlít a webhely inicializálása párbeszédpanelre, de új webhely létrehozására szolgál. Az új webhelyek üresek. Nem tartalmazzák ugyanazokat az alapértelmezett sablonokat, töredékeket, oldalakat és képeket, amelyek az **alapértelmezett** és a **fabrikam** webhelyekhez tartoznak. Szükség esetén azonban nyithat egy támogatási jegyet, amelyből kérheti, hogy az alapértelmezett tartalom egy példányát adják hozzá egy új üres webhelyhez. További információért lásd: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md).

Az új webhely inicializálása után megjelenik a Commerce webhelyszerkesztő **Kezdőlapja**. Ez az oldal a gyakori műveletekre és útmutatási tartalomra mutató hivatkozásokat tartalmaz, amint az a következő ábrán látható.

![Hivatkozások a Commerce webhelyszerkesztő kezdőlapján](media/e-commerce-site-03.png)

## <a name="modify-online-store-channels-or-add-online-store-channels-to-an-e-commerce-site"></a>Online áruházi csatornák módosítása vagy online áruházi csatornák hozzáadása e-kereskedelmi webhelyhez

Az e-kereskedelmi webhely létrehozása után módosíthatja a hozzá társított csatornát, ha követi az [E-kereskedelmi webhely online csatornához való társítása](associate-site-online-store.md) című lépéseit. Az alábbi ábrán látható példa bemutatja, hogyan módosítható a csatorna üzemi egységének száma (OUN) a **Csatornák** oldalon (**Webhelybeállítások \> Csatornák**) oldalon. A módosítás befejezése után válassza a **Mentés és közzététel** lehetőséget. Ily módon biztosítja, hogy a módosítás közzé legyen téve.

![Csatornák lap a Commerce webhelyszerkesztőjében](media/e-commerce-site-04.png)

Új csatornákat a **Csatorna hozzáadása** lehetőséget választva adhat hozzá. Ha új nyelveket szeretne hozzáadni egy csatornához, jelölje ki a csatornát, majd a megjelenő csatorna párbeszédpanelen válassza a **Területi beállítás hozzáadása** lehetőséget. Ahhoz, hogy a területi beállítások megjelenjenek a párbeszédpanelen, az online áruház csatornához előre kell konfigurálni őket a Commerce központjában.

![Csatorna párbeszédpanel a Commerce webhelyszerkesztőben](media/e-commerce-site-05.png)

## <a name="set-up-an-azure-b2c-tenant"></a>Azure B2C-bérlő beállítása

A Dynamics 365 Commerce az Azure Active Directory (Azure AD) vállalat és ügyfél közötti (B2C) protokollt használja a felhasználók hitelesítő adatainak és hitelesítési folyamatainak támogatásához. Az Azure B2C-bérlő beállításáról további információkat a [B2C-bérlő beállítása a Commerce-ben](set-up-b2c-tenant.md), [Egyéni oldalak beállítása felhasználói bejelentkezéshez](custom-pages-user-logins.md) és a [B2C-bérlő konfigurálása Commerce-környezetben](configure-multi-b2c-tenants.md) című témakörben talál.

## <a name="overview-of-the-default-site-pages"></a>Az alapértelmezett webhelyoldalak áttekintése

Az **alapértelmezett** és a **fabrikam** webhelyek előre konfigurált sablonokat, töredékeket és lapokat tartalmaznak az első lépések hez. További információért tekintse át az alábbi témaköröket:

- [Kezdőlap – áttekintés](quick-tour-home-page.md)
- [Termékadatok oldal áttekintése](quick-tour-pdp.md)
- [Kosár és pénztár oldalainak áttekintése](quick-tour-cart-checkout.md)
- [A fiókkezelési oldalak áttekintése](quick-tour-account-management.md)

## <a name="manage-site-settings"></a>Webhelybeállítások kezelése

Ha szeretne többet megtudni a webhelybeállítások kezeléséről, tekintse át az alábbi témaköröket:

- [Az e-kereskedelem felhasználóinak és szerepköreinek kezelése](manage-ecommerce-users-roles.md)
- [A webhely keresőmotor-optimalizálási (SEO) szempontjai](/search-engine-optimization-considerations.md)
- [Tartalomra vonatkozó biztonsági irányelv (CSP) kezelése](manage-csp.md)
- [Webhely témájának kiválasztása](select-site-theme.md)

## <a name="manage-site-content"></a>Webhelytartalom kezelése

Ha szeretne többet megtudni a webhelytartalom kezeléséről, tekintse át az alábbi témaköröket:

- [Oldal modellszószedete](page-elements-overview.md)
- [Állapotok és életciklus dokumentálása](document-states-overview.md)
- [Sablonok és elrendezés](templates-layouts-overview.md)
- [Töredékek használata](work-with-fragments.md)
- [Modulok használata](work-with-modules.md)
- [Digitális eszközkezelés – áttekintés](dam-overview.md)
- [Modultár áttekintése](starter-kit-overview.md)

## <a name="additional-resources"></a>További erőforrások

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Új e-kereskedelmi webhely üzembe helyezése](deploy-ecommerce-site.md)

[Online webhely társítása csatornával](associate-site-online-store.md)

[Tartománynév konfigurálása](configure-your-domain-name.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]