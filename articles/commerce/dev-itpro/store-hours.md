---
title: Nyitvatartási idő létrehozása és frissítése
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni és frissíteni az áruházi órákat a Commerce Headquarters szolgáltatásban.
author: josaw1
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: 000cd02a908ae005c37f9232361a6e7d201f4330
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279595"
---
# <a name="create-and-update-store-hours"></a>Nyitvatartási idő létrehozása és frissítése

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A kiskereskedők egyetlen helyről végezhetik a különböző földrajzi régiókban található üzletek nyitvatartási idejének létrehozását, karbantartását és kezelését. A nyitvatartási idő ezután megjeleníthető a pénztári (POS) terminálokon. Így a pénztárosok megoszthatják a nyitvatartási időt a vevőkkel, és hatékonyabban segíthetnek azokat a vásárlóknak, akik más üzletek készlete iránt érdeklődnek. A nyitvatartási idő a nyugtákra is rányomtatható, az üzletbe később visszatérni kívánó vevők tájékoztatására.

A különböző csatornákhoz több nyitvatartási idő is konfigurálható. Ilyen csatornák a fizikai üzlethelyiségek, a telefonos ügyfélszolgálatok, a mobileszközök és az elektronikus kereskedelmi webhelyek.

Ha egy vevőnek egy másik üzletben felvehető rendelése van, akkor a pénztáros kiválaszthatja azokat a dátumokat, amikor a rendelés felvehetővé válik abban az üzletben. Az üzletkeresésben megjelennek a dátumok és a nyitvatartási idők. A pénztáros kiválaszthat egy dátumot és helyet, valamint kinyomtathat egy átvételi bizonylatot is, amely tartalmazza az üzlet nyitvatartási idejét.

Ez a funkció a Microsoft Dynamics 365 Retail 8.1.2-es és későbbi verzióiban áll rendelkezésre.

## <a name="configure-store-hours"></a>Nyitvatartási idő konfigurálása

A nyitvatartási idő konfigurálásához kövesse az alábbi lépéseket.

1. Ugorjon a következő oldalra: **Retail és Commerce** \> **Csatorna beállítása** \> **Nyitvatartás**.
2. Válassza az **Új** lehetőséget új nyitvatartásiidő-sablon létrehozásához. Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán.
3. A **Tartomány hozzáadása** párbeszédpanelen adja meg a dátumtartományt, a nyitvatartási időt, valamint az esetleges ünnepnapokat.

    - Ha a nyitvatartási idő nem változik, válassza a **Nem ér véget** lehetőséget a **Záró dátum** mezőben.
    - Ha a nyitvatartási idő egy adott hónapra, hétre vagy napra vonatkozik, állítsa be a megfelelő dátumokat a **Kezdő dátum** és a **Záró dátum** mezőben.

    > [!NOTE]
    > Több sablont is létrehozhat, egymást átfedő kezdő és a záró dátumokkal. Így például megadhatja a különböző időzónákban található üzletek nyitvatartási idejét.

    ![Tartomány hozzáadása párbeszédpanel.](../dev-itpro/media/Storehours1.png "Tartomány hozzáadása párbeszédpanel")

4. A nyitvatartási idő sablonját társítsa azokkal az üzletekkel, ahol használatban lesz. A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.

    - Minden üzlethez csak egy nyitvatartásiidő-sablon tartozhat.
    - A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket. A naptár az üzletek vagy üzletcsoportok számára lesz hozzáférhető, és a pénztárnál is megjelenik referenciaként.

    ![Szervezeti csomópontok párbeszédpanel kiválasztása.](../dev-itpro/media/Storehours2.png "Szervezeti csomópontok párbeszédpanel kiválasztása")

5. Az **Elosztási ütemezés** oldalon futtassa a **1070** és **1090** feladatokat, hogy a nyitvatartási időt elérhetővé tegye a pénztárnál.

## <a name="add-store-hours-to-printed-receipts"></a>Nyitvatartási idő hozzáadása a nyomtatott nyugtákhoz

A nyitvatartási idő kinyomtatott pénztári nyugtákon való feltüntetéséhez kövesse az alábbi lépéseket.

1. Nyissa meg a nyugtatervezőt.
2. Válassza ki a **Lábléc** elemet a bal alsó sarokban.
3. Húzza át a **Nyitvatartás** elemet a bal oldali ablaktáblából a nyugta sablonjának alján található láblécbe.
4. A **Nyitvatartás** elem alapértelmezett feliratát igény szerint szerkesztheti.
5. Mentse a nyugtát, és zárja be a nyugtatervezőt.
6. Az **Elosztási ütemezés** lapon futtassa a **1070** és a **1090** feladatot.
7. Bejelentkezés a pénztárba.
8. Hajtson végre egy értékesítést, és válassza a nyugta nyomtatását.

A pénztári nyugtákon ettől kezdve megjelenik a nyitvatartási idő. Ha a sablonban egy vagy több ünnepnap is meg van adva, akkor azok is megjelennek a nyugtán.

![Példanyugta.](../dev-itpro/media/Storehours3.png "Példanyugta")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
