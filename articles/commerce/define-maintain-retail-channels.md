---
title: A kiskereskedelmi csatornák definiálása és karbantartása
description: Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Commerce rendszer „üzlet”-ként hivatkozik). Az üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a2ac4a4a42447e4ee57d24548a79f43b88b03927
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213698"
---
# <a name="define-and-maintain-retail-channels"></a>A kiskereskedelmi csatornák definiálása és karbantartása

[!include [banner](includes/banner.md)]

Ez a témakör a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Dynamics 365 Commerce rendszer „üzlet”-ként hivatkozik). Az üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.

A Commerce számos kiskereskedelmi csatornát támogat, például online áruházakat, hívásközpontokat, és fizikailag létező üzleteket. A tényleges, fizikailag létező boltot üzletnek nevezzük. Az üzletek saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek. Az üzlethez kapcsolódó összes elemet be kell állítania, létrehozás előtt. Miután létrehozta az üzletet, rendelje hozzá az üzlet által kezelendő termékeket. Rendelje hozzá az alkalmazottakat, a jegyzékeket, pénztárgépeket és a fogyasztókat is az üzlethez. Végül helyezze el az új üzletet a szervezeti hierarchiában.

## <a name="setting-up-stores"></a>Üzletek beállításai

Üzlet Commerce rendszerben való beállítása előtt el kell végeznie néhány előfeltételnek számító feladatot. Ezután létrehozhatja az üzletet, és megadhatja a részleteket.

### <a name="prerequisites"></a>Előfeltételek

Üzlet beállítása előtt el kell végeznie az alábbi feladatokat:

1. Konfigurálja a szervezeti struktúráját, majd állítsa be a szervezeti hierarchiát a kiskereskedelmi szortimenthez, feltöltéshez és jelentéshez.
2. Állítson be egy raktárt, amely az üzletet képviseli.
3. Adjon meg számsorozatokat az üzletekhez, üzleti kivonatokhoz és a kivonati bizonylatokhoz.
4. Paraméterek konfigurálása a Commerce számára.
5. Az üzlet által elfogadott fizetési módok beállítása.
6. Beállíthat fizetési szolgáltatásokat is a (POS) pénztárgépek által kezelendő hitelkártya tranzakciók feldolgozásához.
7. Áfacsoportok beállítása.
8. Termékek beállítása. A feladat részeként állítson be termékhierarchiát, termékváltozatot és termék szortimentet.
9. Termékárcsoportok beállítása.
10. Termékárazás beállítása. A feladat további részeként állítson be árkorrekciókat, engedményeket és kedvezmények időszakokat.
11. Munkatársak beállításai.

    > [!NOTE]
    > Megfelelő engedélyeket kell társítania a dolgozókhoz, hogy bejelentkezhessenek és feladatokat hajthassanak végre a POS használatával.

12. Konfigurálja az üzlethez hozzárendelendő profilokat. Ez a feladat számos egyéb feladatot foglal magában, mint például a pénztárgépek és jegyzékek, offline profilok és bevételezési formátumok megadása és azok paramétereinek beállítása.

Tekintse át az előfeltételekben foglalt valamennyi feladatot, és hajtsa végre közülük azokat, amelyek Önre vonatkoznak.

### <a name="set-up-a-store"></a>Egy üzlet beállítása

Miután befejezte az előfeltétel feladatait, hajtsa végre ezeket a feladatokat az üzlet adatainak beállításához:

1. Üzlet létrehozása.
2. Áfacsoportok hozzárendelése az üzlethez.
3. Az elfogadott fizetési módok hozzárendelése az üzlethez.
4. Termékleírások hozzáadása az üzletekben kínált egyes termékekhez. Megadhat például multimédiás szöveget és képeket. Ezek a termék részletek különböző helyeken jelennek meg, például a POS pénztárakban vagy a nyomtatott címkéken.
5. Adja hozzá az üzletet egy olyan alapértelmezett szervezeti hierarchiához, ami hozzá van rendelve az alábbi feladatok valamelyikéhez: **Kiskereskedelmi szortiment**, **Kiskereskedelmi feltöltés**, **Kiskereskedelmi jelentés**.

### <a name="after-you-set-up-a-store"></a>Miután beállította az üzletet

Miután megadta az üzlet részletes adatait, hajtsa végre ezeket a feladatokat az új üzlet adatainak a POS rendszerbe történő küldéséhez:

1. Állítsa be az üzletben használt POS pénztárgépek paramétereit.
2. Szortimentek hozzáadása az online áruházhoz
3. Szortimentek feldolgozása az üzlet szortimentjének tételes kilistázása, és az üzletben kínált termékek elérhetővé tétele érdekében.
4. Számsorozatok, hardverprofilok, POS pénztárgép képernyő-elrendezések adatainak tovább küldése a POS pénztár rendszer nyilvántartásába.
5. Tegye közzé az üzletet az üzlet-adatok POS rendszerbe való továbbításához.
6. Az üzletadatok POS rendszerbe történő küldésére szolgáló rutin futtatása.

## <a name="organization-hierarchies"></a>Szervezeti hierarchiák

A Commerce szervezeti hierarchiákat használ a csatornák strukturált kialakításához. A szervezeti hierarchiák az üzleti rendszer-struktúrát alkotó szervezetek között kapcsolatokat jelölik. Amikor egy üzletet konfigurál, azt egy szervezeti hierarchiához is hozzáadhatja. Az üzletek ezt követően megoszthatják a szortimentekhez, a feltöltéshez és jelentéshez használt adatokat.

> [!NOTE]
> A Commerce értékesítési funkciójának használatához engedélyezni kell a **Több célhely** konfigurációs kulcsát. Ez a konfigurációs kulcs megtalálható a **Kereskedelem konfiguráció** kulcsai között a **Rendszerfelügyelet**\> **Beállítás** \> **Licenckonfiguráció** alatt. Ez az értékesítésirendelés-sor szintjén konfigurált kézbesítési cím alapján végrehajtott különböző érvényesítések miatt szükséges.



[!INCLUDE[footer-include](../includes/footer-banner.md)]