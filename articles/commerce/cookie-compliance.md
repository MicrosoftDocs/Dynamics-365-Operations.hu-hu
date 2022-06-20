---
title: Cookie-k megfelelősége
description: Ez a témakör a sütemény megfelelőségével kapcsolatos szempontokat és az itt szereplő alapértelmezett irányelveket ismerteti Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 03/10/2022
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
ms.openlocfilehash: 6a96ba21f1872b41156768fb7277933e68a16d90
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863553"
---
# <a name="cookie-compliance"></a>Cookie-k megfelelősége

[!include [banner](includes/banner.md)]

Ez a témakör a sütemény megfelelőségével kapcsolatos szempontokat és az itt szereplő alapértelmezett irányelveket ismerteti Microsoft Dynamics 365 Commerce.

Az adatvédelem fontos tényező, amikor az e-kereskedelmi ügyfelekre hattással lévő nyomkövető technológia kerül használatra. Az adatvédelmi előírások, például az Európai Unió (EU) Általános adatvédelmi rendelete (GDPR) miatt, az elektronikus adatvédelmi irányelveket figyelembe kell venni minden olyan webhelyen, amely jelenleg aktív. Mivel számos e-kereskedelmi webhely alapértelmezésben globálisan elérhető, fontos, hogy ellenőrizze az e-kereskedelmi webhely megfelelési szabványait.

