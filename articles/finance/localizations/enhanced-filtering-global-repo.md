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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443853"
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
