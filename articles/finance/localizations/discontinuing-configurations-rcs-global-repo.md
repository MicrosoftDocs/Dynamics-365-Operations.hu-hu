---
title: Konfigurációk megszüntetése az RCS Globális adattárban
description: Ez a témakör leírja, hogyan lehet megszüntetni a konfigurációkat az RCS globális tárházban.
author: gionoder
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace
ms.openlocfilehash: b0605f56058e3c93ea088ee8386ba26c4ce2b65a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272336"
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


