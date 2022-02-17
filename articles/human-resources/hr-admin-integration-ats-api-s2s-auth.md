---
title: Kiszolgálók közötti hitelesítés az ATS integrációs API-hoz
description: Ez a témakör azt ismerteti, hogyan lehet beállítani a kiszolgálók közötti hitelesítést a Dynamics 365 Human Resources pályázókövetési rendszerének (ATS) integrációs API-jával végzett integrációkhoz.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d221e1a47dca85880fd683177ca95dd1b7766fb9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064922"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Kiszolgálók közötti hitelesítés az ATS integrációs API-hoz


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani a kiszolgálók közötti hitelesítést a Dynamics 365 Human Resources pályázókövetési rendszerének (ATS) integrációs API-jával végzett alkalmazásintegrációkhoz. A Microsoft Dataverse virtuális táblájához és a kapcsolódó adatokhoz való hozzáféréshez több biztonsági réteget kell kezelni a szolgáltatás rendszerbiztonsági tagjánál. A felhasználónak hozzáférést kell adni a Dataverse virtuális táblához a Microsoft Power Platform rendszerében, és hozzáférést kell adni az adatokhoz a Dynamics 365 Human Resources rendszerében.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>A Dataverse virtuális táblákhoz való hozzáférés engedélyezése a Power Platform rendszerében

