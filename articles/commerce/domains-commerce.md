---
title: Tartományok a Dynamics 365 Commerce-alkalmazásban
description: Ez a témakör azt mutatja be, hogyan kezelhetők a tartományok a Microsoft Dynamics 365 Commerce alkalmazásban.
author: BrShoo
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: cb2b003168d32d05387bd45796d313736b11a41f
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517355"
---
# <a name="domains-in-dynamics-365-commerce"></a>Tartományok a Dynamics 365 Commerce-alkalmazásban

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan kezelhetők a tartományok a Microsoft Dynamics 365 Commerce alkalmazásban.

A tartományok a webböngészőkben a Dynamics 365 Commerce webhelyekhez való navigálásra használt webcímek . A tartomány kezelését a kiválasztott tartományi névkiszolgálóval (DNS-szolgáltatóval) vezérelheti. A tartományok a Dynamics 365 Commerce webhely-építők között hivatkoznak hogy koordinálják, hogyan lehet elérni a webhelyet a közzétételkor. Ez a témakör azt mutatja be, hogyan kezeli a rendszer a tartományokat a Commerce oldalfejlesztés és indítás életciklusok alatt.

## <a name="provisioning-and-supported-host-names"></a>Üzembe helyezés és támogatott állomásnevek

Egy e-kereskedelmi rendszernek a [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/) szolgáltatásban történő létesítése során az e-kereskedelmi létesítési képernyőn látható **Támogatott állomásnevek** mezője segítségével megadhatja azokat a tartományokat, amelyek a telepített Commerce környezethez lesznek társítva. Ezek a tartományok az e-kereskedelmi webhelyeket tároló, az ügyfelek számára elérhető tartományi névkiszolgálók (DNS). Ha ebben a szakaszban megad egy tartományt, akkor nem indítja el a tartomány forgalmának átirányítását a Dynamics 365 Commerce alkalmazás felé. A tartomány forgalma csak akkor lesz a Commerce végpontjára irányítva, amikor a DNS-CNAME rekord frissítve lesz, hogy a Commerce végpontját használja a tartományhoz.

> [!NOTE]
> A **Támogatott állomásnevek** mezőbe több tartományt is megadhat a pontosvesszőkel elválasztva.

A következő ábra a LCS e-kereskedelmi létesítési képernyőt mutatja, ahol a **Támogatott állomásnevek** mező ki van emelve. 

![LCS e-kereskedelmi létesítési képernyőn a **Támogatott állomásnevek** mező kijelölve](./media/Domains_ProvisioningeCommerceScreen.png)

Szolgáltatási kérelmeket úgy is létrehozhat, hogy további tartományokat adjon hozzá egy környezethez, ha az üzembe helyezés már megtörtént. Szolgáltatási kérelem létrehozásához az LCS-ben a környezeten belül válassza a **Támogatás \> Támogatási problémák** lehetőséget, majd válassza a **Probléma beküldése** elemet.

## <a name="commerce-generated-urls"></a>Commerce által létrehozott URL-címek

A Dynamics 365 Commerce e-kereskedelmi környezet létesítése során a Commerce egy URL-címet fog generálni, amely a környezet működési címe lesz. Ez az URL-cím a környezet létesítése után, szerepel az e-kereskedelmi oldal hivatkozásában, ami megjelenik az LCS-ben. A Commerce által generált URL-cím formátuma `https://<e-commerce tenant name>.commerce.dynamics.com`, ahol az e-kereskedelmi bérlő neve az LCS-ben a Commerce környezethez megadott név.

A termelési webhely állomásneveit a tesztkörnyezetben is használhatja. Ez a beállítás akkor lehet hasznos, ha a wehelyet egy tesztkörnyezetből termelésbe másolja.

## <a name="site-setup"></a>Hely beállítása

Az e-kereskedelmi környezet létesítése után be kell állítania a webhelyet a Commerce webhelyépítőben, hogy a webhelyet a munka URL-címhez rendelje.

Amikor először állít be webhelyet a webhelykészítőben megjelenik a **Webhely beállítása** párbeszédpanel.

A következő ábra egy „default” nevű helyhez tartozó **Webhely beállítása** párbeszédpanelt jeleníti meg, amikor a webhelyet első alkalommal nyitja meg a webhelykészítőben.

![**Webhely beállítása** párbeszédpanel](./media/Domains_SetupyoursiteScreen.png)

A **Tartomány kiválasztása** mező segítségével hozzárendelheti a webhely által biztosított támogatott állomásnevek egyikét az LCS-ben a weboldalhoz a webhelykészítőben.

Az **Elérési út** mezőt üresen hagyhatja, vagy hozzáadhat egy további elérésiút-sztringet is, amely a munka URL-címben tükröződik. Ha üresen hagyja az **Elérési út** mezőt akkor az alap Commerce által létrehozott URL-cím lesz társítva a webhelytervezőben létrehozott webhelyhez. Au elérési utaknak egyedieknek kell lenniük minden webhely-/tartománypár esetében. A kiválasztott webhelyen és tartományban a környezetnek csak egy webhelye használható az üres elérési úttal, vagy társítható egy egyedi elérésiút-karakterlánchoz. A webhely telepítése során az **Elérési út** mezőhöz hozzáadott bármely karakterlánc a webhely webböngészőben való eléréséhez használt, az alap Commerce által előállított URL-cím egyik alútvonala lesz.

