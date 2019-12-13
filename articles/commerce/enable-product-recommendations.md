---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770139"
---
# <a name="enable-product-recommendations"></a>Termékajánlatok engedélyezése

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Javaslatok előzetes ellenőrzése
Az engedélyezés előtt fekhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a F&O-ügyfelek számára támogatott, akik 10.0.6-os builddel rendelkeznek, és tárhelyüket BDL használatával áttelepítették. 

Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak. Ha további tájékoztatást szeretne erről a beállítási folyamatról, kattintson [ide.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Termékjavaslatok bekapcsolása

A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.

1. Válassza a **Retail** &gt; **Termékjavaslatok** &gt; **Ajánlási paraméterek** elemet.
1. A kiskereskedelmi megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.
1. Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.

![termékjavaslatok engedélyezése](./media/enableproductrecommendations.png)

> [!NOTE]
> Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát. A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 for Commerce szolgáltatásban lehet megtekinteni.

## <a name="configure-recommendation-list-parameters"></a>A javaslati lista paramétereinek konfigurálása
Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz. Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának. Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.

## <a name="show-recommendations-on-pos-devices"></a>Javaslatok megjelenítése pénztáreszközökön
Miután engedélyezte a javaslatokat a háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel. Ha további tájékoztatást szeretne erről a folyamatról, lépjen [ide.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Termékjavaslat-listák hozzáadása az oldalakhoz](add-reco-list-to-page.md)

[Ajánlások panel hozzáadása a pénztáreszközökhöz](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


