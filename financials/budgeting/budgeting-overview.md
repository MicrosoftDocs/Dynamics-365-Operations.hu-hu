---
title: "Költségvetés kezdőlap"
description: "Ez a témakör áttekintést ad a Microsoft Dynamics 365 for Operationsben elérhető költségvetési funkció összetevőiről, a költségvetési eszközökről, valamint a jelentéskészítési lehetőségekről."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: dd17842365e357ecb5cb6034ed8878fcd60be5fc
ms.openlocfilehash: aacce0449c9490c4ab66cacb9945ed64fa40de34
ms.contentlocale: hu-hu
ms.lasthandoff: 04/26/2017


---

# <a name="budgeting-home-page"></a>Költségvetés kezdőlap

[!include[banner](../includes/banner.md)]


Ez a témakör áttekintést ad a Microsoft Dynamics 365 for Operationsben elérhető költségvetési funkció összetevőiről, a költségvetési eszközökről, valamint a jelentéskészítési lehetőségekről. 

<a name="components-of-budgeting-functionality"></a>A költségvetés-tervezési funkció összetevői
-------------------------------------

Az erőforrástervezési ciklus egy vállalatnál általában tervezési, költségvetési és előrejelző tevékenységekből áll.
[![A költségvetési funkció összetevői](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) Mind a hosszú távú stratégiai tervezés, mind az éves költségvetés-tervezés folyamatait támogatja egy költségvetéstervezés-dokumentum. A költségvetéstervezés-dokumentumok szorosan integrálódnak a Microsoft Excellel. A felhasználók korlátlan monetáris és mennyiségi eseteket konfigurálhatnak, és meghatározhatnak egy költségvetés-tervezési szervezeti hierarchiát, így a felülről lefelé, illetve az alulról fölfelé épülő költségvetés-tervezési módszereket is támogatja a rendszer. A költségvetés létrehozása és a Microsoft Dynamics 365 for Operations rendszerben történő jóváhagyása után költségvetési tételjegyzék-bejegyzéssé konvertálhatja a költségvetési tervet. A költségvetési tételjegyzék-bejegyzések révén karbantartható a költségvetés, és költségvetési kódok segítségével nyomon követhetők az összegek. A költségvetési tételjegyzék-bejegyzések segítségével felülvizsgálhatók az eredeti költségvetések, és áthozhatók az előző évi költségvetési összegek. A létrehozott költségvetés alapján a vállalat engedélyezheti a költségvetés-ellenőrzést. Az ellenőrzés szintje függ a szervezeti kultúrától és a szervezet érettségi szintjétől. Az alacsonyabb érettségi szintű szervezeteknél előfordulhat, hogy a költségvetést „adott állapotában” hagyják, és inkább reaktívan, mint proaktívan viselkednek, ha a költségvetés nem felel meg az elvárásoknak. Egyéb szervezeteknél előfordulhat olyan költségvetés-ellenőrzési irányelveket engedélyezhetnek, amelyek nem engedik a beszerzést a felhasználóknak, ha a költségvetési források nem érhetők el. Végül pedig a nagyon érett szervezetek kialakíthatnak egy olyan vállalati kultúrát, ahol az alkalmazottak megfelelő oktatást kapnak a szervezeti célokról, és követik ezen célokat, olyan irányelvek révén, mint például az „Online értekezlet megfontolása utazás helyett”. A Dynamics 365 for Operations rendszer olyan költségvetés-ellenőrzési keretrendszert tartalmaz, amely lehetővé teszi a vállalat vezetésének, hogy válasszon a kemény szabályozás (amely megakadályozza az olyan feladásokat, amelyek átlépnék a költségvetést) és a puha szabályozás (amely figyelmezteti a felhasználókat, hogy túllépik az elérhető költségvetési alapokat, de eldönthetik, hogy hogyan haladnak tovább) között. Végül pedig használhat gördülő előrejelzéseket is. A gördülő előrejelzés rendszeres összehasonlítás a költségvetés és a tényleges tételek között, és segítségével meghatározható, a cég milyen jól teljesíti a költségvetést. A gördülő előrejelzés trendek felfedezésére is szolgál. A Microsoft Dynamics 365 for Operations rendszerben a gördülő előrejelzések támogatása kezdeti tervezési tevékenységekként egy költségvetési tervezési dokumentumon keresztül történik. A gördülő előrejelzések elvégezhetőek a következő költségvetési tervezési ciklus tervezésével párhuzamosan.

-   [Alapvető költségvetés-tervezés: Áttekintés és konfiguráció](basic-budgeting-overview-configuration.md)
-   [Költségvetés-ellenőrzés: Áttekintés és konfiguráció](budget-control-overview-configuration.md)
-   [Költségvetés-tervezés: Áttekintés és konfiguráció](budget-planning-overview-configuration.md)
-   [Beosztás előre jelzése](position-forecasting.md)
-   [Költségvetés-tervezés igazoló dokumentumai](budget-planning-justification-docs.md)
-   [Microsoft Excel költségvetés-tervezési sablonok](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Költségvetés-tervezési eszközök a Dynamics 365 for Operations rendszerben
[![Költségvetés-tervezési eszközök](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

A további költségvetés-tervezési eszközök érhetők el a Dynamics 365 for Operations rendszeren keresztül, a főkönyvi költségvetésbe beépítve.

-   **Munkaerő-költségvetések** – A munkerő költségvetésének megtervezése költségelőirányzat-összetevőt tartalmaz beosztások, kompenzációs csoportok stb. tervezéséhez.
-   **Tárgyi eszközök költségvetései** – A tárgyi eszközök adatai alapján ki tudja számolni a tervezett értékcsökkenést és bejegyezhet egyéb, a tárgyi eszközhöz kapcsolódó tervezett tranzakciókat.
-   **Projekt-költségvetések** – A projektmodulban részletes projekt-előrejelzéseket hozhat létre. A projektek előrejelzései részleteket tartalmaznak a tervezett órákról, költségekről, díjakról és cikkekről.
-   **Igény-előrejelzés** – Az előzményi tranzakciós adatok alapján megbecsülheti a jövőbeli készletigényt és igény-előrejelzéseket hozhat létre.

További információért arról, hogy hogyan hívhat be tervezési adatokat más modulokból a költségvetési tervekbe, lásd: [A költségvetés-tervezés integrációja egyéb modulokkal](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Felhasználói felület és jelentési funkciók
A Dynamics 365 for Operations rendszerben a felhasználók költségvetési terveket hozhatnak létre közvetlenül vagy a Dynamics 365 for Operations kliensben (konfigurálható költségvetésiterv-dokumentumlap használatával) vagy az Excel programon keresztül. Az Excel számos további lehetőséget kínál. Például használhat külső adatokat egy költségvetési terv forrásaként, egyéni számításokat végezhet, és használhat Microsoft-kimutatásokat és -diagramokat. A költségvetés-tervezési folyamat változóinak nagy része konfigurálható. Meghatározhatja például, ki tervezi a költségvetést, mire vonatkozik a költségvetés, és milyen legyen a folyamat. Annak ellenére, hogy használhatja az Excel programot a költségvetés-tervezéshez, a Dynamics 365 for Operations rendszer megmarad az igazság egyetlen forrásának, és ez a rendszer segít a költségvetés-ellenőrzési problémák megelőzésében. Ismétlődő folyamatok felhasználásával a kezdeti költségvetés-tervezési adatok átemelhetők a költségvetési tervbe. A jelentésekhez a Dynamics 365 for Operations rendszer szabványosított lekérdezési lapok sorát biztosítja, amelyek lehetővé teszik, hogy megtekintse és elemezze a költségvetés adatait. A költségvetési terv adatai a Felügyeleti jelentéskészítőn keresztül érhetők el; külön költségvetésiterv-esetek jeleníthetők meg oszlopokként a Felügyeleti jelentéskészítő jelentésében.







