---
title: Elektronikus üzenetek funkcióval való munkavégzés
description: Ez a témakör az Elektronikus üzenetek (EM) funkció használatáról tartalmaz információt.
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a65971fa1da60b00bb525d450c0eb59aee57116e
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8733763"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Elektronikus üzenetek funkcióval való munkavégzés

[!include [banner](../includes/banner.md)]

Ha az üzenet szintjén dolgozik, az **Elektronikus üzenetek** oldal (**Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetek**) hasznosabb. Ha az adatgyűjtés vagy az üzenetelem szintjén dolgozik, az **Elektronikus üzenetelemek** oldal (**Adó** \> **Lekérdezések és jelentések** \> **Elektronikus üzenetek** \> **Elektronikus üzenetelemek**) hasznosabb.

## <a name="electronic-messages"></a>Elektronikus üzenetek

A **Elektronikus üzenetek** oldal bemutatja az Ön számára rendelkezésre álló feldolgozást, a szerepkörének megfelelően. A biztonsági szerepköröket a feldolgozás beállításakor társítják a feldolgozáshoz. Minden egyes rendelkezésre álló feldolgozásra vonatkozóan az oldal megjeleníti az elektronikus üzeneteket és a hozzájuk kapcsolódó információt.

Az **Üzenetek** gyorslap a kijelölt feldolgozáshoz jeleníti meg az elektronikus üzeneteket. A kiválasztott üzenet állapotától és az előre meghatározott feldolgozástól függően néhány műveletet a rács feletti gombokkal futtathat:

- **Új** – Ez a gomb az **Üzenet létrehozása** típusú műveletekhez van társítva.
- **Törlés** – Ez a gomb akkor érhető el, ha a **Törlés engedélyezése** jelölőnégyzet be van jelölve a kiválasztott üzenet aktuális állapotához.
- **Adatgyűjtés** – Ez a gomb a **Rekordok feltöltése** típusú műveletekhez van társítva.
- **Jelentés létrehozása** – Ez a gomb az **Elektronikus jelentéskészítési exportálási üzenet** típusú műveletekhez van társítva.
- **Jelentés küldése** – Ez a gomb a **Webes szolgáltatás** típusú műveletekhez van társítva.
- **Válasz importálása** – Ez a gomb az **Elektronikus jelentéskészítés importálása** típusú műveletekhez van társítva.
- **Állapot frissítése** – Ez a gomb az **Üzenetszint felhasználói feldolgozás** típusú műveletekhez van társítva.
- **Üzenetelemek** – Nyissa meg az **Elektronikus üzenetelemek** oldalt.

A **Műveleti napló** gyorslap a kiválasztott üzenethez kapcsolódóan futtatott összes műveletről megjelenít információkat. Ha a művelet hibát okozott, a hibával kapcsolatos információk hozzá lesznek fűzve a kapcsolódó sorhoz a rácsban. Ha szerené áttekinteni a hibával kapcsolatos információkat, válassza az adott sort a rácsban, majd válassza a **Melléklet** gombot (gemkapocs jel) az oldal jobb felső sarkában.

Az **Üzenet további mezők** gyorslapon az üzenetekhez a feldolgozás beállításában meghatározott összes további mező látható. A gyorslapon további mezők értékeit is láthatja.

Az **Üzenetelemek** gyorslap a kiválasztott üzenethez kapcsolódó összes üzenetelemet megjeleníti. A kiválasztott üzenetelem állapotától függően néhány műveletet a rács feletti gombokkal futtathat:

- **Törlés** – Ez a gomb akkor érhető el, ha a **Törlés engedélyezése** jelölőnégyzet be van jelölve a kiválasztott üzenetelemhez.
- **Állapot frissítése** – Ez a gomb a **Felhasználói feldolgozás** típusú műveletekhez van társítva.
- **Eredeti dokumentum** – Megnyit egy oldalt, amely a kiválasztott üzenetelemhez tartozó eredeti dokumentumot jeleníti meg.