Ha többet szeretne megtudni a Microsoft által a cookie-k megfelelősége esetében használt alapelvekről, keresse fel a [Microsoft megbízhatósági központját](https://www.microsoft.com/trust-center). Ezen a webhelyen további információkat is kaphat a megfelelőségi és adatvédelmi területekről.

A következő táblázat felsorolja a Dynamics 365 Commerce helyek által feladott cookie-k jelenlegi hivatkozási listáját.

| Cookie neve                               | Használat                                                        | Élettartam |
| ------------------------------------------- | ------------------------------------------------------------ |  ------- |
| .AspNet.Cookies                             | Microsoft Azure Active Directory (Azure AD) hitelesítési cookie-k tárolása egyszeri bejelentkezéshez (SSO). A titkosított felhasználói adatok tárolása (név, vezetéknév, e-mail). | Munkamenet |
| \_msdyn365___cart_                           | A kosárpéldányhoz hozzáadott termékek listájának beszerzésére használt üzletkosár-azonosító. | Munkamenet |
| \_msdyn365___checkout_cart_                           | A kizietési kosárpéldányhoz hozzáadott termékek listájának beszerzésére használt kifizetési üzletkosár-azonosító. | Munkamenet |
| \_msdyn365___ucc_                            | A cookie-k megfelelőségi jóváhagyásának követése.                          | 1 év |
| ai_session                                  | Azt észleli, hogy a felhasználói tevékenységek számának hány munkafolyamata tartalmazza az alkalmazás bizonyos oldalait és szolgáltatásait. | 30 perc |
| ai_user                                     | Észleli, hogy hány ember használta az alkalmazást és annak funkcióit. A felhasználókat anonim azonosítók alapján számítja a rendszer. | 1 év |
| b2cru                                       | Dinamikusan tárolja az átirányítási URL-t.                              | Munkamenet |
| JSESSIONID                                  | Az Adyen fizetési összekötő használja a felhasználói munkamenet tárolásához.       | Munkamenet |
| OpenIdConnect.nonce.&#42;                       | Hitelesítés                                               | 11 perc |
| x-ms-cpim-cache:.&#42;                          | A kérelem állapotának fenntartására szolgál.                      | Munkamenet |
| x-ms-cpim-csrf                              | A webhelyközi kérések hamisítása (CRSF) jogkivonata, amely a CRSF-től történő védelemhez használatos.     | Munkamenet |
| x-ms-cpim-dc                                | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. | Munkamenet |
| x-ms-cpim-rc.&#42;                              | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. | Munkamenet |
| x-ms-cpim-slice                             | A kérelmeknek a megfelelő termelési hitelesítési kiszolgálópéldány számára történő továbbítására szolgál. | Munkamenet |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Az SSO-munkamenet fenntartására szolgál.                        | Munkamenet |
| x-ms-cpim-trans                             | A tranzakciók nyomon követésére szolgál (azoknak a nyitott lapoknak a száma, amelyeknek hitelesítése vállalatok közötti (B2C) helyhez történik), az aktuális tranzakciót is beleértve. | Munkamenet |
| \_msdyn365___muid_                            | Akkor használatos, ha a kísérletezés aktiválva van a környezetben: felhasználóazonosítóként használatos a kísérletezési célokhoz. | 1 év |
| \_msdyn365___exp_                             | Akkor használatos, ha a kísérletezés aktiválva van a környezetben: a teljesítmény terheléselosztásának mérésére használatos.         | 1 óra |
| d365mkt                                       | Akkor használatos, ha az üzlet helyjavaslataizoz tartozó felhasználói IP-cím nyomon követésének hely alapú észlelési szolgáltatása engedélyezve van a Commerce webhely-szerkesztőjében, a **Webhelybeállítások \> Általános \> Helyalapú áruházészlelés engedélyezése** részen.      | 1 óra |
| \_msdyn365___tuid_                           | Csak akkor használatos, ha a kísérletezés aktiválva van egy környezetben; egy GUID-t generál, amely felhasználói azonosítóként szolgál. Az érték akkor változik, ha a felhasználó bejelentkezési állapota változik.      | 1 év |
| \_msdyn365___aud_0                          | A célzás által használt szegmensértékeket tárolja, és csak akkor használatos, ha a célzás egy lapon vagy egy webhely egyik felhasználója által kért töredéken konfigurálják. A sütit csak akkor helyezi el a rendszer, ha a szegmensértékek egy külső fél szegmentációszolgáltatótól származnak.      | 7 nap |
| \_msdyn365___aud_1                           | A célzás által használt szegmensértékeket tárolja, és csak akkor használatos, ha a célzás egy lapon vagy egy webhely egyik felhasználója által kért töredéken konfigurálják. A sütit csak akkor helyezi el a rendszer, ha a szegmensértékek egy külső fél szegmentációszolgáltatótól származnak.      | 7 nap |
| \_msdyn365___aud_2                           | A célzás által használt szegmensértékeket tárolja, és csak akkor használatos, ha a célzás egy lapon vagy egy webhely egyik felhasználója által kért töredéken konfigurálják. A sütit csak akkor helyezi el a rendszer, ha a szegmensértékek egy külső fél szegmentációszolgáltatótól származnak.      | 7 nap |
| d365gi                                       | Ez a sütemény tárolja a földrajzi elhelyezkedési adatokat harmadik fél földrajzi helyszolgáltatásának használata esetén.      | 1 nap |

Ha egy webhely felhasználója a webhely bármelyik közösségi média hivatkozását kiválasztja, az alábbi táblában található cookie-k is nyomon lesznek követve a böngészőikben.


| Tartomány                      | Cookie               | Leírás                                                  | Forrás                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | LinkedIn-hirdetések azonosítójának szinkronizálása                                      | LinkedIn-csatorna és betekintés címke                                |
| .linkedin.com               | li_sugr                  | Böngésző azonosítója                                           | LinkedIn Címke, ha az IP-cím nem egy kijelölt országban van. |
| .linkedin.com               | BizographicsOptOut       | Meghatározza a harmadik fél követéselutasítási állapotát.              | A LinkedIn vendégvezérlők és az iparág elutasító oldalai           |
| .linkedin.com               | \_guid                    | Böngészőazonosító a Google hirdetésekhez.                            | LinkedIn-csatorna                                                |
| .linkedin.com               | li_oatml                 | Az átalakítások nyomon követésének, újracélzásának és analitikájának a tag közvetett azonosítója. | LinkedIn hirdetések és betekintés címkék                                |
| Különböző belső tartományok | li_fat_id                | Az átalakítások nyomon követésének, újracélzásának és analitikájának a tag közvetett azonosítója. | LinkedIn hirdetések és betekintés címkék                                |
| .adsymptotic.com            | U                        | Böngésző azonosítója                                           | LinkedIn Címke, ha az IP-cím nem egy kijelölt országban van. |
| .linkedin.com                | b                  | Böngészőazonosító cookie                                            | Kérések a LinkedInhez                                         |
| .linkedin.com                | bs                 | Biztonságos böngészőcookie                                        | Kérések a LinkedInhez                                         |
| .linkedin.com               | nyelv                     | Beállítja az alapértelmezett területi beállításokat és a nyelvet.                                 | Kérések a LinkedInhez                                         |
| .linkedin.com                | lidc                     | Útvonaltervezlshez használatos.                                             | Kérések a LinkedInhez                                         |
| .linkedin.com               | aam_uuid                 | Adobe célközönség-kezelői sütemény                                                     | Beállítás azonosítószinkronizáláshoz                                              |
| .linkedin.com               | \_ga                      | Google Analytics cookie                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Google Analytics cookie                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Google Analytics cookie                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | A cookie tartalmazza a jelenleg bejelentkezett felhasználó felhasználói azonosítóját.  |   Facebook                                                           |
| .facebook.com               | datr                     | Annak a webböngészőnek az azonosítására használatos, amely a bejelentkezett felhasználótól Facebook független csatlakozáshoz szükséges. | Facebook                                                             |
| .facebook.com               | wd                       | A böngésző ablakdimenzióit tárolja, és a lap megjelenítésének optimalizálására használja a Facebook. | Facebook                                                             |
| .facebook.com               | xs                       | A munkamenetszámot képviselő kétjegyű szám. Az érték második része egy munkamenet titkos kód. |  Facebook                                                            |
| .facebook.com               | fr                       | Egyedi böngészőt és felhasználói azonosítót tartalmaz a célzott hirdetésekhez. |  Facebook                                                            |
| .facebook.com               | sb                       | A Facebook barátjavaslatokok javítására használható.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | vendégazonosító                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | A cookie tartalmazza a jelenleg bejelentkezett felhasználó felhasználói azonosítóját.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | A cookie tartalmazza a jelenleg bejelentkezett felhasználó felhasználói azonosítóját.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | A cookie oldalakat tartalmaz, amikor a felhasználó a Pinterest gombot választja.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | A cookie oldalakat tartalmaz, amikor a felhasználó a Pinterest gombot választja.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | A felhasználóazonosítót és a cookie létrehozási időbélyegzőjét tartalmazza. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | A cookie oldalakat tartalmaz, amikor a felhasználó a Pinterest gombot választja.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | A cookie oldalakat tartalmaz, amikor a felhasználó a Pinterest gombot választja.      | Pinterest                                                             |
| .pinterest.com              | Helyi tároló            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Szolgáltató dolgozók          |                                                              |  Pinterest                                                            |


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>A webhely felhasználói cookie-hozzájárulásának egy e-commerce webhelyen 

Ha az e-commerce webhely szolgáltatása vagy modulja nem lényeges süteményt használ, a webhely felhasználója által megadott hozzájárulást meg kell szerezni a sütemény nyomon követése előtt. Ahhoz, hogy engedélyezze a webhely felhasználói számára, hogy egy sütemény-hozzájárulást adjanak meg az e-commerce webhelyen, a webhely szerzőjének hozzá kell adnia és be kell állítania egy cookie-hozzájárulási modult a lap fejlécmodulában, hogy a program kér és fogadott legyen. A webhely felhasználói hozzájárulását meg kell adni, mielőtt a nem alapvető cookie-t használó funkció vagy modul a webhely oldalán meg lenne jelenítve.

## <a name="additional-resources"></a>További erőforrások

[Kisegítő funkciók és lehetőségek](accessibility.md)

[Megfelelőség áttekintése](compliance-overview.md)

[Adatvédelmi irányelv oldalának hozzáadása](add-privacy-page.md)

[Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése](replace-IDs-tracked-changes.md)

[Cookie-hozzájárulás modul](cookie-consent-module.md) 
 
[Fejlécmodul](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
