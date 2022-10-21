---
title: Számlarögzítési megoldás áttekintése
description: Ez a cikk a Számlarögzítés megoldással kapcsolatban tartalmaz tájékoztatást.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690992"
---
# <a name="invoice-capture-solution"></a>Számlarögzítési megoldás

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk a számlarögzítési megoldással kapcsolatban tartalmaz tájékoztatást, amely automatikusan létrehozza a szállítói számlákat a digitális számlaképekből.

A Kötelezettségek osztály kezeli és feldolgozza a kapott áruk és szolgáltatások számláit. A könyvelő a következő okokból ellenőrzi a szállítói számlák adatait:

- További munka elkerülése érdekében, ha korrekciók vagy javítások szükségesek az időszak zárása során
- A szállítói számláknak időbeni kifizetése és a hiba vagy csalás miatt esetleg létre nem hozható pénzügyi veszteség megakadályozása

Az optikai karakterfelismerést (OCR) az elmúlt években széles körben használják a különböző ágazatok. Jelenleg általános, hogy a nyomtatott szövegeket számjegyként kell nyomtatni, hogy elektronikusan szerkeszthetők, kereshetőek, tárolódtak és tömöríthetőbbek, és online megjeleníthetőek. A digitális szöveg gépi folyamatokban, például számítógépes számításban, gépi fordításban, szöveg-automatizációban, kulcsadatokban és szövegbányászatban használható.

Az intelligenciát igénylő intelligencia (AI) technológia lehetővé tette a modern OCR-megoldások számára, hogy különféle számlaformátumokat olvassanak el a különböző szállítóktól, és ne szükséges sok emberi beavatkozás. Több vállalat azt ismeri el, hogy a manuális feldolgozás helyett a számlák automatizáláson keresztüli feldolgozásával meg lehet menteni a munkamennyiséget és javítani lehet a pontosságot.

## <a name="system-landscape"></a>Rendszerkép

Az alábbi ábra a Számlarögzítés megoldás fő összetevőit és lépéseit mutatja be.

[![A Számlarögzítés megoldás összetevői és lépései](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Kötelező szerepkörök

Az alábbi táblázat bemutatja a Számlarögzítési megoldás beállításához és alkalmazásához szükséges szerepköröket.

| Szerep          | Műveletek | Rendszerek | Szerepkörnevek |
|---------------|---------|---------|-----------|
| Adminisztrátor | <ul><li>Környezetek beállítása a Microsoft Power Platform.</li><li>Megoldások telepítése a Microsoft Power Platform.</li><li>A Dynamics 365 és a AI Builder.</li><li>Azure Data Lake Storage Helyek beállítása.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Dynamics 365-rendszergazda</li><li>Power Platform-rendszergazda</li><li>Tárolási blob adatainak tulajdonosa</li></ul> |
| AI készítő      | <ul><li>Folyamatok karbantartása.</li><li>Egyéni AI-modellek létrehozása.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Állampolgárok</li></ul> |
| TÉ adminisztrátor      | <ul><li>A szállítói számla előkészítési területének áttekintése és műveletek végrehajtása.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>A besz. adminisztrátor új szerepköre a következőben: Power Platform</li></ul> |
| TÉ adminisztrátor      | <ul><li>Napi műveletek végrehajtása mint adminisztrátor.</li><li>A szállítói számla előkészítő területének megtekintése.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Kötelezettségkezelő adminisztrátor</li></ul> |
  
A Számlarögzítés telepítésével kapcsolatos további tudnivalókat lásd A számlarögzítés [telepítése](../accounts-payable/install-invoice-capture.md).  
