---
title: Kliens kapcsolata megszakad
description: Ez a téma elmagyarázza, hogy mi a teendő, ha az ügyfél nem kapcsolódik a környezethez.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071135"
---
# <a name="client-disconnects"></a>Kliens kapcsolata megszakad


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Környezet részletes adatai** 

A probléma bármely környezetben előfordulhat.
 
**Tünet** 

A vevő kapcsolata megszakad saját környezetével, és nem tudja, ennek mi az oka. A vevőnek a következő hibaüzenetek egyike jelenik meg:

- A kapcsolata megszakadt. A munka folytatásához kattintson a Bezárás gombra.
- Úgy tűnik, hogy megszakadt a hálózati kapcsolat. Az újbóli próbálkozáshoz kattintson az Ismét gombra.

**Piros zászló**

A probléma gyakran előfordul, amikor a felhasználók az implementációs fázisban vannak, termelési és tesztkörnyezetek információit hasonlítják össze, és elfelejtik, hogy munkamenetek között mozognak. Ha a felhasználók ebben a fázisban vannak, akkor nagy valószínűséggel felmerül ez a probléma.

**Kibocsátás** 

**Böngészőtípusok:** Google Chrome, Internet Explorer, és Microsoft Edge

A felhasználók kapcsolata a Microsoft Dynamics 365 Human Resources megoldással megszakad, amikor egyszerre két munkamenet van nyitva ugyanahhoz a felhasználóhoz és ugyanolyan típusú böngészőben. (Például A felhasználó Chrome-ban nézi mind az 1. környezetet, mind a 2. környezetet.) Nem számít, ha a felhasználó különböző böngészőablakokat vagy különböző lapokat nyit meg. Ha azonos felhasználói hitelesítő adatokkal van bejelentkezve az 1. és 2. környezetbe ugyanabban a pillanatban és ugyanolyan típusú böngészővel, a Human Resources alkalmazás az egyik munkamenet kapcsolatát megszakítja.

**Megoldás**

Győződjön meg arról, hogy egyszerre az adott típusú böngészőben csak egy környezetet nyisson meg. A felhasználók több munkamenetet is megnyithatnak ugyanabban a környezetben (azaz egy böngészőben több lapot).

A felhasználóknak, akik egyszerre két környezet között szeretnének mozogni, minden egyes környezetet különböző típusú böngészőben kell megnyitniuk. (Például A felhasználó megnyithatja az 1. környezetet Chrome-ban, és a 2. környezetet Microsoft Edge-ben.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
