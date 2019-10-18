---
title: Projekt-időnyilvántartás mobilalkalmazás
description: Ez a témakör Microsoft Dynamics 365 Project Timesheet mobilalkalmazással kapcsolatban tartalmaz információkat. A Project Timesheet mobilalkalmazás segítségével a felhasználók a mobileszközükön beküldhetek és jóváhagyhatnak projektekhez tartozó munkaidő-nyilvántartásokat.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 91ecccab58e4f1582a43eac62b42c7205b383bb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174489"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Microsoft Dynamics 365 Project Timesheet mobilalkalmazás

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Áttekintés

A Microsoft Dynamics 365 Project Timesheet mobilalkalmazás segítségével a felhasználók a mobileszközükön (iPhone vagy Android) beküldhetek és jóváhagyhatnak projektekhez tartozó munkaidő-nyilvántartásokat. Ez a mobilalkalmazás elérhetővé teszi a munkaidő-nyilvántartási funkciókat a Dynamics 365 Finance projektvezetési és könyvelési területéről, felhasználói termelékenység és hatékonyságának javítása, valamint a projektek munkaidőnyilvántartásainak gyors bevitele és jóváhagyása elősegítése érdekében.

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése

Töltse le és telepítse a Microsoft Dynamics 365 Project Timesheet mobil alkalmazást Android vagy iPhone eszközhöz az eszköz áruházából.

## <a name="enable-the-app"></a>Az alkalmazás engedélyezése 

A Finance alkalmazásban engedélyezni kell a Project Timesheet mobilalkalmazást. A funkcionalitás engedélyezéséhez válassza a **Projektvezetési és könyvelési paraméterek \> Időnyilvántartás** lehetőséget, és válassza ki a **Microsoft Dynamics 365 Project Timesheet engedélyezése** paramétert.

## <a name="sign-in-to-the-app"></a>Bejelentkezés az alkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.

2.  Finance URL-cím hozzáadása.

3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.

4.  Az alapértelmezett vállalatba jelentkezik be.

## <a name="submit-a-project-timesheet"></a>Projekt munkaidő-nyilvántartásának beküldése

Létrehozhat és beküldhet projekt munkaidő-nyilvántartást az alkalmazásban. Egy új munkaidő-nyilvántartást egy előző munkaidő-nyilvántartásra, elmentett sorok vagy projekt hozzárendelések adataira is alapozhatja. Ha Ön meghatalmazottként van kijelölve, más dolgozók számára is megadhat egy munkaidő-nyilvántartást. A munkaidő-nyilvántartás létrehozásához meghatalmazottként válassza ki a **Menü** gombot, majd válassza ki egy erőforrás nevét.

Az idő-nyilvántartási oldal létrehoz egy új munkaidő-nyilvántartást a munkaidő-nyilvántartási időszakához az aktuális dátum alapján. A munkahét jelenik meg. Ha a munkaidő-nyilvántartási időszak több hetet is lefed, választhat egy másik munkahetet is a munkahetek lapon.
Ha a munkaidő-nyilvántartási létezik az aktuális dátumhoz az megjelenik. Ha új időnyilvántartás létrehozására van szüksége egy másik idő-nyilvántartási időszakban válassza a **Menü** gombot, majd válassza az **Új időnyilvántartás** lehetőséget.

Projekt adatainak beviteléhez kattintson a **Idő hozzáadása a** műveletre vagy az **Idő másolása a következő helyről:** műveletre. Az **Idő másolása a következő helyről:** művelet bemásolja a projekt soradatokat, de az órákat nem. Az **Idő másolása a következő helyről:** menü az alábbi lehetőségeket tartalmazza.

- **Másolás meglévő munkaidő-nyilvántartásból** – Munkaidő-nyilvántartási sorok másolása egy meglévő munkaidő-nyilvántartásból.

