---
title: Lízingparaméterek konfigurálása (előzetes verzió)
description: Ez a témakör az Eszközlízing konfigurációs beállításait ismerteti, például a biztonsági információkat és a számlázási beállításokat.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f71006570cd8f2bdc0385388eae0800cd29d3ec8
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444179"
---
# <a name="configure-lease-parameters"></a>Lízingparaméterek konfigurálása

[!include [banner](../includes/banner.md)]

Számos konfigurációs beállítás befolyásolja az Eszközlízing működését. Ezek közé a beállítások közé tartoznak a naplónevek, az általános paraméterek és a feladási profil beállításai.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.
2. A **Lízingek** fülön válassza az **Általános** gyorslapot.

    A **Manuális osztályzás felülbírálásának engedélyezése** paraméter határozza meg, hogy a lízingosztályzás felülbírálható-e a fizetési ütemezés visszautasítása előtt.

    Az **Entitások közötti köteg** paraméter határozza meg, hogy könyvelhet-e más jogi személyeknek az aktuális jogi személytől. Ha ez a paraméter be van kapcsolva, naplóbejegyzéseket hozhat létre azon jogi személyek számára, amelyekhez hozzáférése van.

3. A **Visszaigazolt lízingek törlésének engedélyezése** beállítást állítsa **Igen** értékre a visszaigazolt fizetési ütemezéseket tartalmazó lízingek törlésének engedélyezéséhez. A lízingek nem törölhetők, ha feladott vagy fel nem adott tranzakciók vannak társítva, függetlenül ennek a lehetőségnek a beállításától. A lízingrekord törlés után nem állítható vissza. Ha egy törölt lízinghez tartalmazó rekordokat manuálisan vagy adatentitásokon keresztül tölt fel, a feltöltött adatokat a rendszer újként kezeli, nem pedig egy meglévő lízing frissítéseként.

    Ha ezt a beállítást **Igen** értékre állítja, és a könyv átmeneti típusa az **A vagy B kumulatív felzárkózási lehetőség**, akkor a rendszer a **Járulékos kamatláb** mezőt a **Könyv beállítása** lap átmeneti mezőjében lévő **Járulékos kamatláb váltás alatt** értékére állítja be. Ha ez a lehetőség **Nem** értékre van állítva, akkor a fő lízing kamatlába a **Könyv részletei** lap **Járulékos kamatláb** értékű lesz, függetlenül a könyv átváltási típusától.

4. Állítsa az **Értékcsökkenés sztornírozásának engedélyezése a lezárt könyv verzión** beállítást **Igen** értékre az értékcsökkenési költség tranzakciók sztornírozásának engedélyezéséhez. A költségtranzakciók akkor is sztornírozhatók, ha a könyv verziója le van zárva.

    > [!NOTE]
    > Javasoljuk, hogy tartsa ezt a beállítást **Nem** értéken. Ennek a lehetőségnek a beállítása ellenőrzésként és vezérlésként szolgál, hogy megakadályozza a zárt könyvverzió véletlen értékcsökkenését. Ha a beállításr **Nem** értéken tartja, akkor a nettó könyv szerinti érték és a jövőbeli értékcsökkenési számítások pontosak maradnak.