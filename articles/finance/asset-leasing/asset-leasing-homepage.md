---
title: Eszközlízing – kezdőlap
description: Ez a témakör áttekintést nyújt az eszközlízing-dokumentációról, valamint az adott témakörökre mutató hivatkozásokról.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeasingWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 202a353929fbcd8d81593db155d7bfeebb8f3021
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5898110"
---
# <a name="asset-leasing-home-page"></a>Eszközlízing – kezdőlap

[!include [banner](../includes/banner.md)]

Ez a témakör az eszközlízinghez rendelkezésre álló súgótémaköröket sorolja fel, és konkrét témakörökre mutató hivatkozásokat tartalmaz. 

Az eszközlízing egy speciális modul, amely lehetővé teszi a lízingelt eszközökre vonatkozó pénzügyi tranzakciók kezelését, nyomon követését és automatizálását a Microsoft Dynamics 365 Finance alkalmazásban. Az eszközlízing megfelel a nemzetközi könyvelési szabványoknak (IFRS 16) és az Egyesült Államokban GAAP szabványainak (ASC 842). Az eszközlízing modul rögzíti és dolgozza fel a lízinggel kapcsolatos adatokat, és segítséget nyújt a naplóbejegyzések létrehozásában a lízing életciklusa alatt – a kezdő elszámolástól és a havi naplóbejegyzésektől egészen a lízing értékvesztéséig és lezárásáig.

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a **Funkciókezelés** munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkciókezelés** munkaterületen keresse meg és válassza ki az **Eszközlízing** funkciót, majd kattintson az **Engedélyezés most** gombra.

## <a name="asset-leasing-topics"></a>Eszközlízing témakörök
Az alábbi témakör az eszközlízing konfigurálásához és használatához érhető el. 

 - [Eszközlízing első lépések](asset-leasing-quick-start.md) – Ez a témakör ismerteti az eszközlízing általános képességeit, és felsorolja és meghatározza a szoftverben és a dokumentációban használt kifejezéseket.
 
 ### <a name="set-up-asset-leasing"></a>Eszközlízing beállítása
 Ezek a témakörcsoportok segítenek a szervezetek üzleti helyzetének megfelelő eszközlízing-konfigurálásban.  
  
  - [Lízingparaméterek konfigurálása](config-lease-parameters.md) 
  - [Lízingkönyvek beállítása](set-up-lease-books.md)
  - [Lízingcsoport létrehozása](create-lease-group.md)
  - [Referencia-kamatláb beállítása](set-up-index-rate-types.md)
  - [Költségtípusok beállítása](set-up-expense-types.md)
  - [Lízingnaplónevek beállítása](set-up-lease-journal-names.md)
  - [Lízing feladási számlák beállítása](set-up-lease-posting-accts.md)
  - [Számsorozatok hozzárendelése](leasing-number-sequences.md)
  - [Felhasználói szerepkörök hozzárendelése](lease-user-roles.md)

### <a name="manage-asset-leases"></a>Eszközlízingek kezelése
Ez a témakörcsoport a lízingek hozzáadásának, a fizetési számlák létrehozásának, a lízingszerződések módosításának, a lízingadatok importálásának és a használati joghoz kapcsolódó eszközök értékvesztettsének a folyamatát ismerteti. 

 - [Lízing hozzáadása vagy másolása](add-lease.md)
 - [Fizetési számla létrehozása](create-payment-invoice.md)
 - [Használatijog-eszköz értékcsökkenésének rögzítése](record-rou-asset-depreciation.md)
 - [Fordítva feladott lízingtranzakciók](reverse-posted-lease-trans.md)
 - [Lízing módosítása](adjust-lease.md)
 - [Használatijog-eszköz értékvesztésének könyvelése](impair-rou-asset.md)
 - [Fordítva feladott lízingtranzakciók](reverse-posted-lease-trans.md)
 - [Használatijog-eszköz értékvesztésének könyvelése](impair-rou-asset.md)
 - [Lízing társítása tárgyi eszközhöz](associate-lease-with-fixed-asset.md)
 - [Lízing rögzítése külföldi pénznemben](record-leases-foreign-currency.md)
 - [Referencia-kamatlábhoz kötött lízingdíjfizetések újraértékelése](revalue-payments-tied-2-index-rate.md)
 - [Lízingkötelezettség rövid távú részének átsorolása](reclassify-st-lease-liability.md)
 - [Kötelezettség-, eszköz- és költségtranzakciók megtekintése](view-asset-transactions.md)
 - [Kamatos kamattal érintett intervallumok funkció](compound-interval-functionality.md)
 - [Havi naplóbejegyzések megerősítése kötegben](confirm-payment-schedules-in-batch.md)
 - [Havi naplóbejegyzések létrehozása kötegben](create-monthly-journals-batch.md)
 - [Kettős jelentéskészítés](dual-reporting.md)
 - [Lízing-munkafolyamat beállítása](set-up-lease-wrkflw.md)
 - [Lízingjóváhagyási munkafolyamatok használata](use-create-lease-wrkflw.md)
 - [Lízing kezelése a lízingimportálási keretrendszeren keresztül](manage-leases-thru-imprt-framewrk.md)
 
### <a name="asset-leasing-reporting"></a>Eszközlízing-jelentés
Ez a témakör az eszközlízingek számára elérhető jelentéseket ismerteti. 

 - [Eszközlízing-jelentések](asset-leasing-rprts.md)
 

## <a name="additional-resources"></a>További erőforrások

### <a name="whats-new-and-in-development"></a>Újdonságok és fejlesztés alatt levő megoldások

Lépjen a [Microsoft Dynamics 365 programverzióra vonatkozó kiadási tervek](/dynamics365/release-plans/) oldalára a tervezett új funkciók megtekintéséhez. 

### <a name="blogs"></a>Blogok

A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) és a [Microsoft Dynamics 365 Finance and Operations – Pénzügyek blogon](https://community.dynamics.com/365/financeandoperations/b/financials) véleményeket, híreket és egyéb információkat talál.

A [Microsoft Dynamics Operations Partner közösségi blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) egyetlen erőforrás segítségével tájékoztatja a Microsoft Dynamics-partnereket a Dynamics 365 új és népszerű fejlesztéseiről.

### <a name="videos"></a>Videók

Tekintse meg az útmutató-videókat, amelyek a [Microsoft Dynamics 365 YouTube csatornáján](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) láthatók. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
