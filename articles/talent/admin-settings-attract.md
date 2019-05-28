---
title: Adminisztratív beállítások az Attract alkalmazásban
description: Ez a témakör bemutatja, hogyan lehet engedélyezni a szervezetek és felhasználók szolgáltatásfunkcióit az Attractban.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 0de215103306ef7115ba390b1b4855179979c77b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518219"
---
# <a name="admin-settings-in-attract"></a>Adminisztratív beállítások az Attract alkalmazásban
[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Talent: Attract felügyeleti központja konfigurációs beállításokat, integrációs beállításokat és az Attract alkalmazás beállításait tartalmazza.

## <a name="company-information"></a>Vállalati adatok

Adjon meg egy megjelenített nevet a vállalatnak, és adjon hozzá egy vállalati emblémát. A megjelenített nevet és az emblémát fel lehet használni az állásfeladásokon és a bevezetés szakasz során.

## <a name="linkedin-integration"></a>LinkedIn-integráció

A LinkedIn Recruiter System Connect  (RSC) modul integrációjának beállítása. A LinkedIn kapcsolódás után a LinkedIn hitelesítő adatok használatával, szinkronizálhatja a jelentkező LinkedIn profilját, az alkalmazásokat, az interjú-visszajelzéseket és a felvételi csapat megjegyzéseit. Teljes LinkedIn toborzó licenccel kell rendelkeznie. További tájékoztatásért az LinkedIn Recruiter szolgáltatással kapcsolatban lásd: [Recruiter System Connect (RSC) – GYIK](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Felhasználói jogosultságok

Szerepkörök hozzárendelése felhasználókhoz a szervezetben. A következő szerepkörök állnak rendelkezésre: **Adminisztrátor**, **Toborzó**, **Felvételi vezető** és **Írásvédett**. A felhasználó engedélyekkel kapcsolatos további tudnivalókért tekintse át a [Biztonság és szerepkörkezelés az Attract alkalmazásban](./security-attract.md) részt.

## <a name="feature-management"></a>Funkció kezelése

Ahogy elkészülnek az új funkciók, előfordulhat, hogy nyilvános előnézetként adjuk ki őket. A nyilvános előnézeti funkciók nem felelnek meg az összes szolgáltatási követelménynek. Az elfogadásukkal az adatai külső rendszerekkel való megosztását is elfogadja. Előfordulhat, hogy a vállalata számára nem szükséges minden kiadott új funkció. Ki- és bekapcsolhatja nyilvános előnézeti funkciókat, a vállalata igényeitől függően.

## <a name="template-management"></a>Sablonkezelés

A folyamat sablonja egy állás felvételi folyamatának összes tevékenységet tartalmazza. A szervezete engedélyezheti, hogy a szervezet összes csapattagja, vagy csak a rendszergazdák hozhassanak létre felvételifolyamat-sablonokat. Ahhoz, hogy a csoporttagok saját felvételifolyamat-sablonokat hozhassanak létre, kapcsolja be a sablonkezelés funkciót. Folyamatsablonokkal kapcsolatos további tudnivalókat lásd: [Folyamatsablonok az Attract alkalmazásban](./process-templates-attract.md).

## <a name="email-template-settings"></a>E-mail-sablon beállításai

A szervezetek különböző helyzetekre e-mailsablonokat hozhatnak létre. Az e-mailsablonokba foglalandó fejlécképet kiválaszthatja. A kijelölt fejléc az összes e-mailsablonban meg fog jelenni. A sablon láblécében hivatkozást adhat hozzá, amely a szervezet adatvédelmi nyilatkozatára és kommunikációs használati feltételeire mutat. További tájékoztatás: [E-mailsablonok az Attract alkalmazásban](./email-templates.md).

## <a name="offer-process"></a>Ajánlati folyamat

Beállíthatja az állásajánlat jóváhagyási folyamatát. Megadhatja például, hogy az ajánlatot jóvá kell-e hagyni a pályázónak való elküldés előtt. Megkövetelheti azt is, hogy a jóváhagyóknak meg kelljen adniuk egy megjegyzésben az ajánlatra vonatkozó döntést.

Két jóváhagyási munkafolyamat használható: **Párhuzamos** és **Egymás utáni**.

- **Párhuzamos** – A jóváhagyásokat elküldi a program minden jóváhagyónak egyszerre.
- **Egymás utáni** – A jóváhagyók konkrét sorrendben látják a jóváhagyási kéréseket.

Megadhat a pályázói tapasztalatokkal kapcsolatos beállításokat is. Például egy beállítással megadhatja, hogy pályázó elutasíthatja-e további vitafórum nélkül az ajánlatot. Ha **A jelöltek további vitafórum használata nélkül elutasíthatják az ajánlatot** lehetőség beállítása **Nem**, az **Ajánlat elutasítása** gomb elérhető a pályázóknak. Ha a lehetőség beállítása **Igen**, a pályázó elutasíthatja az ajánlatot az okának kiválasztásával, és az **Ajánlat elutasítása** választásával.

Beállíthat és kikényszeríthet egy lejárati dátumot az ajánlatokhoz. Ha beállítja a **Minden ajánlathoz szükséges lejárati dátum** opciót az **Igen** lehetőségre, az ajánlatok lejárnak a megadott számú óra vagy napok után.

Ajánlat kezelésével kapcsolatos további tudnivalókat lásd: [Ajánlat kezelésének beállítása](./offer-setup.md).
