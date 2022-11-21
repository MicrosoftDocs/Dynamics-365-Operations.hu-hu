---
title: A virtuális tábla alapú integráció biztonságikonfiguráció-koncepciói
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources és más rendszerek közötti integráció felépítését.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759727"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>A virtuális tábla alapú integráció biztonságikonfiguráció-koncepciói

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a [Microsoft Dataverse virtuális táblák (entitások)](/dev-itpro/power-platform/virtual-entities-overview)Dynamics 365 Human Resources és külső rendszerek közötti integráció felépítését írja le. A cikk a biztonsági konfiguráción, valamint a rendszer határok között szükséges hitelesítési és engedélyezési szempontokon van középpontban, hogy működő, biztonságos rendszert építsen ki.

## <a name="prerequisite-reference-articles"></a>Előfeltételek hivatkozási cikkei

Az alábbi cikkek további tájékoztatást tartalmaznak a cikk koncepcióiról:

- [Virtuális entitások áttekintése](/dev-itpro/power-platform/virtual-entities-overview)
- [A virtuális táblákkal (entitásokkal) való első lépések](/developer/data-platform/virtual-entities/get-started-ve)
- [Több bérlős kiszolgáló-kiszolgáló hitelesítés használata (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [OAuth hitelesítés használata a(Microsoft Dataverse)t (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Az OAuth 2.0 ügyfél hitelesítő adatainak áramlása a Microsoft identitás platformján](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Hitelesítés és engedélyezés](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Felépítés 

A következő diagram diagramja bemutatja azokat a fő fogalmakat, amelyek virtuális táblákat (entitásokat) használó integrációban vesznek részt.

![Virtuális tábla alapú integráció.](./media/Hosts.jpg)

Az előző diagram elemeinek magyarázata:

- **Microsoft** – a Microsoft a vevők nevében a különböző Dynamics 365-termékeket működteti és működteti.

    - **Azure Active Directory(Azure AD) C** bérlő – a Azure AD Microsoft tulajdonában álló bérlő. Ez a bérlő az, akihez a Dynamics 365-alkalmazások regisztrálva vannak.

- **Integrációs partner**

    - **Integrációs rendszer** – a Dynamics 365 rendszerrel integrált rendszer. Ez lehet egy bérszámfejtő rendszer vagy bármely olyan rendszer, amely a Dynamics 365-ben tárolt adatokon alapul.
    - **Adapter** – a Dynamics 365 rendszerrel és az integráló rendszerrel való kommunikációért felelős szoftver vagy szolgáltatás.

        > [!NOTE]
        > Ha egy adaptert több Dynamics 365-ügyfélnek is használnia kell, akkor arra számít, hogy a rendszer többen regisztrálja az adaptert a következőben Azure AD:

    - **Azure AD A** bérlő – az Azure AD integráló partner tulajdonában álló bérlő. Az a bérlő, aki regisztrálva van az adapter alkalmazásazonosítója.

- **Kölcsönös vevő** – az a vevő, Dynamics 365 Human Resources aki megvalósítja és integrálja a partner megoldását.

    - **Dynamics 365 Pénzügy vagy Emberi** erőforrások – a Dynamics 365 Pénzügy és az Emberi erőforrások ügyfélspecifikus példánya, amely az integráló rendszer által megkövetelt vevőadatokat tartalmazza.
    - **Dataverse**– a Pénzügy vagy Dataverse az Emberi erőforrások eszközhöz kapcsolódó vevőspecifikus környezet. Dataverse A <a0/1><a2/1><a2/1><a2/<a3/ a Dynamics 365-adatokkal való
    - **Azure AD B bérlő** – a vevő bérlője Azure AD. Ez az azonosító szolgáltatóként (engedélyezési kiszolgáló) és a hívók számára a vevő példányának hívására feljogosító tokenként működik Dataverse.

## <a name="basic-request-flow"></a>Alapvető kérés folyamatábra

Ez a szakasz az integrációba bevont tipikus kérés alapvető folyamatát írja le. A cikk korábbi diagramára hivatkozik.

Egy jellemző kéréshez szükség van a Dynamics 365 adapter adatlekérdezésére, majd az adatok mentésére és szinkronizálására az integráló rendszerrel.

1. Az adapter a web Dataverse API-t hívja meg a vonatkozó adatok lekérdezésére.

    > [!NOTE]
    > A hitelesítés előfeltétele a hitelesítésnek, és a jogkivonat-beszerzés a folyamat egyik fő feltétele. A hitelesítés leírása a hitelesítés [és engedélyezés a rendszer határok között szakaszában található](#authentication-and-authorization-at-system-boundaries).

    Ez a hívás a web Dataverse API-hoz készül egy virtuális táblán keresztül elérhető alkalmazásadatok lekérdezésére. (Lásd: "2. Kezdeti szinkronizálás" és "3. Delta Sync" a diagramban.)

2. Dataverse A <a0/1><a2/1><a2/1><a2/5><a2/<a2/5><a3/ a virtuális tábla proxyján keresztül a virtuális táblából történő lekérdezéssel kezeli a kérést a diagramban. A Dataverse rendszer továbbítja a kérést a Pénzügyi vagy Emberi erőforrások virtuális entitás szolgáltatásnak, hogy lekérdezést kérjen a Pénzügyi vagy Emberi erőforrások adatbázisában ténylegesen tárolt adatokról.
3. A Pénzügy vagy az Emberi erőforrások virtuális entitás szolgáltatás a virtuális entitásra vonatkozó kérést egy, a Dataverse virtuális entitást kiszolgáló pénzügyi vagy emberi erőforrás entitásra vonatkozó lekérdezéssel fordítja le. A program az adatbázisból olvassa be az adatokat, visszaadja Dataverse őket az entitások megjelenítésének, és visszaadja a hívónak.
4. Az adapter befejezi a szükséges megfeleltetéseket és adatfordításokat, és felhívja az integráló rendszert, hogy az adatok megmaradnak az integráló rendszer adatbázisában. (Lásd: "4. Adatmentás a diagramban.)

## <a name="authentication-and-authorization-at-system-boundaries"></a>Hitelesítés és engedélyezés a rendszerhatárok között

*A* hitelesítés igazolja, hogy a felhasználó vagy a pályázat személyazonossága igazolt, és megerősíti, hogy a felhasználó vagy a pályázat az, akinek ének ják. *Az* engedélyezés hozzáférést biztosít a felhasználónak vagy az alkalmazásnak meghatározott alkalmazásszintű engedélyekhez. A további tudnivalókat lásd [a Hitelesítés és engedélyezés ellenében](/azure/active-directory/develop/authentication-vs-authorization).

A legtöbb rendszerközi hívás a cikk korábbi diagramja szerint az adaptert is magába foglalja. Az adapternek hitelesítve kell lennie ahhoz, hogy a következő hívásokat kezdeményezse:

- A hívás a következőre: Dataverse
- Az integráló rendszer hívása

Nézze meg a diagram rendszerhatárát. A rendszerek közötti összes webes kérést hitelesítettnek kell lennie, és az alkalmazásszintű engedélyezési ellenőrzésen át kellesnie, mielőtt az adatokat visszaadja a hívónak. A Pénzügy vagy az Emberi erőforrások által mögött álló Dynamics 365 virtuális tábla igényléséhez a hitelesítési és engedélyezési ellenőrzéseket a következő rendszerhatárok között kell végrehajtani:

- Az adapter és a webes Dataverse API (OData) végpont közötti hívás
- A virtuális entitás Dataverse és a Pénzügyi vagy Emberi erőforrások virtuális entitás szolgáltatás közötti hívás

Mindkét esetben először a hitelesítési ellenőrzéseket kell végezni. Ezt követően az alkalmazásszintű engedélyezési ellenőrzésekkel biztosítható, hogy a hitelesített felhasználó vagy alkalmazás megfelelő alkalmazásszintű jogosultságokkal rendelkezik a kért adatok beolvasásához.

A hívás hitelesítését Dataverse egy olyan jogkivonaton keresztül intézi a rendszer, amely HTTP-fejlécként kell, hogy legyen a webalkalmazásban Dataverse. Az adapternek jogkivonatot kell kapnia a B bérlő példánytól Azure AD. (Lásd: "1. Token bejedése a diagramban.) Azure AD A <a0/10/<a2/<a2/<a2/<a

Az adapter az alkalmazás azonosítójának (nem titkos, Azure AD mint az A bérlőben regisztráltnak) és egy titkos alkalmazásnak vagy tanúsítványnak a megszava hitelesíti magát.

Miután megtörtént a felhasználó vagy alkalmazás Dataverse hitelesítése a hívásokhoz, Dataverse a szintszintű engedélyezési ellenőrzések mindegyik kérésre leselkednek. Az ilyen ellenőrzések során meg kell győződni arról, hogy a hívónak (az adapteralkalmazás identitásának,\<guid A\> amely a diagramban " van) rendelkezik-e a megfelelő alkalmazásengedélyekkel. Az alkalmazásszintű engedélyezést Dataverse egy olyan alkalmazásfelhasználó kezeli, aki az adapter alkalmazásazonosítóját képviseli. Az alkalmazásszintű engedélyek meghatározott Dataverse alkalmazásszerepek megadásával kezelhetők. Ezek a szerepkörök részletes jogosultságokat biztosítanak az alkalmazáshoz.

A részletesebb útmutatást lásd [a Többbéres kiszolgálók kiszolgálókon keresztüli hitelesítés használata.](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication)

Ha Dataverse a -szint alkalmazásengedélyek ellenőrzései vannak átvéve, akkor a virtuális entitás neve és végpontja a Pénzügyi vagy az Emberi erőforrások környezetben hívja meg a virtuális entitás szolgáltatási végpontját. Ez a hívás kiszolgálóról kiszolgálóra (S2S) hitelesítést használ. A pénzügyi és műveleti virtuális adatforrás konfigurációs rekordjában beállított identitást és titkos azonosítót használja.

![A Pénzügy és műveletek virtuális adatforrás konfigurációs rekordja a beérkezett üzenetek környezetében.](./media/sandbox.jpg)

További tájékoztatás: Virtuális [Dataverse entitások konfigurálása](/dev-itpro/power-platform/admin-reference).

A virtuális entitástól Dataverse a Pénzügy vagy az Emberi erőforrások modulba történt hívás tartalmazza az adapterből Dataverse származó eredeti hívás adapter-azonosítóját (\<guid A\> a diagramban "" megjelölt azonosítót). Ha a virtuális entitás adatforrása megfelelően van konfigurálva, és az S2S hitelesítése be van állítva, akkor a Pénzügy vagy az Emberi erőforrások virtuális entitás szolgáltatása az eredeti hívóval (az adapterrel \<guid A\>) összefüggésben futtatja a lekérdezést. A program ellenőrzi a Pénzügy vagy az Emberi erőforrások szintjén az alkalmazásengedélyeket, hogy az adapter rendelkezik-e a lekérdezéssel kért adatentitások eléréséhez szükséges jogosultságokkal.

A Pénzügy és az Emberi erőforrások biztonsági kezelése a következőképpen lehetséges:

1. Az adapter azonosítójának (\<guid A\>) egy konkrét pénzügyi vagy emberi erőforrás-felhasználóhoz való hozzárendelésével. Ez a hozzárendelés az **Azure Active Directory-alkalmazások lapján történik**. További információ a Külső [pályázat regisztrálása oldalon található](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. A Pénzügyi vagy Emberi erőforrások felhasználó számára a megfelelő alkalmazásszintű szerepkörök, feladatok és jogosultságok megadása. További információ a szerepkör-alapú [biztonsággal kapcsolatban tartalmaz tájékoztatást](/dev-itpro/sysadmin/role-based-security).

Ha az adapteralkalmazás (\<guid A\>) meg van adni a kért adatok eléréséhez szükséges jogosultságokat, a következő események történnek:

1. Lefut a lekérdezés.
2. Az adatok visszaszámításra adatokat hoznak létre az entitáslapjára Dataverse.
3. Az adatok visszakerülnek az adapterhez.

> [!IMPORTANT]
> A fejlesztés során az adapter egy Olyan Pénzügyi vagy Emberi erőforrások felhasználóval futtatható, aki a Rendszergazda szerepkörrel rendelkezik. Éles környezetben azonban az adaptert soha nem szabad Rendszergazdai jogosultságokkal futtatni.

## <a name="key-takeaways"></a>Kulcsátutasások

Íme néhány fontos következményei a virtuális tábla vagy az entitás architektúra számára:

- Az Emberi erőforrások által biztonsági biztonsági beállításokat az Emberi erőforrások biztonsági rendszer kezeli.
- A vevő ("Kölcsönös vevő" a cikk korábbi diagramján) teljes mértékben szabályozhatja, hogy milyen jogosultságokat kap az integráló adapter identitása (\<guid A\> ezt a diagram "" jelöli).
- Az ügyfél felelős az emberi erőforrások környezetének megfelelő biztonsági konfigurációért. Az adaptert teremtő integrációs partnernek útmutatást kell adnia az adapter által megkövetelt jogosultságokkal kapcsolatban.
