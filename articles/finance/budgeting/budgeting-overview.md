---
title: Költségvetés-készítés kezdőlap
description: Ez a témakör áttekinti a Microsoft Dynamics 365 Finance szolgáltatásban elérhető költségvetés-tervezési funkció összetevőit, a költségvetés-tervezési eszközöket, valamint a jelentéskészítési lehetőségeket.
author: ShylaThompson
manager: AnnBe
ms.date: 08/09/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e0c6a9e4dd3f3182c98a9f5491b07f8687c21e5c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184071"
---
# <a name="budgeting-home-page"></a>Költségvetés-készítés – kezdőlap

[!include [banner](../includes/banner.md)]

Ez a témakör áttekinti a költségvetés-tervezési funkció összetevőit, a költségvetés-tervezési eszközöket, valamint a jelentéskészítési lehetőségeket. 

<a name="components-of-budgeting-functionality"></a>A költségvetés-tervezési funkció összetevői
-------------------------------------

A vállalatok erőforrás-tervezési ciklusa általában tervezési, költségvetési és előrejelző tevékenységekből áll.

[![A költségvetés-tervezési funkció összetevői](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Mind a hosszú távú stratégiai tervezés, mind az éves költségvetés-tervezés folyamatait költségvetés-tervezési dokumentum segíti. A költségvetés-tervezési dokumentumok szorosan integrálódnak a Microsoft Excel alkalmazással. A felhasználók korlátlan számú monetáris és mennyiségi esetet konfigurálhatnak, és költségvetés-tervezési szervezeti hierarchiát is meghatározhatnak; a felülről lefelé, illetve az alulról fölfelé épülő költségvetés-tervezési módszereket egyaránt támogatja a rendszer. A költségvetés létrehozása és az alkalmazásban történő jóváhagyása után költségvetési tételjegyzék-bejegyzéssé konvertálhatja a költségvetési tervet. A költségvetési tételjegyzék-bejegyzésekkel karbantartható a költségvetés, és – költségvetési kódok segítségével – nyomon követhetők az összegek. A költségvetési tételjegyzék-bejegyzések segítségével felülvizsgálhatók az eredeti költségvetések, és áthozhatók az előző évi költségvetési összegek. A létrehozott költségvetés alapján a vállalat engedélyezheti a költségvetés-ellenőrzést. Az ellenőrzés szintje függ a szervezeti kultúrától és a szervezet érettségi szintjétől. Az alacsonyabb érettségi szintű szervezeteknél előfordulhat, hogy a költségvetést „adott állapotában” hagyják, és inkább reaktívan, mint proaktívan viselkednek, ha a költségvetés nem felel meg az elvárásoknak. Egyéb szervezeteknél előfordulhat olyan költségvetés-ellenőrzési irányelveket engedélyezhetnek, amelyek nem engedik a beszerzést a felhasználóknak, ha a költségvetési források nem érhetők el.

A nagyon strukturált szervezetek olyan szervezeti kultúrát is kialakíthatnak, amelyben az alkalmazottak képzést kapnak a szervezeti célokról, és irányelveken keresztül valósítják meg ezeket a célokat (ilyen irányelv lehet például az „Online értekezletek esetleges használata utazás helyett”). Az alkalmazás olyan költségvetés-ellenőrzési keretrendszert is tartalmaz, amely lehetővé teszi a vállalat vezetésének, hogy válasszon a kemény szabályozás (amely megakadályozza a költségvetést túllépő feladásokat) és a puha szabályozás (amely figyelmezteti a felhasználókat, hogy túllépik az elérhető költségvetést, de ők eldönthetik, hogy hogyan cselekszenek) között. Végül pedig használhat gördülő előrejelzéseket is. A gördülő előrejelzés rendszeres összehasonlítás a költségvetés és a tényleges tételek között, és segítségével meghatározható, a cég milyen jól teljesíti a költségvetést. A gördülő előrejelzés trendek felfedezésére is szolgál. A Finance and Operations rendszerben a gördülő előrejelzések támogatása kezdeti tervezési tevékenységekként egy költségvetési tervezési dokumentumon keresztül történik. A gördülő előrejelzések elvégezhetőek a következő költségvetési tervezési ciklus tervezésével párhuzamosan.

-   [Alapvető költségvetés-tervezés: Áttekintés és konfiguráció](basic-budgeting-overview-configuration.md)
-   [Költségvetés-ellenőrzés: Áttekintés és konfiguráció](budget-control-overview-configuration.md)
-   [Költségvetés-tervezés: Áttekintés és konfiguráció](budget-planning-overview-configuration.md)
-   [Beosztás előrejelzése](position-forecasting.md)
-   [Költségvetés-tervezés igazoló dokumentumai](budget-planning-justification-docs.md)
-   [Microsoft Excel-sablonok a költségvetés-tervezéshez](budget-planning-excel-templates.md)

## <a name="budgeting-tools"></a>Költségvetés-tervezési eszközök
[![Költségvetés-tervezési eszközök](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

A főkönyvi költségvetésbe beépítve további tervezési és költségvetés-tervezési eszközök érhetők el.

-   **Munkaerő-költségvetések** – A munkaerő költségvetésének megtervezése költségelőirányzat-összetevőt tartalmaz beosztások, kompenzációs csoportok stb. tervezéséhez.
-   **Tárgyi eszközök költségvetései** – A tárgyi eszközök adatai alapján ki tudja számolni a tervezett értékcsökkenést és bejegyezhet egyéb, a tárgyi eszközhöz kapcsolódó tervezett tranzakciókat.
-   **Projekt-költségvetések** – A projektmodulban részletes projekt-előrejelzéseket hozhat létre. A projektek előrejelzései részleteket tartalmaznak a tervezett órákról, költségekről, díjakról és cikkekről.
-   **Igény-előrejelzés** – Az előzményi tranzakciós adatok alapján megbecsülheti a jövőbeli készletigényt és igény-előrejelzéseket hozhat létre.

További információ arról, hogy hogyan hívhatók be tervezési adatok más modulokból a költségvetési tervekbe: [A költségvetés-tervezés integrációja egyéb modulokkal](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Felhasználói felület és jelentéskészítési funkciók
A felhasználók költségvetési terveket hozhatnak létre, vagy közvetlenül a kliensben (konfigurálható költségvetésiterv-dokumentumlap használatával), vagy az Excel programon keresztül. Az Excel számos további lehetőséget kínál. Például használhat külső adatokat egy költségvetési terv forrásaként, egyéni számításokat végezhet, és használhat Microsoft-kimutatásokat és -diagramokat. A költségvetés-tervezési folyamat változóinak nagy része konfigurálható. 

Meghatározhatja például, ki tervezi a költségvetést, mire vonatkozik a költségvetés, illetve milyen legyen a folyamat. Ugyan az Excel program is használható a költségvetés megtervezéséhez, azonban kizárólag az alkalmazás számít hiteles információforrásnak, így megelőzhetők a költségvetés-ellenőrzési problémák. Ismétlődő folyamatok felhasználásával a kezdeti költségvetés-tervezési adatok átemelhetők a költségvetési tervbe. A jelentésekhez az alkalmazás számos olyan szabványos lekérdezési oldalt biztosít, amely lehetővé teszi a költségvetés adatainak megtekintését és elemzését. A költségvetési terv adatai a Felügyeleti jelentéskészítőn keresztül érhetők el; külön költségvetésiterv-esetek jeleníthetők meg oszlopokként a Felügyeleti jelentéskészítő jelentésében.