> [!NOTE]
> Ez az elérési út **Egyeztetési útvonal** néven is ismert, amikor csatornát adnak hozzá a **Webhelybeállítások \> Csatornák** konfigurációs részben a webhelykészítőben.

Ha például egy „xyz” nevű e-kereskedelmi bérlőhöz van egy „fabrikam” nevű webhelye a webhelykészítőben és a webhelyet üres útvonallal állítja be, akkor a webböngészőben elérhetővé teszi a közzétett webhely-tartalmat úgy, hogy közvetlenül a Commerce által létrehozott alap URL-címre irányítja a webhelyet:

`https://xyz.commerce.dynamics.com`

Másik esetben, ha a „fabrikam” elérési utat adta hozzá ugyanezen webhely beállítása során, a közzétett webhely tartalmát a következő URL-címen éri el a böngészőben:

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a>Oldalak és URL-címek

Miután a webhely egy elérési úttal be van állítva, a webhelyhez tartozó oldalakhoz társított összes URL-cím a munka URL-címen (a Commerce által előállított URL-címen vagy a Commerce által előállított URL-címen, valamint a webhely elérési útján) épül ki a weboldalhoz. Új URL-cím létrehozása a webhelykészítőben (**URL-ek /> + Új**) egy lap kiválasztásával az **Új URL-cím lista** párbeszédpanelről majd a lap URL-címének megadása az URL-címet és a kijelölt laphoz társítja. Az URL-cím elérési útja ezt követően hozzáfűzi a webhely URL-címét a webhelyhez az oldal eléréséhez és `./<URL path>` címkét kap az **URL-címek** lapon található URL-listában a webhelykészítőben.

A következő ábra az **Új URL-cím** párbeszédpanelét jeleníti meg a webhelykészítőben, ahol ki van emelve egy példa URL-cím. 

![**Új URL-cím** párbeszédpanel a webhelykészítőben](./media/Domains_PageSetup2a.png)

A következő ábra az **URL-címek** oldalt jeleníti meg a webhelykészítőben, ahol ki van emelve egy példa URL-cím a listában.

![Felhasználói folyamatbeállítás futtatása az irányelvben most](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>A webhelykészítő tartományai

A támogatott állomásnevek-értékek tartományhoz társíthatók a webhely beállításakor. A támogatott állomásnév-értékek tartományként történő kiválasztásakor a webhelykészítőben hivatkozott kiválasztott tartományt látja. Ez a tartomány csak egy hivatkozás a Commerce-környezeten belüli, de a tartományhoz kapcsolódó élő forgalmat még nem továbbítja a Dynamics 365 Commerce számára.

Ha webhelyekkel dolgozik a webhelykészítő modulban, és két különböző tartomány van beállítva, akkor a **?domain=** attribútum hozzáfűzhető a munka URL-címhez a közzétett webhely tartalmának böngészővel való eléréséhez.

Például az „xyz” környezet létesítése már megtörtént, és két webhely van létrehozva, és társítva a webhelykészítőben: egy a `www.fabrikam.com` tartománnyal és egy `www.constoso.com` a tartománnyal. Mindkét webhely egy üres útvonallal lett beállítva. Ezt a két helyet ezután egy webböngészőben a következőképpen érhető el **?domain=** attribute:
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

Ha egy tartományilekérdezési karakterlánc nincs megadva olyan környezetben, amelyben több tartomány van, a Commerce a megadott első tartományt használja. Ha például a webhely kiépítése során a „fabrikam” elérési utat adták meg, akkor az URL-cím `https://xyz.commerce.dynamics.com` használható a közzétett `www.fabrikam.com` webhely tartalmának eléréséhez.

## <a name="traffic-forwarding-in-production"></a>Forgalom továbbítása a termelésben

Több tartomány szimulálható a tartományi lekérdezési karakterlánc paraméterei használatával a commerce.dynamics.com végponton is. Ha azonban a élesítés szükséges, akkor az egyéni tartomány forgalmát továbbítania kell a `<e-commerce tenant name>.commerce.dynamics.com` végpontnak.

Az `<e-commerce tenant name>.commerce.dynamics.com` végpont nem támogatja az egyéni tartományi biztonságos csomagrétegeket (SSL), ezért egyéni tartományokat kell beállítania a front door-szolgáltatás vagy content delivery network (CDN) használatával. 

Ha a Front Door-szolgáltatás vagy a CDN használatával egyéni tartományokat szeretne beállítani, akkor két lehetőség közül választhat:

- Egy belépési pont szolgáltatás, mint az Azure Front Door beállítása a kezelőfelületi forgalom kezeléséhez és annak csatlakoztatása a Commerce-környezetéhez. Ez a tartomány-és tanúsítványkezelés és a részletes biztonsági házirendek hatékonyabb kezelését teszi lehetővé.
- A Commerce által biztosított Azure Front Door példány használata. Ehhez együttműködés szükséges a Dynamics 365 Commerce csapattal a tartomány hitelesítéséhez és az SSL-tanúsítványok lekéréséhez a termelési tartományhoz.

A CDN-szolgáltatások közvetlen beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Content Delivery Network (CDN) támogatásának hozzáadása](add-cdn-support.md).

