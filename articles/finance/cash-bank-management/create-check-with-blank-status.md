---
title: Üres állapotú csekkek létrehozása
description: Ez a témakör azt mutatja be, hogyan hozhatók létre üres csekkek egy bankszámlához a Csekkek oldalon.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 94d3a4ac8a3906e48f5a6053c031001c111549ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254035"
---
# <a name="create-checks-that-have-blank-status"></a>Üres állapotú csekkek létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan hozhatók létre üres csekkek. Üres csekket például egy megsérült, fizetéshez nem használható csekk rögzítéséhez hozhat létre.

A **Csekkek** oldalon hajthatók végre a csekkekhez tartozó karbantartási feladatok. Ezen az oldalon létrehozhat például új csekkszámokat, és törölhet csekkeket. **Üres** állapotú csekkeket ugyancsak hozhat létre. A létrehozott üres csekkek nem törölhetők és nem használhatók fel újra a rendszerben.

> [!NOTE]
> Ez a funkció csak akkor érhető el a **Csekkek** oldalon, ha a **Funkció kezelése** oldalon bekapcsolja az **Üres állapotú csekkek létrehozása a Csekkek oldalon** szolgáltatást. Ha nem kapcsolja be a funkciót, akkor **Üres** állapotú csekkek csak a **Fizetés csekkel** párbeszédpanelen, a Kötelezettségek modul kifizetés létrehozására szolgáló folyamata során hozhatók létre.

A **Csekkek** oldal megnyitásához lépjen a **Készpénz- és bankkezelés \> Bankszámlák \> Bankszámlák** részre, és a műveleti ablaktábla **Kifizetések kezelése** lapjának **Kapcsolódó információ** csoportjában válassza a **Csekkek** lehetőséget. Egy másik megoldás, hogy a **Készpénz- és bankkezelés \> Lekérdezések és jelentések \> Csekkek** részre lép.

Ezután az **Üres** állapotú csekkek létrehozásához válassza az **Üres csekkek létrehozása** lehetőséget a műveleti ablaktáblán. Amikor a rendszer üres csekkeket hoz létre, ideiglenesen inaktiválja a társított bankszámlát. Így kisebb annak a kockázata, hogy az üres csekkek létrehozása közben kifizetések jönnek létre. A művelet befejezése után a társított bankszámla újra aktiválódik.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]