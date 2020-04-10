---
title: Termékajánlatok engedélyezése
description: Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak.
author: bebeale
manager: AnnBe
ms.date: 03/19/2020
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
ms.openlocfilehash: d8a579be5df3c5e7718a6fb4720341f3bd01a64c
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154413"
---
# <a name="enable-product-recommendations"></a>Termékajánlatok engedélyezése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet olyan termékjavaslatokat létrehozni, amelyek a Microsoft Dynamics 365 Commerce-felhasználók számára elérhető mesterséges intelligencia gépi tanulás (AI-ML) technológián alapulnak. A termékajánlási listákkal kapcsolatos további tudnivalókat lásd: [Termékajánlások áttekintése](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Javaslatok előzetes ellenőrzése

Az engedélyezés előtt fekhívjuk figyelmét, hogy a termékjavaslatok csak azok számára a Commerce-ügyfelek számára támogatott, akik a tárhelyüket áttelepítették, és az Azure Data Lake Storage (ADLS) felhasználói. 

Az ADLS engedélyezésével kapcsolatos lépéseket lásd [ADLS engedélyezése a Dynamics 365 környezetben](enable-ADLS-environment.md).

Ezenkívül győződjön meg arról, hogy a RetailSale-mértékek engedélyezve vannak. Ha további tájékoztatást szeretne erről a beállítási folyamatról, kattintson [ide.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Termékjavaslatok bekapcsolása

A termékajánlások bekapcsolásához kövesse az alábbi lépéseket.

1. Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási paraméterek** elemet.
1. A megosztott paraméterek listáján válassza az **Ajánlati listák** elemet.
1. Állítsa a **Javaslatok engedélyezése** beállítást **Igen** lehetőségre.

![termékjavaslatok engedélyezése](./media/enableproductrecommendations.png)

> [!NOTE]
> Ez az eljárás elindítja a termékjavaslati listák létrehozásának folyamatát. A listák elérhetővé tételéhez akár több óra szükséges lehet, és a pénztárban (POS) vagy a Dynamics 365 Commerce szolgáltatásban lehet megtekinteni.

## <a name="configure-recommendation-list-parameters"></a>A javaslati lista paramétereinek konfigurálása

Alapértelmezés szerint az AI-ML-alapú termékjavaslati lista javasolt értékeket tartalmaz. Az alapértelmezett javasolt értékek módosíthatók, hogy megfeleljenek az Ön vállalatának. Az alapértelmezett paraméterek módosításával kapcsolatos további tudnivalókat az [AI-ML-alapú termékajánlás eredményeinek kezelése](modify-product-recommendation-results.md) témakörben talál.

## <a name="show-recommendations-on-pos-devices"></a>Javaslatok megjelenítése pénztáreszközökön

Miután engedélyezte a javaslatokat a Commerce háttérirodában, hozzá kell adnia a javaslatok panelt a vezérlő pénztárképernyőhöz az elrendezés eszközzel. A folyamattal kapcsolatos további tudnivalókat lásd: [Ajánlások hozzáadása egy a POS-eszközök tranzakció lapjának vezérléséhez](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Személyre szabott ajánlatok engedélyezése

Ha további tájékoztatást szeretne arról, hogyan lehet személyre szabott ajánlásokat kapni, lásd: [Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md).

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[ADLS engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)

