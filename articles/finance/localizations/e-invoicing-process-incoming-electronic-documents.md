---
title: Bejövő elektronikus dokumentumok feldolgozása
description: Ez a cikk áttekintést nyújt a bejövő elektronikus dokumentumok feldolgozásával kapcsolatos adatokról.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277301"
---
# <a name="processing-of-incoming-electronic-documents"></a>Bejövő elektronikus dokumentumok feldolgozása

[!include [banner](../includes/banner.md)]

A bejövő elektronikus dokumentumok, például a szállítói elektronikus számlák kétféleképpen importálhatók és feldolgozhatók:

- A fájlokat a rendszer külső csatornákból olvassa be, és közvetlenül a csatlakoztatott alkalmazásnak továbbadja. Itt további átalakításon esnek át, majd az adatbázisba importálják őket.
- A fájlok továbbesnek az előfeldolgozáson az Elektronikus számlázás szolgáltatásban, és ezután továbbadják a csatlakoztatott alkalmazásnak.

Az elektronikus számlázás két csatornát támogat a bejövő dokumentumokhoz, az e-mail és a Microsoft mappához SharePoint.

TWP-beállítási típusok határozzák meg, hogy a dokumentumok továbbadják-e az előfeldolgozást, vagy közvetlenül a csatlakoztatott alkalmazásnak továbbadják őket:

- **Adatcsatorna** – a rendszer közvetlenül át fogja adni a dokumentumot a csatlakoztatott alkalmazásnak.
- **Adatcsatorna feldolgozási prognózissal** – további műveleteket is be lehet állítani, amelyek a dokumentumnak a kapcsolódó alkalmazásba való továbbadása előtt futnak.

A bejövő elektronikus dokumentumok különböző [csatornákon történő feldolgozásának helyzetekkel kapcsolatos tudnivalókat lásd: E-mail csatorna konfigurálása](e-invoicing-configure-email.md)[és Csatorna konfigurálása SharePoint](e-invoicing-configure-sharepoint-channel.md).
