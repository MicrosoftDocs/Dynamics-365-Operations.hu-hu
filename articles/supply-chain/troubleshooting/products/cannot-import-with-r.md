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
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474724"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>A Kiadott termékek V2 entitás használatával nem lehet cikket importálni

Tudásbáziscikk száma: 4611825

## <a name="symptoms"></a>Tünetek

Amikor a *Kiadott termékek V2* entitás használatával próbál importálni egy cikket, a következő példához hasonló hibaüzenet jelenik meg:

> Nem hozható létre rekord a Cikkek – nyomon követési dimenziócsoportok (EcoResTrackingDimensionGroupItem) alatt. Cikkszám: 2040663, Köteg. A rekord már létezik.

## <a name="resolution"></a>Felbontás

Új kiadott termékek importálásához a *Kiadott termék létrehozása V2* entitást kell használnia a *Kiadott termékek V2* entitás helyett.
