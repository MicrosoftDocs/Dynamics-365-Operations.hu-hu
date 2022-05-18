---
title: Adóinformációk rányomtatása az átmozgatási rendelésekre
description: Ez a témakör leírja, hogy hogyan nyomtathatók az adószámítási szolgáltatás által meghatározott adóinformációk az átmozgatási rendelések dokumentumaira.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e74336270ab46fc19adb4c797745c9582028391a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687471"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Adóinformációk rányomtatása az átmozgatási rendelésekre

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti az adóinformációk rányomtatását az átmozgatási rendelésekre. Kinyomtathatja átmozgatási rendelés proforma számladokumentumát olyan készletátvitelekhez, amelyek közösségen belüli szállításnak és közösségen belüli beszerzésnek minősülnek az Európai Unió (EU) áfa (ÁFA) rendelkezései alapján. 

Az átmozgatási rendelés dokumentumaihoz a következő adózási adatok kerülnek:

- A készletátvitelhez tartozó kiindulási és szállítási címek
- A szállító és a címzett adóazonosítószámai
- A szállított áruk egységára és adóköteles összege
- Az adókód, az adó mértéke, az adóösszeg és az adóügyi irányelvek

Az adatok konfigurálása érdekében a következő fő lépéseket kell végrehajtania.

1. [Az átátviteli rendelések adófunkciójának engedélyezése és beállítása](tasks/Tax-feature-support-for-transfer-order.md).
2. [Több adószám létrehozása és beállítása egy jogi személyhez](emea-multiple-vat-registration-numbers.md).
3. Állítsa be a mentességi kódot, a leírást, az adóügyi irányelveket, és nyomtassa ki a kódot az adókódok között. Ebben a példában három Microsoft Dynamics adókódot hoz létre és szinkronizál a 365 Pénzügyben: **NL-Exempt**, **BE-RC-21** és **BE-RC+21**.

    1. A Finance-ben lépjen az **Adó** \> **Beállítás** \> **Áfa** \> **Áfamentességi kódok** menüpontra.
    2. Válassza a **Szerkesztés** lehetőséget, és adja meg az **EU** mentességi kód leírását. Például írja be az **Adómentes EK-szállítmányok adóregisztrációs számmal** értéket.
    3. Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.
    4. Válassza ki a **BE-RC-21** adókódot, majd válassza ki az **Adóügyi irányelvek** lehetőséget.
    5. Válassza az **Új** lehetőséget.
    6. A **Nyelv** mezőben válassza az **EN-US** kódot. Ezután a **Szöveg** mezőbe írja be a **Dokumentum, amely meghatározza az áruszállítást a 2006/112/EK EU Áfa irányelv 138. 2. c) cikkelye szerint** szöveget.
    7. Zárja be a lapot.
    8. Válassza az **Áfakulcsot** az **Általános** gyorslap **Nyomtatás** mezőjében.
    8. Válassza ki az **NL-Exempt** adókódot, majd az **Általános** gyorslapon a **Nyomtatás** mezőben válassza az **Áfakulcs** lehetőséget.

    > [!NOTE] 
    > Az adókód, az áfakulcs és az adómentesség leírása nem lesz kinyomtatva az átviteli rendelési dokumentumaira, ha az adókódhoz nincsenek karbantartva mentességi kód leírások és adóügyi irányelvek.

## <a name="print-the-transfer-order---shipment-document"></a>Átmozgatási rendelés – szállítási dokumentum nyomtatása

Az átmozgatási rendelés szállítását követően a következő lépésekkel lehet kinyomtatni az átszállítási rendelés - szállítmány dokumentumot.

1. Ugrás a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Átmozgatási rendelések** \> **Szállítmány** részre.
2. A **Paraméterek** lap **Nyomtatás** csoportjában engedélyezze az **Adóinformáció** elemet.
3. A **Belefoglalandó rekordok** lapon válassza a **Szűrő** lehetőséget, válassza ki az átmozgatási rendelés számát, majd válassza az **OK** gombot.
4. Átmozgatási rendelés – szállítási dokumentum nyomtatásához válassza az **OK** gombot.

## <a name="print-the-transfer-order---receipt-document"></a>Átmozgatási rendelés – átvételi dokumentum nyomtatása

Az átmozgatási rendelés fogadását követően a következő lépésekkel lehet kinyomtatni az átszállítási rendelés - átvétel dokumentumot.

1. Ugrás a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Átmozgatási rendelések** \> **Fogadás** részre.
2. A **Paraméterek** lap **Nyomtatás** csoportjában engedélyezze az **Adóinformáció** elemet.
3. A **Belefoglalandó rekordok** lapon válassza a **Szűrő** lehetőséget, válassza ki az átmozgatási rendelés számát, majd válassza az **OK** gombot.
4. Átmozgatási rendelés – átvételi dokumentum nyomtatásához válassza az **OK** gombot.

## <a name="print-the-transfer-overview-document"></a>Az átvétel összefoglaló dokumentumának nyomtatása

A következő lépések szerint nyomtathatja ki az átviteli áttekintő dokumentumot.

> [!NOTE]
> Az adóinformációk csak akkor érhetők el, ha az átmozgatási rendelés már le van szállítva vagy beérkezett.

1. Ugrás a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Átmozgatási rendelések** \> **Átmozgatás áttekintése** részre.
2. A **Paraméterek** lap **Nyomtatás** csoportjában engedélyezze az **Adóinformáció** elemet.
3. A **Belefoglalandó rekordok** lapon válassza a **Szűrő** lehetőséget, válassza ki az átmozgatási rendelés számát, majd válassza az **OK** gombot.
4. Átmozgatási áttekintés dokumentum nyomtatásához válassza az **OK** gombot.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
