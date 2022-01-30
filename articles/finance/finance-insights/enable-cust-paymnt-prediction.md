---
title: Az ügyfélfizetési előrejelzések lehetővé tétele
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 5002fc79842bef150892347a7ff4702b07cfe5be
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968877"
---
# <a name="enable-customer-payment-predictions"></a>Az ügyfélfizetési előrejelzések lehetővé tétele

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben. Bekapcsolja a funkciót a Szolgáltatáskezelés munkaterületen, és a konfigurációs beállításokat a Pénzügyi információk konfigurációs **oldalon** adja **meg**. Ez a témakör olyan információkat is tartalmaz, amelyek segíthetnek a funkció hatékony használatában.

> [!NOTE]
> A következő lépések elvégzése előtt mindenképpen hajtsa végre az előfeltételeket a [Pénzügyi elemzések konfigurálása](configure-for-fin-insites.md) témakörben.

1. A Vevői kifizetések előrejelzése funkció bekapcsolva:

    1. Nyissa meg a **Funkciókezelés** munkaterületet.
    2. Válassza a **Frissítések keresése** elemet.
    3. A **Mind** lapon keresse meg a **vevői kifizetések előrejelzéseit**. Ha nem találja ezt a funkciót, keresse meg a vevői kifizetések **előrejelzéseit (előnézet).** 
    4. A funkció bekapcsolva.

    A Vevői kifizetések előrejelzése szolgáltatás be van kapcsolva, és konfigurálható.

2. Konfigurálja az Ügyfél fizetési elemzés funkciót:

    1. Ugrás **a Jóváírás és beszedések \> – Beállítás \> pénzügye – \> vevői kifizetési** előrejelzésekhez.
    2. A Pénzügyi információk konfigurációs lapján, a Vevői kifizetések előrejelzése lapon válassza az Előrejelzési modellben használt adatmezők megtekintése lehetőséget az Előrejelzési modell **oldalának** **·** **·** **megnyitásához**. Itt megtekintheti a mesterséges intelligencia (AI) előrejelzési modelljének létrehozásához használt mezők alapértelmezett listáját az ügyfelek fizetési előrejelzéseihez.

        Ha az előrejelzési modell létrehozásához a mezők alapértelmezett listáját szeretné használni, zárja be az Előrejelzési modell oldal adatmezőit, majd a Pénzügyi információk konfigurációs lapján állítsa a Funkció engedélyezése lehetőséget **Igen** **·** **·** **beállításra**.

    3. Adja meg a „nagyon későn” tranzakciós időszakot annak meghatározásához, hogy mit jelent a **Nagyon későn** előrejelzési gyűjtő a vállalkozás számára.

        Minden nyitott számla esetében a rendszer három gyűjtőben jelzi előre meg a fizetés valószínűségét: **Időben**, **Későn** és **Nagyon későn**.

        - **Időben** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek előre jelzett kifizetése a tranzakció esedékességi dátumán vagy előtte történik.
        - **Későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a tranzakció esedékességi dátuma után, de a „nagyon késő” tranzakciós időszak kezdete előtt kerülnek kifizetésre.
        - **Nagyon későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a „nagyon késő” tranzakciós időszak kezdete után kerülnek kifizetésre.

        > [!NOTE]
        > Ha módosítja a „nagyon későn” tranzakciós időszakot, és a **Későn küszöbérték módosítása** lehetőséget választja a vevői kifizetések előrejelzési modelljének létrehozása után, a meglévő előrejelzési modell törlődik, és egy új modell jön létre. Az új előrejelzési modell a tranzakciókat a „nagyon későn” időszakba mozgatja a definiáláshoz megadott beállítások alapján.

    4. Miután befejezte a „nagyon későn” tranzakciós időszak definiálását, válassza az **Előrejelzési modell létrehozása** lehetőséget az előrejelzési modell létrehozásához. A Pénzügyi információk konfigurációs lap előrejelzési modell szakasza **az** **előrejelzési** modell állapotát mutatja.

        > [!NOTE]
        > Az előrejelzési modell létrehozása közben bármikor kiválaszthatja a **Modell létrehozásának visszaállítása** lehetőséget a folyamat újraindításához.

    A funkció most már konfigurálva van, és készen áll a használatra.

Miután a funkció be van kapcsolva és konfigurálva van, és az előrejelzési modell létrejött és működik, a Pénzügyi információk paraméterei lap Előrejelzési modell szakasza bemutatja a **modell** **pontosságát**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
