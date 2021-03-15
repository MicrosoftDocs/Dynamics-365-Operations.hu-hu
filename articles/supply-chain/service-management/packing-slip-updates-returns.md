---
title: Visszárura vonatkozó csomagjegyzék-frissítés
description: Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c82e43beddb8bae0a56b0894ce484ca7605b42e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006716"
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

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]