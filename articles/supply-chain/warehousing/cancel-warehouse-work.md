---
title: A kivétel kezelésére vonatkozó raktári munka visszavonása
description: Ez a témakör a Munka érvénytelenítése funkciót mutatja be, amellyel a raktár felügyelői kezelhetik a blokkolt munkát.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ae4062401cd5be2371c45642b78bf3708b04f664
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001198"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>A kivétel kezelésére vonatkozó raktári munka visszavonása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management Munk érvénytelenítése funkciója lehetővé teszi az adminisztrátor felhasználó számára, hogy jelenleg folyamatban lévő konkrét raktári munkát töröljön, de amit a rendszer blokkolt, vagy nem hajtható végre rendkívüli körülmények miatt. Ez a funkció vonzó és biztonságos alternatívája az SQL-javító parancsfájloknak, amelyek a nem konzisztens adatokat javítják. Azonban mivel ezeket a parancsfájlokat általában informatikai szakemberektől kell kérni, a munka visszavonása funkciót a vállalat rendszergazdai jogosultságokkal rendelkező felhasználói használhatják.

A Munka érvénytelenítése funkciót a **Raktárkezelési** \> **Ismétlődő feladatok** \> **Tisztítás \> Munka érvénytelenítése** helyen érheti el. A **Munka érvénytelenítése** párbeszédpanelen adja meg az érvényteleníteni kívánt munka munkaazonosítóját, majd kattintson az **OK** gombra.

## <a name="warehouse-work-that-can-be-canceled"></a>Nem érvényteleníthető raktári munka

A raktári kitárolási műveletek során előfordulhat, hogy a dolgozó olyan helyzetekkel találkozik, amikor a tárolási helyről bejegyezték a saját felhasználói helyükre, de ekkor nem tudják regisztrálni a betárolási műveletet. Az inkonzisztens raktári adatok gyakran, de nem mindig a munka blokkolásának okát jelentik.

A szokásos Érvénytelenítés funkcióval szemben, amely az **Érvénytelenítés** gombbal érhető el a munka fejlécében a Munka érvénytelenítése funkcióhoz nem szükséges, hogy az utolsó befejezett munkasor **betárolás** típusú legyen. Más szóval a munka érvénytelenítése funkció esetében a visszavonási logika akkor is futtatható, ha egy munkasorban szereplő cikkmennyiség egy felhasználói helyen van.

> [!NOTE]
> A működési okokból érvénytelenítendő munkákhoz a raktári felhasználók toovábbra is a szokásos Érvénytelenítés funkciót kell használják a munka oldalon.

A munka visszavonása funkcióval csak az **Értékesítés**, **Átmozgatási probléma** **Nyersanyag kitárolása** vagy **Újratöltés** típusok érvényteleníthetők. Az érvénytelenítési logika nem futtatható a nyersanyag-kitárolási munkához vagy olyan munkához, amelyet a szokásos megszakítás funkcióval is érvényteleníteni lehet (lásd az előző megjegyzést).

A munka blokkolásának feloldásához a rendszer törli a hátralévő munkasorokat, és rögzíti a munkaazonosítóhoz társított felhasználó által megadott raktári adatokat. A program ezután folytatja az érintett cikkmennyiséget magába foglaló szokásos raktárkezelési műveleteket.

Ha azt szeretné, hogy az érintett elem egy meghatározott helyre kerüljön a munka érvénytelenítése után, a felhasználónak egy készletmozgatás mennyiségi helyesbítési műveletét kell használnia egy mobileszközön.
