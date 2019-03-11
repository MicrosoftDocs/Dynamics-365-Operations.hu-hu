---
title: A szolgáltatás tárgyai
description: A szolgáltatási tárgyak a vevő azon eszközei és termékei, amelyhez szolgáltatást lehet elvégezni.
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5641077de84b6702d2c5621edef74783f2f104fd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "353402"
---
# <a name="service-objects"></a>A szolgáltatás tárgyai 

[!include [banner](../includes/banner.md)]

A szolgáltatási tárgyak a vevő azon eszközei és termékei, amelyhez szolgáltatást lehet elvégezni. A nyújtott szolgáltatás típusától függően az objektumok lehetnek tárgyi vagy nem tárgyi jellegűek:

-  A tárgyi jellegű objektumokon – például gépeken vagy épületen – fizikai jellegű szolgáltatási feladatot lehet végezni.

    A materiális szolgáltatási objektum készletcikk is lehet, amelyet a Megjelent termék részletei képernyőn hoz létre. A a cikkhez csatolt készletdimenzió-csoporttól függően létrehozhat egy olyan részletes szolgáltatási objektumot, amely tartalmazza a cikk sorozatszámát. Ez akkor hasznos, ha nyomon kell követnie azt az adott cikket, amelyet a szolgáltatási tárgy jelöl meg.

    Materiális szolgáltatási objektum lehet olyan cikk is, ami nem kapcsolódik közvetlenül a vállalat közvetlen termelési vagy ellátási láncához. Lehet például a szervizrendelésen szereplő javításokhoz használt eszközcsomag lehet egy szolgáltatási tárgy, amely nem szerepel a készletben. Ebben az esetben nem készletcikként regisztrálja azt.

-  A nem tárgyi jellegű objektumok nem fizikai jellegű elemek, például számlák vagy jogi dokumentumok, amelyeken szervizfeladatokat lehet végezni.

## <a name="example-of-an-intangible-service-object"></a>Immateriális szolgáltatási objektumok például

Az A vállalat pénzügyi nyilvántartást kezel több kisebb vállalat számára. Az A vállalat egyik ügyfele a helyi futballcsapat, amely számára A vállalat heti könyvelést végez, valamint évente auditálja a klub könyvelését. A klub könyvelése A szolgáltatás tárgyai képernyőn van beállítva, és a szolgáltatási szerződésben ez van megadva objektumként. Az objektumhoz két szolgáltatásiszerződés-sor tartozik. Az 1. sor a heti könyvelés a sorokhoz rendelt heti időközökkel, a 2. sor pedig az éves audit, amihez egy éves időtartam van hozzárendelve.

## <a name="related-topics"></a>Kapcsolódó témakörök

[Szolgáltatási objektumok létrehozása](create-service-objects.md)

