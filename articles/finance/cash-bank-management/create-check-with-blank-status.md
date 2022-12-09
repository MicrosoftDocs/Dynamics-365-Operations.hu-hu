---
title: Üres állapotú csekkek létrehozása
description: Ez a cikk azt mutatja be, hogyan hozhatók létre üres csekkek egy bankszámlához.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 86020d9088d8135c83716128a77090608536a78f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804018"
---
# <a name="create-checks-that-have-blank-status"></a>Üres állapotú csekkek létrehozása

[!include [banner](../includes/banner.md)]

Ez a cikk azt mutatja be, hogyan hozhatók létre üres csekkek. Üres csekket például egy megsérült, fizetéshez nem használható csekk rögzítéséhez hozhat létre.

A **Csekkek** oldalon hajthatók végre a csekkekhez tartozó karbantartási feladatok. Ezen az oldalon létrehozhat például új csekkszámokat, és törölhet csekkeket. **Üres** állapotú csekkeket ugyancsak hozhat létre. A létrehozott üres csekkek nem törölhetők és nem használhatók fel újra a rendszerben.

> [!NOTE]
> Ez a funkció csak akkor érhető el a **Csekkek** oldalon, ha a **Funkció kezelése** oldalon bekapcsolja az **Üres állapotú csekkek létrehozása a Csekkek oldalon** szolgáltatást. Ha nem kapcsolja be a funkciót, akkor **Üres** állapotú csekkek csak a **Fizetés csekkel** párbeszédpanelen, a Kötelezettségek modul kifizetés létrehozására szolgáló folyamata során hozhatók létre.

A **Csekkek** oldal megnyitásához lépjen a **Készpénz- és bankkezelés \> Bankszámlák \> Bankszámlák** részre, és a műveleti ablaktábla **Kifizetések kezelése** lapjának **Kapcsolódó információ** csoportjában válassza a **Csekkek** lehetőséget. Egy másik megoldás, hogy a **Készpénz- és bankkezelés \> Lekérdezések és jelentések \> Csekkek** részre lép.

Ezután az **Üres** állapotú csekkek létrehozásához válassza az **Üres csekkek létrehozása** lehetőséget a műveleti panelen. Amikor a rendszer üres csekkeket hoz létre, akkor ideiglenesen inaktiválja a társított bankszámlát. Így kisebb annak a kockázata, hogy az üres csekkek létrehozása közben kifizetések jönnek létre. A művelet befejezése után a társított bankszámla újra aktiválódik.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
