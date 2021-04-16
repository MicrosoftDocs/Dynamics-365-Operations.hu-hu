---
title: Elektronikus számlázás GYIK
description: Ez a témakör az elektronikus számlázással kapcsolatos gyakori kérdéseket tartalmazza.
author: gionoder
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 41cddcdad5043ec314a94dda67f4f2e9de406cac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840172"
---
# <a name="electronic-invoicing-faq"></a>Elektronikus számlázás GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör az elektronikus számlázással kapcsolatos gyakori kérdésekre adott válaszokat tartalmazza. Az elektronikus számlázás kibővíti a Dynamics 365 Finance, Dynamics 365 Supply Chain Management és Dynamics 365 Project Operations meglévő elektronikus számlázási képességeit. 

## <a name="what-is-important-about-electronic-invoicing-and-why-should-it-matter-to-my-organization"></a>Mi fontos az elektronikus számlázással kapcsolatban, és miért fontos ez az én szervezetemnek?

A működési összetettség és a kockázat egyre erősebb mivel a szervezetek globálisan növekednek, és bővítik a jelenlétüket több régióban. A megfelelés fenntartása és a gyakran változó szabályozáshoz való igazodás egyre nagyobb kihívást jelent, és különösen fontos a számlázásnál. A számlázás hagyományosan drága, és gyakran hibák forrása, mivel a vállalatok papírdokumentumokra és munkaintenzív folyamatokra támaszkodnak.  

A szervezetek megkezdték a papíralapú számlákról való átállást, hogy csökkentsék a költségeket, és fel kell gyorsítsak a végpontok számának feldolgozását, és felgyorsítsák a teljes folyamatot. Az adózás digitalizációjának a egyik fő összetevője az elektronikus számlázás lesz a kormányok részéről. Azáltal, hogy a szervezeteknek digitálisan be kell nyújtaniuk a valós idejű adóinformációkat az adóhatóságok számára, a kormányok minimálisra csökkenthetik az adóelkerülést és -manipulációt és visszaszoríthatják a csalásokat. 

A világ a papírmentes dokumentumfeldolgozásra vált, és az elektronikus számlázás bevezetése nélkül a vevők a megfelelési problémákkal, a szükségtelen költségekkel és a versenytársaktól való lemaradással néznek szembe. 

## <a name="doesnt-finance-supply-chain-management-and-project-operations-already-include-electronic-invoicing-functionality-what-value-does-this-provide-to-me-as-a-customer"></a>A Finance, a Supply Chain Management és a Project Operations nem tartalmaz már elektronikus számlázási funkciókat? Milyen értéket ad ez nekem, mint ügyfélnek? 

Az elektronikus számlázás kiterjeszti a Finance, a Supply Chain Management és a Project Operations modulokban meglévő elektronikus számlázási lehetőségeket. Ez a funkció egyszerűbbé teszi a legújabb elektronikus számlázási szabályok betartását, és az elektronikus számlafeldolgozás és -adatcsere során egységes élményt nyújt a különböző földrajzi helyeken. Az elektronikus számlázási képességek számos előnyt nyújtanak, többek között: 

   - Ország-/régióspecifikus követelmények gyorsabb és egyszerűbb elfogadása.
   - Az e-számlázási megoldás implementációk standardizációja. 
   - Továbbfejlesztett elektronikus számlafeldolgozás nyomon követhetőség.  
   - Egyszerűbb karbantartás és megfelelés a változó jogi követelmények és a helyi üzleti gyakorlatoknak. 
   - Egyszerűsített megoldáscsomagolás.
   - Nagy mennyiségű benyújtott dokumentum skálázásának képessége, ami gyorsabb átfutást tesz lehetővé.
   - A megoldások megoszthatóak más vállalatokkal.

## <a name="does-electronic-invoicing-support-the-on-premises-installations-of-finance-supply-chain-management-and-project-operations"></a>Az elektronikus számlázás támogatja a helyszíni számlázást a Finance, a Supply Chain Management és a Project Operations modulokban? 

Az aktuális platform nem tesz lehetővé a helyszíni verzió használatát, és a jövőben sem tervezzük ennek támogatását.

## <a name="does-electronic-invoicing-interface-with-the-vendor-import-automation-feature"></a>Az Elektronikus számlázás együttműködik a szállítói importálás automatizálás funkcióval?

