---
title: Cookie-k megfelelősége
description: Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.
author: BrianShook
ms.date: 05/21/2021
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
ms.openlocfilehash: 8eb610eb819dee09a30368257e36dc88f855e985
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088387"
---
# <a name="cookie-compliance"></a>Cookie-k megfelelősége

[!include [banner](includes/banner.md)]

Ez a témakör a cookie-megfelelőséggel és a Microsoft Dynamics 365 Commerce által tartalmazott alapértelmezett irányelvekkel kapcsolatos szempontokat ismerteti.

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
| \_msdyn365___muid_                            | Akkor használatos, ha a Kísérletezés aktiválva van a környezetben: a kísérletezési célok felhasználóazonosítójához használatos. |
| \_msdyn365___exp_                             | Akkor használatos, ha a Kísérletezés aktiválva van a környezetben: a teljesítmény terheléselosztásának mérésére használatos.         |
| d365mkt                                       | Akkor használatos, ha az üzlet helyjavaslataizoz tartozó felhasználói IP-cím nyomon követésének hely alapú észlelési szolgáltatása engedélyezve van a Commerce webhely-szerkesztőjében, a **Webhelybeállítások > Általános > Helyalapú áruházészlelés engedélyezése** részen.      |

Ha egy webhely felhasználója a webhely bármelyik közösségi média hivatkozását kiválasztja, az alábbi táblában található cookie-k is nyomon lesznek követve a böngészőikben.


| Tartomány                      | Cookie               | Leírás                                                  | Forrás                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | LinkedIn-hirdetések azonosítójának szinkronizálása                                      | LinkedIn-csatorna és betekintés címke                                |
| .linkedin.com               | li_sugr                  | Böngésző azonosítója                                           | LinkedIn betekintés címke, ha az IP-cím nem egy kijelölt országban van |
| .linkedin.com               | BizographicsOptOut       | Meghatározza a harmadik fél követéselutasítási állapotát.              | A LinkedIn vendégvezérlők és az iparág elutasító oldalai           |
| .linkedin.com               | \_guid                    | Böngészőazonosító a Google hirdetésekhez.                            | LinkedIn-csatorna                                                |
| .linkedin.com               | li_oatml                 | Az átalakítások nyomon követésének, újracélzásának és analitikájának a tag közvetett azonosítója. | LinkedIn hirdetések és betekintés címkék                                |
| Különböző belső tartományok | li_fat_id                | Az átalakítások nyomon követésének, újracélzásának és analitikájának a tag közvetett azonosítója. | LinkedIn hirdetések és betekintés címkék                                |
| .adsymptotic.com            | U                        | Böngészőazonosító                                           | LinkedIn betekintés címke, ha az IP-cím nem egy Kijelölt országban van |
| .linkedin.com                | b                  | Böngészőazonosító cookie                                            | Kérések a LinkedInhez                                         |
| .linkedin.com                | bs                 | Biztonságos böngészőcookie                                        | Kérések a LinkedInhez                                         |
| .linkedin.com               | nyelv                     | Beállítja az alapértelmezett területi beállításokat és a nyelvet.                                 | Kérések a LinkedInhez                                         |
| .linkedin.com                | lidc                     | Útvonaltervezlshez használatos.                                             | Kérések a LinkedInhez                                         |
| .linkedin.com               | aam_uuid                 | Adobe-célközönség kezelői cookie                                                     | Beállítás azonosítószinkronizáláshoz                                              |
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


## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Webhely felhasználó cookie-hozzájárulása egy e-kereskedelmi weboldalon 

Ha egy e-kereskedelmi oldal funkciója vagy modulja nem alapvető cookie-t használ, akkor a webhely felhasználójának hozzájárulását a cookie nyomon követése előtt kell beszerezni. Ha engedélyezni szeretné, hogy a webhely felhasználói cookie-hozzájárulást adjanak az e-kereskedelemi webhelyen a webhelyhez tartozó szerzőnek hozzá kell adnia és be kell állítania egy cookie-hozzájárulási modult a lap fejlécmoduljában, hogy a rendszer biztosítsa a jóváhagyás fogadását. A webhely felhasználói hozzájárulását meg kell adni, mielőtt a nem alapvető cookie-t használó funkció vagy modul a webhely oldalán meg lenne jelenítve.

## <a name="additional-resources"></a>További erőforrások

[Kisegítő funkciók és lehetőségek](accessibility.md)

[Megfelelőség áttekintése](compliance-overview.md)

[Adatvédelmi irányelv oldalának hozzáadása](add-privacy-page.md)

[Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése](replace-IDs-tracked-changes.md)

[Cookie-hozzájárulás modul](cookie-consent-module.md) 
 
[Fejlécmodul](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
