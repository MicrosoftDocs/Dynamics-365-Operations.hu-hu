---
title: Commerce Commerce Commerce Commerce commercechannel for Customer Service modul
description: Ez a témakör a Commerce CommerceChannel for Customer Service modult ismerteti a következőben:Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: 99e8b9d66a04390ab70fd1deff9f95fe28bdfae3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690316"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Commerce Commerce Commerce Commerce commercechannel for Customer Service modul

[!include [banner](includes/banner.md)]

Ez a témakör a *Commerce CommerceChannel for Customer Service modult ismerteti* a következőben:Microsoft Dynamics 365 Commerce

A Commerce rendszer 10.0.29-es verziójának kiadásában egy új Commerce CommerceChannel for Customer Service modul lett hozzáadva a Commerce modultárhoz. A Commerce commerce csevegési funkció a Dynamics 365Channel for Customer Service szoftverből elérhető beszélgetési lehetőségeket biztosítja az e-commerce ügyfelek számára, amely az élő ügynöktámogatást tartalmazza a vevői lekérdezések címzésében, az ügyfélszolgálatban, valamint a Commerce rendszer vevőinek való értékesítés megkönnyítése érdekében.

A Commerce csevegési funkció lehetővé teszi a kiskereskedők számára a következő célok elérését:

- A vevőkkel való személyre szabott együttműködés növelése a vevői visszatartás javítása érdekében.
- Az ügyfélszolgálat javítása az emberi ügynök és az önkiszolgálókiszolgáló beszélgetés integrálása révén.
- Segít az ügynököknek abban, hogy tapasztalatokat szereznek a valós idejű vevőprofilban, rendelési és beszerzési adatokban, amelyek a működési fejlesztéseket és a tevékenységeket segítik.
- A vevők általános elégedettségének javítása az értékesítések növelése érdekében.

A Commerce csevegési funkció a következő funkciókat tartalmazza:

- Commerce Commerce Commerce commerce commercechannel for Customer Service
- **A Commerce Call Center alkalmazáslapként** való alkalmazása a Dynamics 365Channel for Customer Service alkalmazásban

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Előfeltételek aChanchannel szolgáltatáshoz az Ügyfélszolgálat számára

Előfeltételként be kell állítania a beszélgetéseket az Ügyfélszolgálat felügyelete eszközben, és be kell szereznie néhány paramétert, hogy be tudja állítani a Commerce-beszélgetés élményét. Az útmutatásért lásd [: Beszélgetéscsatorna konfigurálása](/dynamics365/customer-service/set-up-chat-widget).

Miután konfigurálta a beszélgetéseket az Ügyfélszolgálat felügyelete modulban, a következő példához hasonló forgatókönyvet kap.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

A forgatókönyv másolása, mert a beszélgetésmodul konfigurálására a benne található értékekre lesz szüksége.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Commerce Commerce Commerce Commerce CommerceChannel for Customer Service – kötelező mezők

Az alábbi táblázat bemutatja az Ügyfélszolgálat felügyelete modul Commerce Beszélgetés és channel szolgáltatás moduljának konfigurálához szükséges Scriptchannel for Customer Service eszköz parancsfájlértékét.

| Elem tulajdonsága | Leírás |
| ------------- |--------------|
| Parancsfájl forrása | Arc értéke **a** beszélgetési eszköz parancsfájlában |
| Adatalkalmazás azonosítója | Az adatalkalmazás-azonosító **értéke** a beszélgetési eszköz parancsfájlában |
| Adatszervezet azonosítója | Az adat-org-azonosító **értéke** a csevegési eszköz parancsfájlában. |
| Adatszervezet URL-címe | Az adat-org-URL **értéke** a csevegési eszköz parancsfájlában. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>A Commerce-csevegési tapasztalat konfigurálása az e-commerce webhelyhez

