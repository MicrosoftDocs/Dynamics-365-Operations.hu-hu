---
title: Nem törölhető a szállítólevél, miután ki lett adva egy rendelésből
description: Ha a WMS-hez engedélyezve vannak a kitárolási és szállítási folyamatok, akkor nem vonhatja vissza a szállítólevelet, miután azt az értékesítési rendelésből kiadta. Ez a lap megoldást kínál.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476605"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Nem lehet törölni a szállítólevelet, miután ki lett adva egy értékesítési rendelésből

## <a name="symptoms"></a>Tünetek

Ha a speciális raktárkezeléshez engedélyezve vannak a kitárolási és szállítási folyamatok, akkor nem vonhatja vissza a szállítólevelet, miután azt az értékesítési rendelésből kiadta.

## <a name="resolution"></a>Megoldás

A WMS-hez engedélyezett cikkek könyvelt szállítólevélének helyesbítéséhez a könyvelést a rakományból kell kiadnia, nem pedig közvetlenül a rendelésből. A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás.  

A raktárkezelési folyamatokon keresztül kitárolt és szállított értékesítési rendelés általában a rakományból vagy a szállítmányból és magából az értékesítési rendelésbizonylatból frissíthető. Ha azonban az értékesítési rendelés bizonylatából frissíti az értékesítési rendelést, a csomagjegyzék sztornírozása még mindig nem végezhető el a rakományból vagy értékesítési rendelésből. Ezért azt javasoljuk, hogy használja a szállítólevél kiadást a rakományból. Ebben az esetben a betöltésből elvégzendő sztornírozás engedélyezve lesz.
