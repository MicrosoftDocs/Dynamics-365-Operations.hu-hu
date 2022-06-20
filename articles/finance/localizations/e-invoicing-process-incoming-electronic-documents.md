---
title: Bejövő elektronikus dokumentumok feldolgozása
description: Ez a cikk áttekintést nyújt a bejövő elektronikus dokumentumok feldolgozásával kapcsolatos adatokról.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: dec4c16c8ba9f0ba55f30f3944eff172cf9db724
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910008"
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
