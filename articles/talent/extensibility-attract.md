---
title: Bővíthetőség az Attract szolgáltatásban
description: Ez a témakör leírja, hogyan bővítheti a Microsoft Dynamics 365 Talent – Attract alkalmazást a Microsoft Power platform segítségével.
author: andreabichsel
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9d12a4d48aa369884804c2a0bce9834534b1bec6
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832861"
---
# <a name="extensibility-in-attract"></a>Bővíthetőség az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 Talent a Common Data Service felületre épül, és a Microsoft Power Platform, valamint a Common Data Service lehetőségeivel többféleképpen lehet kiterjeszteni. Ennek megfelelően a rendszer konfigurálható és testreszabható a Microsoft Power Apps és a Microsoft Power Automate segítségével. A Microsoft Power BI használatával kiegészítő analitikát kaphat az emberekről. Ezenkívül új egyéni tevékenységek, például a Power Apps és a webes tartalom (iframe) tevékenységek, minden eddiginél alkalmazkodóbbá teszik a felvételi folyamatot. Ezen tevékenységek segítségével az üzleti igényekhez és folyamatokhoz szabhatja a felvételi folyamatot, és szavatolhatja, hogy a felvételi csoport és a pályázók számára egyaránt zökkenőmentes és személyre szabott legyen a használati élmény.

## <a name="extending-option-sets-in-attract"></a>Beállításkészletek kiterjesztése az Attract alkalmazásban

