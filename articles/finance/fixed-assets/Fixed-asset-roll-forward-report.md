---
title: Jelentés a tárgyi eszköz meghosszabbításáról
description: Ez a cikk bemutatja a Tárgyi eszközök továbbgörgetése jelentés használatát.
author: moaamer
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a4d423b149957e624269231aede510190f0c14c7
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068780"
---
# <a name="fixed-assets-roll-forward-report"></a>Jelentés a tárgyi eszköz meghosszabbításáról

[!include [banner](../includes/banner.md)]

A **Tárgyi eszköz meghosszabbítása** jelentés egyszerűen áttekinthető a Microsoft Excel-formátumban részletes tárgyieszköz-adatokat szolgáltat az időszakzáráshoz, pénzügyi kimutatásokhoz és adóbevalláshoz. A jelentés kezdő és záró egyenleget tartalmaz a tárgyi eszközökhöz az időszak értékelési mozgásaival, valamint az adott időszakban történt új tárgyieszköz-beszerzésekkel és az értékesítésekekkel együtt. Az adatok az egyes tárgyi eszközökre vonatkoznak, és az értékek a tárgyieszköz-csoportok és a jogi személy esetében is összegzésre kerülnek.

A **Tárgyi eszköz meghosszabbítása** jelentés az Elektronikus jelentési (ER) keretrendszert használja. A jelentés futtatása előtt a tárgyi eszközök modelljét és tárgyi eszközök meghosszabbításának konfigurációit importálni kell a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból. További utasításokért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

Ez a jelentés a Microsoft Dynamics 365 Pénzügy, Enterprise kiadás 7.3-as kiadásában vagy a Microsoft Dynamics 365 Pénzügy, Enterprise kiadás gyorsjavításaként érhető el (2017. július). Három gyorsjavítást kell alkalmazni a 2017. júliusi kiadást futtató környezetekben:

- **KB 4041754:** Az elektronikus jelentési (ER) konfiguráció nem tölthető le az LCS-ből, mivel nem alkalmazhat az aktuális alkalmazásverzióra a platformfrissítő csomag telepítése után
- **KB 4056107:** elektronikus jelentés (GER) 5-ös összegző frissítés
- **KB 4056353:** a Tárgyi eszközök kimutatása és Jegyzetek jelentések nem felelnek meg a GAAP és az IFRS követelményeinek

Az alábbi táblázat bemutatja a jelentésben rendelkezésre álló mezőket.