Az e-commerce webhely számára az egyik javasolt megoldás a Commerce Commerce És Az Ügyfélszolgálat modul hozzáadása az e-commerce webhely lapjain használt megosztott fejlécrészlethez.

A következő lépések szerint hozzáadhatja a bővítménymodult a webhely fejlécrészletéhez a Commerce webhelyszerkesztőben.

1. A webhely webhelyszerkesztőjére a Részletek gombra **ugrást kell itt található meg**.
1. Válassza az **Új** lehetőséget.
1. A Részlet **kiválasztása párbeszédpanelen** válassza **ki a Commerce Commerce Beszélgetés** a Vevői szolgáltatás modulban lehetőséget, írja be a részlet nevét, **majd válassza az OK gombra való lehetőséget**.
1. A szerkezeti nézetben válassza **ki az Msdyn365 cs beszélgetéscsatlakozó-bejhelyet**.
1. A jobb oldalon **található Beszélgetéstulajdonságok** ablakban hajtsa végre a következő lépéseket:

    1. A Parancsfájl **forrása mezőben** adja meg azt a forrásértéket, **amelyet** a Vevői szolgáltatás forgatókönyve alapján kapott.
    1. Az Adatalkalmazás **azonosítója mezőben** adja meg azt az adatalkalmazás-azonosító **értéket,** amelyet aChannel for Customer Service parancsfájlból kapott.
    1. Az Adatszervezet **azonosítója mezőben** az az adatszervezet-azonosító érték **,** amelyet az Ügyfélszolgálati parancsfájlból kapott.
    1. Az Adatszervezet **URL-cím** mezőjébe írja be azt az adatszervezeti URL-értéket **,** amelyet az Ügyfélszolgálati parancsfájlból kapott.

    ![Commerce Commerce-modulrészlet létrehozása a Commerce webhelyszerkesztőben](media/Commerce-chat-creating-new-fragment.png)

1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen a Részletrészletek **lapra**, és nyissa meg a webhely fejlécrészletét.
1. Az Alapértelmezett tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a Részlet hozzáadása **lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a korábban létrehozott beszélgetési részletet, majd válassza **az OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

> [!NOTE]
> A konfigurációs paraméterek teljes [listáját lásd a Commerce modul proaktív beszélgetési paramétereinél](chat-proactive-chat-parameters.md).

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>A Commerce Headquarters hozzáadása pályázati lapként az Ügyfélszolgálati szolgáltatáshoz

A Commerce Headquarters for Customer Service alkalmazásban lehetőség van a Commerce Headquarters alkalmazás lapjának hozzáadására. Az élő ügynökök ezután az Ügyfélszolgálati Dynamics 365 Commerce ügynök felhasználói felületének használatával egyszerűen hozzáférhetnek az Ügyfélszolgálat modulhoz, amely a vevő környezetfüggő adatait, valamint értékesítési rendelési adatait tartalmazza. Ezenkívül az ügyfélszolgálati ügynökök új rendeléseket is be tudnak rendelni, visszaküldést kezdeményezhetik, és ellenőrizhetik a rendelési állapotuk adatait.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Új alkalmazáslap létrehozása, amely betölti a Commerce Headquarters alkalmazást egy modulban iFrame 

A következő lépések szerint hozzon létre egy olyan új alkalmazáslapot, amely betölti a iFrame Commerce Headquarters alkalmazást egy modulba.

