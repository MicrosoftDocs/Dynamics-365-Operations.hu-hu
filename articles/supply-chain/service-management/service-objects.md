---
title: Szolgáltatási tárgyak áttekintése
description: Ez a témakör a szolgáltatási objektumok használatával kapcsolatban nyújt áttekintést.
author: kamaybac
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9cf5e146bb7eab4df5807c6a55f773bfb31a4c5e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571377"
---
# <a name="service-objects-overview"></a>Szolgáltatási tárgyak áttekintése

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]