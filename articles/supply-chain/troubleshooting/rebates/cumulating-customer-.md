---
title: Az ügyfél-visszatérítések halmozása sikertelen, ha cikkvisszatérítési csoportokat használnak
description: Ha cikk visszatérítési csoportokkal együttes vevői visszatérítési megállapodásokat használ, a program kiszámítja a visszatérítéseket, de az összesítés sikertelen lesz.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760370"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Az ügyfél-visszatérítések halmozása sikertelen, ha cikkvisszatérítési csoportokat használnak

Tudásbáziscikk száma: 4611372

## <a name="symptoms"></a>Tünetek

Ha cikk visszatérítési csoportokkal együttes vevői visszatérítési megállapodásokat (*mennyiség* típusú) használ, a program kiszámítja a visszatérítéseket, de az összesítés sikertelen lesz.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. A cikkcsoportok csak olyan cikkeket csoportosítnak, amelyekre azonos küszöbérték-feltétel vonatkozik. A visszatérítési feltétel (küszöbérték) az egyes cikkek összegével szemben van beállítva, nem pedig a cikkcsoporton belül bármelyik cikk összesített összegével szemben.
