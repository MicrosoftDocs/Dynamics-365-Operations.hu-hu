---
title: Human Resources alkalmazás a Teams rendszerben
description: Ez a témakör bemutatja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Teams rendszerben.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ffd6967431227b578e227ee570dbe06c356fb8d6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067051"
---
# <a name="human-resources-app-in-teams"></a>Human Resources alkalmazás a Teams rendszerben


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources alkalmazás be Microsoft Teams az alkalmazottak gyorsan kérjenek szabadságot, és tekintsék meg a távolléti idejükre vonatkozó információkat a -ban Microsoft Teams. Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez. A **Szabadság** lapon részletesebb információk olvashatók. Ezenkívül a közelgő szabadságaikról információkat küldhetnek az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.

![Human Resources Teams szabadságkezelő alkalmazás robotja.](./media/hr-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lapja.](./media/hr-teams-leave-app-timeoff-tab.png)

![A Human Resources szabadságkérelem kártyája.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Telepítés és beállítás

A Dynamics 365 Human Resources alkalmazás a Teams áruházban található. A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).

A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](/MicrosoftTeams/teams-app-permission-policies).

Ha azt szeretné, hogy a felhasználók a Távollét és szabadság naptárát az alkalmazásban tekintsék meg, engedélyeznie kell a **Szabadság és távollét naptárja a Teamsben** funkciót a Funkciókezelésben. A funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.

## <a name="update-app"></a>Frissítse az alkalmazást
>[!NOTE]
> 2021. december 20-tól a Microsoft-bérlőben tárolt Human Resources App botszolgáltatások megszűnnek. Ez nincs hatással a telepíthető naprakész bővítményre (1.1.5 verzió). A fő hatás az elavult bővítményre lesz hatással (1.1.4 verzió). A chat bot ebben a verzióban leáll. A **Szabadidő** lap továbbra is működni fog mindkét bővítményben.

Az 1.1.4-es verzió esetén a csevegőbot nem válaszol semmilyen üzenetre. Például, **Belépés**, **megtekintése**, és **Lásd a szabadságot**. Az alkalmazást manuálisan kell frissíteni a legújabb verzióra. További információkért lásd [Frissítse az alkalmazásokat Microsoft Teams](/MicrosoftTeams/apps-update-experience).

Az 1.1.5-ös verzióra való frissítéshez hajtsa végre az alábbi lépéseket:
1. Ban ben Microsoft Teams, menj **Alkalmazások elemre**.
2. Találd meg **Emberi Erőforrások** kb.
3. Válassza ki **Frissítés**.

Az Emberi Erőforrások alkalmazás verzióját a következő oldalon ellenőrizheti **Ról ről** lapon vagy a **Személyes alkalmazás** szakasz. 