Nem. Erre a felületre tervek vannak, de ennek nincs időterve. Ha meg van tervezve, a dátumok a [Kiadási tervekben](https://docs.microsoft.com/dynamics365/release-plans/) lesznek bejelentve.

## <a name="how-does-electronic-invoicing-handle-file-attachments-into-the-electronic-invoice-is-a-sharepoint-server-needed-when-embedding-pdf-files-into-the-xml-file"></a>Hogyan kezeli az Elektronikus számlázás az elektronikus számlához csatolt fájlmellékleteket? Szükség van SharePoint-kiszolgálóra a PDF-fájlok XML-fájlba történő beágyazásához?

Az elektronikus számlához csatolt fájlok egy xml-elembe beágyazott bináris adatként vannak kezelve. A PDF-fájlok beágyazásához nem szükséges SharePoint-kiszolgáló, de a mellékletet a Finance, a Supply Chain Management és a Project Operations dokumentumkezelő rendszerben kell tárolni.

## <a name="is-electronic-invoicing-available-according-to-the-regulations-of-my-countryregion"></a>Az elektronikus számlázás a saját országom/régióm szabályozásának megfelelően érhető el?

Az elektronikus számlázás olyan mikroszolgáltatási platform, amely globálisan elérhető lesz.

A Microsoft azt tervezi, hogy közzéteszi az elektronikus számlaformátumokat és integrációkat a Microsoft által funkcionálisan honosított országokhoz. További információt az [Elektronikus számlázási szolgáltatások elérhetősége](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features) rész tartalmaz.

Ha az ön országának/régiójának elektronikus számlázási formátuma nem szerepel a listán, a platform célja, hogy a jövőben támogassa ezt a forgatókönyvet. Továbbra is élvezheti az elektronikus számlázás konfigurációs lehetőségeit, és saját maga konfigurálhatja az elektronikus számlázási formátumot, vagy dolgozhat egy partnerrel/ISV-vel, hogy a szervezete számára konfigurálják.

## <a name="is-dynamics-365-for-regulatory-services-a-new-module-like-human-resources-or-project-operations-that-is-linked-to-finance-or-supply-chain-management-are-there-extra-costs-for-that"></a>A Dynamics 365 for Regulatory Services egy olyan új modul, mint a Human Resources vagy a Project Operations, amely a Finance vagy a Supply Chain Management modulhoz van társítva? Vannak ennek extra költsége?

A Dynamics 365 for Regulatory Services (RCS) egy felhőszolgáltatás a globalizációs erőforrások konfigurálására. Az RCS minden Finaince, Supply Chain Management és Project Operations licenctulajdonos számára ingyenes.

Az RCS-regisztrációhoz látogasson el a <https://marketing.configure.global.dynamics.com/> oldalra.

További információért lásd a [Kapcsolódás a Regulatory Configuration Services (RCS) szolgáltatáshoz – Globalizációs funkciók](rcs-globalization-feature.md) részt.

## <a name="do-i-need-to-sign-up-to-get-electronic-invoicing--or-just-turn-it-on-in-feature-management"></a>Regisztrálnom kell az elektronikus számlázáshoz, vagy csak be kell kapcsolnom a Szolgáltatáskezelésben?

Ha Finance, Supply Chain Management és Project Operations licenccel rendelkezik, tekintse meg az [Első lépések az Elektronikus számlázás bővítményszolgáltatás adminisztrációjával](e-invoicing-get-started-service-administration.md) részt a feliratkozáshoz az elektronikus számlázásra.

## <a name="does-electronic-invoicing-work-with-tier-1-virtual-machines-what-is-the-minimal-required-environment"></a>Működik az elektronikus számlázás az 1. szintű virtuális gépekkel? Mi a minimálisan szükséges környezet?

Az elektronikus számlázással való integrációhoz legalább egy 2. szintű virtuális gépre van szükség a Finance vagy Supply Chain Management hosztolásához. A környezet tervezésével kapcsolatos további tudnivalókat lásd: [Környezet tervezése](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

## <a name="does-electronic-invoicing-have-a-test-mode-for-testing-invoice-submission"></a>Rendelkezik-e az elektronikus számlázás tesztmóddal a számlabenyújtás tesztelésére?

Ez konfigurációval érhető el. A számlaküldés teszteléséhez felhasználói elfogadási teszt (UAT) környezetből kapcsolódhat a Finance vagy a Supply Chain Management alkalmazáshoz, és küldhet be tesztszámlákat. Az elektronikus számlázás támogatja a teszt digitális tanúsítványok konfigurálást, és a digitális jóváhagyást igénylő e-számlák esetében az adóhatóság által közzétett teszt webszolgáltatások URL-jét.

## <a name="is-there-any-documentation-about-the-out-of-box-country-specific-electronic-invoicing-features"></a>Van-e dokumentáció a gyári országspecifikus elektronikus számlázási funkciókról?

Igen. Az elektronikus számlázási funkciók elérhetőségéről és a támogatott formátumokról lásd [Elektronikus számlázási szolgáltatások elérhetősége](e-invoicing-configuration-rcs.md#availability-of-electronic-invoicing-features).

> [!NOTE] 
> Ha nem találta meg a keresett választ, küldje el kérdését a termékfejlesztési csapatnak a következő címre: <D365EInvoicePreview@microsoft.com>. Vagy felvesszük Önnel a kapcsolatot, vagy javítjuk a GYIK lefedettségét.
