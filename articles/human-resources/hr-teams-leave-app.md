---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2a74b895052d017ccbe397bfb9a45609646b2f93
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639438"
---
# <a name="manage-leave-requests-in-teams"></a>Szabadságkérelmek kezelése a Teamsben

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben. A robottal együttműködhet a szükséges adatok lekéréséhez és a szabadságkérelem elindításához. A **Szabadság** lapon részletesebb információk olvashatók. A közelgő szabadságairól is információkat küldhet az embereknek a Teamsben és a Human Resources alkalmazáson kívüli csevegőfelületeken.

## <a name="install-the-app"></a>Az alkalmazás telepítése

A Dynamics 365 Human Resources alkalmazás a Teams áruházban található.

1. A Microsoft Teamsben lépjen az alkalmazások listájához.
 
2. Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.

3. Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.

Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.

> [!NOTE]
> Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban. 

Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.

> [!NOTE]
> Az alkalmazás most már támogatja a Rendszergazda biztonsági szerepkört.
 
## <a name="use-the-bot"></a>A robot használata

Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.

> [!NOTE]
> A robottal való első interakciót követően szükség lehet a bejelentkezésre. Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.

A robot a következőre kérhető:

- Az aktuális szabadságegyenlegek megtekintése. Elküldheti például a következő üzenetet: „Tekintse meg a szabadságegyenlegeket”.

- Szabadságkérelem indítása az Ön számára. Ha konkrétabb szabadságkérelmet szeretne a szabadság típusához, elküldheti például a következő üzenetet: „Szabadságot kérek a következő csütörtökre és péntekre”. 

  ![Szabadságkérés indítása a Teams-csevegésben.](./media/hr-teams-leave-app-initiate.png)

- A csevegőrobot automatikusan kitölti a szabadságra vonatkozó kérést. Válassza ki a **Távollét kérelmezése** lehetőséget, és szerkessze a kérés részleteit.

   Ha ugyanahhoz a dátumhoz több szabadságtípusra vonatkozóan szeretne szabadságkérelmet küldeni, válassza a **Nap felosztása a következővel** elemet a **További beállítások** menüben. 

   Ha a szabadságkérelem napokban van megadva, de Ön félnapos szabadságot választ, megadhatja, hogy a nap első vagy második felére kéri a szabadságot. Ehhez válassza ki a **Félnapos meghatározás** elemet a **További beállítások** menüben.
   
   ![Félnapos meghatározások.](./media/HalfDayDefinitions.png)

- Ha végzett a szabadságkérés részleteinek szerkesztésével, a **Küldés** gombot kiválasztva küldje el jóváhagyásra.

  ![Szabadságra vonatkozó kérelem elküldése.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Távollét kezelése a Teams alkalmazásban

A **Szabadság** lapon a következők jeleníthetők meg: 

- Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk

- Várható szabadságkérelmek

- Szabadságkérelmek

- Vázlat szabadságkérelmek
 
### <a name="create-a-new-request"></a>Új kérelem létrehozása

1. Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.

2. Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása.](./media/TimeOffHours.png)

3. Ha szükséges, írjon be egy okkódot. Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.

4. Ha több, különböző típusú távolléti kérelmet szeretne ugyanahhoz a dátumhoz kérni, válassza a **Nap felosztása a következővel** elemet a **További beállítások** menüben.

5. Annak meghatározásához, hogy az első vagy a második fél napot szeretné szabadságként kérni, válassza a **Félnapos meghatározás** lehetőséget. Ez a beállítás akkor érhető el, ha a szabadság kérelemegysége nap, és a kért mennyiség 0,5 nap.

6. Ha befejezte az adatok megadását, válassza az **Elküldés** lehetőséget, hogy elküldje jóváhagyásra. Beírhatja a **Mentés piszkozatként** kifejezést is, ha később vissza szeretne térni.

### <a name="manage-draft-requests"></a>Vázlat kérelmek kezelése

1. Válassza ki a **Vázlatok** lapot.

2. A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.

3. Hajtsa végre a szükséges módosításokat. Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra. Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.
   
### <a name="respond-to-teams-notifications"></a>Válaszadás a Teams értesítéseire

Ha Ön vagy egy olyan dolgozó, akinek Ön jóváhagyója a szabadságkérelmet küld be, akkor a Teamsben értesítést kap a Human Resources alkalmazásban. A megtekintéséhez kiválaszthatja az értesítést. Az értesítések megjelennek a **Csevegés** területen is.

Ha a jóváhagyó, akkor az értesítésben kiválaszthatja a **Jóváhagyás** vagy **Elutasítás** lehetőséget. Egy opcionális üzenetet is megadhat.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Várható szabadságadatok küldése a munkatársai számára

Miután telepítette az Human Resources alkalmazást a Teams számára, egyszerűen küldhet információt a Teamsben vagy csevegésekben a munkatársai számára.

