---
title: Dynamics 365 globalizációs szolgáltatások
description: Ez a témakör a Microsoft Dynamics 365 globalizációs szolgáltatásairól nyújt áttekintést.
author: JaneA07
manager: AnnBe
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 8c6f3b7fb4dec0dffe55014e9e2d60620dc3b193
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893048"
---
# <a name="dynamics-365-globalization-services"></a>Dynamics 365 globalizációs szolgáltatások

[!include [banner](../includes/banner.md)]

A következő globalizációs szolgáltatások úgy konfigurálhatók, hogy bővítsék a Microsoft Dynamics 365 online szolgáltatásokban meglévő lehetőségeket:

- A **Regulatory Configuration Service (RCS)** lehetővé teszi a különféle elektronikus dokumentumok és jelentések konfigurálást. Az RCS az elektronikus jelentéskészítő (ER) tervező továbbfejlesztett verzióját biztosítja, ahol a konfigurációs adattár önálló szolgáltatás. A további tudnivalókat lásd: [Regulatory Configuration Service](rcs-overview.md).
- Az **elektronikus számlázásban** az átalakítások, a digitális aláírások és a külső webes szolgáltatásokkal való kapcsolatának konfigurálható integrációja található, beleértve a tanúsítvány- és válaszkezelést. További tájékoztatásért lásd: [Elektronikus számlázás](e-invoicing-service-overview.md).
- Az **adószámítás** nagyobb rugalmasságot biztosít a több adókód, az adókód meghatározása, az adószámítás tervezője és a futásidejű motor segítségével, hogy az egész világra kiterjedően megfeleljen az összetett adótörvények alkalmazásának. További információ: [adószámítás](global-tax-calcuation-service-overview.md).

Ezek a globalizációs szolgáltatások gyárilag beépített integrációt biztosítanak a Dynamics 365 online szolgáltatásaival.

| Online szolgáltatás | RCS | Elektronikus számlázás | Áfaszámítás (előzetes verzió) |
|----------------|-----|----------------------|---------------------------|
| Dynamics 365 Finance | Igen | Igen | Igen | 
| Dynamics 365 Supply Chain Management | Igen | Igen | Igen | 
| Dynamics 365 Project Operations | Igen | Igen | Nem alkalmazható | 
| Dynamics 365 Commerce | Igen | Nem alkalmazható | Nem alkalmazható | 

> [!NOTE]
> Az RCS Azure földrajzi helyeinek (földrajzi helyek) elérhetőségi eltérése miatt a szolgáltatás konfigurálása a megfelelő Dynamics 365 online szolgáltatáshoz kiválasztott földrajzi helyen kívülre továbbíthatja az ügyféladatokat. A további tudnivalókat lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/rcs/D365Productavailabilityguide).