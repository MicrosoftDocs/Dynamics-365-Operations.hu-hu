---
title: "Kiskereskedelmi hierarchiák"
description: "Ez a cikk a Microsoft Dynamics AX kiskereskedelmi hierarchiáit írja le."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2544b299267ec6e21adf5c657c23f545fc66a0b3
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="retail-hierarchies"></a>Kiskereskedelmi hierarchiák

[!include[banner](includes/banner.md)]


Ez a cikk a Microsoft Dynamics AX kiskereskedelmi hierarchiáit írja le.

A kiskereskedelmi csatornáin keresztül értékesített termékek rendszerezéséhez létrehozhatja a termékeket hierarchiáját. Kiskereskedelmi termék hierarchiák segítségével kategóriákba vagy termékek csoportosítása. Ezeket a termékeket, valamint a vevő hűségprogramok létrehozásához használhatja. Kiválaszthatja is termékattribútumok és tulajdonságok hozzárendelése, hozzárendelése egy árképzési szerkezet, a termékek felvétele a termék promóciók, és a termékeket jelentésekhez használja. Létrehozhat egy kategóriahierarchiát a szervezetben lévő összes termék és kategória képviseletére, majd ezt a kategóriahierarchiát több célra használhatja. Másik lehetőségként létrehozhat több kategóriahierarchiát különleges célokra, ilyen például a termékpromóció. Kiskereskedelmi termékhierarchia létrehozásakor hozzá kell rendelnie a kategóriahierarchia típusát a kategóriahierarchia céljának azonosításához. Például egyetlen termék hierarchiák értékcsökkenésével a **Kiskereskedelmi navigációs hierarchia** típus hivatkozott tallózásakor termékek kategóriák szerint online, akár in point of értékesítés (POS).

## <a name="retail-hierarchy-types"></a>A kiskereskedelmi hierarchia képernyői
Az alábbi táblázat felsorolja a választható kategóriahierarchia-típusokat és azok céljait.

| Kategóriahierarchia-típus       | Cél                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kiskereskedelmi termékek hierarchiája      | Válassza ezt a hierarchiatípust a szervezet fő kiskereskedelmi termékhierarchiájának létrehozásához. Ezt a hierarchiatípust árusítási, árképzési és promóciók, jelentések és a szortiment tervezési használható. Csak egy kiskereskedelmi termékek hierarchiájának ezt a hierarchiatípust is hozzárendelhető.                                       |
| Kiegészítő kiskereskedelmi hierarchia | Ez a hierarchia típus használható a létrehozni kívánt kiegészítő kiskereskedelmi kategória hierarchiákhoz. Ha például a forrás, a akkor fürdőruha a promócióban. Emiatt a fürdőruha termékek felvétele külön kategóriahierarchia és alkalmazni lehet különböző termékkategóriákat az Akciós árak. |
| Kiskereskedelmi csatornák navigációs hierarchiája   | Használja ezt a hierarchiatípust csoportosítására és rendszerezésére szolgálnak a termékek kategóriákba úgy, hogy a termékek interneten vagy a POS böngészhetnek.                                                                                                                                                                                       |

Egy kiskereskedelmi kategóriahierarchiát a termékek rendszerezik segítségével állítsa be, és termékattribútumok és a kategória szintjén tulajdonságainak karbantartása. Ezek attribútumok tulajdonságainak tartalmaznak cikkdimenziókhoz és POS beállításait. E terméket rendelt kategóriákat automatikusan öröklik az attribútumok és tulajdonságai, hogy mi. A kijelölt kategóriába tartozó termékek több egyszerre is másolhatja egyetlen termékhez sem beállításait.




