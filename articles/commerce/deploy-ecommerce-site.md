---
title: Új e-kereskedelmi bérlő telepítése
description: Ez a témakör azt mutatja be, hogyan lehet új e-kereskedelmi bérlőt telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.
author: psimolin
manager: annbe
ms.date: 10/31/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2632632b9b21dd3a88e9a4df0e65cfd28e579d2
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697451"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Új e-kereskedelmi bérlő telepítése

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet új e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.

## <a name="overview"></a>Áttekintés
    
A Microsoft Dynamics Lifecycle Services (LCS) egy felhőalapú együttműködési munkaterület, amelyet a partnerek és a vevők a projektjeik és a környezetek kezelésére, a Microsoft Dynamics termékekkel és szolgáltatásokkal kapcsolatos információk megtekintésére, valamint a terméktámogatási események létrehozására, nyomon követésére és böngészésére tudnak használni. Az e-kereskedelem kezelési szolgáltatásai integrálva vannak az LCS-be.

További tájékoztatás az LCS-ről: [Lifecycle Services felhasználói útmutató](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Első lépések

Az e-kereskedelem inicializálásához inicializálnia kell egy projektet, egy környezetet és egy Retail Cloud Scale Unit (RCSU) egységet. Az LCS-ben történő inicializáláshoz a Projekttulajdonos vagy a Környezetkezelő szerepkör engedélyeivel kell rendelkeznie. Támogatottak az éles és a tesztkörnyezeti topológiák.

A környezetekkel kapcsolatos további tudnivalókat lásd: [Környezet tervezése](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). További tájékoztatás az RCSU-val kapcsolatban: [Retail Cloud Scale Unit inicializálása](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Az elektronikus kereskedelem inicializálása

Ezzel az eljárással lehet inicializálni egy létező környezet e-kereskedelmi funkcióját.

A kezdés előtt győződjön meg arról, hogy rendelkezik a következő szükséges információkkal:

- Az használandó RCSU.
- Az e-kereskedelmi rendszeradminisztrátorok esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.
- Az értékelések és vélemények moderátorai esetében használni kívánt Microsoft Azure Active Directory biztonsági csoport.
- A környezethez társítani kívánt tartományok.

Ezenkívül a következő opcionális információkat gyűjtheti:

- Azure AD cég és ügyfél (B2C) közötti információk:

    - Bérlő neve.
    - Ügyfélazonosító.
    - Bejelentkezéshez tartozó egyéni tartomány.
    - Válasz URL.
    - Regisztrációra és bejelentkezésre vonatkozó irányelv azonosítója.
    - Jelszó visszaállítására vonatkozó irányelv azonosítója.
    - Profilszerkesztési irányelv azonosítója.

[!NOTE]
Ez az információ később is hozzáadható szolgáltatási kérelem alapján.

Miután összegyűjtötte a szükséges adatokat, hajtsa végre az alábbi lépéseket az e-kereskedelem inicializálásához.

1. Bejelentkezés az [LCS](https://lcs.dynamics.com) alkalmazásba.
1. Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.
1. A **Környezetek** szakaszban válassza ki a környezetet.
1. A **Környezet funkciói**területen válassza ki a **Kiskereskedelem kezelése** hivatkozást.
1. Az **e-kereskedelem** lapon válassza a **Beállítás** elemet. Megjelenik egy párbeszédpanel, amelyen meg kell adnia a létesítéshez szükséges adatokat.
1. Töltse ki a szükséges adatokat, majd lépjen a következő lapra.
1. A következő lapon töltse ki a szükséges adatokat, majd küldje el az űrlapot. A rendszer visszaküldi az **e-kereskedelem** lapra, amelyen látnia kell, hogy elindult az inicializálás.
1. Az inicializálás állapotának megtekintéséhez válassza a **Frissítés** lehetőséget, vagy térjen vissza később az **e-kereskedelem** lapra.
    
Az e-kereskedelem LCS-ből történő inicializálásakor a rendszer számos olyan összetevőt létesít, amelyek szükségesek az e-kereskedelemhez, és társítja őket a környezethez. A létesítés befejezése után az **e-kereskedelem** lap a **Kiskereskedelem kezelése** oldalon frissítésre kerül, hogy tükrözze a létesítést. A lap megjeleníti a legújabb testreszabási telepítéseket és az egyéb folyamatban lévő telepítések állapotát. Az e-kereskedelmi webhelyhez és az e-kereskedelmi webhelykezelő eszközhöz (szerkesztési eszköz) is tartalmaz hivatkozásokat.

## <a name="access-the-authoring-environment"></a>Hozzáférés a szerkesztési környezethez

A fejlesztői környezet eléréséhez nyissa meg az **e-kereskedelem** lapot a **Kiskereskedelem kezelése** oldalon. Itt talál az e-kereskedelmi webhelyre és a webhelykezelő eszközre mutató hivatkozásokat.

## <a name="additional-resources"></a>További erőforrások

[Online áruház áttekintése](online-store-overview.md)

[E-commerce webhely létrehozása](create-ecommerce-site.md)

[Online webhely társítása csatornával](associate-site-online-store.md)

[A tartománynév konfigurálása](configure-your-domain-name.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)
