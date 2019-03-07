---
title: Az Attact bővíthetősége
description: Ez a témakör leírja, hogyan bővítheti a Dynamics 365 for Talent - Attract alkalmazást a Microsoft Power platform segítségével.
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: d9e1dd3a67c5f64b5d05f0f171226085138e0b44
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304661"
---
# <a name="extensibility-in-attract"></a>Az Attact bővíthetősége

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Talent a Common Data Service (CDS) for Apps platformra épül, és a Microsoft Power Platform, valamint a Common Data Service for Apps lehetőségeivel többféleképpen lehet kiterjeszteni. Ennek megfelelően a rendszer konfigurálható és testreszabható a Microsoft PowerApps és a Microsoft Flow segítségével. A Microsoft Power BI használatával kiegészítő analitikát kaphat az emberekről. Ezenkívül új egyéni tevékenységek, például a PowerApps és a webes tartalom (iframe) tevékenységek, minden eddiginél alkalmazkodóbbá teszik a felvételi folyamatot. Ezen tevékenységek segítségével az üzleti igényekhez és folyamatokhoz szabhatja a felvételi folyamatot, és szavatolhatja, hogy a felvételi csoport és a pályázók számára egyaránt zökkenőmentes és személyre szabott legyen a használati élmény.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Használja ki a Microsoft Power platform előnyeit 

Mivel az Attract összes adata Common Data Service for Apps megoldásban található, a Microsoft Power platform eszközeivel integrálhatja egyedi üzleti igényeinek az Attract rendszerébe.

### <a name="powerapps"></a>PowerApps

A PowerApps segítségével könnyen hozhat létre alkalmazásokat, amelyek csatlakoztatják Attract adatait, és olyan kifejezéseket használnak, mint a Microsoft Excel kifejezései, logika hozzáadásához. A PowerApps segítségével épített alkalmazásokat a weben, az Apple iOS és Google Android eszközökön lehet futtatni.

Megkönnyítheti például a toborzók számára a munkát az egyetemi állásbörzéken azzal, hogy létrehoz egy leegyszerűsített alkalmazást, amely lehetővé teszi az önéletrajzok beolvasását és a pályázók hozzákötését egy pozícióhoz az Attract rendszerében. Másik lehetőségként létrehozható egy alkalmazás, amely segít a szervezet megfelelési követelményeinek teljesítését. A PowerApps és az alkalmazások építésére való használatára vonatkozó további tudnivalókért lásd: [Adatok integrálása a Common Data Service for Apps alkalmazásba](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

A Microsoft Flow segítségével az Attract adatokon futó automatizált munkafolyamatok hozhatók létre. Egyszerűen csatlakozhat több száz népszerű alkalmazáshoz és szolgáltatáshoz kód írása nélkül. Az Attract Munkakör, Pályázó és Jelentkezés entitásaival a Common Data Service for Apps megoldásban együttműködő folyamatok felépítésével automatizálni lehet különböző műveleteket. Például amikor egy jelölt elfogad egy ajánlatot, értesítést lehet küldeni egy bevezetési csoportnak, vagy a híreket be lehet jelenteni a Twitteren. A folyamatokkal kapcsolatos további tudnivalók a [Microsoft Flow rendszer fejlesztői dokumentációjában](https://docs.microsoft.com/en-us/flow/) olvashatók.

### <a name="power-bi"></a>Power BI

Power BI segítségével létrehozhatók és megtekinthetők egyéni jelentések és irányítópultok, amelyekkel mélyebb betekintést nyerhet Attract adataiba. További információért a Power BI témájáról és az interaktív jelentések és irányítópultok létrehozásának módját kapcsolatban lásd: [Power BI dokumentáció](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Egyéni tevékenységek 

A munkakörfolyamat-sablon szintjén vagy amíg létrehoz egy új feladatot, hozzáadhat egyéni tevékenységeket, például a PowerApps alkalmazások és a webes tartalom (iframe) tevékenységeket. Ezek a tevékenységek lehetővé teszik a felvételi folyamat testreszabását, és üzleti logikát hozhatnak az Attract megoldásba, amely egyedi a szervezetre nézve.

#### <a name="powerapps-activity"></a>PowerApps tevékenység 

A PowerApps tevékenység lehetővé teszi, hogy a munkakör vagy a munkakörfolyamat létrehozója egy PowerApps alkalmazás ágyazzon be a felvételi folyamatba. Az alkalmazás létrehozása és közzététele után a tevékenység-konfigurációkban megadhat az alkalmazásazonosítót. Egy PowerApps alkalmazás használatával adatolvasást és -írást hajthat végre a Common Data Service for Apps megoldásban. Akár még be is hivatkozhatja az alkalmazást a folyamatba. Például van egy alkalmazás, amelyet a toborzók egy űrlap kitöltéséhez használnak a telefonos interjúk lebonyolításakor. Ebben az esetben csatolhatja az alkalmazást egy folyamathoz, amely megvizsgálja, hogy a pályázó továbbléptethető-e a munkakör-jelentkezési folyamatban. Ezt a tevékenységtípust csak a felvételi csapattagok láthatják. A PowerApps tevékenység konfigurálásával kapcsolatos további tudnivalókért lásd: [Attract tevékenységek](./activities-attract.md).

> [!NOTE]
> A PowerApps tevékenység csak az átfogó felvételi bővítménnyel érhető el.

#### <a name="web-content-iframe-activity"></a>Webes tartalom (iframe) tevékenység

A webes tartalom (iframe) tevékenység lehetővé teszi egy egyéni webes megoldás beágyazását, amelyet a felvételi folyamat vagy a Candidate portálba épít be. Az adatok írhatók és olvashatók közvetlenül a Common Data Service for Apps megoldás alkalmazásával. A megoldást testreszabhatja, hogy a folyamatokat kezdeményezzen, vagy kihasználja a Microsoft Azure funkciók előnyeit. A webes tartalom tevékenység konfigurálásával kapcsolatos további tudnivalókért lásd: [Attract tevékenységek](./activities-attract.md).

> [!NOTE]
> A webes tartalom tevékenység csak az átfogó felvételi bővítménnyel érhető el.
