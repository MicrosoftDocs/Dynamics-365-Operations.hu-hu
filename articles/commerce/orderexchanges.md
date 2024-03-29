---
title: Csere konfigurálása és feldolgozása visszárurendelésen
description: Ez a cikk a cserék visszáru esetén való konfigurálását részletezi a Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845792"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Csere konfigurálása és feldolgozása visszárurendelésen

[!include [banner](includes/banner.md)]

A Dynamics 365 Commerce korábbi verzióiban a vevő rendelésekre vonatkozó visszárukat a Headquarters szolgáltatásban található visszárurendelési dokumentummal dolgozták fel. Azonban a visszárurendelési dokumentumot csak visszaküldött termékek feldolgozására lehet használni. A visszaküldött termékeket a visszárurendelési sorokban negatív mennyiséggel jelölik. Az értékesítéseket ezzel szemben pozitív mennyiséggel jelölik. A visszárurendelési dokumentum azonban nem támogat pozitív mennyiségeket. Ez a korlátozás azt jelenti, hogy az alkalmazás korábbi verziói nem támogatták az olyan forgatókönyveket, ahol a termékek cseréjét a visszárurendelési dokumentum segítségével végezték.

Azonban a funkció hozzáadásra került azokhoz a támogatási forgatókönyvekhez, ahol a cseréket visszárurendeléseken végzik. A Commerce most az ilyen típusú tranzakciók feldolgozásához a visszárurendelés dokumentum helyett az értékesítési rendelési dokumentumot használja.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>A Commerce konfigurálása a visszárurendeléseken történő cserék támogatására

> [!NOTE]
> A Commerce 10.0.20-as és újabb verziójában elérhető egy "Egységes visszaküldés feldolgozási tapasztalat a pénztárban" nevű új funkció. Ha engedélyezi ezt a funkciót, az alábbi beállítási lépések nem szükségesek. **A visszaküldések feldolgozása értékesítési rendelésként** véglegesen konfigurált beállítássá válnak, és ezt nem lehet megváltoztatni.

A következő lépések szerint konfigurálhatja a rendszert a visszárurendelésekkel kapcsolatos adatcsere támogatására (ha nincs engedélyezve az **Egységes visszaküldés feldolgozási tapasztalat a pénztárban** funkció.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** menüpontra. A **Vevői rendelések** gyorslapon állítsa a **Visszárurendelések feldolgozása értékesítési rendelésként** beállítást **Igen** értékre.
2. Futtassa a **Globális konfigurációelosztási ütemezés** feladatot (**1110**).

## <a name="make-an-exchange"></a>Csere elvégzése

Miután konfigurálta a rendszert az előző lépésben leírtak szerint, a pénztár (POS) felhasználó a visszáru feldolgozására továbbra is értékesítési rendelést vagy értékesítési számlát választ majd, ahogy az alkalmazás korábbi verzióiban is. Azonban miután a visszárucikkeket a kosárhoz adta, a felhasználó új értékesítési sorokat is adhat a kosárhoz.

A felhasználónak ezekhez az új értékesítési sorokhoz meg kell határoznia a vevői rendelési sorok feldolgozásához szükséges összes attribútumot. Az attribútumok között szerepel a szállítás módja és a teljesítési hely is. A tranzakcióra vonatkozóan esedékes fizetés a visszárurendelési sorok és az értékesítési rendelési sorok nettó összege lesz. Amikor a tranzakció kifizetése megtörténik, a visszárurendelés értékesítési rendelési dokumentumként kerül feladásra a Headquarters szolgáltatásban, a rendszer pedig azonnal számlázza a visszárusorokat.

Annak érdekében, hogy a kosár különböző összegei kellően átláthatóak legyenek, három új összegmező található a kosárban. A képernyőtervező segítségével láthatóvá teheti ezeket az új mezőket a pénztár felhasználói felületén (UI).

- **Alkalmazott letét** – A letét összege, amelyet a rendszer a tranzakcióra alkalmaz, amikor a felhasználó vevői rendelés felvételét végzi. Ha nincs letét-felülbírálat, és 10 százalékos letét van beállítva, akkor a mezőben található összeg a vevői rendelés teljes összegének 90 százalékát jeleníti meg.
- **Végrehajtott összeg** – Az olyan sorok teljes összege, ahol a szállítási mód **Végrehajtás** állapotú volt, amikor a vevői rendelést létrehozták vagy szerkesztették, vagy a vevői rendelés cseréje során. A mezőben található összeg tartalmazza az adókat és díjakat.
- **Visszáru összege** – Az olyan sorok teljes összege, amelyek negatív mennyiségekkel rendelkeznek a vevői rendelés cseréje során. A mezőben található összeg tartalmazza az adókat és díjakat.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
