---
title: "Dynamics 365 for Operations mobilalkalmazás kezdőlapja"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e1a9e0eeb45f011ccb2aa091e68aff92782e1ae7
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Dynamics 365 for Operations mobilalkalmazás kezdőlapja

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja a Microsoft Dynamics 365 for Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában.

<a name="overview"></a>Áttekintés
--------

A Microsoft Dynamics 365 for Operations mobilalkalmazás lehetővé teszi a szervezet számára, hogy üzleti folyamatait mobileszközökön is elérhetővé tegye. Miután a rendszergazda lehetővé teszi a mobil munkaterületek funkcióját a szervezetnél, a felhasználók bejelentkezhetnek az alkalmazásba, és azonnal elkezdhetik az üzleti folyamatok mobileszközökről történő futtatását. A Dynamics 365 for Operations mobilalkalmazás a következő olyan funkciókat tartalmazza, amelyek segíthetnek a hatékonyság növelésében:

-   A felhasználók megtekinthetik vagy szerkeszthetik az üzleti adatokat, és reagálhatnak rájuk még akkor is, ha időszakos hálózati kapcsolatuk van, vagy mobileszközeik teljesen offline állapotban vannak. Ha egy eszköz újra hálózati kapcsolatot létesít, az offline adatműveletek automatikusan szinkronizálódnak a Dynamics 365 for Operations programmal.
-   A rendszergazdák vagy fejlesztők képesek olyan mobil munkaterületek létrehozására és közzétételére, amelyeket testre szabtak a szervezetük igényeinek megfelelően. Az alkalmazás a meglévő kódolási lehetőségeket használja. Ezért nem kell ismét implementálnia a validálási eljárásokat, az üzleti logikát vagy a biztonsági konfigurációt.
-   A rendszergazdák vagy fejlesztők könnyen megtervezhetik a mobil munkaterületeket a Dynamics 365 for Operations webes klienshez mellékelt „point-and-click” típusú munkaterület-tervező segítségével.
-   A rendszergazdák vagy fejlesztők opcionálisan optimalizálhatják a munkaterületek offline funkcióit is az Üzleti logika bővítési keretrendszer használatával. Mivel az adatok feldolgozása az eszköz offline állapotában is folytatódik, mobilos forgatókönyvei továbbra is gazdagok és naprakészek maradnak még akkor is, ha az eszközök nem rendelkeznek állandó hálózati kapcsolattal.

## <a name="elements-of-the-mobile-app"></a>A mobilalkalmazás elemei
A mobilalkalmazásban történő navigáció négy egyszerű részből áll: ezek az irányítópult, a munkaterület, az oldalak és a műveletek. 

[![A mobilalkalmazás navigációs fogalmai](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   Az alkalmazás indításakor az **irányítópultra** kerül.
-   Az irányítópulton megtekintheti azon **munkaterületek** listáját, amelyeket közzétettek a Dynamics 365 for Operations környezetben.
-   Minden munkaterületnél látható az adott munkaterület rendelkezésre álló **lapjainak** listája.
-   Egy-egy lapon megtekintheti a Dynamics 365 for Operations szolgáltatásban egy vagy több oldalról összegyűjtött adatokat.
-   A lapokról a kapcsolódó adatokat, például az entitások részleteit vagy a sorokat tartalmazó lapokhoz navigálhat.
-   A lapokon megtekintheti azoknak a **műveleteknek** a listáját, amelyek az adott lap esetében elérhetők.
-   A műveletek segítségével adatokat hozhat létre, vagy módosíthatja a meglévő adatokat.

## <a name="implementation-process"></a>Megvalósítási folyamat
Az alábbi ábra bemutatja a Dynamics 365 for Operations mobilalkalmazás implementálásának folyamatát a szervezeténél. 

[![](./media/mobile-implementation-process_4.png)](./media/mobile-implementation-process_4.png) 

A következő táblázat olyan forrásokra mutató linkeket is tartalmaz, amelyek segíthetnek a Dynamics 365 for Operations mobilalkalmazás szervezeténél történő implementálásában. Az első oszlopban szereplő számok az előzőekben bemutatott számozott lépéseknek felelnek meg.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Lépés</th>
<th>Szerep</th>
<th>Művelet</th>
<th>Források, melyek segítenek a művelet végrehajtásában</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Rendszergazda</td>
<td>A Dynamics 365 for Operations implementálása a szervezetnél.</td>
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, lásd a következő tudnivalókat: <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Rendszergazda</td>
<td>Töltse le és telepítse azokat a tudásbáziscikkeket, amelyek lehetővé teszik a Microsoft által biztosított mobil munkaterületeket.</td>
<td>Lásd az &quot;Előfeltételek&quot; szakaszt arról a mobil munkaterületről, amelyet szervezete használni szeretne:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Költségkontroll mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Aktuális készlet mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Értékesítési rendelések mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Szállítói együttműködési mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Projektidő megadása mobil munkaterület</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Rendszergazda</td>
<td>Tegye közzé a Microsoft által biztosított egyéni mobil munkaterületeket.</td>
<td>Lásd az &quot;Előfeltételek&quot; szakaszt arról a mobil munkaterületről, amelyet szervezete használni szeretne:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Költségkontroll mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Aktuális készlet mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Értékesítési rendelések mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Szállítói együttműködési mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Projektidő megadása mobil munkaterület</a></li>
</ul></td>
</tr>
<tr class="even">
<td>4</td>
<td>Fejlesztő vagy független szoftverszállító (ISV)</td>
<td>Használja a Dynamics 365 for Operations mobil keretrendszert egyéni mobil munkaterületek létrehozására.</td>
<td><ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 for Operations mobil keretrendszer</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">Dynamics 365 for Operations munkaterület X++ API</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Hozzon létre egy telepíthető csomagot, amely egyéni mobil munkaterületeket tartalmaz, és töltse fel a csomagot a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásra.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Telepíthető csomag generálása</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Rendszergazda</td>
<td>Alkalmazza a telepíthető csomagot, amely tartalmazza az ISV által biztosított egyéni munkaterületeket.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Alkalmazzon egy telepíthető csomagot és a Dynamics 365 for Operations rendszerre.</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Rendszergazda</td>
<td>Tegye közzé az ISV által biztosított egyéni mobil munkaterületeket.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/publish-mobile-workspace">Mobil munkaterület közzététele</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Felhasználó</td>
<td>Töltse le és telepítse a Dynamics 365 for Operations mobilalkalmazást.</td>
<td><ul>
<li>Android: <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations a Google Play Áruházban</a></li>
<li>iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 az iTunes App Store áruházban</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Felhasználó</td>
<td>Jelentkezzen be, és használja a Dynamics 365 for Operations mobilalkalmazást. Az alkalmazás tartalmazza a közzétett mobil munkaterületeket.</td>
<td>A Microsoft a következő mobil munkaterületeket kínálja:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Költségkontroll mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Aktuális készlet mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Értékesítési rendelések mobil munkaterületek</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Szállítói együttműködési mobil munkaterület</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Projektidő megadása mobil munkaterület</a></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Lásd még
--------

[A Dynamics 365 for Operations mobilalkalmazáshoz nemrégiben kiadott mobil munkaterületek](mobile-workspaces-released.md)