Az első lépés a Dataverse virtuális táblákhoz való hozzáférés Power Platform rendszerében való engedélyezése során az alkalmazás beállítása a Power Platformon a Dataverse virtuális táblák végpontjaival való hitelesítésre. Ennek lépéseit a [Microsoft Dataverse fejlesztői útmutató](/powerapps/developer/data-platform) részletezi.

  - Egybérlős alkalmazásregisztrációk esetén: [Egybérlős kiszolgálók közötti hitelesítés használata](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Több-bérlős alkalmazásregisztrációk esetén: [Több-bérlős kiszolgálók közötti hitelesítés használata](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Biztonsági szerepkör létrehozása az ATS-integrációkhoz

Az alkalmazásfelhasználó létrehozása után az egyik lépés az, hogy a felhasználót egy olyan biztonsági szerepkörhöz rendeli, amely meghatározza, hogy az alkalmazás milyen hozzáféréssel rendelkezik a végpontokhoz. Ez a 7. lépés az [Alkalmazásfelhasználók létrehozása](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) egybérlős alkalmazásregisztrációkhoz folyamatnak, valamint a [Biztonsági szerepkör létrehozása az alkalmazásfelhasználó számára](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) több-bérlős regisztrációkhoz folyamatban. 

Annak a szerepkörnek, amelyhez az alkalmazásfelhasználót hozzárendeli, hozzá kell férnie az ATS-integrációhoz használt adatentitásokhoz. Ez alapértelmezés szerint nem létezik, ezért új biztonsági szerepkört kell létrehozni. Az új szerepkört a [Biztonsági szerepkör létrehozása](/power-platform/admin/create-edit-security-role#create-a-security-role) című cikk lépéseit követve lehet létrehozni.

Az új szerepkörhöz legalább a következő entitásokhoz kell megfelelő hozzáférést biztosítani az új szerepkör **Egyéni entitások** lapján. Ne feledje, hogy további entitások hozzáadására is szükség lehet, ha az integráció több alkalmazásadatot használ. Az új szerepkör a létrehozása után hozzárendelhető az alkalmazásfelhasználóhoz.

  - Alap dolgozó (mshr)
  - Felveendő jelentkező (mshr)
  - Tanúsítványkompetencia (mshr)
  - Tanúsítvány típusa (mshr)
  - Cég
  - Kompenzáció – beosztás funkciója (mshr)
  - Kompenzáció – beosztás típusa (mshr)
  - Ország/régiók (mshr)
  - Részleg (mshr)
  - Végzettségkompetencia (mshr)
  - Végzettség (mshr)
  - Tantárgyak (mshr)
  - Végzettségi követelmények (mshr)
  - Azonosító (mshr)
  - Azonosítótípus (mshr)
  - Intézmény (mshr)
  - Kibocsátó hatóság (mshr)
  - Beosztás kompenzációja (mshr)
  - Beosztások (mshr)
  - Végzettség szintje (mshr)
  - Fél kapcsolattartói (mshr)
  - Személyek (mshr)
  - Személy címei (mshr)
  - Személy szűrése (mshr)
  - Beosztás típusa (mshr)
  - Beosztások V2 (mshr)
  - Szakmai tapasztalat kompetencia (mshr)
  - Minősítési szint (mshr)
  - Minősítési modellek (mshr)
  - Okkódok (mshr)
  - Toborzási kérelem (mshr)
  - Toborzási kérelem – hely (mshr)
  - Toborzási kérelem – beosztás (mshr)
  - Toborzási kérelem – szakértelem (mshr)
  - Szűréstípus (mshr)
  - Szakértelem-kompetencia (mshr)
  - Szakértelem (mshr)
  - Címek (mshr)
  - Veteránállapot (mshr)
  - Dolgozó (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Alkalmazásengedélyek megadása az emberi erőforrások adataihoz

A második lépés annak biztosítása, hogy az alkalmazás megfelelő engedélyeket kap az emberi erőforrások adataihoz. Ehhez össze kell kapcsolni a Human Resources alkalmazással. Az alkalmazásfelhasználók esetén a Dataverse virtuális táblákon keresztüli, kiszolgálók közötti hívások a Dataverse rendszerében műveletet indító felhasználó (alkalmazás) identitásának kontextusában zajlanak. A virtuális táblák adapterszolgáltatása ezután kikeresi a társított felhasználót a Human Resources rendszeréből, és a felhasználó kontextusán belül lefuttatja a lekérdezést. Ez azt jelenti, hogy a felhasználót a megfelelő szerepkörökkel kell létrehozni a Human Resources rendszerében, hogy hozzáférést biztosítson az integráló alkalmazás számára szükséges adatokhoz.

A Human Resources felhasználójához is az emberi erőforrások adataira vonatkozó megfelelő engedélyeket kell hozzárendelni. A **Toborzási alkalmazás** (HcmRecruitingIntegrator) szerepkör jogosultságokkal rendelkezik a toborzási adatok integrálásához szükséges elsődleges entitásokhoz. Ez a szerepkör a **Felhasználók** lapon rendelhető hozzá az alkalmazásfelhasználóhoz, és megadja a megfelelő hozzáférést az adatokhoz. A Human Resources biztonsági szerepköreivel kapcsolatos további tudnivalókat lásd a [Szerepköralapú biztonság](/fin-ops-core/dev-itpro/sysadmin/role-based-security) című cikkben.

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Az új felhasználó beállítása a megfelelő jogosultságokkal

Az új felhasználó megfelelő jogosultságokkal történő beállításához kövesse ezeket a lépéseket:

  1. Nyissa meg a **Felhasználók** lapot a Human Resources rendszerében, és válassza az **Új** lehetőséget.
  2. Adja meg az új alkalmazásfelhasználó  **Felhasználói azonosítóját** és **Felhasználónevét**. Beírhatja például a „RecruitingIntegration” értéket.

      > [!NOTE]
      > Ha az alkalmazásnak nincs Microsoft Azure Active Directory (Azure AD) felhasználói fiókja vagy e-mail-címe, akkor a felhasználó E-mail-cím és Szolgáltató mezőjébe például a „RecruitingApp” értéket írhatja.

  3. A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök hozzárendelése** műveletet.
  4. A **Szerepkörök hozzárendelése a felhasználóhoz** panelen válassza a **Toborzási alkalmazás** lehetőséget, majd kattintson az **OK** gombra.
  5. Mentse az új felhasználói rekordot.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Kapcsolja össze a Human Resources új felhasználóját az alkalmazással

A felhasználó létrehozása után létre kell hoznia egy rekordot az alkalmazáshoz az **Azure Active Directory alkalmazások** űrlapon az alkalmazás és a Human Resources-felhasználó összekapcsolásához.

  1. Nyissa meg **Azure Active Directory alkalmazások** űrlapot, és válassza az **Új** lehetőséget.
  2. Az **Ügyfélazonosító** mezőben adja meg az alkalmazáshoz létrehozott alkalmazásfelhasználó ügyfélazonosítóját.
  3. A **Név** mezőben adja meg az integrációs alkalmazás nevét.
  4. A **Felhasználói azonosító** mezőben válassza ki a toborzási integrációhoz létrehozott új Human Resources-felhasználót.
  5. Mentse az új rekordot.

Az alkalmazás ezután hozzá fog férni a Human Resources adataihoz, ám a hozzáférése csak a toborzáshoz szükséges adatokra korlátozódik.

## <a name="see-also"></a>Lásd még

[Jelöltek toborzása](hr-personnel-recruit.md)<br>
[Mi az a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[A Microsoft Dataverse webes API használata](/powerapps/developer/data-platform/webapi/overview)<br>
[Beállításkészletek létrehozása és frissítése a webes API segítségével](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
