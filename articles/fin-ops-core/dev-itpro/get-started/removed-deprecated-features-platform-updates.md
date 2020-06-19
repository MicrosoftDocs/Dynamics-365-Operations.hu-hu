---
title: Eltávolított vagy elavult Platform-funkciók
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.
author: sericks007
manager: AnnBe
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6fc699907d30fff2d05e752ea055cae8d1134d9b
ms.sourcegitcommit: 3eaa71c889545318737b3bc88b05eae1a47ad2c0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/05/2020
ms.locfileid: "3433922"
---
# <a name="removed-or-deprecated-platform-features"></a>Eltávolított vagy elavult Platform-funkciók

[!include [banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a platformfrissítésekben a Finance and Operations alkalmazásokból vagy az eltávolításuk be van tervezve.

- Az *eltávolított* szolgáltatások már nem érhetők el a termékben.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére. 

> [!NOTE]
> A Finance and Operations alkalmazások objektumaival kapcsolatban a [Technikai referenciajelentésekben](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep) talál részletes információkat. Ezen jelentések különböző verzióit összehasonlíthatja, hogy megismerje azokat az objektumokat, melyek módosítva lettek vagy el lettek távolítva a Finance and Operations alkalmazások egyes verzióiban.

## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.12 verziójához

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Érvénytelen mezők hivatkozásait tartalmazó rács vagy csoport vezérlő képernyő-kiterjesztések

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A rács vagy csoport vezérlőelem adatcsoport-tulajdonsága automatikusan megjeleníti a mezőcsoport összes mezőjét. A kiterjesztéssel hozzáadott rács vagy csoport tartalmazhat olyan mezőket, amelyek már nincsenek definiálva a mezőcsoportban, vagy hiányoznak azok a mezők, amelyek meg vannak határozva a mezőcsoportban. Ez inkonzisztens működést okozhat futásidőben. A Finance and Operations alkalmazások 10.0.12 verzióihoz tartozó platformfrissítések most már fordítási *figyelmeztetésként* kategorizálják ezt a problémát. A hiba elhárításához nyissa meg a képernyő-kiterjesztést, és mentse.
| **Felváltotta másik szolgáltatás?**   | Ezt a fordítói figyelmeztetést egy jövőbeli frissítés fordítói hibára fog lecserélni. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Egy fordítói figyelmeztetés került bevezetésre a Finance and Operations alkalmazások 10.0.12 verziójának platformfrissítéseiben. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Platform-frissítések az Finance and Operations alkalmazások 10.0.11 verziójához

### <a name="explicit-whitelisting-for-self-service-environments"></a>Explicit engedélyezési lista az önkiszolgáló környezetek számára

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Megváltozott az IP engedélyezési listázás folyamata. Az önkiszolgáló megoldás már nem támogatja az IP engedélyezési lista használatát. |
| **Felváltotta másik szolgáltatás?**   | További információ: [Azure Active Directory feltételez hozzáférés konfigurálása](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Érintett területek**         | Biztonság |
| **Telepítési beállítás**              | Felhőbeli |
| **Állapot**                         | **Elavult:** Ez a funkció teljes mértékben elavult az önkiszolgáló telepítések esetében. |

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A Visual Studio legújabb verzióinak támogatásához néhány módosítást be tenni az X++ Visual Studio kiterjesztések esetében. Ezek a változtatások nem kompatibilisek a Visual Studio 2015 megoldással. |
| **Felváltotta másik szolgáltatás?**   | A Visual Studio 2017 váltja a Visual Studio 2015 verziót a telepített és szükséges verzióként. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Amikor bejelentik az új virtuális gépek (VM) rendelkezésre állását a Visual Studio 2017 megoldással, létező, csak Visual Studio 2015 megoldást használó VM-eket újra kell telepíteni a 2021-es 1. kiadási hullámra. |

### <a name="field-groups-containing-invalid-field-references"></a>Érvénytelen mező hivatkozásokat tartalmazó mezőcsoportok

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A tábla metaadatok definíciójában található mezőcsoportok olyan mezőhivatkozásokat tartalmazhatnak, amelyek nem érvényesek. Ezen mezőcsoportok telepítése esetén hibákat okozhatnak futásidőben a Financial Reporting és a Microsoft SQL Server Reporting Services (SSRS) szolgálatásokban. A 23-as platformfrissítés bevezetett egy fordítási *figyelmeztetést*, amely a metaadat-problémák kezelését teszi lehetővé. A Finance and Operations alkalmazások 10.0.11 verzióihoz tartozó platformfrissítések fordítási *hibaként* kategorizálják ezt a problémát.<p>Ezen hiba javításához kövesse az alábbi lépéseket.</p><ol><li>Távolítsa el az érvénytelen mezőhivatkozást a tábla a mezőcsoport-definíciójából.</li><li>Végezzen újrafordítást.</li><li>Győződjön meg arról, hogy minden hiba orvosolva lett.</li></ol> |
| **Felváltotta másik szolgáltatás?**   | Ez a fordítóhiba véglegesen lecseréli a fordítói figyelmeztetését.  |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | **Elavult:** A fordítói figyelmeztetés fordítói hiba a Finance and Operations alkalmazások 10.0.11 verziójának platformfrissítéseiben. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Az SHA1 kivonatolási algoritmussal létrehozott ISV-licencek

|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A független szoftvergyártói (ISV) licencek létrehozási folyamata módosult. További tájékoztatás: [Független szoftvergyártói (ISV) licencek](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Felváltotta másik szolgáltatás?**   | Igen. Licencek létrehozása a Windows PowerShell használatával. |
| **Érintett területek**         | Visual Studio fejlesztőeszközök |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | <strong>Elavult:</strong> Az SHA1 kivonatolási algoritmussal létrehozott ISV-licencek. Ez az algoritmus a MakeCert segédprogrammal létrehozott tanúsítványokra épített, és ez a segédprogram elavult.<p><strong>Elavult:</strong> Az SHA1 használata biztonsági vagy kivonatolási célokra. Az SHA1 2021 elejétől nem működik majd. Ezért a továbbiakban nem használható.<p><strong>Eltávolítva</strong> : A Transport Layer Security (TLS) 1.0 és TLS 1.1 támogatása a bejövő vagy kimenő kérésekhez. |

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>A munkafolyamat-kérelem módosítási párbeszédpanele már nem tartalmaz felhasználói kiválasztást lehetővé tévő legördülő listát
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | Ez biztonsági hiba volt, mert a módosítási kérelmet nem szándékolt felhasználó számára is lehetett elküldeni. Ez egy használhatósági probléma is volt, mivel a felhasználó rá volt kényszerítve, hogy meghatározza, hogy ki volt a kezdeményező, és manuálisan ki kellet jelölnie.  |
| **Felváltotta másik szolgáltatás?**   | Nem |
| **Érintett területek**         | Munkafolyamat |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | A felhasználó kiválasztása legördülő lista el lett távolítva a 32-es platformfrissítésben. A módosítási kérelmeket a program automatikusan elküldi a létrehozónak, a szándéknak megfelelően. A funkciókkal kapcsolatos további tudnivalókat lásd: [Munkafolyamat-jóváhagyási folyamatok műveletei](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>A beágyazott részletező hivatkozások már nem támogatottak a felhőalapú szolgáltatások által megjelenített oldalszámmal ellátott dokumentumok esetében 
|   |  |
|------------|--------------------|
| **Elavulás/eltávolítás oka** | A szolgáltatás által megjelenített, dokumentumokba ágyazott navigációs URL-címek bizalmas üzleti adatokat is tartalmazhatnak. Biztonsági óvintézkedésként megszüntetjük a dokumentumok beágyazott részletező hivatkozásainak támogatását a vevők adatainak további védelme érdekében. A felhasználók számára is előnyös a jobb teljesítményt, miközben interaktívan állítanak elő dokumentumokat a módosítás eredményeképpen.  |
| **Felváltotta másik szolgáltatás?**   | Nincs |
| **Érintett területek**         | Jelentés |
| **Telepítési beállítás**              | Összes |
| **Állapot**                         | Ez a funkció aktívan el lesz távolítva a szolgáltatásból.<br><br>A korszerű ügyfél számos lehetőséget kínál olyan nézetek készítésére, amelyek automatikusan létrejövő hivatkozásokat is tartalmaznak, hogy segítsék a navigálást az alkalmazásban. A szolgáltatás által megjelenített, oldalszámmal ellátott dokumentumok olyan külső kommunikációhoz ajánlottak, amelyeket e-mailben elküldenek, archiválnak és kinyomtatnak címzetteknek. A dokumentumok közvetlenül a böngészőben történő előnézetének élményét a tapasztalatok alapján javítottuk amely közvetlen hozzáférést biztosít a helyi nyomtatókhoz. A további tudnivalókat lásd: [PDF-dokumentumok előnézete beágyazott megjelenítővel](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Korábbi bejelentések az eltávolított vagy elavult funkciókról
További tájékoztatás a korábbi verziókban eltávolított vagy elavult szolgáltatásokról: [Eltávolított vagy elavult funkciók a korábbi kiadásokban](../migration-upgrade/deprecated-features.md).

