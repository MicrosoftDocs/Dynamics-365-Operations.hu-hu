---
title: Tanúsítvány típusa
description: Ez a témakör a Tanúsítvány típusa entitást írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798393"
---
# <a name="certificate-type"></a>Tanúsítvány típusa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Tanúsítvány típusa entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_hcmcertificatetypeentity

## <a name="description"></a>Leírás

Ez az entitás meghatározza a Human Resources szolgáltatásban beállított szakmai tanúsítványtípusok listáját. Az entitás nem egy jogi személyhez (vállalathoz) kapcsolódik.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Tanúsítványtípus entitásazonosítója**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Írásvédett<br>Szükséges 
Rendszer által előállított | A tanúsítványtípus egyedi elsődleges azonosítója. |
| **Tanúsítvány típusa**<br>mshr_certificatetype<br>*Sztring* | Olvasás/írás<br>Szükséges | A tanúsítványtípus egyedi, felhasználó által olvasható azonosítója. |
| **Leírás**<br>mshr_description<br>*Sztring* | Olvasás/írás<br>Szükséges | Adja meg a tanúsítvány típusának leírását. |
| **Megújítás szükséges**<br>mshr_requirerenewal<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Azt jelzi, hogy kell-e újítást igényelni a tanúsítványhoz. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]