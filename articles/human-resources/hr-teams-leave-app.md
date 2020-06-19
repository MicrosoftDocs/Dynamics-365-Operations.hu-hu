---
title: Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet szabadságot kérelmezni a Dynamics 365 Human Resources alkalmazásban a Microsoft Teams rendszerben.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428828"
---
# <a name="manage-leave-requests-in-teams"></a>Szabadság- és távollétkérelmek kezelése a Teams alkalmazásban

[!include [banner](includes/preview-feature.md)]

A Microsoft Dynamics 365 Human Resources alkalmazás a Microsoft Teams rendszerben lehetővé teszi, hogy gyorsan kérelmezzen szabadságot, és megtekintse a szabadságegyenlegét közvetlenül a Microsoft Teams rendszerben. Egy robottal léphet kapcsolatba információ kéréséhez. A **Szabadság** lapon részletesebb információk olvashatók.

## <a name="install-the-app"></a>Az alkalmazás telepítése

A Human Resources app a Teams áruházban található.

1. A Microsoft Teams rendszerben válassza ki a három pontot.

   ![Human Resources Teams szabadságkezelő alkalmazás három pontja](./media/hr-teams-leave-app-ellipses.png)
 
2. Keresse meg a Dynamics 365 Human Resources alkalmazást, majd válassza ki a **Human Resources** címet.

   ![Human Resources Teams szabadságkezelő alkalmazás HR címe](./media/hr-teams-leave-app-human-resources-tile.png)

3. Válassza a **Hozzáadás** gombot az alkalmazás telepítéséhez.

   ![Human Resources Teams szabadságkezelő alkalmazás telepítése](./media/hr-teams-leave-app-in-store.png)

Ha az alkalmazás nem lépteti be automatikusan, válassza a **Beállítás** lapot a bejelentkezéshez.

