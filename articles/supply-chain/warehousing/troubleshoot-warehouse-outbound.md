---
title: Kimenő raktári műveletek – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a kimenő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 919b6f433db47f24adc9a474942557a1467d1f71
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828178"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Kimenő raktári műveletek – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a kimenő raktári műveleteket végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>A következő hibaüzenet jelenik meg: „Az értékesítési rendelés nem adható ki.”

### <a name="issue-description"></a>Probléma leírása

Ez a hiba több okból is előfordulhat. Például a rendelés hitelkezelés várakozási listán van, és a rendszer nem hozhat létre szállítmányokat mindaddig, amíg az értékesítési rendeléshez társított összes értékesítési sorhoz érvényes postai címet nem ír be. Azt is megteheti, hogy a rendelés várakoztatását a raktárba történő kiadás előtt megoldja. Ez a várakoztatás lehet rendeléssel vagy vevői fiókkal kapcsolatos.

### <a name="issue-resolution"></a>Probléma megoldása

Adja hozzá vagy frissítse a címet az értékesítési rendelés és a rendelési sorokban, majd adja ki a rendelést a raktárba. A rendelések csak akkor adhatók ki a raktárba, ha rendelkeznek érvényes szállítási címmel (a **Szervezet adminisztrációs** moduljának címformátumának beállításával).

Vizsgálja meg a rendelés visszatartását, és oldja meg a problémákat. Ezután távolítsa el a rendelésből vagy a vevőtől a várakoztatást, és adja ki a rendelést a raktárba.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>A következő üzenet jelenik meg: „A(z) 1% rakomány szállítása visszaigazolva”. A sorok azonban nem kerülnek feladásra.

### <a name="issue-description"></a>Probléma leírása

A rakomány szállítása megtörtént, de a feladás nem.

### <a name="issue-resolution"></a>Probléma megoldása

A szállítmány visszaigazolása nem befolyásolja a feladást. Csak a szállítás és a rakomány állapotának frissítése. A feladásnak egy külön folyamatban kell lennie.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>A következő hibaüzenet jelenik meg: „A közvetlen kiszállítás nem tudja feldolgozni az 1% raktárat, mert engedélyezve van a raktárkezelés. Adjon meg egy másik raktárat, amelyben nincs engedélyezve a raktárkezelés.”

### <a name="issue-description"></a>Probléma leírása

A cikkek egy értékesítési sorhoz kerülnek a közvetlen kiszállításhoz a raktárkezelés (WMS) számára engedélyezett raktárból. Ez a hibaüzenet jelenik meg az értékesítési sor frissítésekor. 

### <a name="issue-resolution"></a>Probléma megoldása

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. Jelenleg a WMS nem támogatja a közvetlen kiszállítást. Ezért a közvetlen kiszállítás használatához ki kell választania egy nem WMS-típusú terméket és raktárat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]