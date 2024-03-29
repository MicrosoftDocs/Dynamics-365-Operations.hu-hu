---
title: Szolgáltatásiszint-szerződések áttekintése
description: A szolgáltatásiszint-szerződésben a vevő elfogad egy minimális válaszidőt annak alapján, amikor a szolgáltató cég rögzíti a problémát, és amikor a probléma megoldódik.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b90618d5d283b16ac8374f3b8b2df48611ba270
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014663"
---
# <a name="service-level-agreements-overview"></a>Szolgáltatásiszint-szerződések áttekintése       

[!include [banner](../includes/banner.md)]


A szolgáltatásiszint-szerződés a vevő és a szolgáltatóvállalat közötti szerződés. A szolgáltatásiszint-szerződésben a vevő elfogad egy minimális válaszidőt annak alapján, amikor a szolgáltató cég rögzíti a problémát, és amikor a probléma megoldódik.

A szolgáltatásiszint-szerződések általános megoldást jelentenek a vevőknek nyújtott szolgáltatások bizonyos szintjének biztosítására, ezenkívül a szolgáltató vállalat számára is átláthatóvá teszik a megoldandó szervizfeladatokat.

A programban tetszőleges számú szolgáltatásiszint-szerződés létrehozható a  vevőknek nyújtott szolgáltatások különböző szintjeinek meghatározására.

## <a name="create-a-service-level-agreement"></a>Szolgáltatásiszint-szerződések létrehozása

1.  Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatási szerződések** \> **Szolgáltatásszint-szerződés** lehetőségre.

2.  A **Szolgáltatásiszint-szerződés** mezőben írja be a szolgáltatási szerződéshez kapcsolódó nevet.

3.  Adja meg a szolgáltatásiszint-szerződéshez kapcsolódó szolgáltatási hívások befejezésének kívánt idejét. Ezt követően állítsa be a naptárat, ha a szolgáltatásiszint-szerződést meghatározott naptárra szeretné alapozni.

## <a name="apply-a-service-level-agreement"></a>Szolgáltatásiszint-szerződések alkalmazása

A szolgáltatásiszint-szerződések közvetlenül alkalmazhatók a szolgáltatási szerződésekre.

Azoknál a manuálisan létrehozott szervizrendeléseknél, amelyekhez szolgáltatásiszint-szerződéssel együtt járó szolgáltatási szerződést csatol, automatikusan érvényesek a szolgáltatásiszint-szerződés feltételei.

Az automatikusan létrehozott szervizrendelésekhez a program nem csatol szolgáltatásiszint-szerződést.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Szolgáltatásiszint-szerződés alkalmazása a szolgáltatási szerződésre

1.  Kattintson a **Szolgáltatáskezelés** \> **szolgáltatási szerződések szolgáltatási** \> **szerződései hivatkozásra**. Válassza ki a szolgáltatási szerződést, amelyre a szolgáltatásiszint-szerződést szeretné alkalmazni, és kattintson a **Szerkesztés** elemre a **Műveleti ablakban**.

2.  A **Szolgáltatás szolgáltatásiszint-szerződés** mezőben, válassza ki a hozzárendelni kívánt szolgáltatásiszint-szerződést.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>A szolgáltatásiszint-szerződés alkalmazása szolgáltatási szerződések csoportjára

1.  Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatási szerződések** \> **Szolgáltatásiszerződés-csoportok** lehetőségre.

2.  A **Szolgáltatás szolgáltatásiszint-szerződés** mezőben, válassza ki a hozzárendelni kívánt szolgáltatásiszint-szerződést.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Időmérés a szolgáltatásiszint-szerződéssel érintett szervizrendelésekben

Egy szolgáltatási szerződéshez, amelyhez a szolgáltatásiszint-szerződés hozzá van rendelve, egy új szervizrendelés létrehozásakor a szállítási szolgáltatás időintervalluma elindul, és a rendszer megkezdi a szállítási idő nyomon követését. Ezenkívül a következő beállításokra is lehetőség van:

  - Elindíthatja, illetve leállíthatja a szervizrendelés idejének mérését, ezzel rögzítheti a szervizrendelések teljesítésével töltött összes időt.

  - Nyomon követheti, hogy a szolgáltatásiszint-szerződésben meghatározott időkereten belül elvégezték-e a szolgáltatást.

  - Meghatározhat olyan okkódokat is, amelyeket akkor kell beállítani, ha a szolgáltatásiszint-szerződésben meghatározott időkeretet túllépték.

## <a name="see-also"></a>Lásd még

[A szolgáltatásiszint-szerződésnek való megfelelés ellenőrzése](view-compliance-with-service-level-agreements.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]