---
title: Raktár beállítása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani egy raktárat a Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 476f78d7fe1bc61c2c9b783ed1f82bc660248b02
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273639"
---
# <a name="warehouse-set-up"></a>Raktár beállítása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani egy raktárat a Microsoft Dynamics 365 Commerce.

Minden egyes Commerce-csatornához hozzá kell rendelni egy konfigurált raktárat. A következő eljárások a Commerce csatorna raktárának beállításához szükséges minimális konfigurációját nyújtják. A raktár beállításaival kapcsolatos további tudnivalókat lásd a [Raktárkezelés – áttekintés](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json) című témakörben.

## <a name="configure-a-warehouse-site"></a>Raktár webhelyének konfigurálása

A raktár beállítása előtt konfigurálnia kell egy raktári webhelyet.

A raktári webhely konfigurálásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Webhelyek** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Webhely** mezőben adjon meg egy értéket.
1. A **Név** mezőben adjon meg egy értéket.
1. Az **Általános** szakaszban adja meg a megfelelő **időzónát**.
1. A **Címek** szakaszban adjon meg egy címet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép egy példát mutat a raktárwebhelyre.

![Példa: raktárwebhely.](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Raktár beállítása

Raktár beállításához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Raktár** mezőben adjon meg egy értéket.  Ha ez egy 1:1 hozzárendelés egy üzlethez, vegye fontolóra az üzlet nevének vagy egy területi elosztó központ nevének használatát.
1. A **Név** mezőben adjon meg egy értéket.
1. A **webhely** legördülő listában válassza ki a korábban létrehozott raktári webhelyet.
1. A **Típus** mezőben válassza ki az **Alapértelmezett** lehetőséget.
    - Ha meg kívánja adni a **karanténraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Karantén**.
    - Ha meg kívánja adni a **Tranzitraktárat**, akkor az alábbi lépések követésével hozzon létre egy olyan további raktárat, amelyben a **Típus** legyen **Tranzit**.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="set-up-inventory-aisles"></a>Raktárfolyosók beállítása

A készletfolyosók beállításához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Hely beállítása \> Készletfolyosók** részhez.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Raktár** legördülő listában válassza ki a korábban létrehozott raktárat.
1. A **Folyosó** mezőben adjon meg egy nevet (például „Def”).
1. A **Név** mezőben adjon meg egy nevet (például „Alapértelmezett folyosó”).
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="set-up-warehouse-inventory-locations"></a>Raktári készlethelyek beállítása

A szokásos, sérült és visszaküldött készlet raktári készlethelyének beállításához hajtsa végre az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.
1. Válassza ki a korábban létrehozott raktárat.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A műveleti ablaktáblán válassza a **Raktár** elemet, majd válassza ki a **Készlet helyét**.
1. A műveleti ablaktáblán kattintson az **Új** elemre. A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.
    1. A **folyosó** mezőbe írja be a korábban megadott folyosó nevét. 
    1. Állítsa a **Manuális frissítés** értékét **Igen** értékét
    1. A **Hely** mezőbe írja be a raktár nevét.
    1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
 1. A műveleti ablaktáblán kattintson az **Új** elemre.  A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.
    1. A **folyosó** mezőbe írja be a korábban megadott folyosó nevét.  
    1. Állítsa a **Manuális frissítés** értékét **Igen** értékét
    1. A **Hely** mezőbe írja be a „Sérült” értéket.
    1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
 1. A műveleti ablaktáblán kattintson az **Új** elemre.  A **raktár** legördülő listájának alapértelmezett értéke az új raktárnak kell lennie.
    1. A **folyosó** mezőbe írja be a korábban megadott folyosó nevét. 
    1. Állítsa a **Manuális frissítés** értékét **Igen** értékét
    1. A **Hely** mezőbe írja be a „Visszáruk” értéket.
    1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    
A következő képen a San Francisco raktár készlethely beállítása látható.

![Példa raktári hely beállítására.](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Teljes raktári beállítás

Ennek a raktárbeállításnak a befejezéséhez kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán lépjen a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornák beállítása \> Raktárak** részhez.
1. Válassza ki a korábban létrehozott raktárat.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Készlet- és raktárkezelés** részben:
    1. **Alapértelmezett nyugta helyének** állítsa be a fent létrehozott alapértelmezett helyet.
    1. **Alapértelmezett kibocsátási helynek** válassza ki a fent létrehozott alapértelmezett helyet.
1. A **címek** szakaszban adja meg a raktári címet.
1. A **kiskereskedelmi** szakasz keretében: 
    1. Az **Alapértelmezett visszáruhely** mezőbe írja be a korábban létrehozott visszáru helyet.
    1. Állítsa az **Üzlet** beállítását **Igen** értékre.
    1. A **Tömeget** állítsa a **1,00** értékre. 
    1. A **tárolási dimenziók** mezőbe írja be a korábban létrehozott alapértelmezett helyet.
1. A **Raktár** szakaszban állítsa a **Tényleges negatív készlet** értékét **Igen** értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

A következő kép a konfigurált raktár adatait jeleníti meg.

![Példa konfigurált raktárra.](media/warehouse-sample.png)

## <a name="additional-resources"></a>További erőforrások

[Raktárkezelés áttekintése](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Csatornák áttekintése](channels-overview.md)

[Csatornák beállításának előfeltételei](channels-prerequisites.md)

[Kiskereskedelmi csatorna beállítása](channel-setup-retail.md)
    
[Online csatorna beállítása](channel-setup-online.md)

[Hívásközpont csatorna beállítása](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
