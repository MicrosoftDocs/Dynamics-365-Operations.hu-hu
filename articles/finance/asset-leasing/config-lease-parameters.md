---
title: Lízingparaméterek konfigurálása (előzetes verzió)
description: Ez a témakör leírja az eszközök értékcsökkenésének konfigurációs beállításait, például a biztonsági adatokat és a könyvelési beállításokat.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e878fa7634cfdcc6c0db19a91e771757c545505b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895080"
---
# <a name="configure-lease-parameters"></a>Lízingparaméterek konfigurálása

[!include [banner](../includes/banner.md)]

Számos konfigurációs beállítás befolyásolja az Eszközlízing működését. Ezek közé a beállítások közé tartoznak a naplónevek, az általános paraméterek és a feladási profil beállításai.

1. Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.
2. A **Lízingek** fülön válassza az **Általános** gyorslapot.

    A **Manuális osztályzás felülbírálásának engedélyezése** paraméter határozza meg, hogy a lízingosztályzás felülbírálható-e a fizetési ütemezés visszautasítása előtt.

    A **Keresztentitás kötegparaméter** határozza meg, hogy feladhat-e más jogi személyekhez az aktuális jogi személytől. Ha ez a paraméter be van kapcsolva, naplóbejegyzéseket hozhat létre azon jogi személyek számára, amelyekhez hozzáférése van.

3. A Visszaigazolt **bérletek** **törlésének** engedélyezése lehetőséget Igen beállítással engedélyezheti a visszaigazolt fizetési ütemezésekkel kapcsolatos bérleti bérleti díj törlésének a beállítását. A lízingek nem törölhetők, ha feladott vagy fel nem adott tranzakciók vannak társítva, függetlenül ennek a lehetőségnek a beállításától. A lízingrekord törlés után nem állítható vissza. Ha egy törölt lízinghez tartalmazó rekordokat manuálisan vagy adatentitásokon keresztül tölt fel, a feltöltött adatokat a rendszer újként kezeli, nem pedig egy meglévő lízing frissítéseként.

    Ha ezt a beállítást **Igen** értékre állítja, és a könyv átmeneti típusa az **A vagy B kumulatív felzárkózási lehetőség**, akkor a rendszer a **Járulékos kamatláb** mezőt a **Könyv beállítása** lap átmeneti mezőjében lévő **Járulékos kamatláb váltás alatt** értékére állítja be. Ha ez a lehetőség **Nem** értékre van állítva, akkor a fő lízing kamatlába a **Könyv részletei** lap **Járulékos kamatláb** értékű lesz, függetlenül a könyv átváltási típusától.

4. Állítsa A Lezárt könyv **sztornírozása engedélyezése** **beállítást** Igen beállítással az értékcsökkenési költségtranzakciók sztornírozására. A költségtranzakciók akkor is sztornírozhatók, ha a könyv verziója le van zárva.

    > [!NOTE]
    > Javasoljuk, hogy tartsa ezt a beállítást **Nem** értéken. Ennek a lehetőségnek a beállítása ellenőrzésként és vezérlésként szolgál, hogy megakadályozza a zárt könyvverzió véletlen értékcsökkenését. Ha a beállításr **Nem** értéken tartja, akkor a nettó könyv szerinti érték és a jövőbeli értékcsökkenési számítások pontosak maradnak.

5. A Fizetés összegének **lebontásának** **engedélyezése** lehetőséget Igen beállítással engedélyezheti **a** **Fizetési ütemezési sorok gyorslapján a Bérlése lap fizetési összegének lebontását.** A fizetéslebontási típusok meghatározása a **Fizetés összegei** lap Beállítása lapján **található**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
