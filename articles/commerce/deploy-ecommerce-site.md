---
title: Új e-kereskedelmi bérlő telepítése
description: Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b4b54e10cb4bd897b4c0706a13eeaf32f8892a05f7a09f3b27dbdd3dcdad1606
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750714"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Új e-kereskedelmi bérlő telepítése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet új Dynamics 365 Commerce e-kereskedelmi webhelyet telepíteni a Microsoft Dynamics Lifecycle Services (LCS) segítségével.

A Microsoft Dynamics Lifecycle Services (LCS) egy felhőalapú együttműködési munkaterület, amelyet a partnerek és a vevők a projektjeik és a környezetek kezelésére, a Microsoft Dynamics termékekkel és szolgáltatásokkal kapcsolatos információk megtekintésére, valamint a terméktámogatási események létrehozására, nyomon követésére és böngészésére tudnak használni. Az e-kereskedelmi kezelési szolgáltatásai integrálva vannak az LCS-be.

További tájékoztatás az LCS-ről: [Lifecycle Services felhasználói útmutató](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Első lépések

Az e-kereskedelmi inicializálásához inicializálnia kell egy projektet, egy környezetet és egy Retail Cloud Scale Unit (RCSU) egységet. Az LCS-ben történő inicializáláshoz a Projekttulajdonos vagy a Környezetkezelő szerepkör engedélyeivel kell rendelkeznie. Támogatottak az éles és a tesztkörnyezeti topológiák.

A környezetekkel kapcsolatos további tudnivalókat lásd: [Környezet tervezése](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). További tájékoztatás az RCSU-val kapcsolatban: [Retail Cloud Scale Unit inicializálása](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Az e-kereskedelem inicializálása

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

> [!NOTE]
> Ez az információ később is hozzáadható szolgáltatási kérelem alapján.

Miután összegyűjtötte a szükséges adatokat, hajtsa végre az alábbi lépéseket az e-kereskedelem inicializálásához.

1. Bejelentkezés az [LCS](https://lcs.dynamics.com) alkalmazásba.
1. Nyissa meg azt a projektet, amely tartalmazza a projektet, ahol az e-kereskedelmet inicializálni kívánja.
1. A **Környezetek** szakaszban válassza ki a környezetet.
1. A **Környezet funkciói** területen válassza ki a **Kiskereskedelem kezelése** hivatkozást.
1. Az **e-kereskedelem** lapon válassza a **Beállítás** elemet. Megjelenik egy párbeszédpanel, amelyen meg kell adnia a létesítéshez szükséges adatokat.
1. Töltse ki a szükséges adatokat, majd lépjen a következő lapra.
1. A következő lapon töltse ki a szükséges adatokat, majd küldje el az űrlapot. A rendszer visszaküldi az **e-kereskedelem** lapra, amelyen látnia kell, hogy elindult az inicializálás.
1. Az inicializálás állapotának megtekintéséhez válassza a **Frissítés** lehetőséget, vagy térjen vissza később az **e-kereskedelem** lapra.
    
Az e-kereskedelem LCS-ből történő inicializálásakor a rendszer számos olyan összetevőt létesít, amelyek szükségesek az e-kereskedelemhez, és társítja őket a környezethez. A létesítés befejezése után az **e-Commerce** lap a **Kiskereskedelem kezelése** oldalon frissítésre kerül, hogy tükrözze a létesítést. A lap megjeleníti a legújabb testreszabási telepítéseket és az egyéb folyamatban lévő telepítések állapotát. Az e-kereskedelmi webhelyhez és az e-kereskedelmi webhelyszerkesztési eszközhöz is tartalmaz hivatkozásokat, amelyben a webhelyek készülnek.

## <a name="access-commerce-site-builder"></a>Commerce webhelykészítő elérése

A Commerce webhelykészítő eléréséhez nyissa meg az **E-kereskedelem** lapot a **Kiskereskedelem kezelése** oldalon az LCS-ben, és válassza ki az **e-kereskedelmi webhely felügyeleti eszköze** hivatkozását. A webhelykészítő nyitóoldala bérlő szintű nézetet jelenít meg. Erről az oldalról a következőket teheti:

- Bérlő szintű beállítások módosítása.
- Navigáljon bármelyik létrehozott webhelyhez, és kérjen engedélyt a megtekintésre. 
- A hozzáférés-ellenőrzés olyan funkciókat tartalmaz, mint a moderálás és a jelentés.
- Új webhely létrehozása. További információ a webhelyek létrehozásáról: [E-kereskedelmi webhely létrehozása](create-ecommerce-site.md). 

## <a name="additional-resources"></a>További erőforrások

[Tartománynév konfigurálása](configure-your-domain-name.md)

[E-kereskedelmi webhely létrehozása](create-ecommerce-site.md)

[Dynamics 365 Commerce webhely társítása online csatornával](associate-site-online-store.md)

[robots.txt fájlok kezelése](manage-robots-txt-files.md)

[URL-átirányítások tömeges feltöltése](upload-bulk-redirects.md)

[B2C-bérlő beállítása a Commerce-ben](set-up-B2C-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni lapok beállítása](custom-pages-user-logins.md)

[Több B2C-bérlő konfigurálása egy Commerce környezetben](configure-multi-B2C-tenants.md)

[Tartalomkézbesítési hálózat (CDN) támogatásának hozzáadása](add-cdn-support.md)

[Helyalapú áruházészlelés engedélyezése](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]