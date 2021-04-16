---
title: Integráció a LinkedIn Talent Hub szolgáltatással
description: Ez a témakör bemutatja, hogyan lehet beállítani a Microsoft Dynamics 365 Human Resources és a LinkedIn Talent Hub közötti integrációt.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: efcac2bd82956015eb822c6a493b8625a35cd194
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805058"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integráció a LinkedIn Talent Hub szolgáltatással

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A [LinkedIn Talent hub](https://business.linkedin.com/talent-solutions/talent-hub) egy pályázókövetési rendszer (applicant tracking system, ATS) platform. Ez lehetővé teszi a munkaerő sourcingját, kezelését és alkalmazását egyetlen helyen. A Microsoft Dynamics 365 Human Resources és a LinkedIn Talent hub integrálásával könnyedén létrehozhat alkalmazotti rekordokat a Human Resources alkalmazásban azok számára, akiket felvettek valamilyen beosztásra.

## <a name="setup"></a>Beállítás

A rendszergazdának be kell fejeznie a beállítási feladatokat, hogy engedélyezze a LinkedIn Talent hub integrációját. Először a Power Apps környezetben be kell állítania egy felhasználót és egy biztonsági szerepkört, amely megadja a LinkedIn Talent Hub számára a szükséges engedélyeket az adatok Human Resources alklamazásba történő írására.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>A környezete csatolása a LinkedIn Talent Hub alkalmazáshoz

1. Nyissa meg a [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) alkalmazást.

2. A felhasználói legördülő menüben válassza a **Termék beállításai** lehetőséget.

3. A bal oldali navigációs ablak **Speciális** szakaszában válassza az **Integrációk** elemet.

4. Jelölje be az **Engedélyezés** jelölőnégyzetet a Microsoft Dynamics 365 Human Resources integrációjához.

5. A **Dynamics 365 Human Resources** lapon válassza ki a LinkedIn Talent Hub elemhez kapcsolandó környezetet, majd válassza a **Csatolás** lehetőséget.

    ![LinkedIn Talent Hub előkészítés](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Csak olyan környezetekhez kapcsolódhat, amelyeknél a felhasználói fiók rendszergazdája hozzáférhet mind a Human Resources környezethez, mind a társított Power Apps-környezethez. Ha a Human Resources hivatkozáslapján nem szerepelnek környezetek, győződjön meg arról, hogy a bérlőn engedélyezve legyen a Human Resources környezet, valamint azt, hogy a hivatkozás lapra bejelentkezett felhasználó rendelkezzen rendszergazdai jogosultsággal mind a Human Resources környezethez, mind a Power Apps-környezethez.

### <a name="create-a-power-apps-security-role"></a>Power Apps biztonsági szerepkör létrehozása

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).

2. A **Környezetek** listából válassza ki a LinkedIn Talent Hub példányához csatolni kívánt, a Human Resources környezettel társított környezetet.

3. Válassza a **Beállítások** lehetőséget.

4. Bontsa ki a **Felhasználók + engedélyek** csomópontot, és válassza a **Biztonsági szerepkörök** elemet.

5. A **Biztonsági szerepkörök** lap eszköztárán válassza az **Új szerepkör** elemet.

6. A **Részletek** lapon adja meg a szerepkör nevét, például **LinkedIn Talent Hub HRIS Integráció**.

7. A **Testreszabás** lapon válassza ki a szervezetszintű **Olvasási** engedélyt az alábbi entitásokhoz:

    - Entitás
    - Mező
    - Kapcsolat

8. Mentse el és zárja be a biztonsági szerepkört.

### <a name="create-a-power-apps-application-user"></a>Power Apps-alkalmazásfelhasználó létrehozása

Létre kell hozni egy alkalmazásfelhasználót a LinkedIn Talent Hub adapterhez, aki jogosultságokat biztosít annak, hogy az adapter beírhassa a jelöltrekordokat a Power Apps-környezetbe.

1. Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).

2. A **Környezetek** listából válassza ki a LinkedIn Talent Hub példányához csatolni kívánt, a Human Resources környezettel társított környezetet.

3. Válassza a **Beállítások** lehetőséget.

4. Bontsa ki a **Felhasználók + engedélyek** csomópontot, és válassza a **Felhasználók** elemet.

5. Jelölje ki a **Felhasználók kezelése a Dynamics 365 rendszerben** lehetőséget.

6. A lista fölötti legördülő menü segítségével módosítsa az alapértelmezett **Engedélyezett felhasználók** nézetet erre: **Alkalmazásfelhasználók**.

    ![Alkalmazásfelhasználók nézet](./media/hr-admin-integration-power-apps-application-users.jpg)

7. Válassza ki az eszköztár **Új** gombját.

8. Az **Új felhasználó** oldalon kövesse az alábbi lépéseket:

    1. Módosítsa a **Felhasználótípus** mező értékét erre: **Alkalmazásfelhasználó**.
    2. A **Felhasználónév** mező értékét erre: **Dynamics365 HR LinkedIn HRIS-integráció**.
    3. Állítsa az **Alkalmazásazonosító** mező értékét erre: **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Írjon be bármilyen értéket az **Utónév**, **Családnév** és **Elsődleges e-mail-cím** mezőkbe.
    5. Kattintson az eszköztár **Mentés \& Bezárás** gombjára.

