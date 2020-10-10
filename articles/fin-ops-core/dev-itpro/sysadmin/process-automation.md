---
title: Folyamatok automatizálása
description: Ez a témakör részletesen bemutatja, hogy hogyan lehet a folyamatok automatizálásával egyszerű ütemezést végezni a kötegelt kiszolgálón futtatott folyamatok között.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 08/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: afbef26cb7b37bafb34f12cc20a88fb4aea9f343
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885251"
---
# <a name="process-automation"></a>Folyamatok automatizálása

[!include[banner](../includes/banner.md)]

A folyamatok automatizálásával egyszerű ütemezést lehet végezni a kötegelt kiszolgálón futtatott folyamatok között. Az ütemezett munka frissített naptár nézete lehetővé teszi a végfelhasználók számára, hogy megtekintsék és végrehajtsák az ütemezett és befejezett munkát.

## <a name="administration"></a>Adminisztráció

A rendszer a **Beállítás** menü Rendszeradminisztráció moduljában található összes folyamatautomatizálás központi felügyeleti lapja. Ez a lap felsorolja a rendszerben beállított összes automatizált folyamatot (sorozatot). Ez lehetővé teszi az új folyamatautomatizálások közvetlen hozzáadását ezen a lapon. Ha be van állítva a sorozat, akkor az egyes sorozatok ebből a listából kezelhetők. Választhatja, hogy a teljes sorozatot szerkeszti, törli, egy lista nézetben megtekinti az összes előfordulását, vagy letiltja a sorozatot, ha szüneteltetni szeretné az ütemezett munkát egy adott időszakra. 

A szolgáltatáskezelésben letiltott folyamatok nem jelennek meg, ha a szolgáltatás le van tiltva. Ezenkívül a folyamatautomatizálás ütemezési motorja nem fogja ütemezni a letiltott szolgáltatások eseteit vagy a háttérműveleteit. A funkció újbóli engedélyezése esetén a múltbeli ütemezési események vagy háttérfolyamatok azonnal lefutnak.

## <a name="calendar-view"></a>Naptár nézet

A folyamatok automatizálásának egyik kulcselőnye az a képessége, hogy az ütemezett munka egyszerű naptári nézetben látható legyen.  Ez a nézet lehetővé teszi, hogy egyszerre egy heti munkát jelenítsen meg. Ez a nézet a **Folyamatautomatizálás** lap jobb oldalán jelenik meg. A program kitölti a kiválasztott sorozathoz ütemezett munkát. 

[![Folyamatautomatizálási naptár](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Előfordulás módosításai

Minden előfordulás módosítható anélkül, hogy hatással lenne az azt létrehozó sorozatok által meghatározott egyéb előfordulásokra. Az ütemezett munka előfordulásai szerkeszthetők a naptár nézetből a **Nézet/Szerkesztés** gombra kattintva, majd az **Előfordulás** lehetőséget választva. Ez az oldal lehetővé teszi a sorozat beállítási varázslója által eredetileg megjelenített összes beállítás elérését, és lehetőséget nyújt arra, hogy egyszeri módosítást hajtson végre a kiválasztott előforduláshoz. Az ütemezett munka előfordulását a naptár nézetből a **Letiltás** gomb választásával ki is lehet kapcsolni.

## <a name="developer-documentation"></a>Fejlesztői dokumentáció

A folyamat-automatizálási keretrendszer lehetővé teszi a fejlesztők számára a folyamatok automatizálási keretrendszerének kiterjesztését. A [Folyamatautomatizálási keretrendszer](../process-automation/process-automation-framework.md) dokumentáció tájékoztatást ad arról, hogy hogyan lehet egyéni folyamatokat létrehozni, amelyeket a kötegelt kiszolgálón kell futtatni a folyamatautomatizálási varázslóval ütemezve, és a naptár nézetben automatikusan megjelennek.
