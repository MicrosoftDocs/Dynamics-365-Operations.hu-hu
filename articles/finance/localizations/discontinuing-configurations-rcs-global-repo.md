---
title: Konfigurációk megszüntetése az RCS Globális adattárban
description: Ez a témakör leírja, hogyan lehet megszüntetni a konfigurációkat az RCS globális tárházban.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 4121f45a95e1712f21390c317af532662846a0fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894811"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Konfigurációk megszüntetése az RCS Globális adattárban

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet megszüntetni a konfigurációt az RCS globális tárházban. Korábban csak olyan konfigurációk voltak törölhetők, amelyekre már nem volt szükség. Most azonban egy kiadott konfigurációt **Kifutott** állapotúként jelölhet meg az RCS Globális adattárban. Ezzel a funkcióval a következőkre is lehetőség nyílik: 
 
 - Előzetes értesítés biztosítása egy konfiguráció tervezett megszüntetése esetén.
 - Adja hozzá a cserekonfigurációra vonatkozó részleteket.
 - Állítsa be a **Támogatás határideje** dátumát az adott konfigurációnál, hogy tájékoztassa a felhasználót a konfiguráció megszűnéséről.

Ha megszüntet egy konfigurációs verziót, a következő opcionális adatokat adhatja meg:

  - **Helyettesítés konfigurációja**
  - **Cserekonfiguráció verziója**
  - **Szabadszöveges megjegyzés**: Ebben a mezőben dokumentációhivatkozásokat vagy referenciákat adhat meg.
  - **Támogatás határideje**: Ez a mező azt a javasolt dátumot jeleníti meg, ameddig az aktuális konfiguráció/verzió támogatott lesz. Ezt a dátumot manuálisan kell frissíteni.
  
A konfiguráció megszüntetéséhez kövesse az alábbi lépéseket. 

1. Az **Összes verzió** **Igen** értékre állításával megadhatja, hogy egyetlen verzió vagy egy művelet összes azonos beállítású verziója megszűnjön-e. 
2. A **Megszüntetés** paramétert állítsa **Igen** értékre.
3. A konfigurációk megszüntetéséhez kattintson az **OK** gombra. A módosítások mentésekor a rendszer kitölti a **Megszüntetési dátum** mezőt.

![Konfigurációs adatok megszüntetése.](media/Discontinue-details-2.png)
  
A konfiguráció bármikor visszaállítható a **Megosztott** beállításra, illetve bármikor módosíthatja a megszüntetési adatokat. Ha közös konfigurációt oszt meg, adja meg a **Támogatás határideje** dátumát és a megszüntetéshez kapcsolódó összes egyéb információt, hogy jelezze a jövőbeli megszüntetésre vonatkozó terveit.

Ha egy tervezett megszüntetésről szeretne információkat megosztani még a konfigurálás tényleges megszüntetése előtt, a felhasználó a cserével kapcsolatos összes mezőt előre kitöltheti, de a **Megszüntetés** paramétert **Nem** értéken hagyhatja.

> [!NOTE]
> A megszüntetés nem korlátozza a konfigurációkkal rendelkező műveleteket. A konfigurációk importálását, futtatását és származtatását folytatni lehet – ezek a mezők csak tájékoztatásra valók.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>A Finance rendszer támogatja ezen adatok megjelenítését a 10.0.14-es verziótól kezdve.

A Dynamics 365 Pénzügy 10.0.14-es verziójától kezdve támogatja a nem folytonos adatok megjelenítését. A **Globális adattár** oldalon megtekintheti a megszüntetéshez kapcsolódó naprakész információkat. Alapértelmezés szerint a már megszüntetett konfigurációkat kiszűri a rendszer.
  
Az **Importált konfigurációk** (ERSolutionTable) oldalon megjelennek az importáláskor már megszüntetett konfigurációk. Az importálás után megszüntetett konfigurációk esetén az importálás után megszüntetett adatokat az **Konfigurációfrissítések importálása** feladat futtatásával szinkronizálhatja.


