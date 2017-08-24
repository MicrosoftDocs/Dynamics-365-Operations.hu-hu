---
title: "Készpénzcímletek konfigurálása a POS számára"
description: "A háttérirodában meghatározható a pénztárosok, értékesítési munkatársak és a vezetők által az üzletben levő POS modulban használandó bankjegyek és érmék készpénzcímlete."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d280a11670b5887ae5ae582cedf30c093b4b5d7c
ms.openlocfilehash: 9abcbb706d7120c6bcd91fc759b33cb518802a5b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="configure-cash-denominations-for-pos"></a>Készpénzcímletek konfigurálása a POS számára

[!include[banner](includes/banner.md)]

A háttérirodában meghatározható a pénztárosok, értékesítési munkatársak és a vezetők által az üzletben levő POS modulban használandó bankjegyek és érmék készpénzcímlete. Az ilyen címletek felhasználhatók a napvégi készpénzszámlálási fizetőeszköz-elszámolások vagy egy gyors értékesítés fizetése során.

## <a name="define-denominations"></a>Címletek meghatározása
A címletek üzletenként állíthatók be a **Beállítás** > **Készpénzelszámolási lehetőség az üzlet tulajdonából** lapon. 

![készpénzcímletek](./media/image1-denomination.png)

Címlet meghatározása:
1. Kattintson az **Új** elemre.
1. Adja meg a típust (érme vagy bankjegy).
1. Adja meg az összeget (érték).

![készpénzcímletek](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>A funkcióprofil konfigurálása
A POS-ben készpénzzel történő fizetés esetén a felhasználó a bankjegycímletek segítségével gyorsan beírhatja a vevő által fizetett összeget. A funkcióprofilban beállíthatja a címlet kétféle megjelenítését a POS rendszerben.

**Nagyobb vagy egyenlő az esedékes összeggel**: alapértelmezés szerint a POS csak azokat az esedékes összegnél nagyobb címleteket jeleníti meg, amelyek lehetővé teszik az egyetlen mozdulattal elvégezhető fizetést. Például, ha az esedékes összeg 7,50 dollár, a POS a következő címleteket jelenítené meg: $10, $20, $50 és $100. A fenti összegek bármelyikének megérintése automatikusan kifizeti az értékesítést ehhez az összeghez. A $1 és $5 címletek nem jelennek meg, mivel ezek az összegek kisebbek az esedékes összegnél.

**Minden címlet**: Jelölje be ezt a lehetőséget, hogy minden címletet megjelenítsen a POS rendszerben, függetlenül az esedékes összeg mértékétől. Ez azt jelenti, hogy a felhasználó az esedékes összeget eléréséhez címletkombinációkat használhat. Például ha az esedékes összeg 25,00 dollár, a felhasználó választhatja a $20 és $5 címletet az értékesítés befejezéséhez.

