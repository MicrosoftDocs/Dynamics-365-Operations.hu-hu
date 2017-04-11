---
title: "A POS pénztár kapcsolat nélküli üzemelése"
description: "Ez a cikk a Retail Modern POS offline üzemmódjáról nyújt tájékoztatást; ennek során a pénztári (POS) eszközök a csatorna-adatbázisról automatikusan az offline adatbázisra váltanak, ha a kiskereskedelmi kiszolgáló nem érhető el. A cikk az offline üzemmód beállításával kapcsolatos általános információkat is tartalmaz, illetve bemutatja az offline adatbázis és a csatorna-adatbázis között történő adatszinkronizálást."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>A POS pénztár kapcsolat nélküli üzemelése

Ez a cikk a Retail Modern POS offline üzemmódjáról nyújt tájékoztatást; ennek során a pénztári (POS) eszközök a csatorna-adatbázisról automatikusan az offline adatbázisra váltanak, ha a kiskereskedelmi kiszolgáló nem érhető el. A cikk az offline üzemmód beállításával kapcsolatos általános információkat is tartalmaz, illetve bemutatja az offline adatbázis és a csatorna-adatbázis között történő adatszinkronizálást.

<a name="overview"></a>Áttekintés
--------

A Modern Retail POS egy pont (POS) értékesítés eszköz kerül kapcsolat nélküli módba minden alkalommal, amikor a kiskereskedelmi kiszolgáló nem érhető el. Ezért ha megszakad a kapcsolat a kiskereskedelmi kiszolgálóval, Modern Retail POS automatikusan átvált az offline adatbázis. Egy értékesítési tranzakció során, ha az adatok lekérése nem sikerül a kapcsolat nélküli profilban megszabott időtúllépési intervallum alatt, a Retail Moder POS automatikusan a kapcsolat nélküli adatbázisra vált, és folytatódhat az értékesítési tranzakció. Mialatt a POS pénztárgép kapcsolat nélküli módban van, a Retail Moder POS megpróbál visszacsatlakozni a szerverre, a kapcsolat nélküli profilban megadott újracsatlakozási intervallum után. A újracsatlakozási kísérlet csak a tranzakció kezdetén történik.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>A Retail Modern POS kapcsolat módjának meghatározása

A Retail Modern POS állapotjelzője mutatja a jelenlegi kapcsolati állapotot, a **Kapcsolat állapota** ablak pedig megmutatja, mikor próbált utoljára szinkronizálni a kapcsolat nélküli adatbázis. [![Connection status](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Gomb létrehozása az online és offline módok közötti, manuális váltáshoz

A Retail Modern POS rendszerben hozzáadhat egy gombot az online és offline módok közötti manuális váltáshoz. Hozzon létre egy gombot POS művelethez **917 – Adatbázis kapcsolati állapota**. A gomb neve **Leválasztás** abban az esetben, ha a Retail Moder POS csatlakozva van a kiskereskedelmi szerverhez, valamint a gomb neve **Csatlakozás** lesz, ha nincs csatlakozva a szerverhez. Segítségével ez a gomb tekintheti meg a kapcsolat és a retail server leválasztása vagy csatlakozhasson hozzá. [![Kapcsolat bontása a Modern a Retail POS rendszerben gomb](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>Beállítás
POS eszköz (regiszter) kapcsolat nélküli támogatásának engedélyezéséhez állítsa a **támogatja a kapcsolat nélküli** be **Igen** a a **regisztrálni** oldalon. Csatorna adatbázis új entitás létrehozása és a store csatorna adatcsoport adni. Ezt követően futtasson le minden szükséges forgalmazói ütemezést az offline adatbázis számára szükséges adatcsomagok generálásához. Ezután telepítse a Modern Retail POS offline verzióját. A telepítési folyamatot hoz létre a kapcsolat nélküli adatbázisnak. Továbbá telepítse a Microsoft SQL Server 2014 Express szükség esetén. A kapcsolat nélküli adatszinkronizálás a Retail Modern POS rendszerébe történő első bejelentkezéskor indul el.

## <a name="data-synchronization"></a>Adatszinkronizálás
A Kiskereskedelmi ütemező segítségével a fő adatok elküldésre kerülnek az offline adatbázis számára. Alapértelmezés szerint egy elosztási ütemezés futtatásakor az adatmódosítások a csatorna-adatbázis és az offline adatbázis számára is elküldésre kerül. A Retail Modern POS tartalmazza az aszinkron szinkronizálási könyvtárat, amely minden elérhető adatcsomagot letölt és beilleszt az offline adatbázisba. Ha a tranzakciók offline jönnek létre, a Retail Modern POS feltölti azokat a kiskereskedelmi szerverre így azok beilleszthetővé válnak a csatorna adatbázisba. Kapcsolat nélküli adatszinkronizálás csak akkor történhet, ha a Retail Modern POS fut. [![Offline synchronization](./media/offline-sync-1024x521.png)](./media/offline-sync.png)


