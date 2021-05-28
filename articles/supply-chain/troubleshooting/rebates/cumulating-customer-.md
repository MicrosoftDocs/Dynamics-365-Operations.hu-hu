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
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026565"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Az ügyfél-visszatérítések halmozása sikertelen, ha cikkvisszatérítési csoportokat használnak

Tudásbáziscikk száma: 4611372

## <a name="symptoms"></a>Tünetek

Ha cikk visszatérítési csoportokkal együttes vevői visszatérítési megállapodásokat (*mennyiség* típusú) használ, a program kiszámítja a visszatérítéseket, de az összesítés sikertelen lesz.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték. A cikkcsoportok csak olyan cikkeket csoportosítnak, amelyekre azonos küszöbérték-feltétel vonatkozik. A visszatérítési feltétel (küszöbérték) az egyes cikkek összegével szemben van beállítva, nem pedig a cikkcsoporton belül bármelyik cikk összesített összegével szemben.
