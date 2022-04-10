---
title: Regulatory Configuration Service (RCS) - Lifecycle Services (LCS) tárhely kivezetése
description: Ez a témakör a Regulatory Configuration Service (RCS) globális tárházának kivezetésének a Microsoft Dynamics Lifecycle Services (LCS) tárolók kivezetéséről tájékoztatást.
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 68f1ed6a6d6bb0d15a81539da7f483ad71a4d696
ms.sourcegitcommit: 477efa4cb138f41d4f68bcd82552af3473bcc3d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2021
ms.locfileid: "7715230"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) tárhely kivezetése

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics Lifecycle Services (LCS) használata tárolási adattárként az Elektronikus jelentéskészítés (ER) konfigurációihoz ki lesz vezetve. Ez a kivezetés a következő változásokkal jár:

- A Microsoft Dynamics 365 alkalmazásokban használt Microsoft által előállított konfigurációk a továbbiakban nem lesznek közzétéve az LCS Közös eszköz könyvtárában. Ehelyett csak az RCS globális tárházon keresztül lesznek közzétéve. Ugyanakkor a Dynamics AX 2012 konfigurációi mindaddig közzé lesznek téve az LCS közös eszközkönyvtárában, amíg az AX 2012 támogatási életciklusa véget nem ér.
- Inaktiválva lesz az a funkció, amely lehetővé teszi a konfigurációk feltöltését az LCS projekt eszközkönyvtárába a Finance and Operations alkalmazásokból és az RCS-ből. Ennek ellenére használhatja az LCS böngészőjét a konfigurációknak a Projekt eszköztárba való feltöltésére. Ennek megfelelően továbbra is hozzáadhat konfigurációkat az LCS-hez, hogy azok a megoldáscsomagokba bekerülhessenek.
- Az LCS-ből való konfiguráció importálások egy ideig még elérhetők és támogatottak lesznek a Finance and Operations alkalmazásokban, illetve az RCS szolgáltatásban. Ugyanakkor az a funkció egy idő után ki lesz vezetve. (A kivezetés pontos dátumát később fogjuk bejelenteni.)

## <a name="deprecation-notice"></a>Elavulásáról szóló értesítés

Az LCS tárhelyként való felhasználása kivezetésének kommunikálása a [Dynamics 365 Finance eltávolított vagy avultatott funkciói – LCS avultatás bejelentése](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release) közleményben megtörtént. A tervezett kivezetés dátuma 2022. április 1.

## <a name="key-features"></a>Fő funkciók

- Az RCS használatával ER-konfigurációkat és globalizációs funkciókat hozhat létre és szerkeszthet.
- A konfigurációkat közvetlenül az RCS-tervezőből küldheti át egy csatlakoztatott alkalmazásba, például egy Dynamics 365 Finance környezetbe, így gyorsan el lehet elvégezni és tesztelni a konfigurációk módosításait.
- Az ER-konfigurációk és a globalizációs funkciók életciklusának központi tárolása, megosztása és kezelése a globális tárház központi tárolóján keresztül.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>Útmutatás az egyszeri és folyamatos műveletekhez

Ez a szakasz olyan lépéssorozatokat ír le, amelyeket egyszer kell végrehajtani. Ismerteti azokat a lépéseket is, amelyekre a későbbiekben folyamatosan szükség van.

### <a name="one-time-action"></a>Egyszeri művelet

Importálja az összes szükséges konfigurációt az LCS-ről az RCS szolgáltatásba, majd tegye közzé az RCS rendszerből a globális tárházba. Ha projektspecifikus eszközkönyvtárak segítségével tárolja a származtatott konfigurációkat az LCS szolgáltatásban, a következő lépéseket kell végrehajtani, amíg az LCS elérhető.

1. Ha még nem érhető el RCS-példány, létesítsen egyet. A további tudnivalókat lásd: [RCS áttekintése](rcs-overview.md).
2. A létesített RCS-példányban a származtatott ER-konfigurációkat tartalmazó eszköztár minden LCS-projekthez regisztráljon megfelelő LCS-tárházat.
3. Az LCS-tárházból az RCS-be importálja az ER-konfigurációkat. További információ: [Konfigurációk importálása LCS-ből](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md).
4. Ha nincs automatikusan biztosítva globális tárház, regisztrálja az RCS szolgáltatásban.
5. Az aktuális RCS-példány összes származtatott konfigurációját töltse fel a globális adattárba. A **Konfigurációs csomagok** funkció használata segíthet a feltöltésben. A további tudnivalókat lásd: [RCS globális adattár felöltés](rcs-global-repo-upload.md).

### <a name="going-forward"></a>A későbbiekben

Az RCS vizuális tervezői a következő célokra használhatók:

