---
title: Online áruházak beállítása
description: Ez a cikk olyan témakörökre mutató hivatkozásokat tartalmaz, amelyek segítenek az online áruház központi konfigurálásában és kezelésében.
author: kfend
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 31541
ms.assetid: 7a25f9b4-a0bb-4e8c-95c0-c0799ec0620d
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 87607e2c42ee67d62a7ce2e87744e9d9143dcf81
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734104"
---
# <a name="configure-online-stores"></a>Online áruházak beállítása

[!include [banner](../includes/banner.md)]

Ez a cikk olyan témakörökre mutató hivatkozásokat tartalmaz, amelyek segítenek az online áruház központi konfigurálásában és kezelésében.

A következő táblázatban felsorolt témakörök segítenek konfigurálni a Commerce összetevőit és az online áruházat a kliensben.

## <a name="configure-an-online-store"></a>Online áruház konfigurálása

| Feladat                                                | Részletek                                                                                                                                                                                                                                                                                                                                                   | Témakörök                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurálja az összetevőket.                        | A kereskedelmi műveletek adatainak kezelése és beállítása. Ezen információk tartalma: áruházak, adók, termékek, ajándékutalványok, promóciók és kedvezmények.                                                                                                                                                                                                          | A [Retail beállítása és karbantartása](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-retail) (TechNet-tartalom a Microsoft Dynamics AX 2012-höz)                                                                                                                                                                                                                                                                                          |
| Csatorna navigációs hierarchiájának konfigurálása.    | Hozza létre a csatornák navigációs kategóriahierarchiáját, amely kategóriaszerkezet beállítására használható online áruházon keresztül kínált termékekhez. Ön megadja a kategóriahierarchiát, majd termékeket, termékattribútumok csoportjait és attribútumértékeket rendel a kategóriákhoz. Ezután a kategóriahierarchiát hozzárendeli egy online áruházhoz.                            | [Kiskereskedelmi hierarchia beállítása](/dynamicsax-2012/appuser-itpro/set-up-a-retail-hierarchy)</br> (TechNet-tartalom AX 2012-höz)</br> [Attribútumok és attribútumtípusok beállítása](/dynamicsax-2012/appuser-itpro/set-up-attributes-and-attribute-types) (TechNet-tartalom AX 2012-höz)</br> [Kiskereskedelmi attribútumcsoportok beállítása](/dynamicsax-2012/appuser-itpro/set-up-retail-attribute-groups) (TechNet-tartalom AX 2012-höz) |
| Adja hozzá az online áruházat a szervezeti hierarchiához. | A létrehozott online áruházban termékválaszték hozzárendelése, a megrendelések teljesítése vagy az online áruházi adatokat tartalmazó jelentések előállítása előtt az áruházat hozzá kell rendelnie egy vagy több szervezeti hierarchiához. Az online áruházat hozzá kell rendelnie legalább egy olyan szervezeti hierarchiához, amely termékválasztékot tartalmaz. | [Online áruház beállítása](/dynamicsax-2012/appuser-itpro/set-up-an-online-store) (TechNet-tartalom az AX 2012-höz)                                                                                                                                                                                                                                                                                                     |
| Adjon hozzá szállítási módokat az online áruházhoz.          | Válassza ki a szállítási módokat, amelyeket az online áruház kínál.                                                                                                                                                                                                                                                                                                 | [Online áruház beállítása](/dynamicsax-2012/appuser-itpro/set-up-an-online-store) (TechNet-tartalom a Microsoft AX 2012-höz)                                                                                                                                                                                                                                                                                                     |
| Feleltessen meg attribútumokat és adjon hozzá metaadatokat.                   | Jelölje ki azokat a beállításokat, amelyek az attribútumok viselkedését jelzik az online áruház egyes kategóriáinál vagy csatornatermékeinél a Microsoft SharePoint webhelyen.                                                                                                                                                                                              | [Online áruház beállítása](/dynamicsax-2012/appuser-itpro/set-up-an-online-store) (TechNet-tartalom az AX 2012-höz)                                                                                                                                                                                                                                                                                                     |

## <a name="configure-online-store-products"></a>Online áruház termékeinek beállítása

| Feladat                                 | Részletek                                                                                                                                           | Témakörök                                                                                                                                                                                                                                                                            |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Adjon hozzá szortimenteket az online áruházhoz. | Adja hozzá az online áruházban kínált termékeket tartalmazó termékszortimenteket.                                                                  | [Online áruház beállítása](/dynamicsax-2012/appuser-itpro/set-up-an-online-store) (TechNet-tartalom az AX 2012-höz)                                                                                                                                              |
| Katalógusok kezelése.                     | Termékkatalógusok segítségével azonosítsa azokat a termékeket, amelyeket az online áruházaiban szeretne árusítani.                                                              | [Legfontosabb feladatok: Kiskereskedelmi termékkatalógusokat létrehozni](/dynamicsax-2012/appuser-itpro/key-tasks-create-retail-product-catalogs) (TechNet-tartalom az AX 2012-höz)                                                                                                                           |
| Árak kezelése.                       | Állítson be és használjon árcsoportokat, amelyek a központi kapcsolatot képviselik az árak és engedmények, csatornák, katalógusok, viszonyok és hűségprogramok között. | [Árak beállítása az árcsoportok használatával](/dynamicsax-2012/appuser-itpro/setting-up-prices-using-price-groups) (TechNet-tartalom AX 2012-höz)</br> [Adók beállítása](/dynamicsax-2012/appuser-itpro/setting-up-taxes) (TechNet-tartalom AX 2012-höz) |
| Kedvezmények kezelése.                    | Állítson be és kezeljen ármódosításokat és négyféle engedményt.                                                                                  | [Ármódosítások és engedmények beállítása](/dynamicsax-2012/appuser-itpro/setting-up-price-adjustments-and-discounts) (TechNet-tartalom az AX 2012-höz)                                                                                                                          |
| Szállítási költségek kezelése.             | Állítson be és kezeljen az online áruházra szabott szállítási költségeket.                                                                     | [Az online áruházak szállítási költségeinek beállítása](/dynamicsax-2012/appuser-itpro/set-up-shipping-charges-for-online-stores) (TechNet-tartalom az AX 2012-höz)                                                                                                                           |
| Szállítási módok kezelése.            | Kezelje az online áruházban kínált szállítási módokat.                                                                                        | [Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery) (TechNet-tartalom az AX 2012-höz)                                                                                                                                            |

## <a name="set-up-data-exchange-between-commerce-and-the-online-store"></a>Adatcsere beállítása a Commerce és az online áruház között

| Feladat                                 | Részletek                                                                                                                               | Témakörök                                                                                                                                                                                                                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Csatornaintegrácis profilok beállítása. | A profilok lehetővé teszik az összetevőknek egymással folytatott kommunikációját. Állítson be profilokat az adatcsere beállításainak konfigurálása előtt. | [Real-Time Service profil beállítása](/dynamicsax-2012/appuser-itpro/set-up-a-real-time-service-profile) (TechNet-tartalom AX 2012-höz)</br> [Csatornaprofil beállítása](/dynamicsax-2012/appuser-itpro/set-up-a-channel-profile) (TechNet-tartalom AX 2012-höz) |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
