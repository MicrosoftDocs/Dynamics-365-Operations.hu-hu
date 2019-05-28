---
title: A Talent bővítése a PowerApps és a Microsoft Flow segítségével – forgatókönyvek
description: Ez a témakör néhány példa bővítési forgatókönyvet ír le a Microsoft Dynamics 365 for Talent alkalmazáshoz, amelyek a Microsoft PowerApps és Microsoft Flow megoldásokat használják.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518160"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>A Talent bővítése a PowerApps és a Microsoft Flow segítségével – forgatókönyvek

Ez a témakör néhány példa bővítési forgatókönyvet ír le a Microsoft Dynamics 365 for Talent alkalmazáshoz, amelyek a Microsoft PowerApps és Microsoft Flow megoldásokat használják. Az egyes példákhoz társított megoldáscsomagot importálhatja a PowerApps környezetébe. Majd használhatja a csomagokat iránymutatásként vagy kiindulási pontként a szervezetre vonatkozó forgatókönyvek végrehajtásához.

> [!IMPORTANT]
> Ha a témakörben bemutatott sablonokat és alkalmazást „adott”állapotukban szeretné használni, ügyeljen arra, hogy tesztelje az összeset, és győződjön meg arról minden az Ön implementációjához tartozó forgatókönyvet.


## <a name="prerequisites"></a>Előfeltételek

- Csomagok importálásához felhasználóknak rendelkezniük kell a **Környezetkészítő** engedéllyel.
- Az alkalmazások exportálásához vagy importálásához a felhasználóknak PowerApps Plan 2 licenccel, vagy PowerApps Plan 2 próbalicenccel kell rendelkezniük.

## <a name="flow--form-connect"></a>Flow – Form Connect

A **Flow – Form Connect** sablon adatok beolvasására használható Microsoft Forms űrlapokból illetve azok tárolására a Common Data Service entitásban.

Ez a sablonnal kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen. Íme néhány példa:

- Pályázó értékelések rögzítése.
- Tanfolyami kérdőív eredményeinek rögzítése.
- Interjú kérdések tárházának összeállítása Emberi erőforrások (HR) rendszergazdáknak.
- A jelentkező értékelésének rögzítése az interjúfolyamatból

A Microsoft Dynamics 365: Attract alkalmazásban a képernyők megjelenhetnek Pályázói portálon és a pályázók kitölthetik adataikat. Képernyők be is ágyazhatók tevékenységként a beosztássablonban.

Amikor a jelentkező egy elküld egy űrlapot, a Microsoft Flow rögzíti az űrlap benyújtását, beolvassa az adatokat, és tárolja azt a Common Data Service entitásban.

A **Flow – Form Connects** sablon és az egyéni entitásstruktúra letöltéséhez nyissa meg a [Flow – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) elemet a Microsoft letöltőközpontban.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>A Powerapps részére átadott paraméterek kezdeményezése és kibontása

A **A Powerapps részére átadott paraméterek kezdeményezése és kibontása** sablon bármilyen PowerApps forgatókönyv kiindulópontjaként használható, amely az Attract alkalmazásra jellemző. Az Attract részére átadott összes alapértelmezett paramétert tartalmazza, mint **Álláspályázat**, **Jelentkező azonosítója**, és **JobID**.

Ezzel a sablonnal lekérhető a jelölt értékelési űrlapja, hogy a humánerőforrás-vezető megtekinthesse a pályázó által kitöltött értékelést.

A PowerApps használatával létrehozott alkalmazások beágyazhatók az Attract feladatsablonjába.

