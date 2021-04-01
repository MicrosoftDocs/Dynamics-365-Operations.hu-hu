---
title: Hibás eszköz költségkontrollja
description: Ez a cikk az Eszközkezelés hibás eszköz költségkontrolljának költségét ismerteti.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c25b3efbd0f2f0ec22a08aeac54ffb7fd9398c83
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253830"
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

A hibák beállításával kapcsolatos tudnivalókat lásd a [Hibakezelés](../setup-for-work-orders/fault-management.md) témakörben.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]