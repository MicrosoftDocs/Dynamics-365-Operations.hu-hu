---
title: Folyamatok automatizálása
description: Ez a témakör részletesen bemutatja, hogy hogyan lehet a folyamatok automatizálásával egyszerű ütemezést végezni a kötegelt kiszolgálón futtatott folyamatok között.
author: RyanCCarlson2
manager: tonyafehr
ms.date: 06/24/2020
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
ms.openlocfilehash: 2ab4e7510ff98b9fbf0223096b905e9de47f52e1
ms.sourcegitcommit: 1833c1e07a32c8ad41e4a1516e78100ae04a2156
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/26/2020
ms.locfileid: "3508185"
---
# <a name="process-automation"></a>Folyamatok automatizálása

[!include[banner](../includes/banner.md)]

A folyamatok automatizálásával egyszerű ütemezést lehet végezni a kötegelt kiszolgálón futtatott folyamatok között. Az ütemezett munka frissített naptár nézete lehetővé teszi a végfelhasználók számára, hogy megtekintsék és végrehajtsák az ütemezett és befejezett munkát.

## <a name="administration"></a>Adminisztráció

A rendszer a **Beállítás** menü Rendszeradminisztráció moduljában található összes folyamatautomatizálás központi felügyeleti lapja. Ez a lap felsorolja a rendszerben beállított összes automatizált folyamatot (sorozatot). Ez lehetővé teszi az új folyamatautomatizálások közvetlen hozzáadását ezen a lapon. Ha be van állítva a sorozat, akkor az egyes sorozatok ebből a listából kezelhetők. Választhatja, hogy a teljes sorozatot szerkeszti, törli, egy lista nézetben megtekinti az összes előfordulását, vagy letiltja a sorozatot, ha szüneteltetni szeretné az ütemezett munkát egy adott időszakra. 

## <a name="calendar-view"></a>Naptár nézet 
A folyamatok automatizálásának egyik kulcselőnye az a képessége, hogy az ütemezett munka egyszerű naptári nézetben látható legyen.  Ez a nézet lehetővé teszi, hogy egyszerre egy heti munkát jelenítsen meg. Ez a nézet a **Folyamatautomatizálás** lap jobb oldalán jelenik meg. A program kitölti a kiválasztott sorozathoz ütemezett munkát. 

[![Folyamatautomatizálási naptár](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Előfordulás módosításai
Minden előfordulás módosítható anélkül, hogy hatással lenne az azt létrehozó sorozatok által meghatározott egyéb előfordulásokra. Az ütemezett munka előfordulásai szerkeszthetők a naptár nézetből a **Nézet/Szerkesztés** gombra kattintva, majd az **Előfordulás** lehetőséget választva. Ez lehetővé teszi a sorozat beállítási varázslója által eredetileg megjelenített összes beállítás elérését, és lehetőséget nyújt arra, hogy egyszeri módosítást hajtson végre a kiválasztott előforduláshoz. Az ütemezett munka előfordulását a naptár nézetből a **Letiltás** gomb választásával ki is lehet kapcsolni. 

## <a name="developer-documentation"></a>Fejlesztői dokumentáció 
A fejlesztői dokumentáció jelenleg írás alatt áll, hogy lehetővé tegye a fejlesztők számára a folyamatautomatizálási keretrendszer kiterjesztését. Ez a dokumentáció tájékoztatást ad arról, hogy hogyan lehet egyéni folyamatokat létrehozni, amelyeket a kötegelt kiszolgálón kell futtatni a folyamatautomatizálási varázslóval ütemezve, és a naptár nézetben automatikusan megjelennek.