---
title: NUMSEQVALUE ER-függvény
description: Ez a cikk a NUMSEQVALUE Elektronikus jelentés (ER) funkcióval kapcsolatban tartalmaz tájékoztatást.
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 62255f0a47d3c67468cf2cf3922a1886c29c03d6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271553"
---
# <a name="numseqvalue-er-function"></a>NUMSEQVALUE ER-függvény

[!include [banner](../includes/banner.md)]

A `NUMSEQVALUE` függvény egy *Karakterlánc* értéket ad vissza, amely a megadott számsorozat, hatókör és hatókör-azonosító alapján egy számsorozat új generált értékét jelzi. A hatókör-azonosító egyenlő a vállalati kóddal, amelyet az Elektronikus jelentéskészítési (ER) formátumot futtató kontextus biztosít.

## <a name="syntax-1"></a>Szintaxis 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Szintaxis 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Szintaxis 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argumentumok

`number sequence code`: *Karakterlánc*

Szöveges érték, amely annak a számsorozatnak a kódját jelöli, amelyben az új érték szükséges.

`number sequence record ID`: *Int64*

Az *Int64* érték a NumberSequenceTable tábla rekordjának rekordazonosítóját jelzi, amely annak a számsorozatnak a definícióját tartalmazza, amelyben az új érték szükséges.

`scope type`: *Felsorolási érték*

Az **ERExpressionNumberSequenceScopeType** felsorolási értéke, amely meghatározza annak a számsorozatnak a hatókörét, amelyhez az új érték szükséges. A rendelkezésre álló hatókörtípusok a **Megosztott**, a **Jogi entitás** és a **Vállalat**.

`scope ID`: *Karakterlánc*

Egy *Karakterlánc* érték, amely a megadott hatókörtípus alapján azonosítja a hatókört.

## <a name="return-values"></a>Visszaadott értékek

*Karakterlánc*

Az eredményül kapott szövegérték.

## <a name="usage-notes"></a>Használati megjegyzések

A **Megosztott** hatókörtípus esetében egy üres karakterláncot adjon meg a hatókör-azonosítóként.

A **Vállalat** és a **Jogi személy** hatókörtípusoknál a vállalat azonosítóját adja meg a hatókör-azonosítóként. Ha ezeknél a hatókörtípusoknál egy üres karakterláncot ad meg a hatókör-azonosítóként, az aktuális vállalati azonosító lesz használatos.

Az 1-es szintaxis használatakor a rendszer a **Vállalati** hatókörtípus számsorozatát kéri, és a vállalati kódot az a környezet adja, amely alatt az ER formátum fut.

## <a name="example-1"></a>1. példa

Az ER-formátumában adja meg az **AskNumSeq** adatforrást a *Felhasználó által megadott paraméterek* típusaként. Ez az adatforrás a **Leírás** kiterjesztett adattípusra (EDT) vonatkozik. Ezután adja meg a **NumSeq** adatforrást a *Kiszámított mező* típushoz. Az adatforrás tartalmazza a `NUMSEQVALUE (AskNumSeq)` kifejezést. Amikor a **NumSeq** adatforrást hívják, az eredményül adott számsorozat új generált értékét adja vissza, amely futásidőben, a kódnak a párbeszédpanelen való beírásával került megadásra. A számsorozatot a **Vállalat** hatókörtípus igényli. A vállalati kódot az a kontextus biztosítja, amely alatt az ER-formátum fut.

## <a name="example-2"></a>2. példa

A következő adatforrások megadása a modell-hozzárendelésben történik:

- A *Tábla* típus **LedgerParms** adatforrása. Ez az adatforrás az LedgerParameters táblára hivatkozik.
- A *Számított mező* típus **NumSeq** adatforrása. Az adatforrás tartalmazza a `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)` kifejezést.

Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a számsorozatnak, amely a vállalathoz van beállítva a főkönyvi paraméterekben, amely a kontextust adja, amely alatt az ER-formátumot futtatják. Ez a számsorozat egyértelműen azonosítja naplókat, és kötegszámként viselkedik, amely összekapcsolja a tranzakciókat.

## <a name="example-3"></a>3. példa

A következő adatforrások megadása a modell-hozzárendelésben történik:

- A **365 Pénzügyi felsorolásos típus enum Olyan** Microsoft Dynamics adatforrása, amely a 365 Pénzügyi *felsorolásos típus*. Ez az adatforrás az **ERExpressionNumberSequenceScopeType** felsorolásra vonatkozik.
- A *Számított mező* típus **NumSeq** adatforrása. Az adatforrás tartalmazza a `NUMSEQVALUE ("Gene_1", enumScope.Company, "")` kifejezést.

Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a **Gene\_1** számsorozatnak, amely a vállalathoz van beállítva, amely a kontextust adja, amely alatt az ER-formátumot futtatják.

## <a name="additional-resources"></a>További erőforrások

[Egyéb (üzleti területre jellemző) függvények](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
