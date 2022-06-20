---
title: Előlegek automatikus alkalmazása a szállítói számlákra
description: Ez a témakör azt írja le, hogy képes-e automatikusan előlegeket alkalmazni a szállítói számlákra.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 547573d187460a900df7f4927ac062bd9d456729
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900071"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Automatikus alkalmazás a szállítói számlákra

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, hogy képes-e automatikusan előlegeket alkalmazni a szállítói számlákra. A beszerzési rendelésekhez előleget lehet létrehozni a beszerzési szerződés részeként. A szállítói számla beérkezése után az előleg felhasználható a szállítói számlából származó kötelezettségek kiegyenlítésre. Az új funkció lehetővé teszi, hogy a rendszer automatikusan használja a szállítói számlán szereplő beszerzési rendelési számokat a megfelelő előlegek kikereséséhez a szállítói számla importálása esetén.

Ha találhatók előlegek, és alkalmazhatók, az előlegek alkalmazáshoz sorokat ad a meglévő számlasorokhoz. A számlaegyeztetési folyamat során soha nem számítanak az előlegsorok.

A következő pontok leírják, hogy hogyan vannak alkalmazva az előlegek a különböző beszerzési folyamatok alkalmazása esetén:

- **Beszerzési rendelésenként egy szállítói számla** – A beszerzési rendelés előlege lesz alkalmazva a szállítói számlára.
- **Több beszerzési rendeléshez egy szállítói számla** – Az összes beszerzési rendelés előlege lesz alkalmazva a szállítói számlára.
- **Beszerzési rendelésenként több szállítói számla** – A beszerzési rendelés előlege lesz alkalmazva az első importált szállítói számlára. Ha az előleg összege meghaladja a számla összegét, az előleg alkalmazása sikertelen lesz, és manuálisan kell alkalmaznia az előleget.
- **Több beszerzési rendeléshez több szállítói számla** – A beszerzési rendelések előlegei lesz alkalmazva az első importált releváns szállítói számlára. Ha az előleg összege meghaladja a számla összegét, az előleg alkalmazása sikertelen lesz, és manuálisan kell alkalmaznia az előlegeket. Ha az első számlára előlegek alkalmazása után előlegek megmaradnak, alkalmazhatók az utána következő számlákra.

Ha egy előleg alkalmazása sikertelen, **az** előlegfizetés hibája esetén a Blokkolás-követés automatizálási folyamat beállítása határozza meg a következő lépéseket:

- **Igen** – az automatizálási előzmények között az "Előleg automatikus alkalmazása: Sikertelen" hibaüzenet jelenik meg, és a számla a függőben lévő szállítói számlák listájában marad. A számla mindaddig zárolva marad, amíg ön manuálisan nem alkalmazza az előleget.

Az előlegek manuális alkalmazáshoz menjen a függőben lévő szállítói számlára. A **Számla részletei** lapon állítsa a zárolt számla **Bevonás az automatizált feldolgozásba** beállítását **Nem** értékre. Most manuálisan alkalmazhatja az előleget. Az előleg alkalmazása után állítsa Vissza az **Bevonás az automatizált feldolgozásba** beállítást **Igen** értékre, hogy a számla automatikusan feldolgozható legyen.

Úgy is kikerülheti az előleg automatikus alkalmazását, hogy az **Bevonás az automatizált feldolgozásba** beállítást **Nem** értékre állítja, majd az **Igen** beállításra állítja vissza. A következő üzenet jelenik meg: "Már létezik előleg a beszerzési rendeléshez. Figyelmen kívül hagyja a kijelölt szállítói számlához?" Válassza ki az **Igen** lehetőséget. Az automatizálási előzmények között megjelenik az "Előleg alkalmazása manuálisan mellőzve" üzenet, és a szállítói számla nem lesz letiltva, ha az automatizált folyamat újra fut.

- **Nem** – Az utánkövető automatizálási folyamatok folytatódnak. Kiegyenlítéskor továbbra is alkalmazhatja az előleget.
