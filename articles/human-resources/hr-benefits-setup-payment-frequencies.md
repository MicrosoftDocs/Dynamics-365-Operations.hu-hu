---
title: Fizetési gyakoriságok beállítása
description: A Microsoft Dynamics 365 Human Resources a fizetési gyakoriságok alapján kiszámítja az éves juttatásfizetést, meghatározza a juttatási díj összegét, amelyet az alkalmazott fizet minden fizetési időszakban, és meghatározza a szállítók kifizetésének gyakoriságát.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0472e2203cc20fcf0904d22778092721b4cbce41
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323928"
---
# <a name="set-up-payment-frequencies"></a>Fizetési gyakoriságok beállítása


A Microsoft Dynamics 365 Human Resources a fizetési gyakoriságok alapján kiszámítja az éves juttatásfizetést, meghatározza a juttatási díj összegét, amelyet az alkalmazott fizet minden fizetési időszakban, és meghatározza a szállítók kifizetésének gyakoriságát.

A juttatásfizetési gyakoriságok átváltási tényezőket használnak a juttatásfizetési időszakok havonkénti, félévenkénti, kéthetenkénti, hetenkénti és naponkénti fizetési gyakorisága közötti átalakítására. Ez lehetővé teszi a vállalatok számára a juttatási konstrukciókban szereplő fizetési gyakoriságok közötti kölcsönös függőségek meghatározását.

Az átváltási tényezők mezői határozzák meg a fizetési gyakoriságtól a normál fizetési időszakokra történő átváltás tényezőjét, és lehetővé teszik, hogy a rendszer számításokat hajtson végre a fizetési gyakoriságok között. Az átváltási tényező összege azt is meghatározza, hogy az alkalmazottak által fizetett juttatási díj milyen összegű legyen az egyes gyakoriságoknál.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Fizetési gyakoriságok** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Fizetés gyakorisága** | A fizetési gyakoriság egyedi neve. |
   | **Leírás** | A fizetési gyakoriság leírása. |
   | **Időszak** | Az az alkalmas időszak, amely a legjobban megfelel a juttatásszolgáltató és az alkalmazott fizetési gyakoriságának. Az időszaklista a szokásos fizetési időszakokat tartalmazza. |
   | **A fizetési időszakok száma** | A fizetési időszakok száma, amely meghatározza, hogy milyen gyakran történik fizetés a juttatásszolgáltató vagy az alkalmazottak számára. Ez az összeg lesz használva az alkalmazott évi juttatásfizetési összegének kiszámításához. |
   | **Éves átváltási tényező** | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 1 év) = 12 |
   | **Féléves konverziós tényező** | A fizetési gyakoriság féléves átváltási tényezője. Például a havonkénti fizetési gyakoriság féléves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 2 alkalom évente) = 6 |
   | **Negyedévenkénti konverziós tényező** | A fizetési gyakoriság negyedéves átváltási tényezője. Például a havonkénti fizetési gyakoriság negyedéves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 4 negyedév) = 3 |
   | **Havi konverziós tényező** | A fizetési gyakoriság havi átváltási tényezője. Például a havonkénti fizetési gyakoriság havi átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 12 hónap) = 1 |
   | **Félhavi átváltási tényező** | A fizetési gyakoriság félhavi átváltási tényezője. Például a havonkénti fizetési gyakoriság félhavi átváltási tényezője a következő: </br></br>(12 havi fizetés / 24 (havonta 2x)) = 0,5 | 
   | **Kétheti konverziós tényező** | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 26 hét) = 0,461538 |
   | **Heti átváltási tényező** | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 52 hét) = 0,230769 |
   | **Napi konverziós tényező** | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 365 nap) = 0,032877 |
   | **Óránkénti átváltási tényező** | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 2080 óra) = 0,005769

4. Válassza a **Mentés** lehetőséget. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
