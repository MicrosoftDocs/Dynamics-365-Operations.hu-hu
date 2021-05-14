---
title: Hibás mezőérték a TaxTrans mezőben
description: Ez a témakör a TaxTrans hibás mezőértékeivel kapcsolatos hibaelhárítással kapcsolatban tartalmaz tájékoztatást.
author: bijian
manager: beya
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 97f9bb24d32180f2fccb69c5a13e2aa0349c1ee4
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947648"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Hibás mezőérték a TaxTrans mezőben

[!include [banner](../includes/banner.md)]

Ha a **TaxTrans** egy mezőértéke helytelen, a témakörben található információk alapján próbálja meg megoldani a problémát.

## <a name="overview-of-values"></a>Értékek áttekintése
Az alábbi lista bemutatja, hogy a **TaxTrans**, a **TaxUncommitted** és a **TmpTaxWorkTrans** ugyan hasonló adatkészletek, mégis eltérő módon működnek.

  - A **TaxTrans** az adatbázisban megmaradó végső feladott adótranzakció-eredmény.
  - A **TaxUncommitted** az adatbázisban (ha van) megőrzött köztes számított adó eredmény, amelyet a feladáshoz később lesz használva.
  - A **TmpTaxWorkTrans** az ideiglenes számított adó eredménye a memóriában található táblában (Táblatípus = InMemory).

Ha helytelen **TaxTrans** oszlop kiváltó okát megtalálja, akkor a hibás **TaxUncommitted** vagy **TmpTaxWorkTrans** oszlop kiváltó okát is megtalálta. Ennek az az oka, hogy a három oszlop egymásból van másolva.

Az adószámítás során általában létrejön a **TmpTaxWorkTrans**, majd – ha szükséges – a **TaxUncommitted** is. Az adófeladás során a **TaxTrans** generálódik.


## <a name="add-breakpoints"></a>Töréspontok hozzáadása
Töréspontok hozzáadását a következő lépésekkel végezheti el: 

1. Bővítmények és töréspontok hozzáadása az *insert()* és *update()* alá a bővítményekben az alábbiak szerint.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. Másik megoldásként közvetlenül is hozzá lehet adni töréspontokat, ha a **TaxUncommitted** nem szerepel.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Reprodukálás és hibakeresés

A töréspontok beállítása után minden adatperzisztenciás változás látható a hibakeresés során. Ha a **TaxTrans**, a **TaxUncommitted** vagy a **TmpTaxWorkTrans** oszlop hibájának kiváltó okát kell megtalálni ellenőrizze és jegyezze fel a következő elemeket:

- Az utolsó töréspont, ahol az oszlop helyes.
- Az első töréspont, ahol az oszlop helytelen.
- Mi történik e két pont között.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás
Ha az előző szakaszokban már befejezte a lépéseket, de nem sikerült megoldani a problémát, határozza meg, hogy van-e testreszabás. Ha nincs testreszabás, forduljon segítségért a Microsoft támogatási szolgálatához.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

