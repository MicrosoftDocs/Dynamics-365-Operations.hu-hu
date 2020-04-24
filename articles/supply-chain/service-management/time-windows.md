---
title: Időablakok
description: Időablakok segítségével optimalizálhatja a szervizrendeléssorok ütemezését.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63a166806c2c8ac84cc1d71d6ec84fcb28033feb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206519"
---
# <a name="time-windows"></a>Időablakok  

[!include [banner](../includes/banner.md)]

Időablakok segítségével optimalizálhatja a szervizrendeléssorok ütemezését. Beállíthatja, hogy a rendszer automatikusan létrehozza a szervizrendeléseket. Az időszak által meghatározott feltételek alapján a lehető legtöbb szervizrendeléssort csatlakoztathatja a lehető legkevesebb szervizrendeléshez.

Az időszakok meghatározzák, hogy milyen távol kerülhetnek a szervizrendeléssorok a számított dátumukhoz képest. A kiszámított dátum az a dátum, amikorra a szervizrendeléssor végrehajtását ütemezték. A dátum alapját az intervallum beállítása képezi, továbbá az a szervizidőszak, amelyet meghatározott a **Szervizrendelések létrehozása** lapon. Az időszakok a következő táblázat értékeivel határozhatók meg.

| Metódus | Leírás                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hét   | A szervizrendeléssor dátuma a kiindulási számított dátum hetén belül bármelyik napra áthelyezhető.                                                                                                                                                                                    |
| Hónap  | A szervizrendeléssor dátuma a kiindulási számított dátum hónapján belül bármelyik napra áthelyezhető. Például egy szervizrendeléssor számított dátuma 2017. február 15. A szervizrendeléssor bármelyik hétköznapra ütemezhető 2017. február 1. és 2017. február 28. között. |
| Manuális | Azoknak a napoknak a maximális számát kell meghatároznia, amellyel a szervizrendeléssor a kiindulási számított dátumnál korábbra vagy későbbre ütemezhető.                                                                                                                                                                           |

Ha a szolgáltatásiszerződés-sorra nem határoz meg időszakot, akkor a szerződéssorból származó szervizrendeléssort pontosan azon a napon kell végrehajtani, amelyre eredetileg ütemezték.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Időablakok létrehozása](create-time-windows.md)

