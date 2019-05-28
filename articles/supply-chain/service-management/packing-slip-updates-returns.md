---
title: Visszárura vonatkozó csomagjegyzék-frissítés
description: Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aba61e6acf5fb959917da9ddea94c21fe1460d1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552884"
---
# <a name="packing-slip-updates-for-returns"></a>Visszárura vonatkozó csomagjegyzék-frissítés  

[!include [banner](../includes/banner.md)]


Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak. Ahogyan a számlafrissítés folyamata a pénzügyi tranzakció frissítése, úgy a csomagjegyzék-frissítés folyamata a készletrekord fizikai frissítése, ami azt jelenti, hogy az véglegesíti a készlet változásait. Visszaküldés esetén a csomagjegyzék frissítésekor az intézkedési művelethez tartozó lépéseket is végrehajtják.

A csomagjegyzékek frissítése a cikkérkezési naplóban és a visszárurendelésben is elvégezhető.

A szállítólevelek könyvelési folyamata részeként a csomagjegyzék hivatkozási száma a vevő szállítási dokumentumokból is társíthat a rendelési sorokhoz. Ez a társítás nem kötelező, és csak referenciaként szolgál. Nem hoz létre tranzakciós frissítéseket.

Ha nem érkezik meg minden várt visszáru, akkor a csomagjegyzék frissítésekor csak a kapott mennyiséget kell rögzítenie. A fennmaradó mennyiséget hagyja a rendelésben, amíg a visszáruszállítmány meg nem érkezik.

Ha a cikket karanténból küldik vissza a szállítási részleghez, például mert a karantén felügyelője nem tudja, hogy hol tárolja a cikket a készletben, akkor szintén frissíteni kell a megfelelő csomagjegyzéket, hogy a karantén eredményeként meghatározott intézkedési kódot helyesen regisztrálják, és az intézkedést végrehajtsák.

Amikor frissíti egy értékesítési szerződéshez tartozó visszáru csomagjegyzékét, az adott cikkhez kapcsolódó értékesítési szerződés automatikusan frissül, hogy jelezze a mennyiség vagy összeg változását. 

## <a name="see-also"></a>Lásd még

[Visszárura vonatkozó számlafrissítés végrehajtása](perform-invoice-updates-for-returns.md)

  