|                    Mező                    |                                                                                                                                Leírás                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Egyenleg: Nyitó              |                                                                                           A tárgyi eszköz nettó könyv szerinti értéke a „kezdő” dátumon számítva, amely a jelentésben szerepel.                                                                                           |
|              Egyenleg: Záró              |                                                                                            A tárgyi eszköz nettó könyv szerinti értéke a „záró” dátumon számítva, amely a jelentésben szerepel.                                                                                            |
|         Beszerzések: Nyitó érték         |                                                 Az összes tranzakció összege a <strong>Beszerzés</strong> és <strong>Beszerzés helyesbítése</strong> típusokból a jelentésben megadott „kezdő” dátumig.                                                  |
|      Beszerzések: Időszaki beszerzések      |                                                 Az összes tranzakció összege a <strong>Beszerzés</strong> és <strong>Beszerzés helyesbítése</strong> típusokból, amelyek feladására a jelentés dátumtartományában került sor.                                                  |
|       Beszerzések: Időszaki kivezetések        |                                                                        Az összes beszerzés-sztornírozás összege, amelyeknél kivezetési tranzakcióra került sor a jelentés dátumtartományában.                                                                        |
|         Beszerzések: Záró érték         |                                                  Az összes tranzakció összege a <strong>Beszerzés</strong> és <strong>Beszerzés helyesbítése</strong> típusokból a jelentésben megadott „záró” dátumig.                                                   |
|        Értékcsökkenések: Nyitó érték         | Az összes tranzakció összege az <strong>Értékcsökkenés</strong>, <strong>Értékcsökkenés helyesbítése</strong>, <strong>Különleges értékcsökkenési keret</strong> és <strong>Rendkívüli értékcsökkenés</strong> típusokból a jelentésben megadott „kezdő” dátumig. |
|     Értékcsökkenések: Időszaki értékcsökkenések     |                         Az összes tranzakció összege az <strong>Értékcsökkenés</strong>, <strong>Értékcsökkenés helyesbítése</strong> és <strong>Rendkívüli értékcsökkenés</strong> típusokból, amelyek feladására a jelentés dátumtartományában került sor.                          |
| Értékcsökkenések: Időszaki különleges értékcsökkenések |                                                              Az összes tranzakció összege a <strong>Különleges értékcsökkenési keret</strong> típusból, amelyek feladására a jelentés dátumtartományában került sor.                                                               |
|       Értékcsökkenések: Időszaki kivezetések       |                                                                       Az összes értékcsökkenés-sztornírozás összege, amelyeknél kivezetési tranzakcióra került sor a jelentés dátumtartományában.                                                                        |
|        Értékcsökkenések: Záró érték         |  Az összes tranzakció összege az <strong>Értékcsökkenés</strong>, <strong>Értékcsökkenés helyesbítése</strong>, <strong>Különleges értékcsökkenési keret</strong> és <strong>Rendkívüli értékcsökkenés</strong> típusokból a jelentésben megadott „záró” dátumig.  |
|    Felértékelések/leértékelések: Nyitó érték     |                              Az összes tranzakció összege a <strong>Felértékelési helyesbítés</strong>, <strong>Leértékelési helyesbítés</strong> és <strong>Átértékelés</strong> típusokból a jelentésben megadott „kezdő” dátumig.                               |
|   Felértékelések/leértékelések: Időszaki felértékelések   |                                                                    Az összes tranzakció összege a <strong>Felértékelési helyesbítés</strong> típusból, amelyek feladására a jelentés dátumtartományában került sor.                                                                    |
|  Felértékelések/leértékelések: Időszaki leértékelések  |                                                                   Az összes tranzakció összege a <strong>Leértékelési helyesbítés</strong> típusból, amelyek feladására a jelentés dátumtartományában került sor.                                                                   |
| Felértékelések/leértékelések: Időszaki átértékelések  |                                                                        Az összes tranzakció összege az <strong>Átértékelés</strong> típusból, amelyek feladására a jelentés dátumtartományában került sor.                                                                        |
|   Felértékelések/leértékelések: Időszaki kivezetések   |                                                           Az összes felértékelés-, leértékelés- és átértékelés-sztornírozás összege, amelyeknél kivezetési tranzakcióra került sor a jelentés dátumtartományában.                                                           |
|    Felértékelések/leértékelések: Záró érték     |                               Az összes tranzakció összege a <strong>Felértékelési helyesbítés</strong>, <strong>Leértékelési helyesbítés</strong> és <strong>Átértékelés</strong> típusokból a jelentésben megadott „záró” dátumig.                                |
|          Kivezetések: Kivezetés dátuma           |                                                                                                                A tárgyieszköz-könyv kivezetésének dátuma.                                                                                                                |
|    Kivezetések: Kivezetéskori nettó könyv szerinti érték    |                                                                                                    A tárgyi eszköz nettó könyv szerinti értéke a kivezetés időpontjában.                                                                                                    |
|            Kivezetések:-Értékesítési érték            |                                                                                               A kivezetési-értékesítési tranzakción átesett tárgyieszköz-könyv értékesítési értéke.                                                                                                |
|           Kivezetés: Maradványérték            |                                                                                               A kivezetési-selejtezési tranzakción átesett tárgyieszköz-könyv maradványértéke.                                                                                               |
|           Kivezetések: Nyereség/veszteség            |                                                                                 A nyereség vagy veszteség a tárgyieszköz-könyvön végrehajtott kivezetési tranzakció részeként kalkulált értéke.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

