---
title: Sablonanyagjegyzék létrehozása
description: Különböző módszerek segítségével hozhat létre sablonanyagjegyzéket.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 169b54a0509a2e11ce2e888404da10fd81db475e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678206"
---
# <a name="create-a-template-bom"></a>Sablonanyagjegyzék létrehozása   

[!include [banner](../includes/banner.md)]


Az alábbi módszerek bármelyikével létrehozhat sablonanyagjegyzéket. A **Kezdő dátum** és a **Záró dátum** mezők használata egyik esetben sem kötelező, csak tájékoztatásra szolgálnak.

## <a name="create-a-template-bom-manually"></a>Sablonanyagjegyzék létrehozása manuálisan

1.  Lépjen a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőségre.

2.  Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.

3.  Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Kézi** lehetőséget.

4.  A **Cikkszám** mezőben adjon meg egy **Anyagjegyzék** típusú cikket.

5.  Adjon nevet a sablonnak a **Név** mezőben.

6.  Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.

7.  Válassza ki az **OK** lehetőséget.

Létrejön egy új, üres sablonanyagjegyzék.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Sablonanyagjegyzék létrehozása másik sablonanyagjegyzék alapján

1.  Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.

2.  Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.

3.  Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék-sablon** lehetőséget.

4.  A **Hivatkozási szám** mezőben válasszon egy létező sablonanyagjegyzéket, amelyet átmásol az új sablonanyagjegyzékbe.

5.  Adjon nevet a sablonnak a **Név** mezőben.

6.  Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.

7.  Válassza ki az **OK** lehetőséget.

Egy új sablonanyagjegyzék jön létre az eredeti sablonanyagjegyzék soraival megegyező sorokkal.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Sablonanyagjegyzék létrehozása cikkanyagjegyzék alapján

1.  Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.

2.  Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.

3.  Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be az **Anyagjegyzék** lehetőséget.

4.  A **Hivatkozási szám** mezőben, válasszon ki egy anyagjegyzék-verziót. Egy anyagjegyzék típusú cikket másol a program a **Cikkszám** mezőbe.

5.  Adjon nevet a sablonnak a **Név** mezőben.

6.  Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.

7.  Válassza ki az **OK** lehetőséget.

Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **Anyagjegyzékek** mezőben szereplő anyagjegyzéknek.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Sablonanyagjegyzék létrehozása termelési anyagjegyzék alapján

1.  Válassza a **Szolgáltatáskezelés** \> **Beállítás** \> **A szolgáltatás tárgyai** \> **Sablonanyagjegyzékek** lehetőséget.

2.  Válassza az **Új** elemet, hogy megnyissa a **Sablonanyagjegyzék létrehozása** képernyőt.

3.  Az **Anyagjegyzéksorok másolása hivatkozásból** elemnél jelölje be a **Termelés** lehetőséget.

4.  A **Hivatkozási szám** mezőben, válasszon ki egy termelési anyagjegyzéket.

5.  Adjon nevet a sablonnak a **Név** mezőben.

6.  Adja meg a **Kezdő dátum** és a **Záró dátum** mezőben azt a dátumintervallumot, amelyben aktív a sablonanyagjegyzék.

7.  Válassza ki az **OK** lehetőséget.

Létrejön egy új sablonanyagjegyzék azoknak a soroknak a felhasználásával, amelyek megfelelnek az **AJ** mezőben szereplő anyagjegyzéknek.

## <a name="see-also"></a>Lásd még

[Sablonanyagjegyzékek](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]