---
title: Hozzáférési jogok költségobjektum-ellenőrök számára
description: Ez a témakör a költségobjektum-ellenőrök hozzáférési jogairól nyújt tájékoztatást.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c30a7c2765647aad17a475ba8705b8e688d166593adf242fcd15d90e49334189
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733029"
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

Ez a témakör megmagyarázza, hogy miként rendelheti hozzá a **Költségobjektum-ellenőr** szerepkört egy vezetőhöz.

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
    - Az adatok Power BI-megjelenítései, amelyek a Dynamics 365 Finance kliensbe vannak ágyazva

> [!IMPORTANT]
> - Ahhoz, hogy a Hozzáférési lista hierarchia befolyásolhassa a Power BI adatait, párosítani kell a Hozzáférési lista hierarchiát és a sorszintű biztonságot a Power BI-ben. További információ: [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
> - Ez a témakör azokat az előfeltételeket mutatja be, amelyeknek teljesülniük kell a **Költségkontroll** munkaterület használatához.

További erőforrások

- [Költségellenőrzési munkaterület](cost-control-workspace.md)
- [Dimenzióhierarchia](dimension-hierarchy.md)
- [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
