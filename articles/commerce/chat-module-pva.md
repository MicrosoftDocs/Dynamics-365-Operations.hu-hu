---
title: Commerce Commerce-beszélgetés modullal Power Virtual Agents
description: Ez a témakör a Microsoft webhelyeit integráló Commerce Csevegés modult Power Virtual Agents Power Virtual Agents írja Dynamics 365 Commerce le.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690954"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Commerce Commerce-beszélgetés modullal Power Virtual Agents

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft webhelyeit integráló Commerce Csevegés modult Power Virtual Agents Power Virtual Agents írja Dynamics 365 Commerce le.

A Dynamics 365 e-commerce Power Virtual Agents vevők számára elérhető Commerce-beszélgetés Power Virtual Agents funkció lehetővé teszi, hogy lekérdezéseik kezelésében használniuk kell a beszélgetési lehetőségeket. Dynamics 365 Commerce A 10.0.30-as verziótól ez a funkció a Commerce-modultár részét képezi a Commerce-modultárat használó Commerce Commerce-beszélgetés Power Virtual Agents modullal az e-commerce webhelyekbe is.

A Commerce Commerce-beszélgetés funkcióval Power Virtual Agents a vállalkozások a következő célokat érhetik el:

- A felhasználóival való személyre szabható együttműködés növelése és a visszatartás javítása.
- Az ügyfélszolgálat növelése az önkiszolgáló beszélgetésekkel.
- A vevők elégedettségének növelése, és így az értékesítések növelése.

> [!NOTE]
> A Dynamics 365Channel for Customer Service Power Virtual Agents [és az alkalmazások közötti különbségekről a Commerce modul áttekintésében olvashat bővebben](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a> A használat előfeltételei Power Virtual Agents

A Commerce Csevegés funkció Power Virtual Agents használatához előbb létre kell hoznia egy csevegést az Power Virtual Agents e-commerce webhely számára. Az utasításokat lásd [: Power Virtual Agent létrehozása, amely a gépben található](/power-virtual-agents/authoring-first-bot).

Miután konfigurálta a beszélgetéscsatot, **át kell másolnia a Funkcióazonosító** **és** a Bérlőazonosító paramétereinek értékeit a Commerce-beszélgetési élmény konfigurálása érdekében. Az értékek másolásával kapcsolatos további tudnivalókat lásd [: Beolvasása a paraméterek beolvasása Power Virtual Agents.](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters)

## <a name="configure-your-e-commerce-site"></a>Az e-commerce webhely konfigurálása 

Az e-commerce webhelynek az egyik ajánlott módja a commerce commerce webhely számára a commerce Commerce Commerce- Power Virtual Agents és modul hozzáadása a webhely lapjain használt megosztott fejlécrészlethez.

A következő lépések szerint hozzáadhatja a bővítménymodult a webhely fejlécrészletéhez a Commerce webhelyszerkesztőben.

1. A Webhely Commerce-webhelyszerkesztőjét a Következő helyen található **meg: Részletek**.
1. Válassza az **Új** lehetőséget.
1. A Részlet **kiválasztása párbeszédpanelen** válassza **ki a Commerce Beszélgetés Power Virtual Agents** modullal lehetőséget, írja be a részlet nevét, majd válassza **az OK gombra való lehetőséget**.
1. A szerkezeti nézetben válassza **ki az Msdyn365 pva csevegési csatlakoztató-begúrahelyet**.
1. A jobb oldali tulajdonságablakban hajtsa végre a következő lépéseket:

    1. Hagyja **meg az** alapértelmezett értéket **Bot Framework (például a BotParaméterek területen a Webcsat-Beszélgetés CDN-URL-cím** mezőjében `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. A Hitelesítési **Bot Framework Direct Line URL-cím** mezőben hagyja meg az alapértelmezett értéket (például `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. **A Bot id mezőben** adja Power Virtual Agents **meg a szakasz használatának előfeltételei között átmásolt Bot-azonosító**[Power Virtual Agents](#prereq) értékét.
    1. A Bérlő **azonosítója mezőbe** írja be **a** másolt bérlőazonosító értékét.

1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Menjen a Részletrészletek **lapra**, és nyissa meg a webhely fejlécrészletét.
1. Az Alapértelmezett tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a Részlet hozzáadása **lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki a korábban létrehozott beszélgetési részletet, majd válassza **az OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="proactive-chat-parameters"></a>Proaktív csevegési paraméterek

A proaktív csevegési [konfigurációs paraméterek teljes listáját lásd a Commerce csevegési modul proaktív beállítási paramétereinél](chat-proactive-chat-parameters.md).

> [!NOTE]
> Jelenleg nem Power Virtual Agents támogatja a Azure Active Directory B2C (Azure AD B2C) hitelesítést. Csak a névtelen Retail Cloud Scale Unit (RCSU) hívásokat támogatja a termék elérhetőségének be- vagy más névtelen API-kval való kommunikációra. A hitelesített API-knak a Power Virtual Agents csevegések segítségével történő hívása explicit vevői bejelentkezést igényel.

## <a name="additional-resources"></a>További erőforrások

[Commerce commerce csevegési funkciók – áttekintés](commerce-chat-overview.md)

[Commerce Commerce Commerce Commerce commercechannel for Customer Service modul](commerce-chat-module.md)

[Commerce- és csevegési modul proaktív csevegési paraméterei](chat-proactive-chat-parameters.md)