- **Másolás a kedvencekből** – Új munkaidő-nyilvántartási sorok létrehozása a kedvenceknek kijelölt munkaidő-nyilvántartások beállításainak használatával.

- **Másolás hozzárendelésből** -Új munkaidő-nyilvántartás-sorok létrehozása a hozzárendelt projektekből.

A megjelenített projektadatok függnek a mobil paraméterektől, amelyeket a **Projektvezetési és könyvelési paraméterek** oldalon határozott meg.

A **Jogi személy** mezőben válassza ki azt a jogi személyt, amely számára végezte a projektmunkát. Megjegyzés A **Jogi személy** mező csak akkor érhető el, ha a vállalatközi időnyilvántartás támogatása engedélyezve van a jogi személyhez.

Válassza ki a munkaidő-nyilvántartás projektjéhez tartozó vevőt. Az első kiadás esetében a Android rendszerben, a bevitel vevő szerint nem támogatott, mivel ki kell választania először a projektet. Ha először a projektet választotta ki, a **Vevő** mezőt automatikusan ki lesz töltve.

A **Projekt** mezőben válassza ki azt a projektet, amelynek idejét meg szeretné adni. Az **Ügyfél** mezőt automatikusan kitölti a rendszer.

A vevő és a projekt keresések lehetővé teszik a keresést vevők és projektek között is.

Válassza ki az adatokat a **Kategória**, **Tevékenység**, **Sortulajdonság**, **Áfacsoport**, és **Cikkáfacsoport** mezőket igény szerint. Ezek a mezők felülbírálhatók.

A **Sortulajdonság** mező értéke egy alapértelmezett értékre lesz beállítva a projektvezetési és könyvelési paraméterek alapján. Ha a projekt/kategória és kategória/erőforrás paraméterek engedélyezve vannak, a **Sortulajdonság** értéke az ebben az ellenőrzésben megadott alapértelmezett értékre lesz beállítva. Ha a projekt/kategória és kategória/erőforrás paraméterek nincsenek engedélyezve, a **Sortulajdonság** érték alapértelmezésének beállítása az **Alapértelmezett sortulajdonság engedélyezése** mező alapján történik a **Projektvezetési és könyvelési paraméterek** oldalról. A **Sortulajdonság** értéke felülbírálható.

Válasszon egy napot az idő hozzáadásához. Adja meg minden napra a ledolgozott órák számát.

A bevitt órákkal kapcsolatos megjegyzések hozzáadásához kattintson a **Megjegyzések hozzáadása** elemre, majd adja meg a belső célközönségének vagy vevői célközönségnek szóló megjegyzéseket.
A belső megjegyzéseket a projektmenedzserek tekinthetik meg. Az Ügyfélmegjegyzések a számlákon szerepelnek.

A sor kedvencként történő mentéséhez jelölje be a jelölőnégyzetet, majd kattintson a **Mentés kedvencként** elemre.

A pénzügyi dimenziók és mellékletek nem támogatottak a mobilalkalmazásban.

Folytassa a projektsorok hozzáadásával, ahogy az munkaidő-nyilvántartás kitöltéséhez szükséges.

Kattintson a **Beküldés** gombra a munkaidő-nyilvántartás jóváhagyási munkafolyamatba való elküldéséhez.

## <a name="review-timesheets"></a>A munkaidő-nyilvántartások áttekintése

Ebben a menüben az áttekintendő munkaidő-nyilvántartások listája érhető el. Ez a lehetőség csak akkor érhető el, ha egy munkafolyamat jóváhagyójaként lett kijelölve. Fejléc és sorok jóváhagyása is támogatott. A sorszintű jóváhagyás felajánlja a lehetőséget egy vagy több sor jelölésére jóváhagyásra. A munkaidő-nyilvántartási adatok áttekintését követően kattintson **Jóváhagyás**, **Delegálás** vagy **Visszatérési** lehetőségre a munkafolyamat folytatásához.
