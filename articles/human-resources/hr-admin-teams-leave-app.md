---
title: Human Resources alkalmazás a Teams rendszerben
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776308"
---
# <a name="human-resources-app-in-teams"></a>Human Resources alkalmazás a Teams rendszerben

[!include [banner](includes/preview-feature.md)]

A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy az alkalmazottak gyorsan kérelmezzenek szabadságot, és megtekintsék a szabadságegyenlegükett közvetlenül a Microsoft Teams rendszerben. Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez. A **Szabadság** lapon részletesebb információk olvashatók.

![Human Resources Teams szabadságkezelő alkalmazás robot](./media/hr-admin-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a>Telepítés és beállítás

A Human Resources app a Teams áruházban található. A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).

A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Értesítések engedélyezése a Human Resources alkalmazáshoz a Teamsben

Ha azt szeretné, hogy a felhasználók távolléti értesítéseket a Teams alkalmazásban, engedélyeznie kell az értesítéseket a Human Resources alkalmazásban.

>[!NOTE]
>Csak azok a felhasználók kapják meg az értesítéseket, akik bejelentkeztek a Teams szolgáltatásba és a Human Resources Teams alkalmazást használják.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza a **Hivatkozások** lehetőséget.

3. A **Beállítás** területen válassza ki a **Rendszer paraméterek** lehetőséget.

4. Az **Általános** lapon állítsa be az **Értesítések engedélyezése a Teams alkalmazáshoz** elemet **Igen** értékre.

   ![A Teams alkalmazás értesítések engedélyezése a Rendszer paraméterei között](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Ha minden felhasználó számára be kívánja kapcsolni a Teams értesítéseit, válassza az **Igen** lehetőséget a kérdésnél.

   ![Értesítések engedélyezése a Teams alkalmazáshoz minden felhasználónak](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>A Teams értesítéseinek be-és kikapcsolása egyéni felhasználókhoz

Miután engedélyezte az értesítéseket a Human Resources Teams alkalmazáshoz, ki-és bekapcsolhatja az egyes felhasználók értesítéseit.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza a **Hivatkozások** lehetőséget.

3. A **Felhasználók** területen válassza ki a **Felhasználói beállítások** lehetőséget.

4. Válassza ki a **Munkafolyamat** lapot.

5. Állítsa az **Értesítések engedélyezése a Teams alkalmazáshoz** beállítást **Igen** értékre, hogy engedélyezze az értesítéseket a felhasználó számára. és **Nem** értékre az értesítések letiltásához a felhasználó számára.

   ![A Teams alkalmazásértesítések engedélyezése a felhasználói beállítások Munkafolyamat lapján](./media/hr-admin-teams-leave-app-notifications.png)

6. Válassza a **Mentés** lehetőséget.

## <a name="known-issues"></a>Ismert problémák

| Kiadás | Állapot |
| --- | --- |
| A vízszintes görgetés nem használható Android-telefonokon | A vízszintes görgetés nem jelent problémát iOS- vagy asztali eszközön. Dolgozunk a javításon az Android rendszerhez. |
| Hiba: Probléma adódott a kapcsolódásra szolgáló környezet keresésekor. | Ez a hibaüzenet akkor is megjelenhet, ha ellenőrizte, hogy a felhasználó hozzáférhet-e egy vagy több Human Resources környezethez. Emellett előfordulhat, hogy a várt környezetek nem mindegyike látható. A probléma megoldásáig törölje a felhasználót, majd importálja újra, hogy elkerülje a problémát. |
| Az egyenleg nem helyes, amikor jövőbeli dátumra vonatkozó szabadságot küld be. | Az előrejelzés még nem érhető el. A megjelenített egyenleg az aktuális dátumra vonatkozik. |
| Nem lehet visszavonni egy **Ellenőrzés alatt** állapotú kérelmet. | Ez a funkció jelenleg nem támogatott, és egy későbbi verzióban kerül hozzáadásra. |
| Az egyenleg adatait a mai naptól számítja ki a program. | A rendszer jelenleg nem jeleníti meg a könyvelési időszak egyenlegeit, még akkor sem, ha be van állítva a Szabadság és távollét paraméterei között. |

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez. A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva. A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet. A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla). Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez. 

A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez. A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest. Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek. 

A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során. A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet. 

Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a>Microsoft Azure Esemény rácsa és a Microsoft Teams

Amikor a Teamsben a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették. Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba. Ezeket az adatokat az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez.

## <a name="see-also"></a>Lásd még 

[A Microsoft Teams letöltése és telepítése](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams súgóközpont](https://support.office.com/teams)</br>
[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md)

