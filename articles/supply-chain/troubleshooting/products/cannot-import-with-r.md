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
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764692"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>A Kiadott termékek V2 entitás használatával nem lehet cikket importálni

Tudásbáziscikk száma: 4611825

## <a name="symptoms"></a>Tünetek

Amikor a *Kiadott termékek V2* entitás használatával próbál importálni egy cikket, a következő példához hasonló hibaüzenet jelenik meg:

> Nem hozható létre rekord a Cikkek – nyomon követési dimenziócsoportok (EcoResTrackingDimensionGroupItem) alatt. Cikkszám: 2040663, Köteg. A rekord már létezik.

## <a name="resolution"></a>Felbontás

Új kiadott termékek importálásához a *Kiadott termék létrehozása V2* entitást kell használnia a *Kiadott termékek V2* entitás helyett.
