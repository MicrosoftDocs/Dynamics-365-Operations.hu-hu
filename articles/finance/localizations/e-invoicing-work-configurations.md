---
title: Konfigurációk használata
description: Ez a cikk áttekintést nyújt a globális funkciók munkaterületének elektronikus jelentéskészítési (ER) konfigurációiban történő alkalmazáshoz.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d87559405d2490c314eb2c8b88268af0dc0dfaca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283055"
---
# <a name="work-with-configurations"></a>Konfigurációk használata

[!include [banner](../includes/banner.md)]

Az elektronikus jelentéskészítési (ER) konfigurációk az elektronikus számlázási funkciók fő összetevőinek halmazai. Az ER-konfiguráció tartalmazza a fájlstruktúra beállításait és az adatok átalakítására vonatkozó átalakítási szabályokat, amelyek kétféleképpen alakítják át az adatokat:

- **ER-formátumkonfiguráció** exportálása – ez a konfiguráció átalakítja az adatokat az egységes belső szerkezetből (ER modell) az elektronikus fájlformátumba.
- **ER-formátumkonfiguráció** importálása – ez a konfiguráció átalakítja az adatokat az elektronikus fájlformátumból az egységes belső szerkezetbe (ER-modell).

A kimenő elektronikus fájlok előre meghatározott formátumú előállításán túl az ER-konfigurációkat is nagyban használják a külső webes szolgáltatásokból származó bejövő üzenetek válaszokként történő feldolgozására. Ez a funkció konfigurálható logikát épít ki, amely lehetővé teszi a külső csatornákkal való kommunikáció eredményeit, ezeket az eredményeket (kódokat, üzeneteket és naplókat) konvertálja a felhasználó számára olvasható struktúrára, majd át tudja adni ezeket az adatokat az ügyfélalkalmazásnak.

Ahhoz, hogy az elektronikus számlázási funkcióban elkezdhető legyen az ER-konfigurációk használata, a funkcióhoz kell őket kapcsolni, **és** elérhetővé kell tenni azokat a Konfigurációk lapon az aktuális funkcióverzióhoz. A csatolt ER-konfigurációt a Hozzáadás **, Törlés**, **Szerkesztés** **vagy Nézet lehetőség választásával használhatja** **.**

Az ER-konfigurációkra mutató hivatkozás hozzáadása előtt a konfigurációnak léteznie kell a szabályozó konfigurációs szolgáltatás (RCS) tárházában. A következő lépések szerint tekintse át az RCS-tárházban elérhető ER-konfigurációkat.

1. Jelentkezzen be a RCS-fiókba.
2. Az **Elektronikus jelentéskészítés** munkaterületen, a **Konfigurációk** szakaszban, válassza ki a **Jelentéskészítési konfiguráció** csempét.

Az új ER-konfigurációk létrehozásáról és a meglévő ER-konfigurációnak [a globális tárházból történő importálását az Elektronikus jelentési](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md) tudnivalókat lásd.

Ha módosítani szeretné a kapcsolt ER-konfigurációt, **válassza** a Szerkesztés lehetőséget **a** Konfigurációk lapon az aktuális elektronikus számlázási funkcióhoz. A rendszer automatikusan létrehozza az ER-konfiguráció egy verzióját. Ha az aktuális verziót nem az aktív konfigurációs szolgáltató hozta létre, akkor a rendszer létrehoz egy származtatott verziót, amely a konfigurációs szolgáltatót használja. Ha az aktuális verziót az aktív konfigurációs szolgáltató hozta létre, akkor a rendszer létrehoz egy új verziót. Mindkét esetben módosítani lehet a létrehozott verziót, majd automatikusan el lehet tetetni az összes szükséges frissítést.
