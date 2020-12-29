---
title: Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával
description: Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea8b5e03282aa21aa9dfa486b1deaced6af4601c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429666"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Cikkek regisztrálása speciális raktározásra engedélyezett cikkre, cikkérkeztetési napló használatával

[!include [banner](../../includes/banner.md)]

Ez az eljárás megmutatja, hogyan regisztrálhat cikkeket a cikkérkeztetési napló segítségével, ha a készletkezelési folyamatban speciális raktárkezelést használ. Ezt általában egy bevételezési adminisztrátor végzi. 

Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Az útmutató elkezdése előtt jóváhagyott beszerzési rendelésre van szüksége nyitott beszerzésirendelés-sorral. A sorban szereplő cikknek raktározottnak kell lennie, és nem használhat termékváltozatokat, és nem lehet nyomon követési dimenziója. A cikket egy raktárkezelési folyamatra képes tárolásidimenzió-csoporthoz kell hozzárendelni. A használt raktár számára engedélyezni kell a raktárkezelési folyamatot és a használt helynek azonosítótáblás szabályozásúnak kell lennie. Ha USMF-et használ, a beszerzési megrendeléshez használhatja a 1001-es vállalati számlát, az 51-es raktárat, és az M9200 számú cikket. 

Jegyezze fel a beszerzési rendelés létrehozásakor a számot, valamint a cikkszámot és a helyet, amelyet a beszerzési rendelési sorhoz használt.


## <a name="create-an-item-arrival-journal-header"></a>Cikkérkeztetési napló fejlécének létrehozása
1. Ugorjon a Cikkérkeztetés pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
    * Az USMF használata esetén beírhatja a „WHS” lehetőséget. Ha más adatokat használ, a kiválasztott naplót az alábbiak szerint kell beállítania: A Kitárolási hely ellenőrzése legyen a Nem beállításon, és a Karanténkezelés legyen a Nem beállításon.  
4. Érték beírása a Szám mezőbe.
5. Érték beírása a Telephely mezőbe.
    * Válassza ki a helyet, amelyet a beszerzési rendelési sorhoz használt. Ez egy alapértelmezett értéket biztosít a napló minden sorához. Ha az 51-es raktárt használta USMF-hez, válassza az 5-ös helyet.  
6. Érték beírása a Raktár mezőbe.
    * Válasszon ki egy érvényes raktárat a kiválasztott helyhez. Ez egy alapértelmezett értéket biztosít a napló minden sorához. Ha az USMF-ben a példaértékeket használja, válassza az 51-et.  
7. Írjon be egy értéket a Hely mezőbe.
    * Válasszon ki egy érvényes helyet a kiválasztott raktárban. A helyhez hozzárendelt helyprofil kell, amelyet az azonosítótábla vezérel. Ez egy alapértelmezett értéket biztosít a napló minden sorához. Ha az USMF-ben a példaértékeket használja, válassza a Bulk-008-et.  
8. Kattintson a jobb gombbal a legördülő lista nyilára az Azonosítótábla mezőben, és válassza a Részletek megtekintése lehetőséget.
9. Kattintson az Új lehetőségre.
10. Érték beírása az Azonosítótábla mezőbe.
    * Jegyezze fel az értéket.  
11. Kattintson a Mentés gombra.
12. Zárja be a lapot.
13. Érték beírása az Azonosítótábla mezőbe.
    * Adja meg az újonnan létrehozott azonosítótábla értékét. Ez egy alapértelmezett értéket biztosít a napló minden sorához.  
14. Kattintson az OK gombra.

## <a name="add-a-line"></a>Sor hozzáadása
1. Kattintson az Új sor hozzáadása lehetőségre.
2. A cikkmezőbe írjon egy értéket.
    * Adja meg a cikkszámot, amelyet a beszerzési rendelés sorban használt.  
3. Adjon meg egy számot a Mennyiség mezőben.
    * Adja meg a regisztrálandó mennyiséget.  
    * A Dátum mező határozza meg, hogy mikor lesz a cikk elérhető mennyisége regisztrálva a készletbe.  
    * Az Adagazonosítót kitölti a rendszer, ha egyedileg azonosítható a megadott adatok alapján. Ellenkező esetben manuálisan kell hozzáadni. Ez a mező kötelező, egy adott forrásbizonylatsorhoz kapcsolja a regisztrációt.  

## <a name="complete-the-registration"></a>Véglegesítse a regisztrációt.
1. Kattintson az Érvényesítés gombra.
    * Ez ellenőrzi, hogy a napló feladásra kész. Ha az ellenőrzés sikertelen, a hibákat helyre kell állítani a napló feladása előtt.  
2. Kattintson az OK gombra.
    * Ha az OK gombra kattintott, ellenőrizze az üzenetet. Egy üzenet látható, amely arról tájékoztat, hogy a napló rendben van.  
3. Kattintson a Feladás lehetőségre.
4. Kattintson az OK gombra.
    * Ha az OK gombra kattintott, ellenőrizze az üzenetsávot. Egy üzenet látható, amely arról tájékoztat, hogy a művelet befejeződött.  
5. Zárja be a lapot.

