---
title: Szállítói számlák automatizálási eredményeinek megtekintése (előnézet)
description: Ez a témakör azt mutatja be, hogyan lehet megtekinteni az automatizált munkafolyamatba küldési folyamatban lévő szállítói számlák állapotát.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3b87af4c64f8021a1b23cca5d8f38ac21c8efbd4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248089"
---
# <a name="view-vendor-invoice-automation-results"></a>Szállítói számlák automatizálási eredményeinek megtekintése

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megtekinteni az automatizált munkafolyamatba küldési folyamatban lévő szállítói számlák állapotát. A program minden importált szállítói számlához megőrzi az automatizálási előzmények adatait. Az automatizált üzleti folyamatoktól függően a **Függő szállítói számlák** oldal az **Automatizált nyugtaegyeztetés állapota** és az **Automatizált munkafolyamatba küldés állapota** értékeket jeleníti meg. Megtekintheti a részleteket, és tervet készíthet azon számlákhoz, amelyek nem tartalmaznak automatizált lépést. Ezután a hiba javítását követően újraindíthatja az importált számlára vonatkozó automatizált folyamatot.

A már elküldött számlák szerkesztéséhez szüneteltetni kell az automatikus feldolgozást. Ha szüneteltetni kell egy számlát az automatizált munkafolyamatba küldési folyamatban, akkor a **Szállítói számlák** oldalon állítsa **Nem** értékre az **Automatizált feldolgozás bevonása** mezőt. Az automatizálás addig nem fog futni, amíg az **Automatizált feldolgozás bevonása** mezőt nem állítják át **Igen** értékre. Ha a számla nem szerepel a munkafolyamat-rendszerben és nincs az automatizált folyamatban, a számla további automatizálása szüneteltethető.

Ha egy importált számla a munkafolyamatba küldési folyamatban van, akkor a **Szállítói számlák** oldalon megtekintheti az **Automatizáció állapotát**. A következő állapotok követi végig a rendszer:

- **Bevonva** – Azok az automatizált folyamatok, amelyeket a **Kötelezettségek paraméterei** oldalon definiáltak, megfelelően futnak, de még nem befejeződtek be.
- **Szüneteltetve** – A **Kötelezettségek paraméterei** oldalon definiált automatizált folyamatok, amelyek végigfutottak, de a folyamat legalább egy lépése sikertelen volt. A **Szüneteltetett** állapotot akkor is alkalmazza a program, ha a **Bevonás az automatizált feldolgozásba** mezőt **Nem** értékre állítja. A hibákat a **Legutóbbi eredmények megtekintése** gombbal lehet megtekinteni.
- **Munkafolyamatban** – Az importált számlát a program elküldte a munkafolyamat-rendszerbe akár automatizált munkafolyamatba küldési folyamattal, akár manuálisan.
- **Munkafolyamat befejezve** – Az importált számlához tartozó munkafolyamat befejeződött.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]