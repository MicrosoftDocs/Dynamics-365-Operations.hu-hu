---
title: Beszerzési rendelés jóváhagyása mobil munkaterület
description: Ez a cikk a beszerzési rendelés jóváhagyásának mobil munkaterületével kapcsolatban tartalmaz tájékoztatást, amelynek segítségével megtekintheti a beszerzési rendeléseket, és műveleteken keresztül válaszolhat rájuk. Például jóváhagyhat vagy elutasíthat egy beszerzési rendelést.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b5336549937edca6beb94137896f84b460f257f7
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111330"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Beszerzési rendelés jóváhagyása mobil munkaterület

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ez a cikk a beszerzési rendelés jóváhagyásának **mobileszköz-munkaterületével kapcsolatban** tartalmaz tájékoztatást. A munkaterület segítségével megtekintheti a beszerzési rendeléseket, és műveleteken keresztül reagálhat is rájuk. Például jóváhagyhat vagy elutasíthat egy beszerzési rendelést.
 
## <a name="overview"></a>Áttekintés 
A jóváhagyást igénylő beszerzési rendelések egy jóváhagyási munkafolyamaton esnek át. A munkafolyamat tartalmazhat olyan lépéseket, amelyek egy vagy több ember által végrehajtandó műveleteket igényelnek. Például egy személynek végre kell hajtania egy feladatot, vagy jóvá kell hagynia a beszerzési rendelést. 

A **Beszerzési rendelés jóváhagyása** mobil munkaterület lehetővé teszi, hogy könnyen megtekinthesse a beszerzési rendeléseket a mobileszközéről, és reagálhasson rájuk. A munkaterület lehetővé teszi ugyanazon munkafolyamati műveletek végrehajtását is, amelyeket a webes ügyfelében használhat.

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérőek lehetnek attól függően, hogy a szervezete a Supply Chain Management melyik verzióját használja.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Előfeltételek a Supply Chain Management használatakor 
Amennyiben szervezete telepítette a Supply Chain Management rendszert, a rendszergazdának közzé kell tennie a **Beszerzési rendelés jóváhagyása** mobil munkaterület. Utasításokért lásd: [Mobil munkaterület közzététele](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Előfeltételek a Microsoft Dynamics 365 for Operations 1611-es verzió és Platform update 3 vagy újabb használatakor
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Operations 1611-es verziójánnak 3. vagy újabb Platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket. 

<table>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Szerep</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Telepítse a KB 4017918 programot.</td>
<td>Rendszergazda</td>
<td>A 4017918-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Beszerzési rendelés jóváhagyása</strong> mobil munkaterületet. A KB 4017918 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza telepíthető csomagot</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Tegye közzé a <strong>Beszerzési rendelés jóváhagyása</strong> mobil munkaterületet.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése
Töltse le és telepítse a Pénzügy és műveletek mobilalkalmazást:

- [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
- [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1. Indítsa el az alkalmazást a mobileszközén.
2. Adja meg a Microsoft Dynamics 365 URL-címét.
3. Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4. A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

![Beszerzési rendelés jóváhagyási munkaterülete a rendelkezésre álló munkaterületek listáján.](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Önhöz rendelt megrendelések megtekintése
1. A mobileszközön válassza a **Beszerzési rendelés jóváhagyása** munkaterületet.
2. Válassza a **Hozzám rendelt rendelések** lehetőséget, hogy megtekinthesse azokaz a beszerzési rendeléseket, amelyek esetében a beszerzési rendelés jóváhagyási munkafolyamatában lépéseket kell tennie.
3. Válasszon ki egy rendelést. A **Rendelés részletei** lapon láthatja a rendelés fejlécének adatait és sorait. A munkafolyamat feladataival kapcsolatban is talál útmutatást.
4. Válassza ki a **Könyvelési felosztások** lehetőséget a **Fejléc – könyvelési felosztások** lap megnyitásához.
5. Térjen vissza a **Rendelés részletei** lapra, majd válasszon ki egy sort. A rendeléssor adataiból megtekintheti a sorspecifikus könyvelési felosztásokat is.

## <a name="complete-an-action-on-the-purchase-order"></a>Hajtson végre egy műveletet a beszerzési rendelésen
Miután megtekintette az Önhöz rendelt beszerzési rendelést, és elolvasta a munkafolyamat-útmutatásokat, készen kell állnia a művelet végrehajtására.

1. A mobileszközön válassza a **Beszerzési rendelés jóváhagyása** munkaterületet.
2. Válassza a **Hozzám rendelt rendelések** lehetőséget, hogy megtekinthesse azokaz a beszerzési rendeléseket, amelyek esetében a beszerzési rendelés jóváhagyási munkafolyamatában lépéseket kell tennie.
3. Jelöljön ki egy rendelést, és tekintse meg a részletek lapot.
4. Válassza a **Műveletek** lehetőséget a rendelkezésre álló műveletek megjelenítéséhez. Az elérhető műveletek az Önhöz rendelt feladattól függnek.

    | Feladat művelet    | Jóváhagyási művelet  |
    |----------------|------------------|
    | Kész       | Jóváhagyás          |
    | Visszatérés         | Elutasítás           |
    | Változtatás kérése | Változtatás kérése   |
    | Delegált       | Delegált         |

5. Jelölje ki a megfelelő műveletet.
6. A **Feladat elvégzése** oldalon írjon be egy megjegyzést. Vegye figyelembe, hogy ha bejelöli a **Delegált** műveletet, ki kell választania egy felhasználót, akinek delegálja a feladatot.
7. Válassza a **Kész** lehetőséget. A munkaterület frissítése után a beszerzési rendelés nem lesz többé a listában. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

