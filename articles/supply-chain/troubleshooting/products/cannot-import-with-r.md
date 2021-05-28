---
title: A Kiadott termékek V2 entitás használatával nem lehet cikket importálni
description: A Kiadott termékek V2 entitás használatával nem lehet cikket importálni.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026567"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>A Kiadott termékek V2 entitás használatával nem lehet cikket importálni

Tudásbáziscikk száma: 4611825

## <a name="symptoms"></a>Tünetek

Amikor a *Kiadott termékek V2* entitás használatával próbál importálni egy cikket, a következő példához hasonló hibaüzenet jelenik meg:

> Nem hozható létre rekord a Cikkek – nyomon követési dimenziócsoportok (EcoResTrackingDimensionGroupItem) alatt. Cikkszám: 2040663, Köteg. A rekord már létezik.

## <a name="resolution"></a>Felbontás

Új kiadott termékek importálásához a *Kiadott termék létrehozása V2* entitást kell használnia a *Kiadott termékek V2* entitás helyett.
