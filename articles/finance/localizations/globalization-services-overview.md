---
title: Dynamics 365 globalizációs szolgáltatások
description: Ez a cikk áttekintést nyújt a Microsoft Dynamics 365 globalizációs szolgáltatásokról.
author: kfend
ms.date: 04/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
ms.openlocfilehash: eebf74ab30a544f6561cf5782148d12b58d9c4b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278232"
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