1. Egy csapatban vagy csevegésben a Teamsben válassza a chat ablak alatti Human Resources gombot.

   ![A chat ablak alatti Human Resources gomb.](./media/hr-teams-leave-app-chat-button.png)

2. Válassza ki a megosztani kívánt szabadságkérelmet. Ha meg szeretné osztani egy vázlat szabadságkérelmet, először válassza a **Vázlatok** lehetőséget.

A szabadságkérelem a csevegésben fog megjelenni.

Ha megosztott egy vázlat állapotú kérelmet, akkor a program vázlatként jeleníti meg.

## <a name="view-your-teams-leave-calendar"></a>A csapata szabadságnaptárának megtekintése

Ha Ön közvetlen beosztottakkal rendelkező vezető, akkor megtekintheti a csoport jóváhagyott és függőben távolléteit.

1. A Teamsben a Human Resources alkalmazásban válassza a **Távollét** lehetőséget.

2. Válassza ki a **Csoport naptárát**. A naptárban a közvetlen beosztottjai jóváhagyott és a függőben lévő távollétei láthatók.

   > [!NOTE]
   > Ha nem látja a csapatnaptárat, kérje meg a rendszergazdát, hogy engedélyezze. További információ: [Telepítés és beállítás](hr-admin-teams-leave-app.md#install-and-setup).

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

## <a name="troubleshooting"></a>Hibaelhárítás

Ha nem sikerül bejelentkeznie a Dynamics 365 Human Resources Teams alkalmazásba vagy nem tudja használni, próbálja ki ezeket a hibaelhárítási utasításokat. Ha a hibaelhárítás után sem oldódott meg a probléma, akkor forduljon a támogatáshoz. További információért lásd a [Támogatás kérése](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) lehetőséget.

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Nem lehet bejelentkezni a Human Resources alkalmazásba a Teamsben.

Ha nem tud bejelentkezni az alkalmazásba, akkor előfordulhat, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók nincs alkalmazotti rekordhoz társítva a Dynamics 365 Human Resources alkalmazásban. Forduljon a rendszergazdához, és ellenőrizze, hogy az alkalmazotti rekord helyesen van-e társítva.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>A Dynamics 365 Human Resources környezet nem található a Beállítások között

Ha nem tudja kiválasztani a megfelelő Dynamics 365-környezetet, lehet, hogy a felhasználói rekord szinkronizálása nem megfelelő. Forduljon a rendszergazdához, és hozza létre újra a felhasználói rekordot, és társítsa azt a felhasználói hitelesítő adatokkal. Ezután próbáljon meg néhány perc múlva bejelentkezni a Human Resources alkalmazásba a Microsoft Teamsben.

### <a name="translations-dont-display-correctly"></a>A fordítások nem megfelelően jelennek meg

Ha a fordítások nem a vártnak megfelelően jelennek meg, győződjön meg róla, hogy a Teamsben kiválasztott nyelv megegyezik a Human Resources **Felhasználói beállítások** részén megadott nyelvvel.

A Teamsben nézze meg az **Alkalmazás nyelve** elemet a **Beállítások** között.

![Teams beállításai.](./media/hr-teams-leave-app-settings.png)

A Humar Resources alkalmazásban válassza a **Beállítások** lehetőséget, majd a **Felhasználói beállítások** lehetőséget. Ellenőrizze, hogy a **Nyelv** mező megegyezik-e a Teams **Alkalmazás nyelve** mezőjével.

![Human Resources Felhasználói beállítások.](./media/hr-teams-leave-app-user-options.png)

Ha továbbra is fordítási problémákat tapasztal, tudassa velünk. További információért tekintse át a [Támogatás igénylése a Finance and Operations alkalmazásokhoz vagy a Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json) szolgáltatáshoz.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Hiba történt a Teamsen belüli Human Resource alkalmazásban a szabadságkérelmek jóváhagyásakor.

Ha hibaüzenetet kap, amikor megpróbálja jóváhagyni a szabadságkérelmeket a Teams alkalmazásban, próbálja végrehajtani a következő hibaelhárítási lépéseket:

1. Ellenőrizze, hogy a Microsoft Teamsbe való bejelentkezéshez használt fiók megegyezik-e a Dynamics 365 Human Resources eléréséhez használt fiókkal.

2. Ellenőrizze, hogy Ön-e a kérelem érvényes jóváhagyója a szabadság jóváhagyására vonatkozó munkafolyamaton belüli beállítások ellenőrzésével. A szabadságkérelem munkafolyamatairól további tudnivalókért lásd: [Szabadságkérelmezési munkafolyamat létrehozása](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Hagyja a jóváhagyókat, ha nem kapnak Teams-üzeneteket a szabadságkérések jóváhagyásához

1. Győződjön meg róla, hogy az értesítések engedélyezve vannak a környezet és a felhasználó számára. További információért lásd: [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams), és a [Ki-és bekapcsolhatja az egyes felhasználók értesítéseit](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Győződjön meg róla, hogy a felhasználók ugyanolyan hitelesítő adatokkal vannak bejelentkezve a **Csevegések** fülön, mint a szabadságkérések jóváhagyásához. A „kijelentkezés” és a „bejelentkezés” üzenetekkel jelentkezzen be a megfelelő hitelesítő adatokkal.

3. Ha a probléma továbbra is fennáll, ellenőrizze az Üzleti események rendszer kötegelt feladatának állapotát rendszergazdaként. Ha várakozási vagy végrehajtási állapotban van, térjen vissza néhány perc múlva. Ha az állapot változatlan marad, akkor adjon be egy támogatási jegyet, hogy a csapatunk segíthessen a probléma megoldásában.

## <a name="known-accessibility-issues"></a>Ismert kisegítő lehetőségekkel kapcsolatos problémák

A Teams Human Resources alkalmazásában a következőak adálymentességgel kapcsolatos problémák tapasztalhatók amelyeket a későbbi kiadásokban kijavítunk.

| Kiadás | Megoldás vagy magyarázat |
| --- | --- |
| Ha az asztalon 400%-ra nagyít, a műveletgombok egy része kikerül a képből. | Ehelyett azt javasoljuk, hogy használja a nagyítót, amíg nem tudjuk támogatni ezt a nagyítási szintet. |
| A **Szabadságolás** lapon a Narrátor egy gombműveletet jelent be, miközben elolvassa a szabadságolás rács fejlécét. | A rács fejléce és elemei év szerint vannak csoportosítva, és összecsukhatók. A Narrátor ezt végrehajtható elemként értelmezi, de valójában nem az. |
| A **Szabadságolás** lapon egy további pöccintési kézmozdulat jelenik meg, amikor egy új kérelemben az **Okkódra** navigál. | Nincs olyan rejtett vezérlő, amelyhez a pöccintési navigáció megpróbálna eljutni. |
| Ha a **Szabadságolás** lapon pöccint, miközben a naptár meg van nyitva, akkor a vezérlőn kívülre kerül, nem pedig egy új kérés tetejére, vagy egy kérés szerkesztése közben. | Amikor eléri az **Ugrás a mai napra** elemet, vegye úgy, hogy elért a vezérlő végére, és pöccintsen az ellenkező irányba, hogy visszakerüljön felülre. |
| A **Csevegés** lapon a fókusz visszaugrik a képernyő tetejére, amikor dátumot ad meg a kisegítő eszközt vagy a billentyűzetes navigációt használja. | Használja a Tab billentyűt addig, amíg újra el nem éri a beviteli területet. |

## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez. A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva. A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet. A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla). Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/) kerül, amely kapcsolatba lép a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez. 

A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez. A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest. Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek. 

A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során. A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet. 

Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid és Azure Cosmos DB

Amikor a Microsoft Teams alkalmazásban a Dynamics 365 Human Resources alkalmazás értesítések funkcióját használja , bizonyos ügyféladatok azon a földrajzi területen kívül kerülnek, amelyen a bérlő humánerőforrás-szolgáltatását telepítették.

Dynamics 365 Human Resources az alkalmazott szabadság iránti kérelmének és a munkafolyamat-feladat részleteit átküldi a Microsoft Azure Event Grid és Microsoft Teams szolgáltatásokba. Ezeket az adatokat a Microsoft Azure Event Grid felületen az Egyesült Államokban legfeljebb 24 óráig tárolhatjuk, és a rendszer a szállítás és tárolás során titkosítja, és a Microsoft vagy az alfeldolgozók nem használják a tanításhoz vagy szolgáltatások fejlesztéséhez. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Miközben a csevegőrobottal beszélget a Human Resources alkalmazásban beszélgetett, a beszélgetés tartalma lehet, hogy el lesz tárolva az Azure Cosmos DB-szolgáltatásban és át lesz adva Microsoft Teams alkalmazásnak. Ezeket az adatokat a program legfeljebb 24 óráig tárolhatja az Azure Cosmos DB modulban, és feldolgozható azon a földrajzi régión kívül, amelyen a bérlő Human Resources szolgáltatását telepítették, a szállítás és a nyugalmi állapotban titkosítva van, és a Microsoft vagy annak alfeldolgozói nem használják a tréningek vagy szolgáltatások fejlesztése céljából. Annak megértéséhez, hogy az adatok a Teamsben hol vannak tárolva akkor lásd: [Adatok helye Microsoft Teams-alkalmazásban](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Ha korlátozni szeretné a hozzáférést a szervezethez vagy a szervezeten belüli felhasználókhoz a Human Resources alkamazásban Microsoft Teams alkalmazásban, akkor lásd: [Alkalmazásengedély-irányelvek kezelése a Microsoft Teams-alkalmazásban](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Lásd még

[A Microsoft Teams letöltése és telepítése](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams súgóközpont](https://support.office.com/teams)</br>
[Human Resources alkalmazás a Teamsben](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
