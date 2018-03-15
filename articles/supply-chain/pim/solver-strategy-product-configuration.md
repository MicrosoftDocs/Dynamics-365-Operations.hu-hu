---
title: "Feloldási stratégia termékkonfigurációhoz"
description: "Ez a témakör leírja, hogyan használhatja a feloldási stratégiát a termékkonfiguráció teljesítményének javítása érdekében."
author: cvocph
manager: AnnBe
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 4544128e580b30b14a6236a9a6147ff0a8641d72
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---

# <a name="solver-strategy-for-product-configuration"></a>Feloldási stratégia termékkonfigurációhoz

[!include[banner](../includes/banner.md)]

Ez a témakör leírja, hogyan használhatja a feloldási stratégiát a termékkonfiguráció teljesítményének javítása érdekében.

A feloldási stratégia fogalmát először a Microsoft Dynamics AX 2012 R2 7. összesített frissítése (CU7) vezette be. Később bővítve lett a Microsoft Dynamics AX 2012 R3 és a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 8. összesített frissítésében (CU8) .

A feloldási stratégia fogalma most a következő stratégiákból áll:

- Alapértelmezett
- Előbb a minimumtartományok
- Felülről lefelé
- Z3

## <a name="solver-strategy"></a>Feloldási stratégia 

A termékkonfigurációs modell [kényszerkielégítési problémaként (CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf) fogalmazható meg. A Microsoft Solver Foundation (MSF) kétféle feloldási stratégiát kínál a CSP-k megoldására, amelyek termékkonfigurációs modellekből használhatók. E feloldási stratégiák [heurisztikára](https://techterms.com/definition/heuristic) támaszkodnak, amelynek segítségével meghatározható a CSP a probléma megoldása során figyelembe vett változóinak sorrendje. A heurisztika jelentősen befolyásolhatja a teljesítményt probléma vagy problémaosztály megoldásánál.

A Finance and Operations alkalmazásban a termékkonfigurációs modellek feloldási stratégiája határozza meg, hogy melyik feloldást kell használni heurisztikával. Az **Alapértelmezett**, **Előbb a minimumtartományok** és **Felülről lefelé** stratégiák az MSF-ből származó két megoldót használják, míg a  **Z3** stratégia a Z3 feloldót alkalmazza. 

Valós vevői végrehajtási tanulmányok kimutatták, hogy a termékkonfigurációs modell feloldási stratégiájának változása a válaszidőt percekről milliszekundumokra csökkentheti. Ezért érdemes különböző feloldási stratégiák kipróbálására törekedni a termékkonfigurációs modellhez illő leghatékonyabb stratégia megtalálásához.

## <a name="change-the-settings-for-the-solver-strategy"></a>A feloldási stratégia beállításainak módosítása

A feloldási stratégia módosításához a **Termékkonfigurációs modellek** lapon válassza ki a műveleti ablaktáblában a **Modell tulajdonságai** elemet. Ezután a **Modell részleteinek szerkesztése** párbeszédpanelen válasszon feloldási stratégiát.

[![A feloldási stratégia módosítása](./media/solver-strategy.png)](./media/solver-strategy.png)

Jelenleg nincs olyan logika, amely automatikusan érzékeli, hogy mely feloldási stratégia lesz a leghatékonyabb stratégia a kényszeralapú termékkonfigurációhoz. Ezért próbálja ki a feloldási stratégiákat egymás után.

Az alábbi táblázat ajánlásokat tartalmaz a különböző forgatókönyveknél használható feloldási stratégiákhoz.

| Feloldási stratégia      | A stratégia használata ebben az esetben |
|----------------------|-----------------------------------|
| Alapértelmezett              | Az **Alapértelmezett** stratégia táblakorlátozásokon alapuló modellek megoldására van optimalizálva. Vevői végrehajtási tanulmányok azt mutatják, hogy ez a stratégia a leghatékonyabb stratégia olyan forgatókönyveknél, ahol széles körben használnak táblakorlátozásokat. |
| Előbb a minimumtartomány | Az **Előbb a minimumtartomány** és a **Felülről lefelé** stratégiák szoros kapcsolatban állnak egymással. Vevői végrehajtási tanulmányok azt mutatják, hogy a CU8-cal bevezetett **Felülről lefelé** stratégia jobb teljesítményt nyújt, mint az **Előbb a minimumtartomány** stratégia. Azonban az **Előbb a minimumtartomány** stratégiát megtartottuk a termékben a visszamenőleges kompatibilitás érdekében. Mindkét feloldási stratégia bizonyítottan hatékonyabb egyszerre több aritmetikai kifejezést tartalmazó olyan modellek megoldásához, amelyekben nincsenek táblakorlátozások. Azonban bizonyos esetekben az **Alapértelmezett** stratégia jobb teljesítményt nyújt, mint ez a két stratégia. Ezért ne feledje, hogy minden egyes stratégiát próbáljon ki. |
| Felülről lefelé             | Az **Előbb a minimumtartomány** és a **Felülről lefelé** stratégiák szoros kapcsolatban állnak egymással. Vevői végrehajtási tanulmányok azt mutatják, hogy a CU8-cal bevezetett **Felülről lefelé** stratégia jobb teljesítményt nyújt, mint az **Előbb a minimumtartomány** stratégia. Azonban az **Előbb a minimumtartomány** stratégiát megtartottuk a termékben a visszamenőleges kompatibilitás érdekében. Mindkét feloldási stratégia bizonyítottan hatékonyabb egyszerre több aritmetikai kifejezést tartalmazó olyan modellek megoldásához, amelyekben nincsenek táblakorlátozások. Azonban bizonyos esetekben az **Alapértelmezett** stratégia jobb teljesítményt nyújt, mint ez a két stratégia. Ezért ne feledje, hogy minden egyes stratégiát próbáljon ki. |
| Z3                   | Azt ajánljuk, hogy alapértelmezett feloldási stratégiaként használja a **Z3** stratégiát. Ha érdekli a teljesítmény és a skálázhatóság, akkor értékelheti a többi stratégiát. |

## <a name="additional-resources"></a>További erőforrások

[Termékkonfigurációs modell felépítése](build-product-configuration-model.md)

[Heurisztika](https://techterms.com/definition/heuristic)

[Kényszerkielégítési probléma](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)

