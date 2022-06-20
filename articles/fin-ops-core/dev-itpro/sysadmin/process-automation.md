---
title: Folyamatok automatizálása
description: Ez a cikk részletesen bemutatja, hogy hogyan teszi lehetővé a folyamatautomatizálás a kötegkiszolgáló által futtatott folyamatok egyszerű ütemezését.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: f13392fd6610735f8c539d42b62cf71cece71fba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898609"
---
# <a name="process-automation"></a>Folyamatok automatizálása

[!include[banner](../includes/banner.md)]

A folyamatok automatizálásával egyszerű ütemezést lehet végezni a kötegelt kiszolgálón futtatott folyamatok között. Az ütemezett munka frissített naptár nézete lehetővé teszi a végfelhasználók számára, hogy megtekintsék és végrehajtsák az ütemezett és befejezett munkát.

## <a name="administration"></a>Adminisztráció

A rendszer a **Beállítás** menü Rendszeradminisztráció moduljában található összes folyamatautomatizálás központi felügyeleti lapja. Ez a lap felsorolja a rendszerben beállított összes automatizált folyamatot (sorozatot). Ez lehetővé teszi az új folyamatautomatizálások közvetlen hozzáadását ezen a lapon. Ha be van állítva a sorozat, akkor az egyes sorozatok ebből a listából kezelhetők. Választhatja, hogy a teljes sorozatot szerkeszti, törli, egy lista nézetben megtekinti az összes előfordulását, vagy letiltja a sorozatot, ha szüneteltetni szeretné az ütemezett munkát egy adott időszakra. 

A szolgáltatáskezelésben letiltott folyamatok nem jelennek meg, ha a szolgáltatás le van tiltva. Ezenkívül a folyamatautomatizálás ütemezési motorja nem fogja ütemezni a letiltott szolgáltatások eseteit vagy a háttérműveleteit. A funkció újbóli engedélyezése esetén a múltbeli ütemezési események vagy háttérfolyamatok azonnal lefutnak. A folyamatautomatizálási ütemezési motor a rendszer kötegelt feladatán, a **Folyamatautomatizálás ciklikus lekérdezési rendszerfeladat** futtatásán alapul. A feladat nem változtatható meg és nem módosítható. 

## <a name="calendar-view"></a>Naptár nézet

A folyamatok automatizálásának egyik kulcselőnye az a képessége, hogy az ütemezett munka egyszerű naptári nézetben látható legyen.  Ez a nézet lehetővé teszi, hogy egyszerre egy heti munkát jelenítsen meg. Ez a nézet a **Folyamatautomatizálás** lap jobb oldalán jelenik meg. A program kitölti a kiválasztott sorozathoz ütemezett munkát. 

[![Folyamatautomatizálási naptár.](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Előfordulás módosításai

Minden előfordulás módosítható anélkül, hogy hatással lenne az azt létrehozó sorozatok által meghatározott egyéb előfordulásokra. Az ütemezett munka előfordulásai szerkeszthetők a naptár nézetből a **Nézet/Szerkesztés** gombra kattintva, majd az **Előfordulás** lehetőséget választva. Ez az oldal lehetővé teszi a sorozat beállítási varázslója által eredetileg megjelenített összes beállítás elérését, és lehetőséget nyújt arra, hogy egyszeri módosítást hajtson végre a kiválasztott előforduláshoz. Az ütemezett munka előfordulását a naptár nézetből a **Letiltás** gomb választásával ki is lehet kapcsolni.

## <a name="developer-documentation"></a>Fejlesztői dokumentáció

A folyamat-automatizálási keretrendszer lehetővé teszi a fejlesztők számára a folyamatok automatizálási keretrendszerének kiterjesztését. A [Folyamatautomatizálási keretrendszer](../process-automation/process-automation-framework.md) dokumentáció tájékoztatást ad arról, hogy hogyan lehet egyéni folyamatokat létrehozni, amelyeket a kötegelt kiszolgálón kell futtatni a folyamatautomatizálási varázslóval ütemezve, és a naptár nézetben automatikusan megjelennek.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
