---
title: Számlarögzítési megoldás vezérlőpultja
description: Ez a témakör a Számlarögzítési megoldás irányítópultját írja le.
author: sunfzam
ms.date: 10/15/2022
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
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690147"
---
# <a name="invoice-capture-solution-dashboard"></a>Számlarögzítési megoldás vezérlőpultja

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Számlarögzítésben az irányítópult olyan diagramokat tartalmaz, amelyek áttekintést adnak az importált számlákról. Ezek a diagramok segítséget nyújt a Kötelezettségek (AP) kezelője számára a számla-generálási folyamat teljesítményének elemzésében. Az ap manager megtekintheti a számla-generálási folyamat állapotát, és különböző szűrők alkalmazásával a részleteket is megtekintheti.

## <a name="available-charts"></a>Rendelkezésre álló diagramok

A következő diagramok érhetők el a vezérlőpulton:

- **Minden rögzített számla állapot szerint** – ez a diagram a rögzített számlák következő állapotát mutatja. Az állapot kiválasztásával a felhasználók szűrni tudjak a részletes listában rögzített számlákat.

    - Elfogott
    - Befejezés
    - Ellenőrzés alatt
    - Elavult

- **Rögzített számlák össztérfogata** – ez a diagram a rögzített számlák számát jeleníti meg időszak szerint. A felhasználók a legördülő listában módosíthatjak az időszakot.
- **Rögzített számla a legfontosabb szállítóktól** – ez a diagram szállítónként megjeleníti a számlák összesített számát. A legtöbb számlát vevő szállítók jelennek meg a tetején.
- **Kivételekkel számlázva teljesítő napok** – ez a diagram az egy számla rögzítéséhez szükséges napok átlagos számát jeleníti meg. Ez az információ segítséget nyújt az ap managernek abban, hogy elemezze a számla feldolgozásának idejét, amikor kézi beavatkozás szükséges. Felfelé irányuló trend esetén a felhasználók áttekinthetik a folyamat részleteit, és módosíthatjják a szükséges beállításokat, hogy csökkentse a szükséges napok számát.
- **Befejezetlen számlák függő** idő szerint – ez a diagram azt mutatja, hogy hány napig nem készült rögzített számla a vállalati erőforrás-tervezési (ERP) rendszerben. Minél nagyobb a függő napok száma, annál hosszabb a számla létrehozása. Az ap manager leáshat a részletes rögzített számlákba, és számlákat generálhat az ERP rendszerben.
