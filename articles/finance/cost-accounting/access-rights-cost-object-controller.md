---
title: Hozzáférési jogok költségobjektum-ellenőrök számára
description: Ez a cikk a költségobjektum-kontrollerek hozzáférési jogairól nyújt tájékoztatást.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c40be758c5e5d1d1fb025630ed8321ae46251892
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903189"
---
# <a name="access-rights-for-cost-object-controllers"></a>Hozzáférési jogok költségobjektum-ellenőrök számára

[!include [banner](../includes/banner.md)]

A **Költségkontroll** munkaterület az a központ, ahol a vezetők megtekinthetik a költségobjektumaik teljesítményét. Ez a munkaterület lehetővé teszi, hogy a vezetők költségkönyvelési adatokat fogyaszthassanak annak ellenére, hogy nem költségkönyvelők. A vezetőknek biztonsági okokból csak azoknak a Költségkönyvelési adatoknak a megtekintése engedélyezett, amelyek kapcsolódnak azokhoz a költségobjektumokhoz, amelyekért felelősek.

Négy egyedi szerepkör található a Költségkönyvelésben.

| Szerepkör neve               | Licenc      |
|-------------------------|--------------|
| Költségkönyvelés-kezelő | Tevékenység     |
| Költségkönyvelő munkatárs         | Operations   |
| Költségkönyvelő adminisztrátor   | Operations   |
| Költségobjektum-ellenőr  | Csapattagok |

Ez a cikk bemutatja, hogyan lehet a **költségobjektum-kontroller** szerepkört vezetőhöz rendelni.

Ha hozzá van rendelve a **Költségobjektum-ellenőr** szerepkör a vezetőhöz, akkor a következő feladatokat hajthatja végre:

- A **Költségkontroll** munkaterület elérése (a kliensben).

    - Részletezés és megtekintési hozzáférés azoknál az oldalaknál, amelyek támogatják a részletezést.

- A **Költségkontroll** munkaterület elérése (a mobilalkalmazásban).

> [!NOTE]
> A **Költségobjektum-ellenőr** szerepkör nem szabályozza, hogy melyik költségobjektumhoz férhet hozzá a felhasználó, illetve melyiknek nézheti meg az adatait. A sorszintű biztonság dimenzióhierarchiákon és a hozzáférési lista hierarchiáján keresztül valósul meg.

## <a name="grant-access-rights"></a>Hozzáférési jogosultságok megadása
A következő példában bemutatjuk, hogyan nézhet ki egy dimenzióhierarchia.

**Dimenzióhierarchia részletei**

| Dimenzióhierarchia neve | Dimenzió    | Dimenzióhierarchia típus neve      | Hozzáférési lista hierarchia |
|--------------------------|--------------|------------------------------------|-----------------------|
| Szervezet             | Költséghelyek | Dimenzió-osztályozáshierarchia | **Igen**               |

A hierarchiatervező **Felhasználók** gyorslapja segítségével egy vagy több felhasználói azonosítót illeszthet minden egyes csomóponthoz.

|             Csomópontok                 | Felhasználók            | Forrásdimenzió-tag     |   Céldimenziótag   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| Szervezet                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Rendszergazda                 | Április            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Pénzügy   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | Anna            | CC001                     | CC001                   |
| &nbsp;&nbsp;Termelés            | Dávid            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Csomagolás | Verebélyi            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Szerelvény  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> A költségkönyvelőket a hierarchia felső szintjéhez kell rendelni, hogy láthassák az összes költségkönyvelési tételt.

Ahhoz, hogy a Hozzáférési lista hierarchia és annak biztonsági beállításai alkalmazhatók legyenek, a **Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése** lehetőséget **Igen** értékre kell állítani az **Általános** lapon, a **Költségkönyvelés paraméterei** oldalon (**Költségkönyvelés** > **Beállítás** > **Paraméterek**).

A Hozzáférési lista hierarchiájának beállításait használja a rendszer azoknak az adatoknak az irányítására, amelyek a következő területeken jelennek meg:

- **Költségkontroll** munkaterület (a kliensben):

    - Adatok azokról az oldalakról, amelyeket a részletezésnél használ a rendszer

- **Költségkontroll** munkaterület (a mobilalkalmazásban):

    - Egyenlegek a kártyákon

- Microsoft Power BI:

    - Adatok, amelyek megjelennek a Power BI ábrázolásaiban
    - A Power BI Dynamics 365 Pénzügyi ügyfélben található adatmegjelenítések

> [!IMPORTANT]
> - Ahhoz, hogy a Hozzáférési lista hierarchia befolyásolhassa a Power BI adatait, párosítani kell a Hozzáférési lista hierarchiát és a sorszintű biztonságot a Power BI-ben. További információ: [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
> - Ez a cikk bemutatja azokat az előfeltételeket, amelyek már használatban vannak a Költségellenőrzés **munkaterület használata** előtt.

További erőforrások

- [Költségellenőrzési munkaterület](cost-control-workspace.md)
- [Dimenzióhierarchia](dimension-hierarchy.md)
- [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