![Human Resources Teams szabadságkezelő alkalmazás Beállítások lap](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban. 

Ha egynél több Human Resources-példányhoz van hozzáférése, akkor a **Beállítások** lapon kiválaszthatja, hogy melyik környezethez kíván csatlakozni.

> [!WARNING]
> Az alkalmazás jelenleg nem támogatja a Rendszergazda biztonsági szerepkört, és egy Rendszergazdai fiókkal való bejelentkezéskor hibaüzenet jelenik meg. Másik fiókkal való bejelentkezéshez a **Beállítások** lapon jelölje be a **Fiókok váltása** gombot, majd jelentkezzen be egy olyan felhasználói fiókkal, amely nem rendelkezik Rendszergazdai jogokkal.
 
## <a name="use-the-bot"></a>A robot használata

Az alkalmazás telepítése után egy üdvözlő üzenet jelenik meg, amely ismerteti, hogy milyen típusú intézkedéseket tehet a robot az Ön nevében.

![Human Resources Teams szabadságkezelő alkalmazás robot üdvözlőüzenete](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> A robottal való első interakciót követően szükség lehet a bejelentkezésre. Ha nem jelenik meg a bejelentkezési párbeszédpanel, ellenőrizze, hogy az előugró ablakok engedélyezve vannak-e a böngésző beállításaiban.

A robot a következőre kérhető:

- Az egyes regisztrált szabadságtípusokhoz tartozó szabadságegyenleg-információk megjelenítése.

   ![Human Resources Teams szabadságkezelő alkalmazás egyenlegek megjelenítése](./media/hr-teams-leave-app-bot-balances.png)
 
- Egy adott szabadságtípussal kapcsolatos további részletek megjelenítése.

   ![Human Resources Teams szabadságkezelő alkalmazás részletes adatok megjelenítése](./media/hr-teams-leave-app-bot-details.png)

- Szabadságkérelem indítása az Ön számára.

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság kérelmezése](./media/hr-teams-leave-app-bot-request.png)
 
A szabadság iránti kérelem elindítását követően korrigálhatja a kártyán lévő napokat, vagy a **Részletek szerkesztése** lehetőséget választva további információkat adhat hozzá a kéréshez.

![Human Resources Teams szabadságkezelő alkalmazás kérelem szerkesztése](./media/hr-teams-leave-app-bot-edit.png)
 
Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra. Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.

![Human Resources Teams szabadságkezelő alkalmazás kérelem elküldése](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Távollét kezelése a Teams alkalmazásban

A **Szabadság** lapon a következők jeleníthetők meg:

- Az egyes regisztrált szabadságtípusokhoz tartozó egyenleg-információk

- Várható szabadságkérelmek

- Szabadságkérelmek

- Vázlat szabadságkérelmek

![Human Resources Teams szabadságkezelő alkalmazás Szabadság lap](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Új kérelem létrehozása

1. Új szabadségkérelem létrehozásához válassza az **Új kérelem** lehetőséget.

   ![Human Resources Teams szabadságkezelő alkalmazás Új kérelem](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Adja meg a kivenni kívánt napot vagy napokat, majd válassza a **Hozzáadás** lehetőséget.

   ![Human Resources Teams szabadságkezelő alkalmazás szabadság hozzáadása](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Ha szükséges, írjon be egy okkódot. Adjon meg bármilyen megjegyzést, és vegyen fel hozzá mellékleteket.

4. Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra. Beírhatja a **Mentés piszkozatként** kifejezést is, hogy később visszatérhessen hozzá.

### <a name="manage-draft-requests"></a>Vázlat kérelmek kezelése

1. Válassza ki a **Vázlatok** lapot.

   ![Human Resources Teams szabadságkezelő alkalmazás Vázlatok lap](./media/hr-teams-leave-app-drafts-tab.png)

2. A kérelem szerkesztéséhez válassza ki a ceruzát, vagy válassza ki a szemétkosarat a kérelem törléséhez.

3. Hajtsa végre a szükséges módosításokat. Ha befejezte az adatok megadását, írja be az **Elküldés** kifejezést, hogy elküldje jóváhagyásra. Választhatja a **Mentés piszkozatként** lehetőséget is, hogy később visszatérhessen hozzá.

   ![Human Resources Teams szabadságkezelő alkalmazás vázlat szerkesztése](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a>Adatvédelmi nyilatkozat

A Microsoft Teams rendszer Dynamics 365 Human Resources robotjával elemezhetők a felhasználó szöveges bemenetei az alapul szolgáló kérdés/szándék megértéséhez. A felhasználó bemenete (például a „Contoso fiók keresése”) a Microsoft egyik kognitív szolgáltatásához, a Language Understanding Intelligent Service (LUIS) szolgáltatáshoz van irányítva. A LUIS-ról  [itt](https://www.luis.ai/) olvashat többet. A LUIS szolgáltatás egyértelműsíti vagy megérti a felhasználói bevitel szándékát (ebben az esetben a szándék az, hogy információt találjon) és a cél entitást (ebben az esetben a szándékolt entitás egy Contoso nevű számla). Ez az információ ezután a Microsoft  [Azure bot keretrendszerébe](https://azure.microsoft.com/services/bot-service/)  kerül, amely interaktál a Dynamics 365 Human Resources adataival, és lekéri a kívánt információkat a felhasználói lekérdezéshez. 

A robot telepítésével és a használatához való hozzáférés engedélyezésével Ön elfogadja, hogy a LUIS szolgáltatás és az Azure robot keretrendszer feldolgozza a bemenet mögötti szándékot, ami egy továbbfejlesztett, társalgásszerű felhasználói élményt eredményez. A LUIS szolgáltatás és az Azure robot keretrendszer különböző szintű megfeleléssel rendelkezhet a Dynamics 365 Human Resources alkalmazáshoz képest. Noha a LUIS szolgáltatás csak a felhasználói lekérdezésekhez férhet hozzá, és nem a felhasználó Dynamics 365 Human Resources adataihoz vagy fiókjához való kapcsolódásra készült, a Dynamics 365 Human Resources robot felhasználója önként adhat meg egy lekérdezést, amely tartalmazza a vevői adatokat, személyes adatokat vagy más adatokat, és az ilyen lekérdezés tartalma elküldhető a LUIS szolgáltatásnak és az Azure robot keretrendszernek. 

A felhasználói lekérdezések és üzenetek tartalma legfeljebb 30 napig megmarad a LUIS rendszerben, a nyugalmi formában titkosítva van, és nincs használatban a tréningek vagy a szolgáltatások fejlesztése során. A Cognitive Services szolgáltatással kapcsolatban  [itt](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/) olvashat többet. 

Az Microsoft Teams-alkalmazások felügyeleti beállításainak kezeléséhez nyissa meg a [Microsoft Teams felügyeleti központot](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Lásd még

[A Microsoft Teams letöltése és telepítése](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams súgóközpont](https://support.office.com/teams)</br>
[Human Resources alkalmazás a Teams rendszerben](hr-admin-teams-leave-app.md)
