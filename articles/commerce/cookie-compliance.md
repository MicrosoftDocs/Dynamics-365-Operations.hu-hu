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
# <a name="cookie-compliance"></a>Cookie-k megfelelősége

[!include [banner](includes/banner.md)]

Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.

## <a name="overview"></a>Áttekintés

Az adatvédelem fontos tényező, amikor az e-kereskedelmi ügyfelekre hattással lévő nyomkövető technológia kerül használatra. Az adatvédelmi előírások, például az Európai Unió (EU) Általános adatvédelmi rendelete (GDPR) miatt, az elektronikus adatvédelmi irányelveket figyelembe kell venni minden olyan webhelyen, amely jelenleg aktív. Mivel számos e-kereskedelmi webhely alapértelmezésben globálisan elérhető, fontos, hogy ellenőrizze az e-kereskedelmi webhely megfelelési szabványait.

Ha többet szeretne megtudni a Microsoft által a cookie-k megfelelősége esetében használt alapelvekről, keresse fel a [Microsoft megbízhatósági központját](https://www.microsoft.com/trust-center). Ezen a webhelyen további információkat is kaphat a megfelelőségi és adatvédelmi területekről.

A következő táblázat felsorolja a Dynamics 365 Commerce helyek által feladott cookie-k jelenlegi hivatkozási listáját.

| Cookie neve                               | Használat                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Microsoft Azure Active Directory (Azure AD) hitelesítési cookie-k tárolása egyszeri bejelentkezéshez (SSO). A titkosított felhasználói adatok tárolása (név, vezetéknév, e-mail). |
| &#95;msdyn365___cart&#95;                           | A kosárpéldányhoz hozzáadott termékek listájának beszerzésére használt üzletkosár-azonosító. |
| &#95;msdyn365___ucc&#95;                            | A cookie-k megfelelőségi jóváhagyásának követése.                          |
| ai_session                                  | Azt észleli, hogy a felhasználói tevékenységek számának hány munkafolyamata tartalmazza az alkalmazás bizonyos oldalait és szolgáltatásait. |
| ai_user                                     | Észleli, hogy hány ember használta az alkalmazást és annak funkcióit. A felhasználókat anonim azonosítók alapján számítja a rendszer. |
| b2cru                                       | Dinamikusan tárolja az átirányítási URL-t.                              |
| JSESSIONID                                  | Az Adyen fizetési összekötő használja a felhasználói munkamenet tárolásához.       |
| OpenIdConnect.nonce.&#42;                       | Hitelesítés                                               |
| x-ms-cpim-cache:.&#42;                          | A kérelem állapotának fenntartására szolgál.                      |
| x-ms-cpim-csrf                              | A webhelyközi kérések hamisítása (CRSF) jogkivonata, amely a CRSF-től történő védelemhez használatos.     |
| x-ms-cpim-dc                                | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. |
| x-ms-cpim-rc.&#42;                              | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. |
| x-ms-cpim-slice                             | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Az SSO-munkamenet fenntartására szolgál.                        |
| x-ms-cpim-trans                             | A tranzakciók nyomon követésére szolgál (azoknak a nyitott lapoknak a száma, amelyeknek hitelesítése vállalatok közötti (B2C) helyhez történik), az aktuális tranzakciót is beleértve. |

## <a name="additional-resources"></a>További erőforrások

[Kisegítő funkciók és lehetőségek](accessibility.md)

[Megfelelőség áttekintése](compliance-overview.md)

[Adatvédelmi irányelv oldalának hozzáadása](add-privacy-page.md)

[Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése](replace-IDs-tracked-changes.md)
