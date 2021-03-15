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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f64718e6a96cacc005644cbf4286e743111c02f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996501"
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]