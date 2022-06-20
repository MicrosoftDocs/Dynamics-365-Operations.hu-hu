---
title: Fizetés összegtípusának hozzáadása
description: Ez a cikk bemutatja, hogyan lehet beállítani a fizetési összegtípusokat a Tárgyi eszköz eszköztípusban.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 03fc903e6cfe78ef2fed7e3a0744a8f809f6892d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891609"
---
# <a name="add-payment-amount-types"></a>Fizetés összegtípusának hozzáadása

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani a fizetési összegtípusokat a Tárgyi eszköztípusban. Ily módon a fizetési ütemezés soraiba történő felvétele helyett lehetőség van a bérletfizetés összegének tételére.

A kifizetési összegtípusok hozzáadásához kövesse az alábbi lépéseket.

1. Ugrás a Tárgyi **eszköz beállításához \> – \> Kifizetés összegtípusa**
2. Válassza az **Új** lehetőséget.
3. Adja meg az új fizetéstípust és leírást.

> [!NOTE]
> Az IFRS 16 index átértékelése esetén létre kell hozni egy kifizetési összegtípust, **és azt kell megjelölni az IRFS 16 index átértékelésére használtként**. Ezt a kifizetési összegtípust használja a rendszer, amikor az index-átértékelési folyamat az IFRS 16 könyvvel szemben fut le, és figyelembe veszi az index-átértékelési folyamat miatt bekövetkezett változásokat.
>
> **·** **Ha** a bérlet kifizetéslebontási beállítása Igen, ha fut az IFRS 16 indexátértékelése, de az IFRS 16 kifizetéstípusa nincs, akkor a folyamat nem fog befejeződni.

Csak egy rekordot lehet **megjelölni Az IFRS 16 index átértékelésében használtként**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
