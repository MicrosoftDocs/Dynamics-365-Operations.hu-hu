---
title: Globalizációs funkció befejezése, közzététele és üzembe helyezése
description: Ez a témakör a globalizációs funkciók életciklusával kapcsolatban tartalmaz tájékoztatást.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 21e03660387c7e715bc0f4cb1dbcd3ec9ec6cee2
ms.sourcegitcommit: 1843235766b6f8cf950a13a310e9f4f2f53c59a4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/07/2022
ms.locfileid: "8554561"
---
# <a name="complete-publish-and-deploy-a-globalization-feature"></a>Globalizációs funkció befejezése, közzététele és üzembe helyezése

[!include [banner](../includes/banner.md)]

## <a name="electronic-invoicing-feature-versions"></a>Elektronikus számlázás funkcióverziói

Az elektronikus számlázás szolgáltatásai verziószámra vannak stb. Új verzió létrehozásakor a verziószám automatikusan nő.

Az elektronikus számlázás funkcióverziói egy legfeljebb három állapotú életciklust követnek:

- **Vázlat** – amikor egy funkcióverziónak ez az állapota, módosíthatja annak konfigurációs attribútumát és műtermékét (például fájlformátum-konfigurációit).
- **Kész** – ez az állapot azt jelzi, hogy befejezte a funkcióverzió szerkesztését, és nem kíván további frissítéseket végrehajtani rajta. Amikor egy funkcióverzió állapota ilyen, többé nem lehet sem szerkeszteni, sem az összetevőit.
- **Közzétéve** – ez az állapot azt jelzi, hogy a funkcióverziót közzétették a szervezethez társított globális tárházban. Amikor egy funkcióverzió állapota ilyen, többé nem lehet sem szerkeszteni, sem az összetevőit.

Megadhatja az **elektronikus** számlázási funkció új verziójának hatályos dátumát. Ily módon megadhatja a használható alapértelmezett verziót, vagy ezt lehet felülírni, amikor a szolgáltatást a szolgáltatás környezetére telepítik.

Az elektronikus számlázás funkcióverzió állapotának módosítása érdekében kövesse ezeket a lépéseket.

1. Jelentkezzen be a saját RCS-fiókjába.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Az Elektronikus számlázás **funkció** lap bal oldalán válassza ki az elektronikus számlázás funkciót.
4. A lap **jobb oldalán** található Verziók lapon válassza ki a verziót.
5. Válassza **az Állapot módosítása** lehetőséget, **majd válassza a Kész** lehetőséget (ha **az** aktuális állapot Vázlat) **vagy Közzétett** (ha az aktuális állapot **Kész**).
6. A kérés megerősítéséhez válassza **az Igen** lehetőséget az üzenet mezőben.

A Befejezett állapotról a **Közzétett** **állapotra való manuális** változtatás nem kötelező. Az elektronikus számlázás funkcióverziói **automatikusan** Közzétett állapotúra módosulnak, amikor a szolgáltatási környezetbe telepítik őket.

Az állapotot a Verziók lap **Funkcióverzió állapota** **oszlopában követheti** nyomon.

## <a name="deploy-feature-versions"></a>Funkcióverziók telepítése

Az RCS **esetében** a Deploy paranccsal lehet közzétenni egy elektronikus számlázási funkcióverziót a cél szolgáltatási környezetben vagy a csatlakoztatott alkalmazásban.

1. Az Elektronikus számlázás **funkció** lap bal oldalán válassza ki az elektronikus számlázás funkciót.
2. A lap **jobb** oldalán található Verziók lapon válassza ki azt az elektronikus számlázási funkcióverziót, amely a szolgáltatási környezetbe vagy a csatlakoztatott alkalmazásba telepítve van. A kiválasztott verziónak Kész vagy Közzétett állapotúnak **kell** **lennie**.
3. Válassza **a Telepítés** lehetőséget, majd válassza az alábbi beállítások egyikét vagy mindkettőt a telepítés célának meghatározásához:

    - **Csatlakoztatott alkalmazás** – az alkalmazásbeállítás Microsoft Dynamics által biztosított konfigurációt a 365 Pénzügy Dynamics 365 Supply Chain Management példányán írják, vagy már hozzá társították.
    - **Szolgáltatási környezet** – az elektronikus számlázási funkció verziója a szolgáltatási környezetre van telepítve. Az elektronikus számlázás ezután készen áll a Pénzügy vagy az Ellátásilánc-kezelés által küldött elektronikus dokumentumok fogadására és feldolgozására.

> [!NOTE]
> Általában meg fogja változtatni az elektronikus jelentéskészítési (ER) szolgáltatásnak a szolgáltatási környezetbe telepítve szükséges paramétereit. A csatlakoztatott alkalmazás változtatása ritka lesz. Csak akkor telepítse az új verziókat a csatlakoztatott alkalmazásra, ha módosítja az alkalmazás megfelelő paramétereit.

Annak megállapításához, hogy az elektronikus számlázási funkció egy adott verziójának telepítése konkrét környezetbe van-e telepítve, tekintse át az adatokat a Környezetek **lapon**.

## <a name="remove-feature-versions"></a>Funkcióverziók eltávolítása

Az RCS **szolgáltatásban a Mégse** gombra is be lehet választani, ha az ott telepített elektronikus számlázási funkcióverziót el szeretné távolítani a szolgáltatási környezetből.

> [!IMPORTANT]
> A **Mégse** gomb csak szolgáltatási környezetekben működik. Nem távolít el semmit a csatlakoztatott alkalmazásból az aktuális elektronikus számlázási funkcióhoz.

## <a name="rebase-electronic-invoicing-features"></a>Elektronikus számlázási funkciók lebázisolása

Ha az egyik elektronikus számlázási funkció egy másikból származik, **akkor** az Alapleíró beállítás kiválasztásával frissítheti a származtatott szolgáltatást az eredeti (szülő) funkcióban végrehajtott változtatásokkal.

A létrehozott funkciók származtatott verzióinak lebázisa az alábbi lépések szerint lehet.

1. A funkció legújabb verziójának bejezése a globális tárházból történő importálás segítségével. A további tudnivalókat lásd [az Importálás globális tárházból funkcióval](e-invoicing-import-feature-global-repository.md) kapcsolatban.
2. A szolgáltatások listájában válassza ki az új alapra helyezendő funkciót.
3. A Verziók **lapon** válassza az Új lehetőséget **vázlatverzió** létrehozásához.
4. Válassza az **Új alap** lehetőséget.
5. Az Adatbázis **párbeszédpanelen** válassza ki, hogy a funkciónak mi a lebázisa.
6. Válassza ki az **OK** lehetőséget.
7. Tekintse át a funkció összetevőit, és végezze el a szükséges módosításokat.
8. Az új alapra helyezett funkció befejezéséhez válassza az **Állapot módosítása** parancsot. Az új alapra helyezetés befejezése után további műveleteket is végre lehet hajtani.

## <a name="get-a-specific-version-of-electronic-invoicing-features"></a>Az elektronikus számlázással kapcsolatos funkciók adott verziójának bejezése

Amikor létrehozza egy elektronikus számlázási funkció új verzióját, a rendszer létrehozza a legújabb funkcióverzió másolatát. Ha egy új verzió alapjaként a funkció egy korábbi verzióját is használni kívánta, válassza ki a verziót, **majd válassza a Verzió bejede parancsát**. A funkció új vázlatverziója a kijelölt verzió másolata lesz.
