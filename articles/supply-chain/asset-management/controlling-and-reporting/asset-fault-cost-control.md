---
title: Hibás eszköz költségkontrollja
description: Ez a témakör bemutatja az eszköz-hibaköltség-ellenőrzést az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 553b89a43b656669b7730b19898f3a5d81a3873a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889664"
---
# <a name="asset-fault-cost-control"></a>Hibás eszköz költségkontrollja

[!include [banner](../../includes/banner.md)]

 

Az Eszközkezelés modulban kiszámíthatja a hibáseszköz-regisztrációk költségét, így áttekintést kaphat a tényleges költségekről a költségvetési költségekhez képest. A tényleges költségek a feladott tranzakciókon alapulnak. A dátum a hiba dátuma, amikor a hibajelenség rögzítése megtörtént.

1. Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközhiba** > **Hibás eszköz költségkontrollja**.

2. Ha szükséges, a **Hibás eszköz költségkontrollja** párbeszédablakban válasszon ki egy pénzügyi dimenziót, amelyet be kíván venni a számításba.

4. Ha a nulla költséget tartalmazó eredményeket nem szeretné megjeleníteni, állítsa a **Nulla kihagyása** választógombot „Igen” értékre.

5. A **Szint** mezőben megadhatja, hogy a költségellenőrzési sorok milyen részletesen jelenítsék meg a munkavégzési helyszíneket. 

    Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a hibás eszköz költségkontrolljának minden munkavégzési helyszínhez tartozó sora a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. 
    
    Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a hibás eszköz költségkontrollja minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

6. Ha szűkíteni szeretné a keresést, kiválaszthat meghatározott eszközöket, meghibásodási dátumokat és hibaokokat a **Szerepeltetni kívánt rekordok** gyorslapon.

7. Kattintson az **OK** gombra az számítás indításához.

8. Kattintson a **Csoportosítási szempont...** gombokra a költségszámításhoz kívánt részletességi szintjének a megjelenítéséhez. A kiválasztott **Csoportosítási szempont…** ablaktáblacsoport gombjai ki vannak emelve. A gombra kattintva aktiválhatja vagy inaktiválhatja a funkciót.

## <a name="example"></a>Példa

Ez a példa egy eszköz hibás költségellenőrzési számítását jeleníti meg.

- Az **Eredeti költségvetés** mezőben a munkarendelési előrejelzésből származó költségvetési költségek láthatók. 
- A **Tényleges költség** mező a munkarendeléseken feladott költségeket jeleníti meg. 
- A **Vállalt költség** mezőben a teljes költség látható, amelyet a vállalat a munkarendelésekkel kapcsolatban vállalt.

    ![1. ábra](media/05-controlling-and-reporting.png)

A hibák beállítását lásd [a Hibakezelés cikkében](../setup-for-work-orders/fault-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]