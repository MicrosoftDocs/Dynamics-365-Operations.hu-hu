---
title: "Mobilalkalmazás kezdőoldala"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Unified Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 663a03dc37cc1631bd285a76ef564993a34ed057
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017


---

# <a name="mobile-app-home-page"></a>Mobilalkalmazás kezdőoldala

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a Microsoft Dynamics 365 for Unified Operations mobilalkalmazást, és olyan forrásokra mutató linkeket tartalmaz, amelyek segíthetnek annak szervezeténél történő implementálásában.

> [!NOTE]
> A mobilalkalmazás neve korábban *Microsoft Dynamics 365 for Finance and Operations* volt.

<a name="overview"></a>Áttekintés
--------

A mobilalkalmazás lehetővé teszi a szervezet számára, hogy üzleti folyamatait mobileszközökön is elérhetővé tegye. Miután a rendszergazda lehetővé teszi a mobil munkaterületeket a szervezetnél, a felhasználók bejelentkezhetnek az alkalmazásba, és azonnal elkezdhetik az üzleti folyamatok mobileszközökről történő futtatását. A mobilalkalmazás a következő olyan funkciókat tartalmazza, amelyek segíthetnek a hatékonyság növelésében:

- A felhasználók megtekinthetik vagy szerkeszthetik az üzleti adatokat, és reagálhatnak rájuk még akkor is, ha időszakos hálózati kapcsolatuk van, vagy mobileszközeik teljesen offline állapotban vannak. Amikor egy eszköz helyreállítja a hálózati kapcsolatot, az offline adatműveletek automatikusan szinkronizálódnak a Dynamics 365 for Finance and Operations, Enterprise kiadás, vagy a Microsoft Dynamics 365 for Finance and Operations programmal.
- A rendszergazdák vagy fejlesztők képesek olyan mobil munkaterületek létrehozására és közzétételére, amelyeket testre szabtak a szervezetük igényeinek megfelelően. Az alkalmazás a meglévő kódolási lehetőségeket használja. Ezért nem kell ismét implementálnia a validálási eljárásokat, az üzleti logikát vagy a biztonsági konfigurációt.
- A rendszergazdák vagy fejlesztők könnyen megtervezhetik a mobil munkaterületeket a webes klienshez mellékelt „point-and-click” típusú munkaterület-tervező segítségével.
- A rendszergazdák vagy fejlesztők opcionálisan optimalizálhatják a munkaterületek offline funkcióit is az Üzleti logika bővítési keretrendszer használatával. Mivel az adatok feldolgozása az eszköz offline állapotában is folytatódik, mobilos forgatókönyvei továbbra is gazdagok és naprakészek maradnak még akkor is, ha az eszközök nem rendelkeznek állandó hálózati kapcsolattal.

## <a name="elements-of-the-mobile-app"></a>A mobilalkalmazás elemei
A mobilalkalmazásban történő navigáció négy egyszerű részből áll: ezek az irányítópult, a munkaterület, az oldalak és a műveletek. 

[![A mobilalkalmazás navigációs fogalmai](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Az alkalmazás indításakor az **irányítópultra** kerül.
2. Az irányítópulton látható a közzétett **Munkaterületek** listája.
3. Minden munkaterületnél látható az adott munkaterület rendelkezésre álló **lapjainak** listája.
4. Az oldalakra lépve több művelet végezhető el. Íme néhány példa:

    - Részletes adatok megtekintése.
    - Navigálás a kapcsolódó adatokat, például az entitások részleteit vagy a sorokat tartalmazó lapokra.
    - Lásd az adott oldalon rendelkezésre álló **műveletek** listáját. A műveletek segítségével adatokat hozhat létre, vagy módosíthatja a meglévő adatokat.

## <a name="implementation-process"></a>Megvalósítási folyamat
A következő ábra a Microsoft által biztosított, valamint az egyéni mobil munkaterületek implementálásának folyamatát mutatja. 

![Mobilalkalmazások megvalósítási folyamata](./media/Mobile-implementation-process-5.png)

Az alábbi táblázat azokra az erőforrásokra mutató hivatkozásokat tartalmaz, amelyek segítenek a Microsoft által biztosított, valamint az egyéni mobil munkaterületek implementálásában. Az első oszlopban szereplő számok az előzőekben bemutatott számozott lépéseknek felelnek meg.

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
<td>A Finance and Operations vagy a Finance and Operations végrehajtása a szervezeten belül.</td>
<td><ul><li>Ha még nem telepítette a Microsoft Dynamics 365 valamely verzióját, lásd: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.</li><li>A használható mobil munkaterületek listájának megtekintéséhez lásd <a href="mobile-workspaces-released.md">Nemrég kiadott mobil munkaterületek</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Rendszergazda</td>
<td><strong>A Microsoft Dynamics 365 for Finance and Operation 1611-es verziójának használatakor:</strong> Töltse le és telepítse azokat a tudásbáziscikkeket, amelyek lehetővé teszik a Microsoft által biztosított mobil munkaterületeket.</td>
<td>További információ a következő témakörökben olvasható:
<ul>

<li><a href="/dynamics365/unified-operations/financials/cost-accounting/cost-controlling-mobile-workspace">Költségkontroll mobil munkaterületek</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Aktuális készlet mobil munkaterület</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Értékesítési rendelések mobil munkaterületek</a></li>
<li><a href="/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Szállítói együttműködési mobil munkaterület</a></li>
<li><a href="/dynamics365/unified-operations/financials/project-management/project-time-entry-mobile-workspace">Projektidő megadása mobil munkaterület</a></li>
<li><a href="/dynamics365/unified-operations/financials/expense-management/expense-management-mobile-workspace">Költségkezelés mobil munkaterület</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Rendszergazda</td>
<td>Tegye közzé a Microsoft által biztosított egyéni mobil munkaterületeket.</td>
<td><a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Fejlesztő vagy független szoftverszállító (ISV)</td>
<td>Használja a mobil keretrendszert egyéni mobil munkaterületek létrehozására.</td>
<td><ul>
<li><a href="mobile-platform.md">Mobil keretrendszer</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">Munkaterület X++ API-k</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Hozzon létre egy telepíthető csomagot, amely egyéni mobil munkaterületeket tartalmaz, és töltse fel a csomagot a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásra.</td>
<td><a href="../deployment/create-apply-deployable-package.md">Telepíthető csomag létrehozása</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Rendszergazda</td>
<td>Alkalmazza a telepíthető csomagot, amely tartalmazza a független szoftverszállító (ISV) által biztosított egyéni munkaterületeket.</td>
<td><a href="../deployment/apply-deployable-package-system.md">Telepíthető csomag alkalmazása</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Rendszergazda</td>
<td>Tegye közzé az ISV által biztosított egyéni mobil munkaterületeket.</td>
<td><a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Felhasználó</td>
<td>Töltse le és telepítse a mobilalkalmazást.</td>
<td><ul>
<li><a href="https://go.microsoft.com/fwlink/?linkid=850662">Android-telefonok esetében:</a></li>
<li><a href="https://go.microsoft.com/fwlink/?linkid=850663">iPhone esetében:</a></li></ul>
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Felhasználó</td>
<td>Jelentkezzen be, és használja a mobilalkalmazást. Az alkalmazás tartalmazza a rendszergazda által közzétett mobil munkaterületeket.</td>
<td>A Microsoft által biztosított mobil munkaterületek listájának megtekintéséhez lásd <a href="mobile-workspaces-released.md">Nemrég kiadott mobil munkaterületek</a>.
</td>
</tr>
</tbody>
</table>

