---
title: Belső adatok szerkesztésének engedélyezése a főkönyvi bizonylatokon
description: Ez a cikk a főkönyvi bizonylatok belső adatainak szerkesztésére vonatkozó tudnivalókat tartalmaz.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 26fc6518f0b4eae815e047db1dbaadd7c56a2e67
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220713"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Belső adatok szerkesztésének engedélyezése a főkönyvi bizonylatokon

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]


Könyvelési bejegyzések főkönyvbe **való** feladott feladott tételeinek leírása gyakran használható belső megjegyzések vagy dokumentumok tárolására. Ha helytelenek az adatok, akkor ez félreértést okozhat, és az időszak végi zárást nehéz lesz. Ezzel a funkcióval a főkönyvvezető **vagy** a főkönyvvezető kijavíthatja a hibákat, ha szerkeszti a főkönyvbe feladott bizonylatok Leírás mezőjét.

A főkönyvben feladott bizonylatok módosításai csak belső jellegű adatokra korlátozódnak. Ez a funkció soha nem teszi lehetővé az adatok (például összegek, feladási dátumok, főkönyvi számlák és a tranzakció pénznemének) szerkesztését. Az adatok módosításai a pénzügyi kimutatások külső jelentésére is hatással lesznek, csak új főkönyvi bizonylatokkal lehet őket végezni.

> [!NOTE]
> A Dynamics 365 Pénzügy 10.0.29-es **verziója csak a Leírás mezőben szerkeszthető**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Főkönyvi bizonylatok belső adatainak szerkesztése

Ahhoz, hogy a főkönyvi bizonylatok belső adatait szerkeszteni lehet, **·** **engedélyeznie kell a Belső adatok szerkesztésének engedélyezése a főkönyvi bizonylatok belső adatait a Funkciókezelés** munkaterületen.
A funkció engedélyezése után a feladott bizonylatokat szerkesztő felhasználót hozzá kell rendelni a főkönyvelési vezető vagy a főkönyvelési felügyelő szerepkörhöz. A biztonsági szerepkörök testreszabásával más szerepkörökhöz is adhat jogosultságokat.

A szerkesztési folyamat csak a Bizonylattranzakciók lapon engedélyezett.

1. Ugrás a Főkönyv **lekérdezések** > **és jelentések** > **bizonylattranzakcióihoz**.
2. **A SysQuery párbeszédpanelen** adja meg a keresési feltételeket a bizonylatok kiválasztásához.
3. Válassza ki a szerkeszteni kívánt bizonylatok sorait, **·** > **majd válassza a Bizonylat szerkesztése belső bizonylatadatok szerkesztése lehetőséget**.

    [![Bizonylattranzakciók lapja.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
A Belső bizonylatadatok **szerkesztése** lapon a kiválasztott sorokhoz a következő adatok jelennek meg:
  
  - Főkönyvi számla
  - Számla neve
  - Bizonylat 
  - Jelenlegi leírás
  - Új leírás

    [![Naplóbizonylat.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Csak az **Új leírás** mező szerkeszthető. Alapértelmezés szerint az érték **megegyezik** az Aktuális leírás mező értékével, így gyorsan kijavíthatja a leírás kisebb hibáit.

4. Az egyes **sorok Új** leírás mezőjének módosítása, vagy a leírás törlése az egyes sorokból.

   Ha több sort kell ugyanazsal az értékkel frissíteni, a következő lépéseket kell követni:

      1. Válassza ki a szerkeszteni kívánt sorokat, majd válassza a Kijelölt **rekordok tömeges frissítését**.
      2. A szerkeszteni **kívánt mezőben** válassza ki a szerkeszteni kívánt mezőt. A keresés jelenleg csak az Új leírás **mezőt tartalmazza**.
      3. Adjon meg **egy új** leírást az Új érték mezőben.
      4. Válassza ki a **Frissítés** lehetőséget. Minden kijelölt rekord frissül az új értékkel.

      [![A kijelölt rekordok tömeges frissítése párbeszédpanel.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. A Szerkesztés **oka mezőben** adjon meg egy megjegyzést, hogy miért történt a szerkesztés. Ez a megjegyzés a bizonylatszerkeszti **oldal Könyvvizsgálati ellenőrzése lapon** jelenik meg.

   Ugyanannak a bizonylatnak több szerkesztése is lehet, és mindegyik szerkesztést nyomon követi a alkalmazás.

## <a name="audit-trail-of-voucher-edits"></a>Szerkesztett bizonylatok könyvvizsgálati ellenőrzése

A könyvvizsgálati ellenőrzést a rendszer kifejezetten az ezen a funkción keresztül végrehajtott módosítások nyomon követésére használja. A bizonylatszerkesztvények könyvvizsgálati ellenőrzéséhez kétféleképpen lehet hozzáférni:

  - Ugrás a Főkönyv **lekérdezések** > **és jelentések** > **bizonylattranzakcióihoz**. A Bizonylatkérések **lapon** válassza **·** > **a Bizonylat-ellenőrzés szerkesztése bizonylatszerkesztésekhez beállítását**. A könyvvizsgálati ellenőrzés csak a kiválasztott bizonylatrekordra érvényes. 
   
    Ha így nyitja meg a lekérdezést, akkor az adott bizonylatrekord minden szerkesztésére fókuszálhat.
  
  - Ugrás a** Főkönyv** > **a** > **Bizonylat szerkesztései időszakos feladatok könyvvizsgálati ellenőrzése elemre** A párbeszédpanelen adja meg azokat a bizonylatokat, amelyek alapján meg szeretné tekinteni a szerkesztések könyvvizsgálati ellenőrzési feltételeinek megadását. Az összes bizonylat könyvvizsgálati ellenőrzésének megtekintéséhez hagyja üresen a feltételeket, és válassza az **OK gombra való lehetőséget**. 
    
    A lekérdezés ilyen módon való megnyitásával szűrheti az adott dátumon vagy adott felhasználó által készített módosításokat.

A **Szerkesztések könyvvizsgálati lapja** a következő adatokat mutatja:

- **Létrehozás dátuma és időpontja** – a szerkesztés dátuma és időpontja.
- **Szerkesztés oka** – az az ok, amiért a felhasználó a szerkesztést megadta.
- **Létrehozta** – a szerkesztést létrehozó felhasználó.

Az egyes könyvvizsgálati ellenőrzés részleteinek megtekintéséhez leáshat **a Létrehozás dátuma és időpontja értéknél**. A **Szerkesztett bizonylattulajdonságok** megtekintése lapon ugyanazok az adatok megjelenik, mint az eredeti szerkesztési lap, köztük az előző leírás és a frissített leírás.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
