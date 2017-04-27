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
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: f7b4efc06b8e64c05da026850b41cb5b68c33ec3
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-home-page"></a>Költségvetés kezdőlap

[!include[banner](../includes/banner.md)]


Ez a témakör áttekintést ad a Microsoft Dynamics 365 for Operationsben elérhető költségvetési funkció összetevőiről, a költségvetési eszközökről, valamint a jelentéskészítési lehetőségekről. 

<a name="components-of-budgeting-functionality"></a>A költségvetés-tervezési funkció összetevői
-------------------------------------

Az erőforrástervezési-ciklus egy vállalatnál általában tervezési, költségvetési, és előrejelző tevékenységekből áll.
[![A költségvetési funkció összetevői](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) Mind a hosszú távú stratégiai tervezés, mind az éves költségvetés-tervezés folyamatait támogatja egy költségvetéstervezés-dokumentum. Költségvetési terv dokumentumai rész szorosan integrálódik a Microsoft Excellel. A felhasználók korlátlan monetáris és mennyiségi eseteket konfigurálhatnak, és meghatározhatnak egy költségvetés-tervezési szervezeti hierarchiát, így a felülről lefelé illetve az alulról fölfelé épülő költségtervezési módszereket is támogatja a rendszer. A költségvetés létrehozása és a Microsoft Dynamics 365 for Operations rendszerben történő jóváhagyása után költségvetési tételjegyzék-bejegyzéssé konvertálhatja a költségvetési tervet. Költségvetési tételjegyzék-bejegyzések eszközök révén érhető el a költségvetés karbantartásának és, hogy az összegek költségvetési kódok segítségével nyomon követhető. Költségvetési tételjegyzék-bejegyzések segítségével vizsgálja felül az eredeti költségvetések átvitelek végrehajtása és áthozott költségvetési összegeket az előző év. A létrehozott költségvetési alapján, a vállalat engedélyezheti a költségvetés-ellenőrzés. Az ellenőrzés szintje függ a szervezet szokásaitól és a szervezet érettségi szintjétől. Az alacsonyabb érettségi szintű vállalatoknál előfordulhat, hogy a költségvetést „adott állapotában” hagyják és inkább reaktívan mint proaktívan viselkednek, ha a költségvetés nem felel meg az elvárásoknak. Egyéb szervezetek előfordulhat, hogy engedélyezze a költségvetési szabályával, amely megakadályozza, hogy a felhasználók beszerzési, ha a költségvetési források nem érhetők el. Végül pedig a nagyon érett szervezetek kialakíthatnak egy olyan vállalati kultúrát, ahol az alkalmazottak megfelelő oktatást kapnak a szervezeti célokról, és követik ezen célokat, olyan irányelvek révén, mint például „Online értekezlet megfontolása utazás helyett”. A Dynamics 365 for Operations rendszer egy olyan költségtervezési keretrendszert tartalmaz, amely lehetővé teszi a vállalat vezetésének, hogy válasszon a kemény szabályozás (amely megakadályozza az olyan feladásokat, amelyek átlépnék a költségvetést) és a puha szabályozás (amely figyelmezteti a felhasználókat, hogy túllépik az elérhető költségvetési alapokat, de eldönthetik, hogy hogyan haladnak tovább) között. Végül pedig használhat gördülő előrejelzéseket is. A gördülő előrejelzés egy rendszeres összehasonlítás a költségvetés és a tényleges tételek között, és ahhoz használatos, hogy meghatározzuk, a cég milyen jól teljesíti a költségvetést. Gördülő előrejelzés felfedezhet olyan trendeket is szolgál. A Microsoft Dynamics 365 for Operations rendszerben a gördülő előrejelzések egy költségtervezési-dokumentumon keresztül vannak támogatva, kezdeti tervezési tevékenységekként. A gördülő előrejelzések elvégezhetőek a következő költségtervezési-ciklus tervezésével párhuzamosan.

-   [Alapvető költségvetés-tervezés: Áttekintés és konfiguráció](basic-budgeting-overview-configuration.md)
-   [Költségvetés-ellenőrzés: Áttekintés és konfiguráció](budget-control-overview-configuration.md)
-   [Költségvetés-tervezés: Áttekintés és konfiguráció](budget-planning-overview-configuration.md)
-   [Pozíció-előrejelzés](position-forecasting.md)
-   [Költségvetési tervezés igazoló dokumentumai](budget-planning-justification-docs.md)
-   [Microsoft Excel-sablonok költségvetés-tervezéshez](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Költségvetés-tervezési eszközök Dynamics 365 for Operations rendszerben
[![Költségvetés-tervezési eszközök](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

A további költségvetés-tervezési eszközök a Dynamics 365 for Operations rendszeren keresztül érhetőek el, és be vannak építve a főkönyvi költségvetésbe.

-   **A munkaerő-költségvetések** – Költségvetési munkaerő tartalmaz részletes költségvetési költségösszetevőnek megtervezése a beosztások, a kompenzációs csoportokat, és így tovább.
-   **Tárgyi eszközök költségvetései** – A tárgyi eszközök adatai alapján ki tudja számolni a tervezett értékcsökkenést és bejegyezhet egyéb, a tárgyi eszközhöz kapcsolódó tervezett tranzakciókat.
-   **Projekt-költségvetések** – A projektmodulban részletes projekt-előrejelzéseket hozhat létre. A projektek előrejelzései részleteket tartalmaznak a tervezett órákról, költségekről, díjakról és cikkekről.
-   **Igény-előrejelzés** – Az előzményi tranzakciós adatok alapján megbecsülheti a jövőbeli készletigényt és igény-előrejelzéseket hozhat létre.

További információért arról, hogy hogyan hívhat be tervezési adatokat más modulokból a költségvetési tervekbe lásd: [A költségvetés-tervezés integrációja egyéb modulokkal](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Felhasználói felület és a jelentési funkciók
A Dynamics 365 for Operations a felhasználók költségvetési terveket hozhatnak létre közvetlenül vagy a Dynamics 365 for Operations kliensben (konfigurálható költségvetésiterv-dokumentum lap használatával) vagy az Excel programon keresztül. Az Excel számos további lehetőségeket tartalmaz. Például használhat külső adatokat egy költségvetési terv forrásaként, egyéni számításokat végezhet, és használhat Microsoft kimutatásokat és diagramokat. A nagy része a költségvetés-tervezési folyamat változókat is beállítható. Meghatározhatja például ki a költségvetés tesz, mi a tervezett és a folyamat néz. Annak ellenére, hogy használhatja az Excel programot a költségvetés-tervezéshez, a Dynamics 365 for Operations rendszer megmarad az igazság egyetlen forrásának, és segít a költségvetés-ellenőrzési problémák megelőzésében. Ismétlődő folyamatok ahhoz, hogy a kezdeti adatokat át a költségvetési terv költségvetés-tervezéshez használható. A jelentésekhez a Dynamics 365 for Operations rendszer a szokásos lekérdezési lapok egy készletét biztosítja, amely lehetővé teszi, hogy megtekintse és elemezze a költségvetési adatait. A költségvetési terv adatai hozzáférhetőek a Felügyeleti jelentéskészítőn keresztül, és külön költségvetésiterv-esetek jeleníthetők meg oszlopokként a Felügyeleti jelentéskészítő jelentésében.







