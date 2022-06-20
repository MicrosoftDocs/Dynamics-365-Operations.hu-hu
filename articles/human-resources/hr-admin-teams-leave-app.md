---
title: Human Resources alkalmazás a Teamsben
description: Ez a cikk bemutatja a Microsoft alkalmazást a következőben Dynamics 365 Human Resources :Microsoft Teams
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a7ff576efbfeb0c5383a48756fdd7e79f1abdba2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902256"
---
# <a name="human-resources-app-in-teams"></a>Human Resources alkalmazás a Teamsben


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Microsoft Dynamics 365 Human Resources alkalmazás segítségével az Microsoft Teams alkalmazottak gyorsan időt kérhetnek, és megtekinthetik az időkorlegük adatait a következőben:Microsoft Teams Az alkalmazottak egy robottal léphetnek kapcsolatba információ kéréséhez. A **Szabadság** lapon részletesebb információk olvashatók. Ezenkívül a közelgő szabadságaikról információkat küldhetnek az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.

![Human Resources Teams szabadságkezelő alkalmazás robotja.](./media/hr-teams-leave-app-bot.png)

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lapja.](./media/hr-teams-leave-app-timeoff-tab.png)

![A Human Resources szabadságkérelem kártyája.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Telepítés és beállítás

A Dynamics 365 Human Resources alkalmazás a Teams áruházban található. A Teams alkalmazás telepítésével kapcsolatos tudnivalókat lásd: [Szabadságkérelmek kezelése a Teams rendszerben](hr-teams-leave-app.md).

A Teams alkalmazásengedélyeinek kezelésével kapcsolatos információkért lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams rendszerben](/MicrosoftTeams/teams-app-permission-policies).

Ha azt szeretné, hogy a felhasználók a Távollét és szabadság naptárát az alkalmazásban tekintsék meg, engedélyeznie kell a **Szabadság és távollét naptárja a Teamsben** funkciót a Funkciókezelésben. A funkciók aktiválásával kapcsolatos további részletekért tekintse meg a [Szolgáltatások kezelése](hr-admin-manage-features.md) oldalt.

## <a name="update-app"></a>Alkalmazás frissítése
>[!NOTE]
> 2021. december 20-án kezdődően elindul a Microsoft bérlőben tárolt Emberi erőforrások alkalmazás szolgáltatás. A telepítésre elérhető, naprakész bővítményekre (verziókra és verziókra1.1.5) lesz hatással. A fő hatással lesz az elavult kiterjesztésre (1.1.4). A verzióban elérhető csevegési program leáll. Az **Idő-idő** lap mindkét kiterjesztésben továbbra is működni fog.

Az 1.1.4-es verziónál a beszélgetési program leállítja a válaszadást bármilyen üzenetre. Például bejelentkezés, **·** **egyenlegek megtekintése** és **idő-idő megtekintése**. Az alkalmazást manuálisan kell frissíteni a legújabb verzióra. A további tudnivalókat lásd [Az alkalmazások frissítése itt:Microsoft Teams](/MicrosoftTeams/apps-update-experience)

A következő lépések szerint frissít az 1.1.5-ös verzióra:
1. Az Microsoft Teams Alkalmazások 2003 alkalmazásba **ugrás**
2. Az Emberi erőforrások **alkalmazás** megkeresve.
3. Válassza a **Frissítés lehetőséget**.

Az Emberi erőforrások **alkalmazás** **verzióját úgy ellenőrizheti, hogy vagy a Személyes lapra, vagy a Személyes alkalmazás szakaszra** megy. 

![Emberi erőforrások **A** lap.](./media/HR-teams-about.png)

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
| Az egyenleg adatait a mai naptól számítja ki a program. | A rendszer jelenleg nem mutatja az egyenlegeket a könyvelési időszaknak megfelelően, még akkor sem, **ha be van állítva a Szabadság és távollét paraméterei oldalon**. |

## <a name="troubleshooting"></a>Hibaelhárítás

Ha egy felhasználónak sikerül bejelentkeznie a Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat. Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz. További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>A Teams Emberi erőforrások alkalmazás naprakészen tartásának biztosítása
Ha problémákat észlelt a Teams Emberi erőforrások alkalmazással, meg kell erősítenie, hogy a legújabb verziót futtatja. A minimális támogatott verzió az 1.1.5. A Teams-alkalmazások frissítésével kapcsolatos tudnivalókat lásd a Teams [dokumentációjában](/MicrosoftTeams/apps-update-experience).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.

