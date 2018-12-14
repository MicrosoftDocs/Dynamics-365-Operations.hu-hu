---
title: A Talent-kliens kapcsolata megszakad
description: "Ez a témakör bemutatja, hogy mi a teendő, ha a vevő kapcsolata megszakad saját környezetével, és nem tudja, ennek mi az oka."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 4f96b986059c179268f8a96ea7e7725831a93524
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="talent-client-disconnects"></a>A Talent-kliens kapcsolata megszakad

[!include [banner](includes/banner.md)]

**Környezet részletes adatai** 

A probléma bármely környezetben előfordulhat.
 
**Tünet** 

A vevő kapcsolata megszakad saját környezetével, és nem tudja, ennek mi az oka. A vevőnek a következő hibaüzenetek egyike jelenik meg:

- A kapcsolata megszakadt. A munka folytatásához kattintson a Bezárás gombra.
- Úgy tűnik, hogy megszakadt a hálózati kapcsolat. Az újbóli próbálkozáshoz kattintson az Ismét gombra.

**Piros zászló**

A probléma gyakran előfordul, amikor a felhasználók az implementációs fázisban vannak, termelési és tesztkörnyezetek információit hasonlítják össze, és elfelejtik, hogy munkamenetek között mozognak. Ha a felhasználók ebben a fázisban vannak, akkor nagy valószínűséggel felmerül ez a probléma.

**Probléma** 

**Böngésző típusok:** Google Chrome, Internet Explorer, és Microsoft Edge

A felhasználók kapcsolata a Microsoft Dynamics 365 for Talent platformmal megszakad, amikor egyszerre két munkamenet van nyitva ugyanahhoz a felhasználóhoz és ugyanolyan típusú böngészőben. (Például A felhasználó Chrome-ban nézi mind az 1. környezetet, mind a 2. környezetet.) Nem számít, ha a felhasználó különböző böngészőablakokat vagy különböző lapokat nyit meg. Ha azonos felhasználói hitelesítő adatokkal van bejelentkezve a felhasználó az 1. és 2. környezetbe ugyanabban a pillanatban és ugyanolyan típusú böngészővel, a Talent az egyik munkamenet kapcsolatát megszakítja.

**Megoldás**

Győződjön meg arról, hogy egyszerre az adott típusú böngészőben csak egy környezetet nyisson meg. A felhasználók több munkamenetet is megnyithatnak ugyanabban a környezetben (azaz egy böngészőben több lapot).

A felhasználóknak, akik egyszerre két környezet között szeretnének mozogni, minden egyes környezetet különböző típusú böngészőben kell megnyitniuk. (Például A felhasználó megnyithatja az 1. környezetet Chrome-ban, és a 2. környezetet Microsoft Edge-ben.)

