---
title: Vevői fizetési előrejelzések
description: Ez a témakör olyan fizetési előrejelzéseket ismertet, amelyek segítségével jobban megértheti az ügyfél általános fizetési gyakorlatát. Ez a funkció segíthet azonosítani azokat a körülményeket, amelyek a begyűjtési folyamatok az eredeti kezdésnél korábbi megkezdését okozhatják..
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 5d16b42b4538a18ca3dd9d3bac25ed1af1441ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903160"
---
# <a name="customer-payment-predictions"></a>Vevői fizetési előrejelzések

[!include [banner](../includes/banner.md)]

Ez a témakör olyan fizetési előrejelzéseket ismertet, amelyek segítségével jobban megértheti az ügyfél általános fizetési gyakorlatát. Ez a funkció segíthet azonosítani azokat a körülményeket, amelyek a begyűjtések folyamatainak az eredeti kezdésnél korábbi megkezdését okozhatják..

## <a name="overview"></a>Áttekintés

Szervezetek gyakran nehezen jósolják meg, hogy a vevők mikor fizetik ki a számláikat. Az információhiány a következő problémákhoz vezethet:

- Kevésbé pontos pénzforgalmi előrejelzések
- Túl későn elindított gyűjtési folyamatok
- Azoknak a vevőknek kiadott rendelések, akik elmulaszthatják a kifizetést

A vevői kifizetések előrejelzései segítik a szervezeteket annak előrejelzésében, hogy mikor lesz kifizetve a vevői számla. Ezért olyan gyűjtési stratégiákat hozhatnak létre, amelyek növelik annak valószínűségét, hogy időben fizessenek.

## <a name="predictions"></a>Előrejelzések

A kifizetési előrejelzések révén a szervezetek javíthatják az üzleti folyamatokat, és segítik azonosítani azokat a számlákat, amelyeket valószínűleg késve fizetnének ki. A szervezet ezt az információt olyan műveletekhez használhatja, amelyek javítják annak a lehetőségét, hogy időben fizessenek.

A Vevői kifizetési előrejelzések funkció egy gépi tanulási modellt használ, amellyel pontosabban megjósolhatja, hogy a vevő mikor fizet egy kinnlévő számlát. Ez a gépi tanulási modell tartalmazza a múltbeli számlákat, a kifizetéseket és a vevői adatokat.

Minden nyitott számlához a funkció három kifizetési valószínűséget rendel:

- Annak valószínűsége, hogy a kifizetésre időben sor kerül
- Annak valószínűsége, hogy a kifizetésre későn kerül sor
- Annak valószínűsége, hogy a kifizetésre nagyon későn kerül sor

A szolgáltatás a várható kifizetések összesített nézetét is tartalmazza.

[![Kifizetési előrejelzések összesített nézete.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Minden számlához hozzárendeli a rendszer az időben való fizetés valószínűségét. Azoknál a számláknál, amelyeknél az időben való fizetés valószínűsége 50%-nál alacsonyabb, akkor a rendszer a számlát piros körrel jelöli meg, amellyel jelzi, hogy ezekre a számlákra a pénzbehajtó fokozott figyelme szükséges.

[![Kifizetési valószínűségek listája.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

A Vevői kifizetési előrejelzések funkció kontextus szerinti adatokat is tartalmaz az előrejelzés elmagyarázása érdekében. Ezek az adatok a legjelentősebb tényezőket tartalmazzák, amelyek befolyásolják az előrejelzést, a vevővel folytatott üzleti állapotot, valamint a vevő múltbeli fizetési magatartásának részleteit.

A beszedési folyamat számos vállalkozásban reaktív tevékenység. Más szóval a beszedési folyamat addig nem kezdődik, amíg a számlák esedékessé válnak. A vevői kifizetésekkel kapcsolatos előrejelzések segítenek a szervezeteknek proaktívabban kezelhetik a beszedéseket. A programnak már nem kell megvárnia a beszedési folyamat elkezdéséhez, hogy a tranzakció esedékessé váljon. Helyette a fizetési előrejelzések képességgel meghatározhatja, hogy a proaktív beszedések javítják-e az időben történő fizetés valószínűségét.

## <a name="methodology"></a>Módszertan

A múltban általában nehéz mesterséges intelligencia-(AI) megoldást fejleszteni és alkalmazni. A folyamatnak adatszakértők, adott téma szakértői (SME-k) és mérnökök csapatára van szükség, akik idővel dolgoznak egy használható AI-megoldás kialakításán, fejlesztésén, üzembe helyezésén és karbantartásán. A vevői kifizetések előrejelzései megkönnyítik az AI-megoldás Microsoft Dynamics üzembe helyezését és használatát a 365 Pénzügyben. A Microsoft előre csomagolja a Microsoftra épülő AI-megoldásokat AI Builder. Ezért a felhasználók egyetlen kattintással telepíthetik az AI megoldást, hogy kihasználhassák egy intelligens előrejelzés előnyeit. Ha nem elégedett az előrejelzések pontosságával, egy felhasználó (ismét, egyetlen kattintással) AI Builder megadhatja a hosszabbítást, majd kiválaszthatja vagy törli a megfelelő mezőket, amelyek az előrejelzések generálásával használatosak. Ha készen áll a programra, akkor „tanítsa be” a modellt, majd tegye közzé a változtatásokat. A rendszer automatikusan felveszi az újonnan modellmodellt, hogy előrejelzéseket generáljon a Dynamics 365 Pénzügyben.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
