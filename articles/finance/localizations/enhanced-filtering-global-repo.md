---
title: Továbbfejlesztett szűrés a RCS/globális tárházban
description: Ez a témakör a RCS globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a további szűrőket is kaptak.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
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
ms.openlocfilehash: 1adbd690795139778dc77a574e9d5f91a4bdeb3c
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249165"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a>A globális tárházban a konfigurációk megkeresésére szolgáló továbbfejlesztett szűrési lehetőségek

[!include [banner](../includes/banner.md)]

Ez a témakör a Regulatory Configuration Service (RCS) globális tárház továbbfejlesztett szűrési képességeit írja le, amelyek a következő szűrőkkel lettek továbbfejlesztve: 
- **Ország/terület** – ISO-országkódok alapján  
- **Címkék** -a funkcionális/jellemző területen; Ipar; Üzleti dokumentum típusa 

Szűrőket egyenként vagy csoportosan is alkalmazhatja a adott vagy kapcsolódó konfigurációk megtalálására. Például a szállítói számlákhoz kapcsolódó összes konfigurálható üzleti dokumentum megkereséséhez alkalmazhatja az **Üzleti dokumentum típusa** szűrőt. 

A keresést tovább finomíthatja, ha kiválasztja az országkódot, majd a **Szűrő alkalmazása** elemre kattint.  

[![Szűrő szakasz a globális tárházhoz](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

A következő példa azt jeleníti meg , hogy milyen eredmények szerepelnek az **Üzleti dokumentum típusa** elemre szűrés során. 

[![Alkalmazott szűrő és Importálás az üzleti dokumentum típushoz](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

A szűrt eredmények a importálhatók az RCS vagy Dynamics 365 Finance környezetbe, akár egyenként, akár egy készletként (a konfigurációk csoportjának kiválasztásával), majd az **Importálás** elemre kattintással.