![Emberi Erőforrások **Névjegy** lap.](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Értesítések engedélyezése a Human Resources alkalmazáshoz a Teamsben

Ha azt szeretné, hogy a felhasználók távolléti értesítéseket a Teams alkalmazásban, engedélyeznie kell az értesítéseket a Dynamics 365 Human Resources alkalmazásban.

>[!NOTE]
>Csak azok a felhasználók kapják meg az értesítéseket, akik bejelentkeztek a Teams szolgáltatásba és a Dynamics 365 Human Resources Teams alkalmazást használják.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza a **Hivatkozások** lehetőséget.

3. A **Beállítás** területen válassza ki a **Rendszer paraméterek** lehetőséget.

4. Az **Általános** lapon állítsa be az **Értesítések engedélyezése a Teams alkalmazáshoz** elemet **Igen** értékre.

   ![A Teams alkalmazás értesítések engedélyezése a Rendszer paraméterei között.](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Ha minden felhasználó számára be kívánja kapcsolni a Teams értesítéseit, válassza az **Igen** lehetőséget a kérdésnél.

   ![Értesítések engedélyezése a Teams alkalmazáshoz minden felhasználónak.](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>A Teams értesítéseinek be-és kikapcsolása egyéni felhasználókhoz

Miután engedélyezte az értesítéseket a Dynamics 365 Human Resources Teams alkalmazáshoz, ki-és bekapcsolhatja az egyes felhasználók értesítéseit.

1. A Human Resources alkalmazásban válassza a **Rendszerfelügyelet** elemet.

2. Válassza a **Hivatkozások** lehetőséget.

3. A **Felhasználók** területen válassza ki a **Felhasználói beállítások** lehetőséget.

4. Válassza ki a **Munkafolyamat** lapot.

5. Állítsa az **Értesítések engedélyezése a Teams alkalmazáshoz** beállítást **Igen** értékre, hogy engedélyezze az értesítéseket a felhasználó számára. és **Nem** értékre az értesítések letiltásához a felhasználó számára.

   ![A Teams alkalmazásértesítések engedélyezése a felhasználói beállítások Munkafolyamat lapján.](./media/hr-admin-teams-leave-app-notifications.png)

6. Válassza a **Mentés** lehetőséget.

## <a name="supported-languages"></a>Támogatott nyelvek

A Dynamics 365 Human Resources alkalmazásban a Teamsben az alábbi nyelvek támogatottak:

| Területibeállítás-azonosító | Nyelv |
| --- | --- |
| de-DE | Német (Németország) |
| es-ES | Spanyol (Spanyolország) |
| es-MX | Spanyol (Mexikó) |
| fr-CA | Francia (Kanada) |
| fr-FR | Francia (Franciaország) |
| it-IT | Olasz (Olaszország) |
| nl-NL | Holland (Hollandia) |
| pt-BR | Portugál (Brazília) |
| tr-TR | Török (Törökország) |
| zh-CN | Kínai (egyszerűsített) |

## <a name="notes"></a>Jegyzetek

A következő munkaelemek a későbbi verziókban jelennek meg:

| Munkatétel | Állapot |
| --- | --- |
| Az egyenleg nem helyes, amikor jövőbeli dátumra vonatkozó szabadságot küld be. | Az előrejelzés még nem érhető el. A megjelenített egyenleg az aktuális dátumra vonatkozik. |
| Nem lehet visszavonni egy **Ellenőrzés alatt** állapotú kérelmet. | Ez a funkció jelenleg nem támogatott, és egy későbbi verzióban kerül hozzáadásra. |
| Az egyenleg adatait a mai naptól számítja ki a program. | A rendszer jelenleg nem jeleníti meg a felhalmozási időszak egyenlegeit, még akkor sem, ha az a **A szabadság és távollét paraméterei** oldalon. |

## <a name="troubleshooting"></a>Hibaelhárítás

Ha egy felhasználónak sikerül bejelentkeznie a Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat. Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz. További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>Győződjön meg arról, hogy a Teams Human Resources alkalmazás naprakész
Ha problémákat tapasztal a Teams Human Resources alkalmazással kapcsolatban, meg kell erősítenie, hogy a legújabb verziót használja. A minimálisan támogatott verzió az 1.1.5. A Teams-alkalmazások frissítésére vonatkozó utasításokért lásd: [Csapatok dokumentációja](/MicrosoftTeams/apps-update-experience).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.

Ha egy felhasználó azzal keresi meg Önt, hogy nem tud bejelentkezni az alkalmazásba, akkor ellenőrizze, hogy a felhasználóhoz tartozik-e társított alkalmazotti rekord a HR-ben.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.

Ha egy felhasználó hibaüzenetet kap, miközben a Teams alkalmazásban hagyja jóvá a kilépési kérelmeket, próbálkozzon a következő hibaelhárítási lépésekkel:

1. Ellenőrizze, hogy a Teams-fiókjuk megegyezik-e azzal a fiókkal, amelyet a HR eléréséhez használnak.

2. Ellenőrizze, hogy ők-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével. A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Hagyja a jóváhagyókat, ha nem kapnak Teams-üzeneteket a szabadságkérések jóváhagyásához

1. Győződjön meg róla, hogy az értesítések engedélyezve vannak a környezet és a felhasználó számára. További információért lásd: [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams), és a [Ki-és bekapcsolhatja az egyes felhasználók értesítéseit](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Győződjön meg róla, hogy a felhasználók ugyanolyan hitelesítő adatokkal vannak bejelentkezve a **Csevegések** fülön, mint a szabadságkérések jóváhagyásához. A „kijelentkezés” és a „bejelentkezés” üzenetekkel jelentkezzen be a megfelelő hitelesítő adatokkal.

3. Ha a probléma továbbra is fennáll, ellenőrizze az állapotát **Üzleti események rendszer** kötegelt munka rendszergazdaként. Ha az a **Várakozás** vagy **Végrehajtó** szakaszban, ellenőrizze újra néhány perc múlva. Ha az állapot nem változik, naplózzon egy támogatási jegyet, hogy csapatunk segítsen a probléma megoldásában.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

A ... val Dynamics 365 Human Resources bot be Microsoft Teams, a felhasználó szövegbevitelét elemzi a mögöttes lekérdezés/szándék megértése érdekében. A felhasználó által bevitt bevitel, például a „Search account Contoso”, a Microsoft Language Understanding Intelligent Service (LUIS) nevű kognitív szolgáltatásába kerül. A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet. A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla). Ezt az információt ezután továbbítják a Microsoftnak [Azure bot keretrendszer](https://azure.microsoft.com/services/bot-service/), amely kölcsönhatásba lép a származó adatokkal Dynamics 365 Human Resources és lekéri a kívánt információt a felhasználói lekérdezéshez.

A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez. A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest. Míg a LUIS szolgáltatás csak a felhasználói lekérdezésekhez fér hozzá, és nem úgy van kialakítva, hogy csatlakozzon a felhasználó lekérdezéséhez Dynamics 365 Human Resources adatok vagy fiók, a felhasználó a Dynamics 365 Human Resources A bot önkéntesen megadhat egy lekérdezést, amely ügyféladatokat, személyes adatokat vagy egyéb adatokat tartalmaz, és az ilyen lekérdezés tartalma elküldésre kerülhet a LUIS szolgáltatásnak és az Azure bot-keretrendszernek. 

A felhasználói lekérdezések és üzenetek tartalmát a LUIS rendszerben legfeljebb 30 napig őrzik meg, nyugalmi állapotban titkosítják, képzésre vagy szolgáltatásfejlesztésre nem használják fel. A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet. 

Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid és Azure Cosmos DB

Amikor a Dynamics 365 Human Resources alkalmazás be Microsoft Teams, bizonyos ügyféladatok azon a földrajzi régión kívül is áramolhatnak, ahol a bérlő humánerőforrás-szolgáltatása telepítve van.

Dynamics 365 Human Resources részére továbbítja a munkavállaló szabadságigénylését és a munkafolyamat-feladat részleteit Microsoft Azure Event Grid és Microsoft Teams. Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak. Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Lásd még 

[A Microsoft Teams letöltése és telepítése](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams súgóközpont](https://support.office.com/teams)</br>
[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