Egy **Beállításkészlet** (választólista) olyan mezőtípus, amely egy entitásba foglalható. Beállítások készletét határozza meg. Egy beállítás megjelenítésekor egy űrlapon legördülő lista vezérlőként jelenik meg.  Az Attract alkalmazásban, több mező is van, amely beállításkészlet.  Elkezdtük bevezetni a képességet a beállításkészletek kiterjesztésére, kezdve az Elutasítás okkód mezővel a Foglalkoztatási típusa mezővel, és Szolgálati idő típusa mezővel.   Ezenkívül lefordított megjelenő címkéket is hozzáadhat a felvett beállításokhoz. További tudnivalókért lásd: [Beállításcímkék testreszabása](https://docs.microsoft.com/powerapps/developer/common-data-service/customize-labels-support-multiple-languages).

> [!NOTE]
> Az álláshirdetés a LinkedIn-re funkcióhoz a **Foglalkoztatási típusa** és **Szolgálati idő típusa** mezők szükségesek az **Állás részletei** lapon. Ezen a mezők az alapértelmezett értékekeit a LinkedIn támogatja és meg lesznek jelenítve az állás feladásakor. Tehát, ha állásokat tesz közzé a LinkedIn-en, és ezen a mezők a meglévő beállításkészlet-értékeit módosítja, az állás továbbra is közzé lesz téve, de LinkedIn nem jeleníti meg az egyéni **Foglalkoztatási típusa** és **Szolgálati idő típusa** értékeket.  

Az alábbiakban az **Elutasítás oka** mező frissítésének lépéseit találja olyan értékekre, amelyek a vállalatának megfelelők.  

1. Az **Elutasítás oka** beállításkészlet kiterjesztéséhez menjen [Power Apps felügyeleti webhelyre](https://admin.powerapps.com).
2. Lehetséges, hogy fel lesz kérve, hogy jelentkezzen be fiókjával. Adja meg felhasználónevét és jelszavát, amelyet a Dynamics365 és/vagy Office365 bejelentkezéshez használ, és kattintson a **Következő** gombra.
3. A **Környezetek** lapon válassza ki a környezetet, amelyet kezelni szeretne, és kattintson duplán a **Részletek** lap megnyitásához.
4. A **Részletek** lapon jelölje be a **Dynamics 365 felügyeleti központ** lehetőséget.
5. Válassza ki a módosítani kívánt példányt, és válassza a **Megnyitás** lehetőséget.
6. Keresse meg **Beállítások**, majd a **Testreszabások** lehetőséget, és válassza a **Rendszer testreszabása** lehetőséget.
7. Keresse meg az entitást, amelyhez bővíteni szeretné a beállításkészletet, válassza az **Entitások** lehetőséget, és bontsa ki a csoportot. Ebben a példában ez az **Állásjelentkezés entitás** lesz.
8. Menjen a mezőre, amelyhez ki szeretné bővíteni a beállításkészletet, ehhez válassza a **Mezők** lehetőséget. Ebben a példában ez az **msdyn_rejectionreason** lesz. Kattintson duplán a mezőre.
9. A **Beállításkészlet** mezőben válassza a **Szerkesztés** lehetőséget.
10. Válassza ki a **+** ikont.
11. Adja meg a **Címke** elemet  (Ez legyen egyedi érték – nem lehet duplikált).
12. Válassza a **Mentés** lehetőséget.
13. Válassza a **Közzététel** lehetőséget az oldal tetején.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Használja ki a Microsoft Power Platform előnyeit 

Mivel az Attract összes adata Common Data Service platformon található, a Microsoft Power Platform eszközeivel integrálhatja egyedi üzleti igényeinek az Attract rendszerébe.

### <a name="power-apps"></a>Power Apps

A Power Apps segítségével könnyen hozhat létre alkalmazásokat, amelyek csatlakoztatják Attract adatait, és olyan kifejezéseket használnak, mint a Microsoft Excel kifejezései, logika hozzáadásához. A Power Apps segítségével épített alkalmazásokat a weben, az Apple iOS és Google Android eszközökön lehet futtatni.

Megkönnyítheti például a toborzók számára a munkát az egyetemi állásbörzéken azzal, hogy létrehoz egy leegyszerűsített alkalmazást, amely lehetővé teszi az önéletrajzok beolvasását és a pályázók hozzákötését egy pozícióhoz az Attract rendszerében. Másik lehetőségként létrehozható egy alkalmazás, amely segít a szervezet megfelelési követelményeinek teljesítését. A Power Apps és az alkalmazások építésére való használatára vonatkozó további tudnivalókért lásd: [Adatok integrálása a Common Data Service](https://docs.microsoft.com/powerapps) megoldásba.

### <a name="microsoft-power-automate"></a>Microsoft Power Automate 

A Microsoft Power Automate segítségével az Attract adatokon futó automatizált munkafolyamatok hozhatók létre. Egyszerűen csatlakozhat több száz népszerű alkalmazáshoz és szolgáltatáshoz kód írása nélkül. Az Attract Munkakör, Pályázó és Jelentkezés entitásaival a Common Data Service megoldásban együttműködő folyamatok felépítésével automatizálni lehet különböző műveleteket. Például amikor egy jelölt elfogad egy ajánlatot, értesítést lehet küldeni egy bevezetési csoportnak, vagy a híreket be lehet jelenteni a Twitteren. A folyamatokkal kapcsolatos további tudnivalók a [Microsoft Power Automate dokumentációjában](https://docs.microsoft.com/flow/) olvashatók.

### <a name="power-bi"></a>Power BI

Power BI segítségével létrehozhatók és megtekinthetők egyéni jelentések és irányítópultok, amelyekkel mélyebb betekintést nyerhet Attract adataiba. További információért a Power BI témájáról és az interaktív jelentések és irányítópultok létrehozásának módját kapcsolatban lásd: [Power BI dokumentáció](https://docs.microsoft.com/power-bi/).

### <a name="custom-activities"></a>Egyéni tevékenységek 

A munkakörfolyamat-sablon szintjén vagy amíg létrehoz egy új feladatot, hozzáadhat egyéni tevékenységeket, például a Power Apps alkalmazások és a webes tartalom (iframe) tevékenységeket. Ezek a tevékenységek lehetővé teszik a felvételi folyamat testreszabását, és üzleti logikát hozhatnak az Attract megoldásba, amely egyedi a szervezetre nézve.

#### <a name="power-apps-activity"></a>Power Apps-tevékenység 

A Power Apps tevékenység lehetővé teszi, hogy a munkakör vagy a munkakörfolyamat létrehozója egy Power Apps alkalmazás ágyazzon be a felvételi folyamatba. Az alkalmazás létrehozása és közzététele után a tevékenység-konfigurációkban megadhat az alkalmazásazonosítót. Egy Power Apps alkalmazás használatával adatolvasást és -írást hajthat végre a Common Data Service megoldásban. Akár még be is hivatkozhatja az alkalmazást a folyamatba. Például van egy alkalmazás, amelyet a toborzók egy űrlap kitöltéséhez használnak a telefonos interjúk lebonyolításakor. Ebben az esetben csatolhatja az alkalmazást egy folyamathoz, amely megvizsgálja, hogy a pályázó továbbléptethető-e a munkakör-jelentkezési folyamatban. Ezt a tevékenységtípust csak a felvételi csapattagok láthatják. A Power Apps tevékenység konfigurálásával kapcsolatos további tudnivalókért lásd: [Tevékenységek a toborzási folyamatban](./activities-attract.md).

> [!NOTE]
> A Power Apps tevékenység csak az átfogó felvételi bővítménnyel érhető el.

#### <a name="web-content-iframe-activity"></a>Webes tartalom (iframe) tevékenység

A webes tartalom (iframe) tevékenység lehetővé teszi egy egyéni webes megoldás beágyazását, amelyet a felvételi folyamat vagy a Candidate portálba épít be. Az adatok írhatók és olvashatók közvetlenül a Common Data Service megoldás alkalmazásával. A megoldást testreszabhatja, hogy a folyamatokat kezdeményezzen, vagy kihasználja a Microsoft Azure funkciók előnyeit. A webes tartalom tevékenység konfigurálásával kapcsolatos további tudnivalókért lásd: [Tevékenységek a toborzási folyamatban](./activities-attract.md).

> [!NOTE]
> A webes tartalom tevékenység csak az átfogó felvételi bővítménnyel érhető el.
