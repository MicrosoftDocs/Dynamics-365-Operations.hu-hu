---
title: Gyártható vagy beszerezhető termékek beállítása
description: A termékek több forrásból is származhatnak - előállíthatók (gyárthatók) vagy beszerezhetők (vásárolhatók). Ez a cikk néhány jellegzetes pontot ismertet, amelyeket figyelembe kell venni amikor a termékek többszörös forráshoz való konfigurálását végzi.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2052d72774068b8f1cbfd8e2e2bdb57424a6452c32ace83a6985e91aea88600b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761116"
---
# <a name="set-up-products-that-can-be-produced-or-procured"></a>Gyártható vagy beszerezhető termékek beállítása

[!include [banner](../includes/banner.md)]

A termékek több forrásból is származhatnak - előállíthatók (gyárthatók) vagy beszerezhetők (vásárolhatók). Ez a cikk néhány jellegzetes pontot ismertet, amelyeket figyelembe kell venni amikor a termékek többszörös forráshoz való konfigurálását végzi. 

Többszörös-forrás általában használatos egy beszerzett cikket időnként gyártanak, vagy a cikket, amelyet egy gyártott cikket elsődlegesen volt, hogy a jelenleg elsősorban a beszerzett cikk változásának. A cikk kezdetben gyártott cikként lesz megadva az anyagjegyzék- és útvonal-információk megadásához, valamint a cikkre vonatkozó termelési rendelések alátámasztására. A termelés típusa értékre kell állítani **Anyagjegyzék** (vagy a gyártási folyamat, **Képlet** vagy **Társtermék**).

Elszámolóár használata esetén a cikk-költség rekord kiszámítható a legyártott cikkre vonatkozóan. A szükséges elszámolóárat manuálisan kell bevinni, és aktiválni kell a cikk-költség rekordhoz. A szükséges elszámolóárat manuálisan kell bevinni, és aktiválni kell a cikk-költség rekordhoz. A költségszámítás a speciális Anyagjegyzék vagy útvonal csökkentése érdekében az eltéréseket, időbeli eloszlás szerint, a pénzügyi időszak során a termék a készletek kombinációs jelölő használatával figyelembe kell venni. Ezenkívül egy gyártott cikket az egyik helyen át lehet vinni egy másik helyen. Emiatt a cikk-költség kell manuálisan megadott és a helyet, amelyhez a cikk átkerül aktiválva. Amikor a legyártott cikket magasabb szintű termék összetevőjeként felhasználják, az összetevő költségeit beszerzett cikként kell kezelni attól függetlenül, hogy azok számítással vagy manuális bevitellel álltak elő. Ezen iránymutatás vonatkozik, függetlenül attól, hogy az összetevő költségeit azt, hogy megtörtént kiszámított vagy manuálisan kell megadni. Tehát az anyagjegyzék-számításnak a cikk költségét beszerzett összetevőként kell kezelnie ahelyett, hogy az anyagjegyzék és az útvonal adatai alapján kiszámítaná a költséget. 

A számítást a cikkhez rendelt anyagjegyzék-számítási csoporthoz tartozó **Alábontást leállító** jelző beállításával lehet megakadályozni. Az alapütemezési számításoknál a cikken keresztül megakadályozható az igények alábontása, ha a cikkhez tartozó, (cikkfedezethez) alábontást leállító jelző 0 (nulla) napra van állítva. Az alapütemezés kiszámításában majd kezeli a cikk beszerzett cikként, és nem számításokat további a cikkhez tartozó Anyagjegyzék és útvonal-információkat.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]