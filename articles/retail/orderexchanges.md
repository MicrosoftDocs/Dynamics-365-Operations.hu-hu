---
title: "Csere konfigurálása és feldolgozása visszárurendelésen"
description: "Ez a témakör a cserék visszáru esetén való konfigurálását részletezi a Microsoft Dynamics 365 for Retail szolgáltatásban."
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3331b984693c58c6ee8c49b98ed7d3a8df5b79ff
ms.openlocfilehash: 45b628376a483d3d639e5c018dd93570ed8ce7af
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Csere konfigurálása és feldolgozása visszárurendelésen

[!include [banner](includes/banner.md)]

A Microsoft Dynamics 365 for Retail korábbi verzióiban a vevő rendelésekre vonatkozó visszárukat a Kiskereskedelmi központban található visszárurendelési dokumentummal dolgozták fel. Azonban a visszárurendelési dokumentumot csak visszaküldött termékek feldolgozására lehet használni. A visszaküldött termékeket a visszárurendelési sorokban negatív mennyiséggel jelölik. Az értékesítéseket ezzel szemben pozitív mennyiséggel jelölik. A visszárurendelési dokumentum azonban nem támogat pozitív mennyiségeket. Ez a korlátozás azt jelenti, hogy a Retail korábbi verziói nem támogatták az olyan forgatókönyveket, ahol a termékek cseréjét a visszárurendelési dokumentum segítségével végezték.

Azonban a funkció hozzáadásra került azokhoz a támogatási forgatókönyvekhez, ahol a cseréket visszárurendeléseken végzik. A Retail most az ilyen típusú tranzakciók feldolgozásához a visszárurendelés dokumentum helyett az értékesítési rendelési dokumentumot használja.

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a>A Retail konfigurálása a visszárurendeléseken történő cserék támogatására

Kövesse az alábbi lépéseket, ha szeretné a rendszert úgy konfigurálni, hogy támogassa a visszárurendeléseken történő cseréket.

1. Lépjen a **Kiskereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** menüpontra. A **Vevői rendelések** gyorslapon állítsa a **Visszárurendelések feldolgozása értékesítési rendelésként** beállítást **Igen** értékre.
2. Futtassa a **Globális konfigurációelosztási ütemezés** feladatot (**1110**).

## <a name="make-an-exchange"></a>Csere elvégzése

Miután konfigurálta a rendszert az előző lépésben leírtak szerint, a pénztár (POS) felhasználó a visszáru feldolgozására továbbra is értékesítési rendelést vagy értékesítési számlát választ majd, ahogy a Retail korábbi verzióiban is. Azonban miután a visszárucikkeket a kosárhoz adta, a felhasználó új értékesítési sorokat is adhat a kosárhoz.

A felhasználónak ezekhez az új értékesítési sorokhoz meg kell határoznia a vevői rendelési sorok feldolgozásához szükséges összes attribútumot. Az attribútumok között szerepel a szállítás módja és a teljesítési hely is. A tranzakcióra vonatkozóan esedékes fizetés a visszárurendelési sorok és az értékesítési rendelési sorok nettó összege lesz. Amikor a tranzakció kifizetése megtörténik, a visszárurendelés értékesítési rendelési dokumentumként kerül feladásra a Kiskereskedelmi központban, a rendszer pedig azonnal számlázza a visszárusorokat.

Annak érdekében, hogy a kosár különböző összegei kellően átláthatóak legyenek, három új összegmező található a kosárban. A képernyőtervező segítségével láthatóvá teheti ezeket az új mezőket a pénztár felhasználói felületén (UI).

- **Alkalmazott letét** – A letét összege, amelyet a rendszer a tranzakcióra alkalmaz, amikor a felhasználó vevői rendelés felvételét végzi. Ha nincs letét-felülbírálat, és 10 százalékos letét van beállítva, akkor a mezőben található összeg a vevői rendelés teljes összegének 90 százalékát jeleníti meg.
- **Végrehajtott összeg** – Az olyan sorok teljes összege, ahol a szállítási mód **Végrehajtás** állapotú volt, amikor a vevői rendelést létrehozták vagy szerkesztették, vagy a vevői rendelés cseréje során. A mezőben található összeg tartalmazza az adókat és díjakat.
- **Visszáru összege** – Az olyan sorok teljes összege, amelyek negatív mennyiségekkel rendelkeznek a vevői rendelés cseréje során. A mezőben található összeg tartalmazza az adókat és díjakat.

