---
title: RCS továbbfejlesztett szűrés a RCS/globális tárházban
description: Ez a témakör az RCS globális tárház továbbfejlesztett szűrési funkcióit írja le, amelyek a további szűrők használatával tovább tökéletesítettek.
author: kfend
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace
ms.openlocfilehash: e0408d0561c0cfead8781b9f49fdb84d5caf179a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274512"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS által továbbfejlesztési szűrési lehetőségek a konfigurációk az RCS-ben/globális tárházban való keresése esetén

[!include [banner](../includes/banner.md)]

Ez a témakör a Szabályozó konfigurációs szolgáltatások (RCS) globális tárház továbbfejlesztett szűrési lehetőségeit írja le, amelyek kibővítettek a következő feltételekkel történő szűrésre: 
- **Ország/terület** – ISO-országkódok alapján  
- **Címkék** típusai a következőkhöz:
  - Működési terület
  - Szolgáltatásterület
  - Ágazat 
  - Üzleti dokumentum 

Szűrőket egyenként vagy csoportosan is alkalmazhatja az adott vagy kapcsolódó konfigurációk könnyebb megtalálására. Ha például a szállítói számlákhoz kapcsolódó konfigurálható üzleti dokumentumok egyetlen típusát szeretné megkeresni, akkor a dokumentumtípus megkereséséhez alkalmazhatja az **Üzleti dokumentum típusa** szűrőt. 

[![Szűrő szakasz a globális tárházhoz.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

A keresés tovább finomítható a dokumentumtípus kiválasztásával, például "szállítói számla", mjad a **szűrő alkalmazása** parancsra kattintva. A következő példa azt jeleníti meg, hogy milyen eredmények szerepelnek az **Üzleti dokumentum típusa** elemre szűrés során, ha a dokumentumtípust is hozzáadja. 

[![Alkalmazott szűrő és Importálás az üzleti dokumentum típushoz.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

A szűrt eredmények importálhatók RCS-tárházba vagy Dynamics 365 Pénzügyi környezetbe, akár egyénileg, akár beállítottként. Ehhez válassza ki a konfigurációk csoportját, majd kattintson az **importálás** gombra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
