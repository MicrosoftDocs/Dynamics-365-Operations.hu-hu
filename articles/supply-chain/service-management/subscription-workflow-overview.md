---
title: "Előfizetési munkafolyamat áttekintése"
description: "Ez a témakör az előfizetési munkafolyamatról nyújt áttekintést."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b4872c0753b54bdddf2c7778a13819726eea4a90
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="subscription-workflow-overview"></a>Előfizetési munkafolyamat áttekintése 

[!include [banner](../includes/banner.md)]


Ön egy világítási cég előfizetési felelőse, a vállalat pedig világosítóberendezések előfizetéses karbantartását kínálja. Egy ügyfél a vállalatához fordul, hogy éves előfizetést vásároljon világosítóberendezés karbantartására.

## <a name="setting-up-subscriptions"></a>Előfizetések beállítása

Előfizetés beállításához először hozzon létre egy előfizetési csoportot az új szolgáltatási szerződéshez vagy ellenőrzze egy előfizetési csoport meglétét. Ha létezik egy előfizetési csoport, be kell állítani, hogy évente számlázzon a vevőnek, és elhatárolja az értékesítési bevétel minden hónapban az év során. Az előfizetések beállításának módjáról bővebben lásd: [Előfizetési csoportok beállítása](set-up-subscription-groups.md).

Az előfizetési csoport létrehozása után létrehozhatja az előfizetést. Szolgáltatási előfizetések létrehozásával kapcsolatos további tudnivalókat lásd: [Szolgáltatási előfizetés létrehozása előfizetési csoportból](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Előfizetési tranzakciók létrehozása és módosítása

Miután beállította az előfizetést, létrehozza az első számlázási időszak előfizetési díjtranzakcióját, ami egy év. A tranzakció típusa **Normál**. Ezért csak ott hozhat létre előfizetési tranzakciókat, ahol a kezdő dátum és a záró dátum megfelel a korábban létrehozott időszakoknak az **Időszaktípusok** képernyőn. Díjtranzakciókkal kapcsolatos további tudnivalókat lásd: [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md).

Miután beállította az előfizetést a vevőhöz, eszébe jut, hogy a tárgyalások során a szolgáltatás ajánlatokból 10 százalékos engedményt adott. Emiatt az Ön által létrehozott tranzakciós díj árát csökkentenie kell.

Aznap később a vevő kapcsolattartója felhívja azzal, hogy bár továbbra is akarja a világosítóberendezésekre a szolgáltatási szerződést, azt tervezi, hogy egy új világosítóberendezést vezet be az adott évben később. Ezért csak 2013 októberéig kér karbantartást. A vevő előfizetési hónapok számának csökkentéséhez az új előfizetési díj tranzakciót hoz létre a **Csökkentési napok** típussal. A napok csökkentéséről a további tudnivalókat lásd: [Előfizetési díjak napjainak csökkentése](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Előfizetési tranzakciók számlázása és könyvelése

Ezzel befejezte az előfizetés beállítását, és készen áll a számlázásra a vevő számára. Az előfizetések számlázásának módjáról bővebben lásd: [Előfizetési tranzakciók számlázása](invoice-subscription-transactions.md).

Két nappal később a vevő telefonál, hogy az előfizetés számlázandó USAb dollárban, nem euróban. Emiatt ön jóváírást hoz létre, és a megfelelő pénznemben is létrehoz egy új előfizetési tranzakciót. Az előfizetési tranzakciók jóváírásának módjáról bővebben lásd: [Előfizetési tranzakciók jóváírása](credit-subscription-transactions.md).

A vevő előfizetéseiből minden hónap végén egy havi bevétel lekönyvelhető az eredményszámlára és a folyamatban lévő munka számlájára. Az előfizetési bevételek könyvelésével kapcsolatos további tudnivalók: [Előfizetési bevétel könyvelése](accrue-subscription-revenue.md).

  



