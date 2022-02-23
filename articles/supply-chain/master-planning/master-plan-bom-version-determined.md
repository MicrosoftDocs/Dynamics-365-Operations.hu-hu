---
title: Az AJ verziójának meghatározása
description: Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a90a257debe8f24e149ddca1738d8376b2124012
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966980"
---
# <a name="determine-the-bom-version"></a>Az AJ verziójának meghatározása

[!include [banner](../includes/banner.md)]

Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján. 

A helydimenzió mindig ismert és megjelenik az igénytranzakcióban. A következő folyamat használható, hogy meghatározza a használandó anyagjegyzék-verziót:

-   Ha van anyagjegyzék-verzió meghatározva a cikkhez az igény telephelyén, akkor a telephelyfüggő anyagjegyzék verzió kerül használatra.
-   Ha nincs telephelyfüggő anyagjegyzék-verzió meghatározva egy cikkhez az igény telephelyén akkor az általános anyagjegyzék-verzió kerül használatra. Az általános anyagjegyzék nem határozza meg a telephelyet, és több telephelyre is érvényes. Ha van általános anyagjegyzék, akkor használatra kerül.
-   Ha nincs használható általános anyagjegyzék, akkor az igény alábontása ezen a ponton leáll.

Minden érvényes anyagjegyzék-verziónak, legyen az telephelyre jellemző vagy általános verzió, teljesítenie kell a dátumra és a mennyiségre vonatkozó kötelező feltételeket.