A Commerce által biztosított Azure Front Door-példány használatához létre kell hoznia egy szolgáltatási kérelmet a CDN telepítéséhez a Commerce előkészítő csapatával. 

- Meg kell adnia a vállalat nevét, a termelési tartományt, a környezet azonosítóját és a termelési e-kereskedelmi-bérlő nevét. 
- Meg kell erősítenie, ha ez egy létező (jelenleg aktív helyen használt) tartomány vagy egy új tartomány. 
- Új tartomány esetében a tartományhitelesítés és az SSL-tanúsítvány egyetlen lépésben érhető el. 
- A meglévő webhelyet kiszolgáló tartományhoz egy több lépésből álló folyamat szükséges a tartományhitelesítés és az SSL-tanúsítvány létrehozásához. Ennek a folyamatnak egy 7 munkanapos szolgáltatásiszint-szerződése (SLA) egy tartomány élesítéséhez, mivel több egymást követő lépést is tartalmaz.

Szolgáltatási kérelem létrehozásához az LCS-ben a környezeten belül válassza a **Támogatás \> Támogatási problémák** lehetőséget, majd válassza a **Probléma beküldése** elemet.

> [!NOTE]
> Az SSL-t használó egyéni tartományok csak termelési környezetekben támogatottak. A nem termelési környezetekhez, például a tesztkörnyezetekhez és a felhasználói elfogadás teszteléséhez (UAT) használja a Commerce által készített URL-címet a közzétett tartalom webböngészőben való eléréséhez.

## <a name="ssl-certificate-process"></a>SSL-tanúsítvány folyamata

Szolgáltatási kérelem benyújtása esetén a Commerce-csapat a következő lépéseket fogja egyeztetni Önnel.

Új tartományok esetében:
- A Commerce csapat beállítja az Azure Front Door-példányát (Commerce-üzemeltetésű).
- A Commerce csapat ezt követően megadja a CNAME-rekordot, ami az Ön tartományára mutat.
- A CNAME rekord frissítése után a Commerce által üzemeltetett Azure Front Door példány ellenőrizheti a tartomány tulajdonjogát, és megkaphatja az SSL-tanúsítványt.

Meglévő/aktív tartományok esetében:
- A Commerce csapat arra kéri, hogy vegyen fel egy `afdverify.<custom-domain>` CNAME-rekordot, amely biztosítja a tartomány DNS-szolgáltatóját.
- Ha elkészült, a Commerce csapat hozzáadja a tartományt az Azure Front Door példányához, és további DNS-TXT típusú rekordokat ad hozzá a tartomány DNS-éhez.
- A TXT típusú rekordok befejezése után a Commerce csapat végrehajtja a tartományhoz tartozó, az SSL-tanúsítványt beállító tartományhoz tartozó Azure Front Door frissítéseket.

## <a name="apex-domains"></a>Apex-tartományok

A Commerce rendszerbeli Azure Front Door példány nem támogatja a apex-tartományokat (az altartományokat nem tartalmazó gyökértartományok). A apex-tartományokhoz IP-cím szükséges a feloldáshoz, és a Commerce Azure Front Door példánya csak a virtuális végpontokhoz van hozzárendelve. Az apex tartomány használatához két lehetőség közül választhat:

- **1. lehetőség** – A DNS-szolgáltató segítségével irányíthatja át a apex-tartományt egy „www” tartományba. Például fabrikam.com átirányítása a következőre `www.fabrikam.com`, ahol a `www.fabrikam.com` a CNAME-rekord, amely a Commerce saját Azure Front Door péládnyára mutat.

- **2. lehetőség** – Hozzon létre egy CDN / belépési pont példányt a saját a apex-tartományának hosztolásához.

> [!NOTE]
> Ha Azure Front Doort használ, akkor egy Azure DNS-t is be kell állítania ugyanabban az előfizetésben. Az Azire DNS-ben található APEX-tartomány egy alias-rekordként mutathat az Azure Front Door-ra. Ez az egyetlen áthidaló megoldás, hiszen az apex-tartományoknak mindig egy IP-címre kell mutatniuk.

  ## <a name="additional-resources"></a>További erőforrások

  [Új e-kereskedelmi bérlő telepítése](deploy-ecommerce-site.md)

  [Online áruház csatornájának beállítása](online-stores.md)

  [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

  [Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

  [Robots.txt fájlok kezelése](manage-robots-txt-files.md)

  [URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

  [B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

  [Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

  [Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

  [Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

  [Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)