A **Powerapps részére átadott paraméterek kezdeményezése és kibontása** sablon és az egyéni entitásstruktúra letöltéséhez látogassa meg a [A Powerapps részére átadott paraméterek kezdeményezése és kibontása](https://go.microsoft.com/fwlink/?linkid=2081991) elemet a Microsoft letöltőközpontban.

## <a name="integration-with-office-365"></a>Integráció a Office 365 rendszerrel

Az **Office 365 integráció** alkalmazást használható a csapatinformációk lekéréshez a Microsoft Office 365 bejelentkezett felhasználói számára. Ez a Talent dolgozóira hivatkozik az érkezéskori és távozáskori blokkolás részletes adatai, és a kivételbejegyzések lekéréséhez. Az Érkezéskori és távozáskori blokkolás adatai egyéni Common Data Service entitásokban vannak tárolva. A program feltételezi, hogy ezek az adatok ki vannak töltve integráción keresztül egy harmadik fél rendszeréből.

Ez az alkalmazás kiterjeszthető, hogy egyéb forgatókönyvekben is használható legyen. Például egy csapat szabadságadatainak, a naptár események és a más csapat-specifikus eseményeket megjelenítésére is használható.

Az **Office 365 integráció** és az egyéni entitásstruktúra letöltéséhez lépjen az [Office 365 integráció](https://go.microsoft.com/fwlink/?linkid=2081787) helyre a Microsoft letöltőközpontban.

## <a name="flow--email-notification"></a>Flow – E-mail-értesítés

A **Flow – E-mail-értesítés** sablon e-mail értesítési forgatókönyvekhez használható. Használható értesítő e-mailek indítására azon pályázók számára, akiket a toborzócsapat elutasít a toborzási folyamat bármelyik szakaszában.

Ez a sablon kiterjeszthető a változások nyomon követésére a toborzási folyamat során a pályázó fokozatra és értesítés küldéséhez, a felvételi csapat és jelölt számára.

Általában a Common Data Service rendszerben tárolt entitásokhoz a folyamatok beállíthatók úgy, hogy értesítést küldjenek a Core HR, Attract vagy Dynamics 365 Talent: Onboard rendszerben történt eseményekről.

A **Flow – E-mail-értesítés** sablon letöltéséhez ugorjon a [Flow – E-mail-értesítések](https://go.microsoft.com/fwlink/?linkid=2082103) oldalra a Microsoft Letöltőközpontban

## <a name="flow--sql-connect-and-execute"></a>Flow – SQL csatlakozás és végrehajtás

A **Flow – SQL csatlakozás és végrehajtás** sablon csatlakozik a Microsoft SQL Server kiszolgálóhoz, és lehetővé teszi az SQL-lekérdezések futtatását.

Annak ellenére, hogy ez a sablon célja SQL táblák olvasása és frissítése, bővíthető, hogy más forgatókönyvekhez is használható legyen. Például használható előkészítési tábla kitöltés;re Common Data Service rekordokkal SQL Server kiszolgálóról, és előkészítési tábla rendszeres időközönkénti szinkronizálásához növekményes leküldéssel egy SQL Server kiszolgálóról.

A **Flow – SQL csatlakozás és végrehajtás** sablon letöltéséhez nyissa meg a [Flow – SQL csatlakozás és végrehajtás](https://go.microsoft.com/fwlink/?linkid=2081789) elemet a Microsoft letöltőközpontban.

## <a name="flow--sharepoint-integration"></a>Flow – SharePoint-integráció

A **Flow – SharePoint-integráció** sablon használható adatok beolvasására egy Microsoft SharePoint-listát, a lista mezőértékeinek összehasonlításához bármely Common Data Service entitással, és az összehasonlítás eredményéről egy értesítő e-mail küldéséhez. 

Előfordulhat, hogy a szervezetnek sürgősen szüksége van egy szakértelemre. A szakértelmek tárolható SharePoint megoldásban, egy SharePoint listában. Ha egy jelölt olyan munkára jelentkezik, amelyhez szakértelmek vannak felsorolva, ha jelentős egyezés figyelhető meg a jelentkező szakértelme és a SharePoint megoldásban tárolt szakértelem között, egy értesítő e-mail érkezik. Ezzel a módszerrel pozíciókat, amelyek sürgősen szükségesek gyorsabban be lehet tölteni, mivel az értesítések lehetővé teszik a toborzóknak, hogy felvegyék a kapcsolatot és felvegyék a jelentkezőket szervezet szintjén.

Ezzel a sablon bővíthető, így minden a SharePoint integrációt érintő forgatókönyvhöz használható.

A **Flow – SharePoint integráció** sablon letöltéséhez ugorjon a [Flow – SharePoint integráció](https://go.microsoft.com/fwlink/?linkid=2082109) oldalra a Microsoft Letöltőközpontban

## <a name="admin-console-to-manage-talent-pools"></a>Felügyeleti konzol a tehetségállományok kezeléséhez

Ha engedélyezi a LinkedIn integrációját, az Attract automatikusan létrehoz egy LinkedIn tehetségállományt. Amikor egy állásközvetítő InMail-t cserél LinkedIn-en keresztül, az Attract létrehoz egy profilt a toborzotthoz, és a toborzott tagja lesz a LinkedIn tehetségállományának. Ez a PowerApps alkalmazás jól használható a tehetségállományokban lévő jelöltek átszervezéséhez a szakértelem alapján.

Futtassa ezt a PowerApps alkalmazást felügyeleti konzolként a következő feladatok végrehajtásához:

- Jelöltek lsitázása a tehetségállományban
- A tehetségállományból jelöltek hozzáadása egy álláshoz vagy eltávolításuk
- Jelöltek áthelyezése egyik tehetségállományból egy másikba
- Annak meghatározása, hogy a jelöltek már részei-e egy tehetségállománynak, mielőtt áthelyezik azokat
- A jelentkezők szakértelmének ellenőrzésére, mielőtt áthelyeznék őket egy másik tehetségállományba

Ez a PowerApps alkalmazás több a többhöz kapcsolatot használ, így sablonként használhatja más esetekhez, ahol olyan rekordokat kell kinyernie, amelyek több a többhöz kapcsolattal rendelkeznek.

A **Felügyeleti konzol a tehetségállományok kezeléséhez** sablon kezeléséhez, nyissa meg [Felügyeleti konzol a tehetségállományok kezeléséhez](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) oldalt a Microsoft letöltőközpontban.

## <a name="additional-resources"></a>További erőforrások

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Alkalmazás bérlők és környezetek közötti áttelepítése](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
