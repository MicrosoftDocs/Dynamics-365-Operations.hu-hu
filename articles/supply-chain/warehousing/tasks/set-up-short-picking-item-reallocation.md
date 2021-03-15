---
title: Rövid kitárolásra jelölt cikkek újbóli felosztásának beállítása
description: Ez a témakör bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab8baf846d65e6fefe9ca575b5af5a2dbceac666
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976888"
---
# <a name="set-up-short-picking-item-reallocation"></a>Rövid kitárolásra jelölt cikkek újbóli felosztásának beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan engedélyezze a raktári dolgozók számára az alternatív helyek gyorsan megtalálását, ha nincs elegendő készlet a helyen, ahová átirányították őket. 

Az újrafelosztási folyamatot egy **Munkakivétel** vezérli, és a raktári **dolgozó** használja.

Lehetőség van Automatikus, Kézi vagy mindkét újrafelosztási folyamat használatára:

- Automatikus újrafelosztás – A rendszer a helyutasítások használatával határozza meg, hogy az áruk egy másik helyen elérhetők-e. Ha lehetséges, a program frissíti a munkát, és a rendszer átirányítja a raktári felhasználót az alternatív helyre.
- Manuális újrafelosztás – Lehetővé teszi a raktári felhasználó számára, hogy válasszon egy vagy több nem lefoglalt mennyiségű áruval rendelkező hely közül. 
- Automatikus és manuális – Ha a rendszer nem képes automatikus újrafelosztásra, és a nem lefoglalt mennyiséggel rendelkező helyek érhetők el, akkor a program felkéri a felhasználót, hogy válasszon egy helyet.

## <a name="set-up-work-exceptions"></a>Munkakivételek beállítása
Lehetőség van több munkakivétel meghatározására eltérő cikkfelosztási irányelvekkel, amelyek lehetővé teszik, hogy a raktáros válasszon egyet a feldolgozott szállítmány szükségletei szerint.

Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához.

1. A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Munka > Munkakivételek** lehetőségre.
2. Kattintson az **Új** elemre. 
3. Adjon meg egy értéket a **Munkakivételkód** mezőben. Ez lesz a kivétel címe. Például: Rövid kitárolási kézikönyv.
4. Írjon egy értéket a **Leírás** mezőbe. Ez a kivétel használatának rövid leírása lesz. Például: Rövid kitárolás – a cikk nem érhető el.
5. A **Kivétel típus** mezőben válassza ki a **Rövid kitárolás** lehetőséget.
6. Jelölje be a **Készlethelyesbítés** jelölőnégyzetet. Ha ki van választva, automatikusan megtörténik a készlet helyesbítése 0-ra a rövid kitárolás helyén.
7. Adjon meg vagy válasszon ki egy értéket az **Alapértelmezett helyesbítéstípus-kód** mezőben. Például az USMF-ben kiválaszthatja a **Remove Res Adj Out** elemet. Minden Helyesbítésitípus-kód négy jellemzőt tartalmaz: név, leírás, készletnapló neve, és a **Foglalások eltávolítása**. Ha a **Foglalások eltávolítása** lehetőséget engedélyezi, a program eltávolítja a rövid kitárolású rendelési sor foglalásait.  
8. A **Cikk újbóli felosztása** mezőben válasszon egy értéket, mint például a Kézi. Ha bejelöli a manuális, vagy az automatikus és manuális lehetőséget, a raktáros számára engedélyezni kell a manuális újbóli felosztást.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>A dolgozó beállítása a manuális cikk-újbólifelosztás használatára

Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához.

1. Zárja be a lapot.
2. A **Navigációs ablaktáblán** ugorjon a **Raktárkezelés > Beállítás > Dolgozó >** lehetőségre.
3. Kattintson a **Szerkesztés** lehetőségre.
4. A listában válassza a dolgozót. Példa: Julia Funderburk.
5. Bontsa ki a **Felhasználók** gyorslapot.
6. A listában válasszon ki egy **Felhasználóazonosító** elemet. Például, 24 elem.
7. Bontsa ki a **Munka** gyorslapot.
8. Válassza ki az **Igen** lehetőséget a **Cikk újbóli manuális felosztásának engedélyezése** mezőben.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]