Az adott üzenethez létrehozott és fogadott jelentések csatolva vannak az üzenethez. Ha szerené áttekinteni egy üzenethez kapcsolódó mellékleteket, válassza ki az adott üzenetet, majd válassza a **Melléklet** gombot (gemkapocs jel) az oldal jobb felső sarkában.

![Csatolmány gomb](media/attachment-icon.png)

A **Mellékletek** oldal jeleníti meg a kiválasztott üzenethez kapcsolódó összes mellékletet. A fájlok megtekintéséhez jelölje ki őket a bal oldali listán, majd válassza **Megnyitás** lehetőséget a Művelet panelen.

![Megnyitás gomb](media/open-button.png)

Áttekintheti az adott művelethez kapcsolódó olyan mellékleteket, amelyet korábban egy üzenethez futtattak. Az **Elektronikus üzenetek** oldal **Üzenetek** gyorslapján válassza ki az üzenetet. A **Műveletnapló** gyorslapon válassza ki a műveletet, majd kattintson az oldal jobb felső sarkában a **Melléklet** gombra (gemkapocs jel).

Lefuttathatja az egész feldolgozást vagy csak egy bizonyos műveletet, ha kiválasztja a **Feldolgozás futtatása** lehetőséget a Művelet panelen.

## <a name="electronic-message-items"></a>Elektronikusüzenet-elemek

Az **Elektronikus üzenetelemek** oldalon az összes üzenetelem és az egyes üzenetelemekhez futtatott műveletek naplója megtekinthető. Ezenfelül az oldal az üzenetelemekhez meghatározott további mezőket is megjeleníti, valamint a további mezők értékeit.

Az alábbi táblázat ismerteti az **Üzenetelemek** oldalon elérhető mezőket.

<table>
<thead>
<tr>
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Feldolgozás</td>
<td>A feldolgozás neve, amelyet az üzenetelem létrehozásához használtak.</td>
</tr>
<tr>
<td>Üzenetelem</td>
<td>Az üzenetelem azonosítója. Az azonosító automatikusan kerül hozzárendelésre, az <b>Üzenetelem</b> számsorozata alapján, amelyet a <b>Főkönyvi paraméterek</b> oldalon határoztak meg.</td>
</tr>
<tr>
<td>Üzenetelem dátuma</td>
<td>Az üzenetelem létrehozásának dátuma.</td>
</tr>
<tr>
<td>Üzenetelem típusa</td>
<td>Az üzenetelem típusa. Számos típusú üzenetelemet be lehet állítani ugyanahhoz a feldolgozáshoz (például <b>Bejövő számlákat</b> és <b>Kimenő számlákat</b>). Ezt a mezőt csak akkor lehet automatikusan beállítani, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Üzenetelem-állapot</td>
<td><p>Az üzenetelem aktuális állapota. A lehetséges állapotok az üzenetelem típusától függően változnak. Íme néhány példa:</p>
<ul>
<li><b>Feltöltött</b> – Egy rekordot hozzáadtak az Üzenetelemek táblához.</li>
<li><b>Értékelve</b> – Az üzenetelemhez további attribútumok kerültek kiszállításra.</li>
<li><b>Jelentve</b> – Az üzenetelemet sikeresen hozzáadták egy jelentéshez.</li>
<li><b>Kizárt</b> – Ez az állapot akkor lehet hasznos, ha bizonyos üzenetelemeket ki kell zárnia a jelentésből az exportálás előtt.</li>
</ul>
</td>
</tr>
<tr>
<td>Átvitel dátuma</td>
<td>Oylyan feldolgozás esetén, amely automatikusan elküldi a létrehozott jelentést a rendszeren kívülre, a dátum, amikor az üzenetelemet elküldték.</td>
</tr>
<tr>
<td>Bizonylatszám</td>
<td>A mező automatikusan beállításra kerül a Rekordfeltöltés művelet beállítása alapján. Ezt a mezőt csak akkor lehet automatikusan beállítani, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Számlaszám</td>
<td>A vevő vagy szállító számlaszáma vagy másik mezőérték a Rekordfeltöltés műveletben megadottaknak megfelelően. Ezt a mezőt csak akkor lehet automatikusan beállítani, ha az Üzenetelemek táblához hozzáadnak egy számlát.</td>
</tr>
<tr>
<td>Üzenet</td>
<td>Az üzenet száma. A szám automatikusan kerül hozzárendelésre az <b>Üzenet</b> számsorozata alapján, amelyet a <b>Főkönyvi paraméterek</b> oldalon határoztak meg.</td>
</tr>
<tr>
<td>Üzenet állapota</td>
<td>Az elektronikus üzenet aktuális állapota.</td>
</tr>
<tr>
<td>Következő művelet</td>
<td>A következő műveletek, amelyeket az üzenetelem aktuális állapotához lehet indítani.</td>
</tr>
</tbody>
</table>

