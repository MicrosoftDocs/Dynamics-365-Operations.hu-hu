---
title: Számlarögzítés - fogadott fájlok
description: Ez a cikk bemutatja, hogyan lehet összegyűjteni a számlafájlokat a számlarögzítés különböző forrásaiból.
author: sunfzam
ms.date: 10/13/2022
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
ms.openlocfilehash: 3c55540d11a67d4d4c4c8477d51cb6f1f5777767
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690148"
---
# <a name="invoice-capture-received-files"></a>Számlarögzítés - fogadott fájlok

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Számlarögzítésben a Beérkezett **fájlok** lap egy központi hely, ahol különböző forrásból származó számlafájlok érkezikk.

## <a name="upload-invoice-files"></a>Számlafájlok feltöltése

A Kötelezettségek – adminisztrátorok úgy tölthetik fel a számlaképeket, hogy **a Feltöltés párbeszédpanel megnyitásához egy** **fájl** feltöltése gombra választják. Miután egy ap adminisztrátor kiválaszt egy fájlt, elérhetővé válik **a Feltöltés** gomb.

## <a name="include-or-obsolete-invoice-files"></a>Tartalmazza az elavult számlafájlokat

A felhasználók kiválaszthatják azokat a számlákat, amelyekben hibák vagy figyelmeztetések vannak, majd a megfelelő gomb kiválasztásával választhatják ki a hibákat vagy figyelmeztetéseket, majd a megfelelő gomb választásával vagy elavultá válnak. Az elavultként megjelölt számlák nem **jelennek meg a Beérkezett fájlok (Elavult) nézetben**.

## <a name="view-captured-invoices"></a>Rögzített számlák megtekintése

A fogadott fájl sikeres felismerése után az AI-modell visszaadja a rögzített számla adatait, és be is rögzíti Microsoft Dataverse. A szállító adminisztrátora ezután a rögzített számla megtekintése lehetőség választásával ellenőrizheti a számla **részleteit**. A felhasználók szükség szerint letölthetik az eredeti számlafájlt.
