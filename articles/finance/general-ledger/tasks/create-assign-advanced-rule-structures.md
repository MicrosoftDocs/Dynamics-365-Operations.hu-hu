---
title: Speciális szabálystruktúrák létrehozása és hozzárendelése
description: Ez a témakör leírja, hogyan hozhat létre és rendelhet hozzá egy speciális szabályszerkezetet egy számlastruktúrához.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b81e3cc169bf0164af0b9c4de4faeb936df6784
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837057"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Speciális szabálystruktúrák létrehozása és hozzárendelése

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogyan hozhat létre és rendelhet hozzá egy speciális szabályszerkezetet egy számlastruktúrához. Az útmutató az USMF bemutatócéget használja.

## <a name="create-an-advanced-rule-structure"></a>Speciális szabálystruktúra létrehozása
1. Ugrás a következő útvonalra: **Navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Speciális számlastruktúrák**.
2. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. A **Speciális szabálystruktúra** mezőbe írjon be egy nevet a szabálystruktúra leírásához.
4. Válassza ki az **OK** lehetőséget.
5. Válassza a **Szegmens hozzáadása** lehetőséget.
6. A szegmensek listájáról válassza ki a pénzügyi dimenziót. Például: **Bolt**.  
7. Válassza a **Szegmens hozzáadása** lehetőséget.
8. Válassza az **Aktiválás** lehetõséget.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Speciális szabály alkalmazása egy számlastruktúrához
1. Ugrás a következő útvonalra: **navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása**.
2. A listában keresse meg és válassza ki azt a számlastruktúrát, amelyhez a speciális szabályt alkalmazni szeretné.
3. Válassza ki a **Szerkesztés** opciót. Ha a **Speciális szabályokra** kattint, a rendszer kérni fogja a számlastruktúra **Vázlat módba** történő helyezését.  
4. Válassza a **Speciális szabályok** lehetőséget.
5. Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. Írjon be egy értéket a **Speciális szabály** mezőbe.
7. Írjon be egy értéket a **Név** mezőbe.
8. Válassza a **Létrehozása** lehetőséget.
9. Kattintson az **Új feltételek hozzáadása** elemre.
10. A **Honnan** mezőben válassza ki a fő számlát vagy a pénzügyi dimenziót.
11. A **Kezelő** mezőben válasszon ki egy lehetőséget, például a **között**, vagy a **tartalmazza** elemet.
12. Érték beírása az **Érték** mezőbe.
13. Írjon be egy értéket a **–** mezőbe.
14. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
15. A listában keresse meg azt a speciális szabálystruktúrát, amelyet akkor szeretne használni, amikor a megadott feltételek teljesülnek.
16. Válassza a **Hozzáadás** lehetőséget.
17. Zárja be a lapot.
18. Válassza az **Aktiválás** lehetõséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]