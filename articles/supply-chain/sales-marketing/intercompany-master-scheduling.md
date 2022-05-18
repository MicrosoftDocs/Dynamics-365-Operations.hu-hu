---
title: Vállalatközi alapütemezés
description: Ez a témakör bemutatja a vállalatközi alapütemezést
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 02d1a3675cfe30f2e72237f69509398122d17f05
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671870"
---
# <a name="intercompany-master-scheduling"></a>Vállalatközi alapütemezés

[!include [banner](../../includes/banner.md)]

A vállalatközi alapütemezés segítségével számítja ki a program az igényeket és hozza létre a több belső vállalat közti tervezett vállalatközi rendeléseket. A vállalatközi alapütemezést a megadott számú iterácó végrehajtásával számítja ki a program. Ha engedélyezni szeretné, hogy a Microsoft Dynamics 365 Supply Chain Management végezze el a vállalatközi alapütemezést, akkor minden egyes vállalatnál be kell állítani az alapütemezést. Az így kiváltott iterációk során a Microsoft Dynamics 365 Supply Chain Management automatikusan létrehoz egy vállalatközi beszerzési rendelést, amely vállalatközi értékesítési rendelések létrehozásához vezet, ami viszont újabb igényeket támaszt.

A vállalatközi alaptervet és a vállalatközi ütemezési sorrendet az egyes vállalatközi vállalatok **Alaptervezés** paramétereiben lehet megadni.

Ha egy igényt szeretne a teljes vállalatközi láncra kiterjeszteni, akkor be kell állítani a megfelelő paramétereket, hogy a tervezett beszerzési rendelések megerősítése automatikusan megtörténjen, vagyis hogy a rendelés idő vagy mennyiség tekintetében ne legyen módosítható. Állítsa be a **Megerősítési időkorlátot** a Fedezeti csoporton vagy a **Megerősítési időkorlátot** az Alaptervezésen. Ha nincs beállítva **Megerősítési időkorlát**, akkor nem készülnek automatikusan vállalatközi beszerzési megrendelések. Csak az alapütemezés első végrehajtása esetén lesz tervezett rendelés. Mivel azonban nem jön létre vállalatközi beszerzési rendelés, nem jön létre vállalatközi értékesítési rendelés, így több vállalatközi beszerzési rendelés sem jön létre stb.

A vállalatközi alapütemezés indítása során a Microsoft Dynamics 365 Supply Chain Management minden egyes vállalatközi vállalatnál elvégez egy alapütemezést, majd minden egyes vállalatközi vállalatnál elvégez egy második alapütemezést, és így tovább, amíg a program el nem éri az iterációk kívánt számát. Maximum 30 iteráció állítható be, ugyanakkor minél többet állít be, annál hosszabb ideig tart az ütemezés.

A vállalatoknál az alapütemezést a vállalatközi ütemezési sorozat szabályozza, amellyel a program meghatározza az egyes vállalatközi vállalatok közötti alapütemezések prioritását, mivel vállalatközi alapütemezés bármely vállalatközi vállalatból elindítható. Mivel a vállalatközi ütemezési sorozat határozza meg a vállalatok közötti alapütemezés sorrendjét, nem fontos, hogy hol indítják el a vállalatközi alapütemezést. Minden egyes ismétlés esetén az aktuális vállalat hajtja végre utoljára az ütemezést.

> [!NOTE]
> A legjobb gyakorlat az, ha engedélyezi, hogy egy Microsoft Dynamics 365 Supply Chain Management vállalat kezdeményezze a vállalatközi alapütemezést.

A **Vállalatközi alaptervezés** oldalon elindíthatja az alapütemezés sorozatát, amely az alapütemezést először azzal az alapszabállyal hajtja végre, hogy frissítse az összes vállalatközi vállalathoz kiválasztott igényszámításokat. Az ezután következő iterációk a következő iterációhoz beállított alapszabályt alkalmazzák, és a beállított iterációs szám eléréséig ez lesz az alkalmazott alapszabály.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
