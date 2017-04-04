---
title: "Költségvetés kezdőlap"
description: "Ez a témakör a költségvetési funkció berendezések, eszközök költségvetés, és jelentési képességek Microsoft Dynamics 365 műveletek áttekintése."
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

Ez a témakör a költségvetési funkció berendezések, eszközök költségvetés, és jelentési képességek Microsoft Dynamics 365 műveletek áttekintése.

<a name="components-of-budgeting-functionality"></a>A költségvetés-tervezési funkció összetevői
-------------------------------------

Az erőforrástervezési-ciklus egy vállalatnál általában tervezési, költségvetési, és előrejelző tevékenységekből áll.
[![Költségvetés-tervezési funkciók összetevők](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) a költségvetés-tervezési dokumentum keresztül támogatja a hosszú távú stratégiai tervezés és éves költségvetés-tervezési folyamatok. Költségvetési terv dokumentumai rész szorosan integrálódik a Microsoft Excellel. A felhasználók korlátlan monetáris és mennyiségi eseteket konfigurálhatnak, és meghatározhatnak egy költségvetés-tervezési szervezeti hierarchiát, így a felülről lefelé illetve az alulról fölfelé épülő költségtervezési módszereket is támogatja a rendszer. A költségvetés létrehozása és a Microsoft Dynamics 365 for Operations rendszerben történő jóváhagyása után költségvetési tételjegyzék-bejegyzéssé konvertálhatja a költségvetési tervet. Költségvetési tételjegyzék-bejegyzések eszközök révén érhető el a költségvetés karbantartásának és, hogy az összegek költségvetési kódok segítségével nyomon követhető. Költségvetési tételjegyzék-bejegyzések segítségével vizsgálja felül az eredeti költségvetések átvitelek végrehajtása és áthozott költségvetési összegeket az előző év. A létrehozott költségvetési alapján, a vállalat engedélyezheti a költségvetés-ellenőrzés. Az ellenőrzés szintje függ a szervezet szokásaitól és a szervezet érettségi szintjétől. Az alacsonyabb érettségi szintű vállalatoknál előfordulhat, hogy a költségvetést „adott állapotában” hagyják és inkább reaktívan mint proaktívan viselkednek, ha a költségvetés nem felel meg az elvárásoknak. Egyéb szervezetek előfordulhat, hogy engedélyezze a költségvetési szabályával, amely megakadályozza, hogy a felhasználók beszerzési, ha a költségvetési források nem érhetők el. Végül nagyon érett szervezetek elemévé egy szervezeti kultúra, ahol alkalmazottak vannak kapcsolatban a szervezeti célok oktatásban, és hajtsa végre az ezen célok házirendek, például a "Fordítson figyelmet online értekezlet helyett egy utazás." 365 Dynamics műveletekhez tartalmaz egy költségvetés-ellenőrzési keretrendszer, amely lehetővé teszi, hogy a vállalat vezetősége, jelölje ki mindkét merevlemez vezérlőt (amely megakadályozza a könyvelést a költségvetés felett helyezkedik el) vagy gyenge (ahol a felhasználók figyelmeztetést kapnak, hogy azok meghaladja a rendelkezésre álló költségvetési alapok, de is eldönthetik, hogy hogyan). Végezetül működés közbeni előrejelzések is használhatja. Gördülő előrejelzés tényleges költségvetés rendszeres összehasonlítását, és segítségével meghatározható, hogy milyen jól működik, a vállalat a tervezetthez. Gördülő előrejelzés felfedezhet olyan trendeket is szolgál. A Microsoft Dynamics 365 for Operations rendszerben a gördülő előrejelzések egy költségtervezési-dokumentumon keresztül vannak támogatva, kezdeti tervezési tevékenységekként. A gördülő előrejelzések elvégezhetőek a következő költségtervezési-ciklus tervezésével párhuzamosan.

-   [Alapvető költségvetés-tervezés: Áttekintés és konfiguráció](basic-budgeting-overview-configuration.md)
-   [Költségvetés-ellenőrzés: Áttekintés és konfiguráció](budget-control-overview-configuration.md)
-   [Költségvetés-tervezés: Áttekintés és konfiguráció](budget-planning-overview-configuration.md)
-   [Pozíció-előrejelzés](position-forecasting.md)
-   [Költségvetés-tervezési indoklás dokumentumok](budget-planning-justification-docs.md)
-   [A Microsoft Excel sablonok költségvetés-tervezés](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Költségvetés-tervezési eszközök Dynamics 365 for Operations rendszerben
[![Költségvetési eszközök](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

A további költségvetés-tervezési eszközök a Dynamics 365 for Operations rendszeren keresztül érhetőek el, és be vannak építve a főkönyvi költségvetésbe.

-   **A munkaerő-költségvetések** – Költségvetési munkaerő tartalmaz részletes költségvetési költségösszetevőnek megtervezése a beosztások, a kompenzációs csoportokat, és így tovább.
-   **Tárgyi eszközök költségvetései** – A tárgyi eszközök adatai alapján ki tudja számolni a tervezett értékcsökkenést és bejegyezhet egyéb, a tárgyi eszközhöz kapcsolódó tervezett tranzakciókat.
-   **Projekt-költségvetések** – A projektmodulban részletes projekt-előrejelzéseket hozhat létre. A projektek előrejelzései részleteket tartalmaznak a tervezett órákról, költségekről, díjakról és cikkekről.
-   ** Igény-előrejelzés ** – tranzakció történelmi adatok alapján, a becsült jövőbeni készlet igény szerint és igény-előrejelzések létrehozása.

További információért arról, hogy hogyan hívhat be tervezési adatokat más modulokból a költségvetési tervekbe lásd: [A költségvetés-tervezés integrációja egyéb modulokkal](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Felhasználói felület és a jelentési funkciók
A Dynamics 365 for Operations a felhasználók költségvetési terveket hozhatnak létre közvetlenül vagy a Dynamics 365 for Operations kliensben (konfigurálható költségvetésiterv-dokumentum lap használatával) vagy az Excel programon keresztül. Az Excel számos további lehetőségeket tartalmaz. Például használhat külső adatokat egy költségvetési terv forrásaként, egyéni számításokat végezhet, és használhat Microsoft kimutatásokat és diagramokat. A nagy része a költségvetés-tervezési folyamat változókat is beállítható. Meghatározhatja például ki a költségvetés tesz, mi a tervezett és a folyamat néz. Annak ellenére, hogy használhatja az Excel programot a költségvetés-tervezéshez, a Dynamics 365 for Operations rendszer megmarad az igazság egyetlen forrásának, és segít a költségvetés-ellenőrzési problémák megelőzésében. Ismétlődő folyamatok ahhoz, hogy a kezdeti adatokat át a költségvetési terv költségvetés-tervezéshez használható. A jelentésekhez a Dynamics 365 for Operations rendszer a szokásos lekérdezési lapok egy készletét biztosítja, amely lehetővé teszi, hogy megtekintse és elemezze a költségvetési adatait. A költségvetési terv adatai hozzáférhetőek a Felügyeleti jelentéskészítőn keresztül, és külön költségvetésiterv-esetek jeleníthetők meg oszlopokként a Felügyeleti jelentéskészítő jelentésében.





