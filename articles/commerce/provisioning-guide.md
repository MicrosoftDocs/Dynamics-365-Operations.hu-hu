---
title: Üzenetkészlet Dynamics 365 Commerce környezetének létesítása
description: Ez a cikk bemutatja, hogy hogyan lehet beépített bemutatóadatokkal rendelkezni a Microsoft Dynamics 365 Commerce bemutató- és azbox-használathoz.
author: psimolin
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013134"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Üzenetkészlet Dynamics 365 Commerce környezetének létesítása

[!include [banner](includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet beépített bemutatóadatokkal rendelkezni a Microsoft Dynamics 365 Commerce bemutatók környezetében. A termelési környezet beállításának folyamata hasonló, de részletesebb, mivel abox környezet számos előfeltétele már létezik a bemutató adatai között.

Javasoljuk, hogy mielőtt nekikezdana, olvassa el gyorsan ezt a cikket, és olvassa el, hogy mire van szükség a folyamat során.

A Commercebox környezet sikeres telepítéséhez meg kell adnia néhány paramétert a környezethez és a COMMERCE SCALE Unit (COMMERCE SCALE Unit) számára, amely a Commerce rendszer későbbi építésű telepítéséhez lesz használva. Az ebben a témakörben található útmutatás a létesítés befejezéséhez szükséges összes lépést és a szükséges paramétereket írja le.

Miután sikeresen létesíti a Commerce-környezetet, néhány telepítés utáni lépést végre kell végrehajtania ahhoz, hogy előkészítse használatra. A lépések egy része nem kötelező, a rendszer kívánt szempontjaitól függően. A választható lépéseket a későbbiekben bármikor befejezheti.

A Commerce-környezet beállításának a beállítását követően a [Commerce üzenetkészlet-környezet konfigurálása tudnivalókat tartalmaz](cpe-post-provisioning.md). A Commerce rendszer választható funkcióinak konfigurálásról a Commerce [üzenetdoboz környezet választható funkcióinak konfigurálása oldalon található részletes tájékoztatás](cpe-optional-features.md).

## <a name="prerequisites"></a>Előfeltételek

A Commerce rendszer telepítése előtt a következő előfeltételeknek meg kell jelennie:

- Elérhetővé teszi a Microsoft Dynamics Lifecycle Services (LCS) portál elérését.
- Microsoft Dynamics Ön 365-ös partner vagy ügyfél, és van egy implementáció-projektje, amely már létre van hozva, és az LCS-ben való használatra elérhető.  
- Létrehozott egy Azure Active Directory (Azure AD) biztonsági csoportot, amely felhasználható a Commerce rendszer rendszergazdai csoportjaként, és az azonosítója elérhető.
- Létrehozott egy biztonsági Azure AD csoportot, amely minősítésként és moderátorcsoportként használható, és elérhetővé válik az azonosítója. (Ez a biztonsági csoport ugyanaz lehet, mint a Commerce Rendszer rendszergazdai csoportja.)
- Telepített egy központpéldányt az LCS-n belül. További tájékoztatás: Új [környezet telepítése](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Ne felejtse el, hogy ez a lista nem teljes. Ha bármilyen problémába ütközik forduljon a Microsoft-partnere kapcsolattartójához.

## <a name="provision-your-commerce-environment"></a>Commerce-környezet létesítása

Az alábbi eljárások a Commerce rendszer építését ismertetik. A lépések sikeres befejezése után a Commerce rendszer készen áll a konfigurálásra. Az alábbi lépések mindegyikét az LCS-portálon kell leírni.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>A Commerce Scale Unit (felhő) inicializálása

A CSU-cím inicializálásához kövesse az alábbi lépéseket.

1. Az LCS-listából válassza ki a környezetet.
1. A jobb oldali **KÖRNYEZET nézetben válassza a Teljes** részletek **lehetőséget**. Megjelenik a környezeti részletek nézet.
1. A KÖRNYEZET SZOLGÁLTATÁSOK **területen a Környezet kezelése** szakaszban **válassza** a Kezelés **lehetőséget**.
1. Válassza az **Inicializálás lehetőséget a Commerce** Scale Units **lapon**. **Megjelenik a Skálaegység hozzáadása** nézet.
1. **A RÉGIÓ mezőben** válassza ki azt a régiót, amely megegyezik vagy közel van ahhoz a régióhoz, amelybe telepítette a környezetet.
1. A Verzió **legördülő** listáról válassza ki a rendelkezésre álló legújabb verziót.
1. Válassza az **Inicializálás** elemet.
1. A figyelmeztető párbeszédpanelen, amely rákérdez a Commerce Scale Unit inicializálásának megerősítésére, válassza az **Igen lehetőséget**. A STB. várakozik a létesítésen.
1. Mielőtt tovább kíván haladni, győződjön meg arról, hogy AZ IS állapota **SIKERES**. Az inicializálás körülbelül két-öt órát vesz igénybe.

Ha nem találja a **Kezelés** hivatkozást a környezet részletei nézetben, kérjen segítséget a Microsoft kapcsolattartótól.

### <a name="initialize-e-commerce"></a>Az elektronikus kereskedelem inicializálása

A Commerce inicializálása előtt hajtsa végre a következő lépéseket.

1. Az **e-kereskedelem** lapon válassza a **Beállítás** elemet.
1. Az **E-kereskedelmi környezet neve** mezőben adjon meg egy nevet. Fontos megjegyezni, hogy ez a név az e-kereskedelem példányra mutató néhány URL-címen látható lesz.
1. A **Commerce Scale Unit neve** mezőben válassza ki az CSU-t a listából. (A listában csak egy opciónak kell lennie.)

    Az **e-commerce földrajz** mező automatikusan be van állítva.

1. A folytatáshoz kattintson a **Tovább** gombra.
1. A **Támogatott állomásnevek** mezőbe írjon be egy tetszőleges érvényes tartományt, például `www.fabrikam.com`.
1. Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoportja rendszergazdának** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez. Válassza ki a megfelelő biztonsági csoportot a listából.
1.  Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoport minősítési és értékelési moderátornak** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez. Válassza ki a megfelelő biztonsági csoportot a listából.
1. Hagyja az **Értékelések és vélemények szolgáltatás engedélyezése** beállítást **Igen** értéken.
1. Válassza az **Inicializálás** elemet. Újra megjelenik a **Commerce Management** nézet, amelyen a **e-kereskedelem** lap ki van választva. Az e-kereskedelem inicializálása elindult.
1. A folytatás előtt várja meg, amíg a Commerce inicializálás sikeresen **befejeződött**.
1. A jobb alsó sarokban található **Hivatkozások** részben jegyezze fel a következő hivatkozások URL-címeit:

    * **e-kereskedelmi webhely** -Az e-kereskedelmi webhely gyökerére mutató hivatkozás.
    * **e-kereskedelmi webhelykészítő** - A webhelykezelési eszközre mutató eszköz.

## <a name="next-steps"></a>További lépések

A Commerce-környezet létesítés és konfigurálás folyamatának folytatásáról [a Commerce üzenetbox környezetének konfigurálása](cpe-post-provisioning.md) része.

## <a name="additional-resources"></a>További erőforrások

[Abox Dynamics 365 Commerce környezet konfigurálása](cpe-post-provisioning.md)

[BoPIS konfigurálásabox Dynamics 365 Commerce környezetben](cpe-bopis.md)

[Az üzenetdoboz-környezet választható funkcióinak Dynamics 365 Commerce konfigurálása](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (felhő)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
