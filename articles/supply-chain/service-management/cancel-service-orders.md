---
title: Szervizrendelések érvénytelenítése
description: A szervizrendelést és annak sorait magából a rendelésből is érvénytelenítheti, több szervizrendelés egyidejű érvénytelenítéséhez pedig futtathat egy ismétlődő feladatot.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228b76d6f6f0bb048662c8e82df76f51b7cb3652
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017376"
---
# <a name="cancel-service-orders"></a>Szervizrendelések érvénytelenítése   

[!include [banner](../includes/banner.md)]


A szervizrendelést és annak sorait magából a rendelésből is érvénytelenítheti, több szervizrendelés egyidejű érvénytelenítéséhez pedig futtathat egy ismétlődő feladatot.


> [!NOTE]
> <P>A szervizrendelések nem érvényteleníthetők akkor, ha állapotuk ezt nem teszi lehetővé, vagy ha cikkszükségleteik vannak, valamint akkor sem, ha már feladták őket.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Szervizrendelés érvénytelenítése a Szervizrendelések képernyőn

1.  Kattintson a **Szolgáltatáskezelés szervizrendelések** \> **szervizrendelések** \> **lehetőségre**. Válassza ki a szervizrendelést, majd kattintson a **Rendelés törlése** gombra a Műveletpanelen.

## <a name="cancel-a-service-order-line"></a>Szervizrendeléssor érvénytelenítése

1.  Kattintson a **Szolgáltatáskezelés szervizrendelések** \> **szervizrendelések** \> **lehetőségre**. Kattintson duplán az érvényteleníteni kívánt sort tartalmazó szervizrendelésre.

2.  Válassza ki a érvényteleníteni kívánt szervizrendeléssort, és kattintson a **Rendelési sor érvénytelenítése** lehetőségre ahhoz, hogy a sor állapotát **töröltre** módosítsa.


> [!TIP]
> <P>A szervizrendeléssor érvénytelenítésének visszavonásához és állapot <STRONG>elkészültre</STRONG> változtatásához kattintson az <STRONG>Érvénytelenítés visszavonása</STRONG> lehetőségre.</P>


## <a name="cancel-multiple-service-orders"></a>Több szervizrendelés érvénytelenítése

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Rendszeres** \> **Szervizrendelések** \> **Szervizrendelések érvénytelenítése**.

2.  Kattintson a **Kiválaszt** gombra.

3.  A **Lekérdezés** képernyőn, a **Kritériumok** oszlopban válassza ki az érvényteleníteni kívánt szervizrendeléseket.

4.  A **Lekérdezés** képernyő az **OK** gombra kattintva zárható be.

5.  Ha információs naplót szeretne megjeleníteni az érvénytelenített szervizrendelésekről, jelölje be az **Információs napló mutatása** jelölőnégyzetet.

6.  Jelölje be az **Érvénytelenítés visszavonása** jelölőnégyzetet azoknál a szervizrendeléseknél, ahol vissza szeretné vonni a **Törölt** állapotot.

7.  Kattintson az **OK** gombra.

A kiválasztott szervizrendelések vagy érvénytelenítésre kerülnek, vagy a **Törölt** állapotuk visszavált a **Folyamatban** értékre.


> [!NOTE]
> <P>Ha bejelöli az <STRONG>Érvénytelenítés visszavonása</STRONG> jelölőnégyzetet, akkor a <STRONG>Törölt</STRONG> állapotú szervizrendelések visszaállnak az eredeti állapotba, a <STRONG>Folyamatban</STRONG> lévő szervizrendelések pedig nem kerülnek érvénytelenítésre.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]