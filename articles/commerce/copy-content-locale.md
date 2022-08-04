---
title: Tartalom másolása másik területi adatokba
description: Ez a témakör azt ismerteti, hogyan lehet átmásolni a meglévő tartalmat a Microsoft Dynamics 365 Commerce webhelyszerkesztő egy másik területi tartalmának más területére.
author: psimolin
ms.date: 07/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: bcfa3c7cb2ea8018422803d85df6b6761b8d1145
ms.sourcegitcommit: d719d0a549aecac231fad0abb42250eab9dd0ded
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/07/2022
ms.locfileid: "9126467"
---
# <a name="copy-content-to-another-locale"></a>Tartalom másolása másik területi adatokba

[!include[banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet átmásolni a meglévő tartalmat a Microsoft Dynamics 365 Commerce webhelyszerkesztő egy másik területi tartalmának más területére.

Amikor a Commerce Webhelyszerkesztőben tartalmat hoz létre, az mindig társítva van egy területi azonosítóhoz, például az "en-us" azonosítóhoz. Az egyes lapokat és eszközöket ugyanannak az e-commerce webhelynek más-más területi beállításokba másolhatja, ha módosítja a területi beállításokat a tartalomelem szerkesztésekor, majd létrehoz egy új változatot a cikkből. Bizonyos esetekben, például amikor teljesen új területi elemet indít el az üzletben, akkor van értelme egy létező területi rendszer összes tartalomelemét az új területi értékbe másolni. Ha az új területi beállításoknak ugyanaz az alapnyelvük, mint a meglévőké, akkor a meglévő területi beállításokat használhatja a területi beállítások forrás területi beállításokként a területi beállítások másolási műveletében. (Például az "en-us" és az "en-au" területi beállítások egyaránt az angol nyelvet használják.) Ily módon csökkentheti a tartalom honosítani kívánt tartalmának az új területi tartalmának honosítani kívánt munkamennyiségét.

Az alábbi eljárás bemutatja, hogyan lehet új területi beállításokat hozzáadni egy meglévő csatornához, átmásolni egy létező területi beállítások összes tartalmát egy új területi beállításokba, és figyelni a területi beállítások másolási műveletének állapotát.

## <a name="add-a-new-locale"></a>Új területi idő hozzáadása

A Commerce Webhelyszerkesztőben a következő lépésekkel adhat hozzá új területi feltételeket.

1. A webhelyszerkesztőben menjen a webhelyre.
1. A bal oldali navigációs ablakban válassza ki a Webhely **beállításait**, majd válassza a Csatornák **lehetőséget**.
1. A **Csatorna** mezőben válassza ki azt a csatornát, amelybe az új területi beállításokat hozzá kell adni.
1. A jobb oldalon megjelenő csatorna párbeszédpanelen válassza a Területi **beállítás hozzáadása lehetőséget**.
1. A Területi **beállítás hozzáadása** **párbeszédpanel** Terület mezőjében válassza ki a kívánt területi beállításokat.
1. Ellenőrizze a tartományérték **helyességét**.
1. Az **Elérési út** mezőben adjon meg egy egyedi URL-címet (**például hu-hu** **vagy angol-us**).
1. Válassza ki az **OK** lehetőséget.
1. Zárja be a csatorna párbeszédpanelét.
1. A **Csatorna** alatt győződjön meg arról, hogy az új területi lista a megfelelő csatorna mellett van felsorolva.
1. Válassza a **Mentés és közzététel** lehetőséget.

> [!NOTE]
> Ahhoz, hogy az új területi beállításokat konfigurálni tudja a webhelyszerkesztőben, hozzá kell adni a Commerce Headquarters kapcsolódó online áruházi csatornáihoz.

## <a name="copy-all-content-items-to-a-new-locale"></a>Minden tartalomelemek másolása új területi adatokba

Ha az összes tartalomelemet át kell másolni a Commerce webhelyszerkesztő egy új területi példányába, kövesse ezeket a lépéseket.

1. A webhelyszerkesztőben menjen a webhelyre.
1. A bal oldali navigációs ablakban válassza ki a Webhely **beállításait**, majd válassza a Csatornák **lehetőséget**.
1. Válassza a parancssorból a **Másolat létrehozása parancsot**.
1. A Területmásolat **létrehozása** párbeszédpanel jobb oldalán, **a Forráshely** csoportban győződjön meg arról, hogy a megfelelő hely van kiválasztva.
1. A Forrás csatorna **mezőben** válassza ki a forrás csatornát.
1. A Cél **csatorna mezőben** válassza ki ugyanazt a forráscsatornát.
1. A Forrás **területi beállítás mezőben** válassza ki a forrás területi beállítását.
1. A Cél **területi beállítás mezőben** válassza ki az új területi beállításokat.
1. Válassza a **Másolás területi beállítását**. Az értesítések megerősítik, hogy elindult a területi másolási művelet.

> [!NOTE]
> A különböző csatornák között tartalom is más-más módon másolhatók.

## <a name="monitor-the-status-of-the-locale-copy"></a>A területi másolat állapotának figyelése

A területi másolási műveletek állapotának figyelése érdekében kövesse az alábbi lépéseket.

1. A webhelyszerkesztőben menjen a webhelyre.
1. A bal oldali navigációs ablakban válassza ki **a** Webhely beállításait, majd válassza a Feladatok **lehetőséget**.
1. Az Aktuális **feladatok mezőben** válassza ki a figyelni kívánt feladatot. A feladat részletei a jobb oldalon megjelenő párbeszédpanelen jelennek meg.
