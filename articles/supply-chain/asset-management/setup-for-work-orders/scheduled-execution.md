---
title: Ütemezett végrehajtás
description: Ez a témakör azt ismerteti, hogyan lehet ütemezett végrehajtást beállítani az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d9c8afc139c96e32efb3161d35fde685b8abcc5
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874670"
---
# <a name="scheduled-execution"></a>Ütemezett végrehajtás

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Az ütemezett végrehajtás beállításához a munkarendelés szolgáltatási szintjét is használhatja. (A munkarendelés szolgáltatási szintjeivel kapcsolatos további tudnivalókat lásd itt: [Szolgáltatási szint és leírás](service-level-and-description.md).) Az ütemezett végrehajtás kellő rugalmasságot ad a karbantartási dolgozók munkájának megtervezéséhez, mivel részletesebb vagy kevésbé részletes követelményeket is beállíthat ahhoz az időszakhoz, amely alatt a munkarendelést végre kell hajtani. Előfordulhat például, hogy az a karbantartási dolgozó, aki a vártnál gyorsabban végez munkájával az egyik gyártólétesítményben, elkezdhet egy másik, az aktuális hétre tervezett, de nem feltétlenül az aktuális napra ütemezett feladatot. Ez a megközelítés lehetővé teszi a dolgozók munkatervének és a feladatok befejezésének optimalizálását.

A munkarendelésekhez kapcsolódó ütemezett végrehajtás beállítása lehet általános vagy specifikus. Beállíthat olyan általános sorokat, amelyek nem korlátozódnak meghatározott munkarendelés-típusokra, eszköztípusokra stb. Azt is megteheti, hogy olyan ütemezett végrehajtási sorokat hoz létre, amelyek egy adott munkarendelés-típusra, eszköztípusra stb. vonatkoznak.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Ütemezett végrehajtás** elemet.
2. Ha új ütemezett végrehajtást szeretne létrehozni, kattintson az **Új** elemre.
3. A **Munkavégzési helyszín**, a **Munkarendelés típusa**, az **Eszköztípus**, a **Gyártó**, a **Modell**, a **Karbantartási feladat típuskategóriája**, a **Karbantartásifeladat-típusok**, a **Karbantartási feladat típusának változata**, valamint a **Kereskedelem** mezőben válassza ki a szükséges értékeket.
4. Válassza ki a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben. Ha üresen hagyja ezt a mezőt, akkor a legáltalánosabb típusú ütemezési végrehajtási sort alkalmazhatja. Ha szeretne példát látni az általános sorhoz, tekintse meg a következő illusztráció első rekordját. Ez a sor minden olyan munkarendelést aktivál, amelyekhez nem tartozik egy adott dátumra és időpontra ütemezendő munkarendelési szolgáltatási szint.
5. Válassza ki az időintervallumot az **Ütemezett végrehajtás** mezőben.
6. Válassza a **Mentés** lehetőséget.

![1. ábra](media/20-setup-for-work-orders.png)
