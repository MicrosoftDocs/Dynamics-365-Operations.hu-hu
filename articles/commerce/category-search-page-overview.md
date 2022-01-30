---
title: Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése
description: Ez a témakör a Dynamics 365 Commerce alkalmazás alapértelmezett kategória-céloldalának és keresési találatoldalának áttekintését nyújtja
author: ashishmsft
ms.date: 06/30/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6f61ee8ec212185e195e2cf1a9d6d25c31e4f672
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982434"
---
# <a name="default-category-landing-page-and-search-results-page-overview"></a>Alapértelmezett kategória-céloldal és keresési találatoldal áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce e-Commerce alkalmazás alapértelmezett kategória-céloldalának és keresési találatoldalának áttekintését nyújtja.

## <a name="default-category-landing-page"></a>Alapértelmezett kategória-céloldal

Az alapértelmezett kategória kezdőlap az a lap, ahova a rendszer a webhely felhasználóit általában irányítja, amikor egy kategóriát választanak ki a navigációs hierarchiában. A kategória lapon tallózhat, és a kategorizált termékeket is rendezheti és finomíthatja.

![Alapértelmezett kategória-céloldal.](./media/SimpleCategoryLandingDressCategory.png)

A lap tetején egy fejléc jelenik meg, amelyen látható az összes termékkategória és egyéb lap, amelyet a termékkihelyezési vezető kategorizált. A konfiguráció a csatorna navigációs hierarchiájának konfigurációja részeként történik. A lap alján van egy lábléc, amely gyorshivatkozásokat tartalmaz a különböző témákhoz, amelyek érdekesek lehetnek a vevők számára.

A következő összetevők elengedhetetlenek a kategóriákhoz:

- A **Termékelhelyezési csempék** azokat a termékeket jelenítik meg, amelyeket a termékkihelyezési vezető meghatározott egy kategóriában a navigációs hierarchia konfigurációjának részeként.
- A **Finomítások és választási lehetőségek összefoglalása** olyan szűrők, amelyek számokat biztosítanak, és a cikkek finomítására használhatók. A termékkihelyezési vezető a csatornakategóriákhoz és termékattribútumokhoz kapcsolódó metaadatok konfigurációjának részeként konfigurálja őket.
- A **Rendezési beállításokat** a webhely látogatói a termékek rendezéséhez használják. Alapértelmezés szerint a következő rendezési lehetőségek érhetők el:

    - Ár – növekvő sorrend
    - Ár – csökkenő sorrend
    - Termék neve – \[A–Z\]
    - Termék neve – \[Z–A\]
    - Értékelések – növekvő sorrend
    - Értékelések – csökkenő sorrend

- Az **Oldalszámozás** segítségével a webhely látogatói a kategorizált termékek találatainak egyik lapjáról a másikra kerülnek.
- A **Teljes szám** az adott kategóriába tartozó termékek teljes számát adja meg.

## <a name="enrich-a-category-landing-page"></a>Kategória céloldalának gazdagítása

Ha azt szeretné, hogy a kategória kezdőlapja egy adott kategóriára vonatkozóan testre szabottabb élményt nyújtson, akkor „bővítheti” az adott kategóriához tartozó céloldalt. Hozzáadhat például egy marketingvideót és némi kategórialeírást a vásárló figyelmének felkeltéséhez. A további tudnivalókat lásd: [Kategória céloldalának bővítése](enrich-category-page.md).

![Bővített kategória-céloldal.](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>Automatikus javaslat és keresési eredmények lapjai

A webhely felhasználói felfedezhetik a webhelyet úgy, hogy a navigációs hierarchia egyik kategóriájába lépnek, vagy egy keresési kifejezés beírásával megadják a keresési feltételt a keresési mezőben.

Amint a felhasználó megkezdi a gépelést a keresési mezőben, megtapasztalhatja a keresési kifejezéseket ajánló automatikus javaslatok élményét.

Az alábbiakban a javaslatok néhány típusa látható:

- A **Kulcsszavak** a cikkeknek a csatorna szortimentjébe tartozó összes termék közötti keresésére szolgálnak.
- A **Termékek** közvetlen kapcsolatot biztosítanak a termék részletes lapjához.
- A **Hatókörön belüli kategória javaslatai** különböző kategóriákat sorolnak fel, és lehetővé teszik a felhasználók számára, hogy egy adott kategóriában keressenek rá a kulcsszóra.

![Modern automatikus ajánlások.](./media/ImmersiveAutoSuggestUX.png)

Amikor a felhasználók kiválasztják a kulcsszó vagy a hatókörön belüli kategória keresési javaslatainak valamelyikét, vagy ha a megadott keresési kifejezésre nem található javaslat, akkor a program a keresési találatok lapra irányítja őket. A felhasználók ezután böngészhetik, rendezhetik és finomíthatják a keresési eredmények listáját a kívánt cikk megkereséséhez.

![Keresés céloldala.](./media/SearchLanding.png)

A következő összetevők elengedhetetlenek a keresési találatok laphoz:

- A **Termékelhelyezési csempék** a felhasználó kereséséhez jelenítik meg a termékeket. Alapértelmezés szerint ezek a csempék a felhasználó keresés felhőalapú relevancia-pontszáma alapján vannak sorba rendezve.
- A **Finomítások és választási lehetőségek összefoglalása** olyan szűrők, amelyek számokat biztosítanak, és a cikkek finomítására használhatók. A termékkihelyezési vezető a „csatornakategóriákhoz és termékattribútumokhoz” kapcsolódó metaadatok konfigurációjának részeként konfigurálja őket.
- A **Rendezési beállításokat** a webhely látogatói a termékek rendezéséhez használják. Alapértelmezés szerint a következő rendezési lehetőségek érhetők el:

    - Ár – növekvő sorrend
    - Ár – csökkenő sorrend
    - Termék neve – \[A–Z\]
    - Termék neve – \[Z–A\]
    - Értékelések – növekvő sorrend
    - Értékelések – csökkenő sorrend
    - Alapértelmezett

- Az **Oldalszámozás** segítségével a webhely látogatói a kategorizált termékek találatainak egyik lapjáról a másikra kerülnek.
- A **Teljes szám** az adott kategóriába tartozó és a keresési feltételeknek megfelelő termékek teljes számát adja meg.

>[!NOTE]
>Ezek a felhőalapú keresési funkciók a 10.0.8 verziótól érhetők el. Ellenőrizze, hogy a **Kereskedelmi paraméterek > Konfigurációs paraméterek** között van-e egy bejegyzés a következőhöz: „ProductSearch. UseAzureSearch 'igaz' értékre állítva”. 
![A felhőalapú keresés konfigurációs paraméterei.](./media/CloudPoweredSearchConfigurationParameters.png)

## <a name="additional-resources"></a>További erőforrások

[Felhőalapú keresés – áttekintés](cloud-powered-search-overview.md)

[Kezdőlap – áttekintés](quick-tour-home-page.md)

[Termékadatok oldalainak áttekintése](quick-tour-pdp.md)

[Kosár és pénztár oldalainak áttekintése](quick-tour-cart-checkout.md)

[Fiókkezelési oldalak áttekintése](quick-tour-account-management.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]