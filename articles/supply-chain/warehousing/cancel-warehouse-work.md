---
title: A kivétel kezelésére vonatkozó raktári munka visszavonása
description: Ez a témakör a munka megszakítására használható funkciókat írja le, amelyek segítségével a raktárvezetők kezelni tudnák a zárolt munkát.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9404421"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>A kivétel kezelésére vonatkozó raktári munka visszavonása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management visszavonási funkciói lehetővé teszi a rendszergazda felhasználó számára a jelenleg folyamatban lévő, de a rendszer által blokkolt, illetve kivételes körülmények miatt nem teljesíthető raktári munkát. Ez a funkció vonzó és biztonságos alternatívája az SQL-javító parancsfájloknak, amelyek a nem konzisztens adatokat javítják. Bár ezeket a forgatókönyveket jellemzően informatikai szakemberek kérik, a visszavonási funkciókat a vállalat rendszergazdai jogokkal dolgozó felhasználói használhatja.

A Mégse funkcióhoz **a** \> **·** \> **Raktárkezelés időszakos feladatai – A mégse munka törlése funkció is \> elérhető.** A **Munka érvénytelenítése** párbeszédpanelen adja meg az érvényteleníteni kívánt munka munkaazonosítóját, majd kattintson az **OK** gombra.

## <a name="warehouse-work-that-can-be-canceled"></a>Nem érvényteleníthető raktári munka

A raktári kitárolási műveletek során előfordulhat, hogy a dolgozó olyan helyzetekkel találkozik, amikor a tárolási helyről bejegyezték a saját felhasználói helyükre, de ekkor nem tudják regisztrálni a betárolási műveletet. Az inkonzisztens raktári adatok gyakran, de nem mindig a munka blokkolásának okát jelentik.

**Ellentétben** a rendszeres visszavonási funkcióval, amely a munkafejléc Mégse gombjával érhető el, a mégse munkafunkcióhoz nem szükséges, hogy az **utolsó** befejezett munkasor berakodva legyen. Más szóval a munka visszavonása esetén az érvénytelenítési logika akkor is futtatható, ha a munkasor cikkmennyisége felhasználói helyen van.

> [!NOTE]
> Olyan munka esetén, amely üzemeltetési okokból vissza kell függesnie a raktári felhasználóktól, a munkalapon továbbra is a szokásos megszakítási funkciókat kell használniuk.

Csak az Értékesítés, Áttárolási **·** **kiadás**, Nyersanyag-kitárolás **·** **vagy** Feltöltés típusú munka érvénytelenedhet a munka megszakítása funkcióval. A befagyasztott nyersanyag-kitárolási munkához vagy az általános érvénytelenítési funkcióval visszavonható munkához nem lehet érvénytelenítési logikát futtatni (lásd az előző megjegyzést).

A munka blokkolásának feloldásához a rendszer törli a hátralévő munkasorokat, és rögzíti a munkaazonosítóhoz társított felhasználó által megadott raktári adatokat. A program ezután folytatja az érintett cikkmennyiséget magába foglaló szokásos raktárkezelési műveleteket.

Ha azt szeretné, hogy az érintett elem egy meghatározott helyre kerüljön a munka érvénytelenítése után, a felhasználónak egy készletmozgatás mennyiségi helyesbítési műveletét kell használnia egy mobileszközön.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]