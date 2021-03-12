---
title: RCS továbbfejlesztett szűrés a RCS/globális tárházban
description: Ez a témakör a RCS globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a további szűrőket is kaptak.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a67a4345271cbeffc100fc1d9077cc866846a4d4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005842"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS által továbbfejlesztési szűrési lehetőségek a konfigurációk az RCS-ben/globális tárházban való keresése esetén

[!include [banner](../includes/banner.md)]

Ez a témakör a Regulatory Configuration Service (RCS) globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a következő feltételek alapján történő szűrőkkel lettek továbbfejlesztve: 
- **Ország/terület** – ISO-országkódok alapján  
- **Címkék** típusai a következőkhöz:
  - Működési terület
  - Szolgáltatásterület
  - Ágazat 
  - Üzleti dokumentum 

Szűrőket egyenként vagy csoportosan is alkalmazhatja az adott vagy kapcsolódó konfigurációk könnyebb megtalálására. Ha például a szállítói számlákhoz kapcsolódó konfigurálható üzleti dokumentumok egyetlen típusát szeretné megkeresni, akkor a dokumentumtípus megkereséséhez alkalmazhatja az **Üzleti dokumentum típusa** szűrőt. 

[![Szűrő szakasz a globális tárházhoz](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

A keresés tovább finomítható a dokumentumtípus kiválasztásával, például "szállítói számla", mjad a **szűrő alkalmazása** parancsra kattintva. A következő példa azt jeleníti meg, hogy milyen eredmények szerepelnek az **Üzleti dokumentum típusa** elemre szűrés során, ha a dokumentumtípust is hozzáadja. 

[![Alkalmazott szűrő és Importálás az üzleti dokumentum típushoz](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

A szűrt eredmények importálhatók egy felhasználó RCS-adattárába vagy egy Dynamics 365 Finance-környezetbe, egyesével vagy csoportban is. Ehhez válassza ki a konfigurációk csoportját, majd kattintson az **importálás** gombra.