### <a name="assign-a-security-role-to-the-new-user"></a>Biztonsági szerepkör hozzárendelése az új felhasználóhoz

Miután elmentette és bezárta az új alkalmazásfelhasználót az előző szakaszban, a program visszaviszi a **Felhasználólista** lapra.

1. A **Felhasználólista** lapon módosítsa a nézetet erre: **Alkalmazásfelhasználók**.

2. Válassza ki az előző szakaszban létrehozott alkalmazásfelhasználót.

3. Válassza ki az eszköztár **Szerepkörök kezelése** elemét.

4. Válassza ki az integráció céljára korábban létrehozott biztonsági szerepkört.

5. Válassza ki az **OK** lehetőséget.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Adjon hozzá egy Azure Active Directory-alkalmazást a Human Resources alkalmazásban

1. A Dynamics 365 Human Resources alkalmazásban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.
2. Adjon hozzá egy új rekordot a listához és állítsa be a következő mezőket:

    - **Ügyfélazonosító**: adja meg az alábbit: **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Név**: adja meg a korábban létrehozott Power Apps biztonsági szerepkör nevét, például **LinkedIn Talent Hub HRIS Integráció**.
    - **Felhasználói azonosító**: válassza ki azt a felhasználót, akinek van engedélye a Személyzet kezelése szakasz adatainak írására.

### <a name="create-the-table-in-dataverse"></a>Tábla létrehozása a Dataverse szolgáltatásban

> [!IMPORTANT]
> A LinkedIn Talent Hub integrációja a Dataverse Human Resources számára létrehozott virtuális tábláitól függ. A beállítás előfeltétele a virtuális táblák konfigurálása. A virtuális táblák konfigurálásával kapcsolatos tudnivalókért lásd: [Dataverse virtuális táblák konfigurálása](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

1. A HR-modulban nyissa meg a **Dataverse integrációja** oldalt.

2. Válassza ki a **Virtuális táblák** lapot.

3. Az entitáslistájár zűrje az entitások címkéi szerint, hogy megtalálja a **LinkedIn exportált pályázóit**.

4. Válassza ki a jogi személyt, majd kattintson a **Létrehozás/frissítés** lehetőségre.

## <a name="exporting-candidate-records"></a>Jelöltrekordok exportálása

A telepítés befejezése után a toborzók és az emberi erőforrások (HR) szakemberei a LinkedIn Talent hub **Exportálás a HRIS-be** funkcióját használhatják a LinkedIn Talent Hub programból a Human Resources felé átadott jelöltrekordok exportálására.

### <a name="export-records-from-linkedin-talent-hub"></a>Rekordok exportálása a LinkedIn Talent Hub alkalmazásból

Miután a pályázó végigment a toborzási folyamaton, és már felvették, exportálhatja a LinkedIn Talent Hub alkalmazásból a Human Resources rendszerbe a pályázó rekordját.

1. A LinkedIn Talent Hub alkalmazásban nyissa meg azt a projektet, amelyhez az új alkalmazottat felvette.

2. Válasszon ki egy jelöltrekordot.

3. Válassza ki a **Szakasz módosítása** elemet, majd kattintson a **Felvéve** gombra.

4. A pályázó három ponttal (**...**) jelölt menüpontjában válassza az **Exportálás a HRIS-be** lehetőséget.

5. Az **Exportálás a HRIS-be** ablaktáblában adja meg a exportálandó adatokat:

    - A **HRIS-szolgáltató** mezőben válassza a **Microsoft Dynamics 365 Human Resources** elemet.
    - A **Kezdő dátum** mezőben válasszon egy értéket az új alkalmazott számára.
    - A **Beosztás** mezőbe írja be az új alkalmazott feladatköréhez tartozó beosztást.
    - A **Telephely** mezőbe írja be azt a telephelyet, ahol az alkalmazott alapvetően dolgozni fog.
    - Adja meg vagy ellenőrizze az alkalmazott e-mail-címét.

![Exportálás a HRIS-be ablaktábla a LinkedIn Talent hub alkalmazásban](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Előkészítés befejezése a Human Resources alkalmazásban

A LinkedIn Talent Hub alkalmazásból a Human Resources felé exportálandó jelöltrekordok a **Személyzet kezelése** oldal **Foglalkoztatható jelöltek** szakaszában találhatók.

1. A Human Resources alkalmazásban nyissa meg **Személyzet kezelése** lapot.

2. A **Foglalkoztatható jelöltek** szakaszban a kiválasztott pályázó esetén válassza a **Felvétel** lehetőséget.

3. Az **Új dolgozó felvétele** párbeszédpanelen ellenőrizze a rekordot, és adja meg a szükséges adatokat. Kiválaszthatja azt a beosztást is, amelyre a pályázót már felvette.

Miután megtörtént a szükséges információk megadása, folytathatja az alkalmazottak rekordjainak és szokásos folyamatainak létrehozását, illetve az alkalmazottak előkészítését.

A program az alábbi adatokat importálja és viszi fel az új alkalmazotti rekordba:

- Keresztnév
- Vezetéknév
- Foglalkoztatás kezdő dátuma
- E-mail cím
- Telefonszám

## <a name="see-also"></a>Lásd még

[Dataverse virtuális táblák konfigurálása](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Mi az a Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]