- A Microsoft által biztosított sablonok kibővítése.
- A szervezet számára szükséges új konfigurációk létrehozása.
- Az elektronikus számlázás és az adószámítási szolgáltatás globalizációs funkcióinak testreszabása.

A Globalizációs tárhely a következő célokra használható:

- Hozzáférés a Microsoft által készített konfigurációkhoz és a globalizációs funkciókhoz.
- Töltse fel a létrehozott vagy kibővített konfigurációkat a globális tárházba, és ossza meg azokat a szervezete Dynamics 365 alkalmazáskörnyezetében vagy külső szervezetekkel. A további tudnivalókat lásd: [Hozzon létre ER-konfigurációkat a RCS-ben, és töltse fel őket a globális tárházba](rcs-global-repo-upload.md).

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>Ez a módosítás azt jelenti, hogy az LCS nem használható központi tárolóként a konfigurációkhoz?

Igen. Ki lesz vezetve az a funkció, amely lehetővé teszi a konfigurációk feltöltését az LCS projekt eszközkönyvtárába a Finance and Operations alkalmazásokból és az RCS-ből ki. Ennek ellenére használhatja az LCS böngészőjét a konfigurációknak a Projekt eszköztárba való feltöltésére igény szerint.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>Úgy gondoltam, hogy az RCS egy helyettesítő tárház a globális sablonfájlok importálásához. Nem hittem, hogy ez konfigurációk tárolására használatos. Mi a valóság?

Az RCS az ER-konfigurációk létrehozására és szerkesztésére szolgáló tervezőszolgáltatás. Az RCS-nek saját saját tárháza van, a Globális adattár. Ez az adattár az RCS-ben létrehozott konfigurációk tárolására használható. Miután az LCS-t tárolási funkció ki lesz vezetve, a globális tárház lesz a Microsoft-konfigurációk egyetlen forrása. Egy egyszeri műveletet kell végrehajtania ahhoz, hogy importálni tudja az összes szükséges konfigurációt az LCS-ről az RCS szolgáltatásba, majd közzéteheti azokat RCS-ben a globális tárházban.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>Az LCS nélkül milyen módszer javasolt a konfigurációk tárolására, hogy a "teszt" és a "termelési" konfigurációk egyszerűen kezelhetők és átvihetők legyenek?

Az RCS a *csatlakoztatott alkalmazás* koncepcióját használja. A csatlakoztatott alkalmazás kapcsolatot létesít az RCS és minden Finance and Operations alkalmazáspéldány között. Mivel az RCS a konfigurációk szerkesztésére használható, a csatlakoztatott alkalmazás segítségével közvetlenül lehet átküldeni a konfigurációkat a tervezőből a Finance and Operations alkalmazáskörnyezetbe. Így gyorsan módosíthatja és tesztelheti a konfigurációkat, ahelyett, hogy végig kellene mennie az LCS-projektszintű tárhelyen.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>Vannak példák a beállításokra és a kezelésre?

Nincsenek példák, de a témakör korábbi lépései alapján át lehet telepíteni a konfigurációkat az RCS globális tárházba.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>Az RCS előfeltétele az Elektronikus jelentéskészítés konfigurálásának?

Igen. Az RCS olyan funkciókat tartalmaz, amelyek támogatják a globalizációs szolgáltatások, például az elektronikus számlázás és az adószámítási szolgáltatás által használt globalizációs funkciók beállítását. A szolgáltatás ugyanakkor ugyanazokkal a vizuális tervezői funkciókkal rendelkezik, amelyek révén új ER-konfigurációkat lehet kibővíteni vagy létrehozni. Az RCS az ER-konfigurációkhoz és a globalizációs funkciókhoz is biztosít életciklus-kezelési funkciókat.

### <a name="which-regions-can-rcs-be-deployed-in"></a>Mely régiókban telepíthető az RCS-k?

Az RCS a következő Azure-régiókban érhető el:

- Egyesült Államok
- India
- Franciaország
- Európa

A terméktámogatásról a [Dynamics globalizációs szolgáltatások áttekintése](globalization-services-overview.md) cikk nyújt további tájékoztatást. A földrajzi támogatással kapcsolatos további tudnivalókat lásd: [Dynamics 365 és Power Platform: Elérhetőség, adatok helye, nyelv és honosítás](https://aka.ms/rcs/D365Productavailabilityguide).

### <a name="whats-the-cost-of-using-rcs"></a>Mi az RCS használatának költsége?

Az RCS és a globalizációs tárház ingyenesen elérhető a meglévő Finance and Operations alkalmazáslicencek részeként. Nincs külön költség társítva az RCS tervezőszolgáltatás használatához vagy a konfigurációknak a globális tárházban való tárolásához. Jelenleg nincs korlátozva a konfigurációk vagy a csatlakoztatott alkalmazások száma.
