---
title: Online áruházak beállítása
description: Ez a cikk olyan témakörökre mutató hivatkozásokat tartalmaz, amelyek segítenek az online áruház központi konfigurálásában és kezelésében.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 31541
ms.assetid: 7a25f9b4-a0bb-4e8c-95c0-c0799ec0620d
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 142a7fa8a18b14347761d3f116c30f2fa5476115
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025745"
---
# <a name="configure-online-stores"></a>Online áruházak beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk olyan témakörökre mutató hivatkozásokat tartalmaz, amelyek segítenek az online áruház központi konfigurálásában és kezelésében.

A következő táblázatban felsorolt témakörök segítenek konfigurálni a Retail összetevőit és az online Retail-áruházat a kliensben.

## <a name="configure-an-online-store"></a>Online áruház konfigurálása

| Feladat                                                | Részletek                                                                                                                                                                                                                                                                                                                                                   | Témakörök                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Retail-összetevők konfigurálása.                        | A kiskereskedelmi műveletek adatainak kezelése és beállítása. Ezen információk tartalma: áruházak, adók, termékek, ajándékutalványok, promóciók és kedvezmények.                                                                                                                                                                                                          | A [Retail beállítása és karbantartása](https://technet.microsoft.com/library/hh597201.aspx) (TechNet-tartalom a Microsoft Dynamics AX 2012-höz)                                                                                                                                                                                                                                                                                          |
| Kiskereskedelmi csatorna navigációs hierarchiájának konfigurálása.    | Hozza létre a kiskereskedelmi csatornák navigációs kategóriahierarchiáját, amely kategóriaszerkezet beállítására használható online áruházon keresztül kínált termékekhez. Ön megadja a kategóriahierarchiát, majd termékeket, termékattribútumok csoportjait és attribútumértékeket rendel a kategóriákhoz. Ezután a kategóriahierarchiát hozzárendeli egy online áruházhoz.                            | [Kiskereskedelmi hierarchia beállítása](https://technet.microsoft.com/library/hh580593.aspx) (TechNet-tartalom az AX 2012-höz) [Attribútumok és attribútumtípusok beállítása](https://technet.microsoft.com/library/hh227548.aspx). (TechNet-tartalom az AX 2012-höz) [Kiskereskedelmi attribútumcsoportok beállítása](https://technet.microsoft.com/library/jj728713.aspx). (TechNet-tartalom az AX 2012-höz) |
| Adja hozzá az online áruházat a szervezeti hierarchiához. | A létrehozott online áruházban termékválaszték hozzárendelése, a megrendelések teljesítése vagy az online áruházi adatokat tartalmazó jelentések előállítása előtt az áruházat hozzá kell rendelnie egy vagy több szervezeti hierarchiához. Az online áruházat hozzá kell rendelnie legalább egy olyan szervezeti hierarchiához, amely termékválasztékot tartalmaz. | [Online áruház beállítása](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                                                                                                                                                                                                     |
| Adjon hozzá szállítási módokat az online áruházhoz.          | Válassza ki a szállítási módokat, amelyeket az online áruház kínál.                                                                                                                                                                                                                                                                                                 | [Online áruház beállítása](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-tartalom a Microsoft AX 2012-höz)                                                                                                                                                                                                                                                                                                     |
| Feleltessen meg attribútumokat és adjon hozzá metaadatokat.                   | Jelölje ki azokat a beállításokat, amelyek az attribútumok viselkedését jelzik az online áruház egyes kategóriáinál vagy csatornatermékeinél a Microsoft SharePoint webhelyen.                                                                                                                                                                                              | [Online áruház beállítása](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                                                                                                                                                                                                     |

## <a name="configure-online-store-products"></a>Online áruház termékeinek beállítása

| Feladat                                 | Részletek                                                                                                                                           | Témakörök                                                                                                                                                                                                                                                                            |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Adjon hozzá szortimenteket az online áruházhoz. | Adja hozzá az online áruházban kínált termékeket tartalmazó termékszortimenteket.                                                                  | [Online áruház beállítása](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                                              |
| Katalógusok kezelése.                     | Termékkatalógusok segítségével azonosítsa azokat a termékeket, amelyeket az online áruházaiban szeretne árusítani.                                                              | [Legfontosabb feladatok: Kiskereskedelmi termékkatalógusokat létrehozni](https://technet.microsoft.com/library/jj728712.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                           |
| Árak kezelése.                       | Állítson be és használjon árcsoportokat, amelyek a központi kapcsolatot képviselik az árak és engedmények, csatornák, katalógusok, viszonyok és hűségprogramok között. | [Árcsoportok segítségével árak beállítása](https://technet.microsoft.com/library/hh597169.aspx) (TechNet-tartalom az AX 2012-höz) [Adók beállítása](https://technet.microsoft.com/library/hh580571.aspx) (TechNet-tartalom az AX 2012-höz) |
| Kedvezmények kezelése.                    | Állítson be és kezeljen ármódosításokat és négyféle engedményt.                                                                                  | [Ármódosítások és engedmények beállítása](https://technet.microsoft.com/library/hh597114.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                          |
| Szállítási költségek kezelése.             | Állítson be és kezeljen az online áruházra szabott szállítási költségeket.                                                                     | [Az online áruházak szállítási költségeinek beállítása](https://technet.microsoft.com/library/jj728714.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                           |
| Szállítási módok kezelése.            | Kezelje az online áruházban kínált szállítási módokat.                                                                                        | [Szállítási módok beállítása](https://technet.microsoft.com/library/jj728719.aspx) (TechNet-tartalom az AX 2012-höz)                                                                                                                                            |

## <a name="set-up-data-exchange-between-microsoft-dynamics-365-retail-and-the-online-store"></a>Adatcsere beállítása a Microsoft Dynamics 365 Retail és az online áruház között

| Feladat                                 | Részletek                                                                                                                               | Témakörök                                                                                                                                                                                                                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Csatornaintegrácis profilok beállítása. | A profilok lehetővé teszik a Retail összetevőinek egymással folytatott kommunikációját. Állítson be profilokat az adatcsere beállításainak konfigurálása előtt. | [Valós idejű szolgáltatási profil beállítása](https://technet.microsoft.com/library/hh580631.aspx) (TechNet-tartalom az AX 2012-höz) [Csatornaprofil beállítása](https://technet.microsoft.com/library/jj677402.aspx) (TechNet-tartalom az AX 2012-höz) |





