---
title: "A kiskereskedelmi csatornák definiálása és karbantartása"
description: "Ez a cikk a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Microsoft Dynamics 365 for Operations rendszer „kiskereskedelmi üzlet”-ként hivatkozik). A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b775ba34ef7d88dd0b47904e4a3e9be79664f14b
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-maintain-retail-channels"></a>A kiskereskedelmi csatornák definiálása és karbantartása

[!include[banner](includes/banner.md)]


Ez a cikk a hagyományos üzlethelyiségek beállításának folyamatáról nyújt áttekintést (ezekre a Microsoft Dynamics 365 for Operations rendszer „kiskereskedelmi üzlet”-ként hivatkozik). A kiskereskedelmi üzlet beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.

A kiskereskedelem és kereskedelem a Dynamics 365 for Operations programban támogatja a többszörös kiskereskedelmi csatornát, mint például online boltok, hívásközpontok, és hagyományos boltok. A kiskereskedelemben és kereskedelemben a hagyományos boltokat kiskereskedelmi boltnak hívjak. Az üzletek saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek. Az üzlethez kapcsolódó összes elemet be kell állítania, létrehozás előtt. Miután létrehozta a kiskereskedelmi üzletet, rendelje hozzá az üzlet által kezelendő termékeket. Rendelje hozzá az alkalmazottakat, a jegyzékeket, pénztárgépeket és a fogyasztókat is az üzlethez. Végül helyezze el az új üzletet a szervezeti hierarchiában.

## <a name="setting-up-retail-stores"></a>Kiskereskedelmi áruházak beállításai
A kiskereskedelmi üzlet a Dynamics 365 for Operations programban való beállítása előtt el kell végeznie néhány előfeltétel feladatot. Ezután létrehozhatja a kiskereskedelmi üzletet, és megadhatja a részleteket.

### <a name="prerequisites"></a>Előfeltételek

Kiskereskedelmi üzlet beállítása előtt el kell végeznie az alábbi feladatokat:

1.  Konfigurálja a szervezeti struktúráját, majd állítsa be a szervezeti hierarchiát a kiskereskedelmi szortimenthez, feltöltéshez és jelentéshez.
2.  Állítson be egy raktárt, amely a kiskereskedelmi üzletet képviseli.
3.  Adjon meg számsorozatokat a kiskereskedelmi áruházakhoz, áruházi kivonatokhoz és a kivonati bizonylatokhoz.
4.  A kiskereskedelem paramétereinek konfigurálása.
5.  Az üzlet által elfogadott fizetési módok beállítása.
6.  Beállíthat fizetési szolgáltatásokat is a kiskereskedelmi (POS) pénztárgépek által kezelendő hitelkártya tranzakciók feldolgozásához.
7.  Áfacsoportok beállítása.
8.  Kereskedelmi termékek beállítása. A feladat részeként állítson be kiskereskedelmi termék hierarchiát, termékváltozatot és termék szortimentet.
9.  Termékárcsoportok beállítása.
10. Kiskereskedelmi termékárképzés beállítása. A feladat további részeként állítson be árkorrekciókat, engedményeket és kedvezmények időszakokat.
11. Munkatársak beállításai. **Megjegyzés:** Megfelelő engedélyeket kell társítania a dolgozókhoz, hogy bejelentkezhessenek és feladatokat hajthassanak végre a kiskereskedelmi POS pénztár Dynamics 365 for Operations rendszerében.
12. Konfigurálja a kiskereskedelmi POS pénztárban az üzlethez hozzárendelendő profilokat. Ez a feladat számos egyéb feladatot foglal magában, mint például a pénztárgépek és jegyzékek, offline profilok és bevételezési formátumok megadása és azok paramétereinek beállítása.

Tekintse át az előfeltételekben foglalt valamennyi feladatot, és hajtsa végre közülük azokat, amelyek Önre vonatkoznak.

### <a name="set-up-a-retail-store"></a>Kiskereskedelmi áruház beállítása

Miután befejezte az előfeltétel feladatait, hajtsa végre ezeket a feladatokat a kiskereskedelmi üzlet adatainak beállításához:

1.  Kiskereskedelmi üzlet létrehozása.
2.  Áfacsoportok hozzárendelése az üzlethez.
3.  Az elfogadott fizetési módok hozzárendelése az üzlethez.
4.  Termékleírások hozzáadása a kiskereskedelmi üzletekben kínált egyes termékekhez. Megadhat például multimédiás szöveget és képeket. Ezek a termék részletek különböző helyeken jelennek meg, például a POS pénztárakban vagy a nyomtatott címkéken.
5.  Adja hozzá az üzletet egy olyan alapértelmezett szervezeti hierarchiához, ami hozzá van rendelve az alábbi feladatok valamelyikéhez: **Kiskereskedelmi szortiment**, **Kiskereskedelmi feltöltés**, **Kiskereskedelmi jelentés**.

### <a name="after-you-set-up-a-retail-store"></a>Miután beállította a kiskereskedelmi üzletet

Miután megadta a kiskereskedelmi áruház részletes adatait, hajtsa végre ezeket a feladatokat az új áruház adatainak a kiskereskedelemi POS pénztár rendszerbe történő küldéséhez.

1.  Állítsa be az üzletben használt POS pénztárgépek paramétereit.
2.  Szortimentek hozzáadása az online áruházhoz
3.  Szortimentek feldolgozása a kiskereskedelmi üzlet szortimentjének tételes kilistázása, és az üzletben kínált termékek elérhetővé tétele érdekében.
4.  Számsorozatok, hardverprofilok, POS pénztárgép képernyő-elrendezések adatainak tovább küldése a kiskereskedelmi POS pénztár rendszer nyilvántartásába.
5.  Tegye közzé a kiskereskedelmi üzletet az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe való továbbításához.
6.  Az üzlet-adatok kiskereskedelmi POS pénztár rendszerbe történő küldésére szolgáló munka futtatása.

## <a name="organization-hierarchies"></a>Szervezeti hierarchiák
A kiskereskedelmi csatorna strukturálásához a Microsoft Dynamics AX programban a kiskereskedelmek szervezeti hierarchiát használnak. A szervezeti hierarchiák az üzleti rendszer-struktúrát alkotó szervezetek között kapcsolatokat jelölik. Amikor egy üzletet konfigurál, azt egy szervezeti hierarchiához is hozzáadhatja. Az üzletek ezt követően megoszthatják a szortimentekhez, a feltöltéshez és jelentéshez használt adatokat.