Ha egy felhasználó azzal keresi meg Önt, hogy nem tud bejelentkezni az alkalmazásba, akkor ellenőrizze, hogy a felhasználóhoz tartozik-e társított alkalmazotti rekord a HR-ben.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.

Ha egy felhasználó hibaüzenetet kap, miközben szabadságkéréseket próbál jóváhagyni a Teams alkalmazásban, próbálja meg a következő hibaelhárítási lépéseket:

1. Ellenőrizze, hogy a Teams-fiókjuk megegyezik-e azzal a fiókkal, amelyet a HR eléréséhez használnak.

2. Ellenőrizze, hogy ők-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével. A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Hagyja a jóváhagyókat, ha nem kapnak Teams-üzeneteket a szabadságkérések jóváhagyásához

1. Győződjön meg róla, hogy az értesítések engedélyezve vannak a környezet és a felhasználó számára. További információért lásd: [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams), és a [Ki-és bekapcsolhatja az egyes felhasználók értesítéseit](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Győződjön meg róla, hogy a felhasználók ugyanolyan hitelesítő adatokkal vannak bejelentkezve a **Csevegések** fülön, mint a szabadságkérések jóváhagyásához. A „kijelentkezés” és a „bejelentkezés” üzenetekkel jelentkezzen be a megfelelő hitelesítő adatokkal.

3. Ha a probléma továbbra is fennáll, ellenőrizze az **Üzleti** események rendszer kötegelt feladatának állapotát rendszergazdaként. Ha Várakozás **vagy** **Végrehajtás** szakaszban van, ellenőrizze újra pár perc múlva. Ha az állapot változatlan marad, akkor jelentkezzen be egy támogatási jegyre, hogy a mi csapatunk segíthet kijavítani a problémát.

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

A felhasználói Dynamics 365 Human Resources szövegbevitel Microsoft Teams elemzése után a program elemzi a bejövő szövegeket, hogy megértsük a mögöttes lekérdezést/célját. A felhasználó által megadott adatok például a "Search account Contoso" a Microsoft language Understanding Intelligens szolgáltatás (LANGUAGE Understanding Intelligens szolgáltatás) nevű szolgáltatásának, a Language Understanding Intelligens szolgáltatásnak (STB) az egyikéhez vannak irányítva. A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet. A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla). Ezt követően a rendszer áttér az adatra a Microsoft [Azure felhasználói](https://azure.microsoft.com/services/bot-service/) keretrendszerére, amely az adatokkal kommunikál a felhasználói lekérdezésből, Dynamics 365 Human Resources és beolvassa a kívánt adatokat.

A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez. A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest. Habár az ORI Dynamics 365 Human Resources szolgáltatás csak a felhasználói lekérdezésekhez van hozzáférése, és nincs a felhasználó adataihoz vagy fiókjához való csatlakozásra tervezve, az Dynamics 365 Human Resources adatbázis egy felhasználója tudott egy vevői adatokat, személyes adatokat vagy más adatokat tartalmazó lekérdezést, és ezeket a lekérdezési tartalmat el lehet küldeni aKISZOLGÁLÓ szolgáltatásnak és az Azure-keretrendszernek. 

A felhasználó lekérdezései és üzenetei legfeljebb 30 napig megmaradnak a SSL rendszerben, más titkosítással vannak titkosítva, és nem használható képzésre és szolgáltatásfejlesztésre. A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet. 

Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid és Azure Cosmos DB

Az alkalmazás Dynamics 365 Human Resources használata esetén Microsoft Teams bizonyos vevőadatok azon a földrajzi területen kívülre is kiterjedhetnek, ahová a bérlő emberi erőforrások szolgáltatását telepítik.

Dynamics 365 Human Resources az alkalmazott távolléti kérelmét és a munkafolyamat-feladat részleteit továbbítja az Microsoft Azure eseményrács és Microsoft Teams a. Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak. Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Lásd még 

[A Microsoft Teams letöltése és telepítése](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams súgóközpont](https://support.office.com/teams)</br>
[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
