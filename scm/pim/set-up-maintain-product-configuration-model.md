---
title: "Termékkonfigurációs modell beállítása"
description: "Ez a cikk bemutatja a termékkonfigurációs modell létrehozásának és beállításának lépéseit."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: e7138dcc15cb8e16ad5cee83b40ba72555d89e6a
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-a-product-configuration-model"></a>Termékkonfigurációs modell beállítása

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja a termékkonfigurációs modell létrehozásának és beállításának lépéseit.

| Feladat                                                        | Leírás                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alaptermék létrehozása.                                    | Hozzon létre egy alapterméket az **Alaptermék** listából. Adja ki az alapterméket az összes érintett vállalat számára. Egy olyan alaptermék esetében, amely egy termékkonfigurációs modell változataként vagy alapösszetevőként használatos, válassza ki a **Megszorításon alapuló konfiguráció** lehetőséget konfigurációs technológiaként, és a konfigurációs dimenziót csak a termékdimenzió-csoporthoz kell kiválasztani. |
| Hozzon létre összetevőket.                                          | Összetevők létrehozása az **Összetevők** oldalon. Az összetevők a termékkonfigurációs modell építőkövei, és több termékkonfigurációs modellhez is felhasználhatók.                                                                                                                                                                                                                      |
| Attribútumtípusok létrehozása.                                     | Attribútumtípusok létrehozása az **Attribútumtípusok** oldalon. Az attribútumtípusok határozzák meg a termékkonfigurációs modellben az összes attribútumhoz használt adatok típusát. A rögzített listájú **Logikai**, **Szöveg** attribútumok és az **Egész**, típusok választékával rendelkező attribútumok felsorolják azokat az értékeket, amelyek elérhetők egy termékkonfigurációs modell alapján egy termékváltozat konfigurálásakor.       |
| Termékkonfigurációs modell létrehozása                       | Termékkonfigurációs modell létrehozása az **Új termékkonfigurációs modell** oldalon.                                                                                                                                                                                                                                                                                                              |
| Attribútumok hozzáadása egy termékkonfigurálási modellhez.            | Hozzon létre egy attribútumot az **Attribútumok** gyorslapon, a **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon. Az attribútumok ismertetik a termékkonfigurációs modell jellemzőit.                                                                                                                                                                                                       |
| Megszorítások hozzáadása egy termékkonfigurálási modellhez.           | Hozzon létre megszorításokat a **Megszorítások** gyorslapon, a **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon. A megszorítások korlátozások, melyeknek a termékkonfiguráció meg kell, hogy feleljen. A megszorítások kifejezést vagy táblázatot korlátozhatnak.                                                                                                                                 |
| Alösszetevők hozzáadása termékkonfigurációs modellhez.         | Hozzon létre egy alösszetevőket az **Alösszetevők** gyorslapon, a **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon. Az alösszetevők az összetevőkhöz kapcsolódnak, és az alösszetevőt megjelenítő cikkekhez vannak csatolva.                                                                                                                                                                       |
| Felhasználói követelmények hozzáadása egy termékkonfigurációs modellhez.     | A felhasználói követelmények hasonlóak alösszetevőkhöz, de nem hivatkoznak egy cikkre. A felhasználói igényekre úgy tekinthetünk, mint egy látszólagos AJ-re. Bármely anyagjegyzéksor vagy útvonalművelet, amely közvetlenül a felhasználói követelmény alá kerül, a fölérendelt összetevőbe csukódik össze.                                                                                                                       |
| AJ-sorok hozzáadása egy termékkonfigurálási modellhez.             | Hozzon létre AJ-sorokat az **AJ-sorok** gyorslapon, a **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon. Az AJ-sorok egy termékváltozat létrehozásához szükséges részt képviselnek.                                                                                                                                                                                                 |
| Útvonalműveletek hozzáadása termékkonfigurációs modellhez.      | Hozzon létre útvonalműveleteket az **Útvonalműveletek** gyorslapon, a **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon. Az útvonalműveletek egy termékváltozat létrehozásakor végrehajtott lépések sorozatában egy lépést képviselnek.                                                                                                                                                    |
| Aktív verzió létrehozása egy termékkonfigurációs modellhez. | A termékkonfigurációs modell egy aktív verziójának létrehozása a **Verziók** lapon. A verzió egy termékkonfigurációs modell és egy alaptermék közötti kapcsolat. Az aktív verzióval rendelkező termékkonfigurációs modell konfigurálható egy értékesítési rendelésből, árajánlatból, beszerzési rendelésből vagy termelési rendelésből.                                                               |
| Termékkonfigurációs modell tesztelése.                         | A termékkonfigurációs modell tesztelése a **Megszorításon alapuló termékkonfigurációs modell részletei** lapról vagy a **Termékkonfigurációs modellek listája** oldalról. A termékkonfigurációs modell tesztelése szimulálja a termékmodell konfigurálási folyamatát, amely a rendeléskezelés során zajlik.                                                                                                |
| Termékkonfigurációs modell sablonjának létrehozása.                | Termékkonfigurációs modell sablonjának létrehozása a **Konfigurációs sablonok** oldalon. Konfigurációs sablon attribútumértékeket tartalmaz a termékkonfigurációs modellben. Válassza ki az attribútumértékeket a **Sor konfigurálása** oldalon. A termékmodell konfigurálása során kiválaszthatja a betölteni kívánt termékmodell-konfiguráció sablont.                                                   |
| Cikk konfigurálása.                                          | A termékkonfigurációs modellek konfigurálhatók egy értékesítési rendelésből, árajánlatból, beszerzési rendelésből vagy termelési rendelésből.                                                                                                                                                                                                                                                                           |