1. Nyissa meg a [Power Apps Készítő portált](https://make.powerapps.com).
1. Válassza az Alkalmazásokat a bal oldali navigációs **ablakban**.
1. Válassza ki **az Ügyfélszolgálat adminközpontját**.
1. Ugrás az ügynök **tapasztalatihoz**
1. Az **Alkalmazás lapsablonok csoportjában válassza** a **Kezelés lehetőséget**.
1. A Harmadik fél webhelytípusú **új alkalmazáslap** létrehozása. Az útmutatás az alkalmazás lapsablonjainak [kezelése útmutatóban található](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. A **Paraméterek** területen, az **URL**-paraméter **Érték mezőjében adja meg a következő URL-címet**, `<YourOrganizationHeadquartersURL>``<LegalEntityname>` ahol a megfelelő értékek felülírják őket. Achannel ügyfélszolgálat a csevegési **{AccountNumber}** környezetből olvassa be az olvasott szövegeket. Ezért hagyja úgy **{AccountNumber}**, ahogy van.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Hagyja üresen **az** adatparaméter Érték **mezőjét**.

![Alkalmazás lap létrehozása a Dynamics 365Channel ügyfélszolgálatában](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Új alkalmazáslap engedélyezése vevők ügynökei számára a Dynamics 365Channel for Customer Service alkalmazásban

A következő lépésekkel új alkalmazáslapot engedélyezheti a vevők ügynökei számára a Dynamics 365Channel for Customer Service alkalmazásban.
    
1. Nyissa meg a [Power Apps Készítő portált](https://make.powerapps.com).
1. Válassza az Alkalmazásokat a bal oldali navigációs **ablakban**.
1. Válassza ki **az Ügyfélszolgálat adminközpontját**.
1. Ugrás az Ügyféltámogatási **\> munkafolyamok höz**.
1. Nyissa meg az ügynökök számára létrehozott munkafolyamot, **majd** a Speciális beállítások csoportban válassza az Alapértelmezett **munkamenetek lehetőséget**.
1. Az **Alkalmazáslapok lapon válassza** a **Meglévő pályázat** hozzáadása lapot, majd adja hozzá a korábban létrehozott új pályázatlapot. Ez a lépés gondoskodik arról, hogy egy olyan alkalmazáslap jelenjen meg, amely a Commerce Headquarters iFrame alkalmazást betölti egy modulban, amikor az ügynök bejövő beszélgetéshívást kap az e-commerce webhelyről.

> [!NOTE]
> A munkabb rétegben nem módosíthatja az alapértelmezett munkamenetsablont. Emiatt előfordulhat, hogy a frissítéshez létre szeretne hozni egy új sablont, vagy ismétlődő sablont szeretne létrehozni a meglévő sablonból. A további tudnivalókat lásd [a sablonok társítása a munkafolyamhoz](/dynamics365/app-profile-manager/associate-templates).

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Környezeti változók hozzáadása a Dynamics 365Channel for Customer Service szolgáltatáshoz

A következő lépések szerint adhat hozzá környezetváltozókat a Dynamics 365Channel for Customer Service szolgáltatáshoz.

1. Nyissa meg a [Power Apps Készítő portált](https://make.powerapps.com).
1. Válassza az Alkalmazásokat a bal oldali navigációs **ablakban**.
1. Válassza ki **az Ügyfélszolgálat adminközpontját**.
1. Ugrás az Ügyféltámogatási **\> munkafolyamok höz**.
1. Nyissa meg az ügynökök számára létrehozott munkafolyamot, **majd** a Speciális beállítások területen nyissa **meg a Környezet változó szakaszt**.
1. Válassza a **Szerkesztés lehetőséget, majd adja hozzá** az AccountNumber **értékét szövegtípus környezeti változójaként** **.** Ez a változó segít a Commerce Headquarters számára a vevőadatok megfelelő számlaszámokkal való betöltésében.

> [!NOTE]
> Ha e-commerce csatornából szeretné beolvasni az e-mail címeket és a bejelentkezett felhasználók nevét, **·** **az** AccountNumber **környezetváltozó mellett felveheti az E-mail és a Név értékét is szövegtípus környezeti változóiként.** **·**

## <a name="additional-resources"></a>További erőforrások

[Commerce commerce csevegési funkciók – áttekintés](commerce-chat-overview.md)

[Commerce Commerce-beszélgetés modullal Power Virtual Agents](chat-module-pva.md)

[Commerce- és csevegési modul proaktív csevegési paraméterei](chat-proactive-chat-parameters.md)