A **További mezők** lap megjeleníti a kijelölt üzenetelemhez tartozó további mezőket, és ezek értékeit.

### <a name="run-processing"></a>Feldolgozás futtatása

A Művelet panelen válassza a **Feldolgozás** lehetőséget az üzenetelemekhez tartozó feldolgozás futtatásához. Ha specifikus műveletet akar futtatni, akkor a **Feldolgozás futtatása** párbeszédablakban állítsa a **Művelet választása** lehetőséget **Igen** értékre, majd válasszon ki egy műveletet. Ha a teljes feldolgozást le akarja futtatni, hagyja a **Művelet választása** beállítást **Nem** értéken.

### <a name="generate-report"></a>Jelentés létrehozása

A Művelet panelen válassza ki a **Jelentés létrehozása** elemet. Ez a gomb az **Elektronikus jelentéskészítési exportálás** típusú műveletekhez van társítva.

### <a name="update-status"></a>Állapot módosítása

A Művelet panelen válassza az **Állapot frissítése** lehetőséget, ha egy vagy több üzenetelem állapotát szeretné frissíteni. Az **Állapot frissítése** párbeszédpanelen használja a **Belefoglalandó rekordok** gyorslapot a frissítendő üzenetelemek kiválasztására. Ellenőrizze, hogy helyesen határozta-e meg a kiválasztási feltételt, mivel az üzenetelem-állapotok frissítése a feltételek, a kiválasztott művelet kiindulási állapota és az **Új állapot** mező Ön által meghatározott értéke alapján történik. Az állapotfrissítés befejezése után nehéz megállapítani, hogy mely elemek frissültek. Emiatt nehéz lenne az állapotfrissítés visszaállítása.

### <a name="electronic-messages"></a>Elektronikus üzenetek

A Művelet panelen válassza az **Elektronikus üzenetek** lehetőséget a kiválasztott üzenetelemhez kapcsolódó elektronikus üzenet áttekintéséhez.

Ezenkívül megtekintheti az összes olyan fájlt, amely egy megadott üzenetelemhez kapcsolódik. Válassza ki az üzenetelemhez tartozó **Üzenet** mezőt, vagy válassza az **Elektronikus üzenetek** elemet a Művelet panelen. Az **Elektronikus üzenet** oldalon válassza ki azt az üzenetet, amelynek fájljait át szeretné tekinteni, majd válassza a **Melléklet** gombot (gemkapocs jel) az oldal jobb felső sarkában.

A **Mellékletek** oldal jeleníti meg az üzenethez kapcsolódó összes mellékletet. A fájl megtekintéséhez jelölje ki a bal oldali listán, majd válassza **Megnyitás** lehetőséget a Művelet panelen.

### <a name="original-document"></a>Eredeti dokumentum

Válassza az **Eredeti dokumentum** elemet a Művelet panelen a kiválasztott üzenetelemhez tartozó eredeti dokumentum megnyitásához.
