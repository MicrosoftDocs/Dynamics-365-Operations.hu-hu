---
title: Fizetési gyakoriságok beállítása
description: A Microsoft Dynamics 365 Human Resources a fizetési gyakoriságok alapján kiszámítja az éves juttatásfizetést, meghatározza a juttatási díj összegét, amelyet az alkalmazott fizet minden fizetési időszakban, és meghatározza a szállítóknak végrehajtott fizetések gyakoriságát.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b786485ab53dcdb3b7e5ff02562f674a7f8e6eae
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092591"
---
# <a name="set-up-payment-frequencies"></a>Fizetési gyakoriságok beállítása

[!include [banner](includes/preview-feature.md)]

A Microsoft Dynamics 365 Human Resources a fizetési gyakoriságok alapján kiszámítja az éves juttatásfizetést, meghatározza a juttatási díj összegét, amelyet az alkalmazott fizet minden fizetési időszakban, és meghatározza a szállítóknak végrehajtott fizetések gyakoriságát.

A juttatásfizetési gyakoriságok átváltási tényezőket használnak a juttatásfizetési időszakok havonkénti, félévenkénti, kéthetenkénti, hetenkénti és naponkénti fizetési gyakorisága közötti átalakítására. Ez lehetővé teszi a vállalatok számára a juttatási konstrukciókban szereplő fizetési gyakoriságok közötti kölcsönös függőségek meghatározását.

Az átváltási tényezők mezői határozzák meg a fizetési gyakoriságtól a normál fizetési időszakokra történő átváltás tényezőjét, és lehetővé teszik, hogy a rendszer számításokat hajtson végre a fizetési gyakoriságok között. Az átváltási tényező összegével határozható meg az is, hogy az alkalmazottak által fizetett juttatási díj milyen összegű legyen az egyes gyakoriságoknál.

1. A **Juttatások kezelése** munkaterület **Beállítás** részén válassza a **Fizetési gyakoriságok** elemet.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | Fizetés gyakorisága | A fizetési gyakoriság egyedi neve. |
   | Leírás | A fizetési gyakoriság leírása. |
   | Időszak | Az az alkalmas időszak, amely a legjobban megfelel a juttatásszolgáltató és az alkalmazott fizetési gyakoriságának. Az időszaklista a szokásos fizetési időszakokat tartalmazza. |
   | A fizetési időszakok száma | A fizetési időszakok száma, amely meghatározza, hogy milyen gyakran történik fizetés a juttatásszolgáltató vagy az alkalmazottak számára. Ez az összeg lesz használva az alkalmazott évi juttatásfizetési összegének kiszámításához. |
   | Éves átváltási tényező | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 1 év) = 12 |
   | Féléves konverziós tényező | A fizetési gyakoriság féléves átváltási tényezője. Például a havonkénti fizetési gyakoriság féléves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 2 alkalom évente) = 6 |
   | Negyedévenkénti konverziós tényező | A fizetési gyakoriság negyedéves átváltási tényezője. Például a havonkénti fizetési gyakoriság negyedéves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 4 negyedév) = 3 |
   | Havi konverziós tényező | A fizetési gyakoriság havi átváltási tényezője. Például a havonkénti fizetési gyakoriság havi átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 12 hónap) = 1 |
   | Félhavi átváltási tényező | A fizetési gyakoriság félhavi átváltási tényezője. Például a havonkénti fizetési gyakoriság félhavi átváltási tényezője a következő: </br></br>(12 havi fizetés / 24 (havonta 2x)) = 0,5 | 
   | Kétheti konverziós tényező | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 26 hét) = 0,461538 |
   | Heti átváltási tényező | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 52 hét) = 0,230769 |
   | Napi konverziós tényező | A fizetési gyakoriság éves átváltási tényezője. Például a havonkénti fizetési gyakoriság éves átváltási tényezője a következő: </br></br>(12 havonkénti fizetés / 365 nap) = 0,032877 |

4. Válassza a **Mentés** lehetőséget. 
