---
title: Kifizetés-visszatérítések feldolgozása
description: Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani.
author: Henrikan
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce813f0f5d9aa750828b524dd9fdf9b4a9f0854
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572457"
---
# <a name="process-rebates-for-payment"></a>Kifizetés-visszatérítések feldolgozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani. Ezt az útmutatót használhatja az USMF bemutatócégben. Az útmutató előfeltétele, hogy egy vagy több olyan visszatérítési igénnyel rendelkezzen, amelynek az állapota be van jelölve. Az USMF használatakor futtatnia kell a „Vevői visszatérítések létrehozása és feldolgozása” útmutatót, az útmutató megkezdése előtt.


## <a name="convert-rebate-claims-to-credit-note"></a>Visszatérítési igények átalakítása jóváírássá
1. Ugorjon a Minden vevő elemre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. A Művelet panelen kattintson a Beszed elemre.
5. Kattintson a Tranzakcióinak kiegyenlítése gombra.
6. Kattintson a Funkciók elemre.
7. Kattintson a Visszatérítési program elemre.
    * A Visszatérítés lapon láthatja azokat a visszatérítési igényléseket, amelyeket feldolgozott a vevői visszatérítési munkaterületen, és amelyek állapota be van jelölve.    
8. Kattintson a Szerkesztés lehetőségre.
    * A Jelölés mezőben jelölje be azoknak az igényléseknek a jelölőnégyzetét, amelyeket szerepeltetni szeretne a jóváírásban.   
9. Kattintson a Funkciók elemre.
10. Kattintson a Jóváírás létrehozása elemre.
    * Megjelenik egy üzenet, amely arról tájékoztatja, hogy a napló feladása megtörtént (Ez a Kinnlevőség-felhasználási napló, ahogy az a Kinnlevőségek paraméterei lapon is szerepel). Ezzel a valós kötelezettség (hitel) összegét a vevő egyenlegébe helyezi át. Ez azt jelenti, hogy a rendszer a vevő számláját jóváírta, és a visszatérítés könyvelési számlát megterhelte.  
11. Zárja be a lapot.
12. Kattintson a Mégse gombra.
    * Ezzel frissíti a lapot, így láthatja a frissítéseket.  
13. A Művelet panelen kattintson a Beszed elemre.
14. Kattintson a Tranzakcióinak kiegyenlítése gombra.
    * Vegye figyelembe, hogy a teljes visszatérítés összegét jelentő negatív összegű tranzakciót a rendszer számlahivatkozás nélkül hozzáadta a vevő egyenlegéhez.   
15. Kattintson a Mégse gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]