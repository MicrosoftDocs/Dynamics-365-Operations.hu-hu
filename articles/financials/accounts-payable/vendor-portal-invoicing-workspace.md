---
title: Szállítói együttműködési számlázás munkaterület
description: Ez a témakör bemutatja, hogyan tekintheti meg a szállítói számlákat, és hogyan küldheti be a számlákat a szállítói együttműködési számlázás munkaterületen.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1f9e57e95a03b3e6f8bd940d38a426e9db559624
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1508505"
---
# <a name="vendor-collaboration-invoicing-workspace"></a>Szállítói együttműködési számlázás munkaterület

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan tekintheti meg a szállítói számlákat, és hogyan küldheti be a számlákat a szállítói együttműködési számlázás munkaterületen.

A **Szállítói együttműködési számlázás** munkaterület a szállítói számla adatainak megtekintésére, és a számlák küldésére használható a Microsoft Dynamics 365 for Finance and Operations megoldásba a munkafolyamat-lehetőségeinek használatával.


<a name="vendor-collaboration-invoicing-workspace"></a>Szállítói együttműködés számlázási munkaterülete
----------------------------------------

### <a name="summary-tiles"></a>Összesítő csempék

Az **Összesítés** csempék áttekintést adnak a kiválasztott szállító számláiról. A számlák állapotuk szerint tekinthetők meg.
-   A vázlat számlák nem lettek elküldve a munkafolyamatba.
-   Az elküldött, nem jóváhagyott számlák olyan számlák, amelyeket a szállító már benyújtott, de még nincsenek feladva a Finance and Operations megoldásba.
-   A jóváhagyott, nem fizetett számlák olyan számlák, amelyeknek a feladása már megtörtént a Finance and Operations megoldásba, de még nincsenek teljes mértékben kifizetve.
-   A kifizetett számlák olyan számlák, amelyeket teljes mértékben kifizettek a Finance and Operations megoldásban.

Kattintson egy csempére, és megnyílik a **Számlalisták** lap szűrt nézete.

### <a name="tabular-lists"></a>Táblázatos listák

A **táblázatos listák** szakaszban a számlázás állapotának bontása megegyezik az összesítés csempékével: Vázlat és Elküldött, jóváhagyással még nem rendelkező listák. Vázlat állapotban a számlát be lehet küldeni a munkafolyamatba, vagy törölni lehet. Az utolsó táblázatos lista a számlák keresésére szolgáló beállítás. A gyorsabb keresés érdekében lehetőség van a keresés közbeni szűrésre.

### <a name="all-vendor-invoices-list-page"></a>Az összes szállítói számla listaoldal

Minden feladott és feladatlan szállítói számla megtekinthető a **Szállítói együttműködési számlák** listaoldalon. A listaoldal segítségével a számlák fizetési állapota jeleníthető meg. A kifizetés állapota lehet Feladatlan, Kifizetetlen, Részben fizetve és Teljesen kifizetve.
Új számla létrehozása beszerzési rendelés alapján

Létrehozhat egy új szállítói számlát a következő kiválasztásával: **Új** a **Szállítói együttműködési számlázás** munkaterületen. A beszerzési rendelés számát és számlaszámát a szállítónak kell megadnia. Alapértelmezés szerint a szállító beszerzési rendelésének összes sora meg fog jelenni az új számlán. A mennyiség- és költségadatokat a szállítói számla munkafolyamatba küldése előtt lehet szerkeszteni. A számlához a beküldése előtt fájlokat, megjegyzéseket, képeket és URL-címeket csatolhat.

További tájékoztatás: [A külső szállítókkal történő szállítói együttműködés](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)



