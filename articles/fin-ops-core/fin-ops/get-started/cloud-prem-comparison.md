---
title: Felhő és helyszíni szolgáltatások összehasonlítása
description: A témakör bemutatja, hogy mely szolgáltatásokat támogatja a felhőalapú és a helyszíni megoldás.
author: sericks007
manager: AnnBe
ms.date: 02/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: a918d9fa1ad7ed5adcbb1d056bb8cc3306507aec
ms.sourcegitcommit: 8ff2413b6cb504d2b36fce2bb50441b2e690330e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081970"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Felhőalapú és helyszíni szolgáltatások összehasonlítása

[!include [banner](../includes/banner.md)]

Ez a témakör a felhőalapú és helyszíni szolgáltatások összehasonlítását mutatja be a következő alkalmazások számára:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

A [fejlesztési és adminisztrációs szolgáltatásokkal](cloud-prem-comparison.md#development-and-administration-features) kapcsolatos információk is itt érhetők el.

A következő táblázatokban az alkalmazási területek listája található. A felhő és helyszíni támogatás a szolgáltatás egészére nézve van felsorolva. Ha bizonyos szolgáltatások eltérnek az általános területtől, ezek a szolgáltatások külön sorban jelennek meg a szolgáltatás oszlopban.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Terület**             | **Szolgáltatás**                | **Felhőbeli** | **Helyszíni** |
|---------------------|-----------------------------|-----------|-----------------|
| Megfelelés és tanúsítványok        |                                                                                           | Igen       | Igen             |
|                                      | SOC 1 1. típusú tanúsítvány                                                                | Igen       | Nem              |
| Adatok integrálása és kezelése      |                                                                                           | Igen       | Igen             
|                                      | Adatok exportálása a saját adatraktárba                                                    | Igen       | Igen             |
|                                      | Növekményes frissítések exportálásának engedélyezése egy adatentitásba                                 | Igen       | Igen              |
|                                      | Adatintegrálások                                                                         | Igen       | Igen             |
| Dokumentumkezelés                  |                                                                                           | Igen       | Igen             |
| Pénzgazdálkodás                 |                                                                                           | Igen       | Igen             |
| Súgó                                 |                                                                                           | Igen       | Nincs              |
| Emberi erőforrások                      |                                                                                           | Igen       | Igen             |
| Intelligencia                         |                                                                                           | Igen       | Igen             |
|                                      | Elektronikus jelentés (EJ)                                                                 | Igen       | Igen             |
|                                      | ER: Integráció az LCS rendszerrel                                                                  | Igen       | Nem              |
|                                      | ER: Integráció a SharePoint szolgáltatással                                                           | Igen       | Nem              |
|                                      | ER: Integráció a Regulatory Configuration Service (RCS) szolgáltatással                              | Igen       | Nem              |
|                                      | ER: Helyi fájlrendszer használata ER konfigurációk tárhelyeként, amelyeket ER tárházakon keresztül lehet elérni | Nem        | Igen             |
|                                      | PowerBI.com integrálása                                                              | Igen       | Nem              |
|                                      | Integráció a PowerBI Desktop rendszerrel                                                          | Nem        | Igen             |
|                                      | Elemzési munkaterületek                                                                     | Igen       | Nem              |
|                                      | Intelligens üzleti folyamat: ajánlások                                             | Igen       | Szám              |
|                                      | Power BI jelentések készítése az OData segítségével a Power BI asztal vagy az Excel PowerQuery eszközök használatával    | Igen       | Szám              |
|                                      | Az SQL Server Reporting Services (SSRS) támogatja a méretezést                                 | Igen       | Nem              |
|                                      | A telemetria-adatokat átviszik a felhőbe                                                   | Igen       | Nem              |
| Lifecycle Services                   |                                                                                           | Igen       | Igen             |
|                                      | Konfigurálható üzleti folyamatok                                                           | Igen       | Nem              |
| Honosítások                        |                                                                                           | Igen       | Igen             |
| Mobilalkalmazás, munkaterületek és platform |                                                                                           | Igen       | Igen             |
| Office-integráció                   |                                                                                           | Igen       | Igen             |
| Szervezeti adminisztráció          |                                                                                           | Igen       | Igen             |
| Bérlista                              |                                                                                           | Igen       | Igen             |
|                                      | Közvetlen átutalás                                                                            | Igen       | Nem              |
| Projektvezetés és könyvelés    |                                                                                           | Igen       | Igen             |
| Biztonság                             |                                                                                           | Igen       | Igen             |
| Szolgáltatáskezelés                   |                                                                                           | Igen       | Igen             |
| Webes ügyfél                           |                                                                                           | Igen       | Igen             |
|                                      | Feladatrögzítő – Feladatrögzítések mentése vagy betöltése a BPM-tárból                         | Igen       | Nincs              |
| Támogatás                              |                                                                                           | Igen       | Igen             |
|                                      | A Súgó és támogatás menüvel hozzáférés a támogatáshoz                                             | Igen       | Nem              |
|                                      | Üzleti események                                                                           | Igen       | Igen (vagy internetkapcsolat szükséges, vagy egyéni végpontokat kell megvalósítani az intraneten belüli üzleti események küldéséhez és fogadásához)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Terület**                | **Funkció**             | **Felhőbeli** | **Helyszíni** |
|-------------------------|-------------------|-----------|-----------------|
| Megfelelés és tanúsítványok        |                                                                                           | Igen       | Igen             |
|                                      | SOC 1 1. típusú tanúsítvány                                                                | Igen       | Szám              |
| Költségkönyvelés                      |                                                                                           | Igen       | Igen             |
|                                      | Költségkönyvelés tartalomcsomag Power BI szolgáltatáshoz                                                 | Igen       | Szám              |
|                                      | Költségkönyvelés munkaterülete mobil alkalmazáshoz                                                  | Igen       | Szám              |
| Költségkezelés                      |                                                                                           | Igen       | Igen             |
|                                      | Költségkezelési tartalomcsomag Power BI-hez                                                 | Igen       | Szám              |
| Adatok integrálása és kezelése      |                                                                                           | Igen       | Igen             |
|                                      | Konfigurációs alapú kiterjesztés                                                            | Igen       | Nincs              |
|                                      | Adatok exportálása a saját adatraktárba                                                    | Igen       | Igen             |
|                                      | Növekményes frissítések exportálásának engedélyezése egy adatentitásba                                 | Igen       | Nem              |
|                                      | Adatintegrálások                                                                         | Igen       | Igen             |
| Dokumentumkezelés                  |                                                                                           | Igen       | Igen             |
| Súgó                                 |                                                                                           | Igen       | Nem              |
| Intelligencia                         |                                                                                           | Igen       | Igen             |
|                                      | Elektronikus jelentés (EJ)                                                                 | Igen       | Igen             |
|                                      | ER: Integráció az LCS rendszerrel                                                                  | Igen       | Nem              |
|                                      | ER: Integráció a SharePoint szolgáltatással                                                           | Igen       | Nem              |
|                                      | ER: Integráció a Regulatory Configuration Service (RCS) szolgáltatással                              | Igen       | Nem              |
|                                      | ER: Helyi fájlrendszer használata ER konfigurációk tárhelyeként, amelyeket ER tárházakon keresztül lehet elérni | Nem        | Igen             |
|                                      | PowerBI.com integrálása                                                              | Igen       | Nem              |
|                                      | Integráció a PowerBI Desktop rendszerrel                                                          | Nem        | Igen             |
|                                      | Elemzési munkaterületek                                                                     | Igen       | Nem              |
|                                      | Intelligens üzleti folyamat: ajánlások                                             | Igen       | Szám              |
|                                      | Power BI jelentések készítése az OData segítségével a Power BI asztal vagy az Excel PowerQuery eszközök használatával    | Igen       | Szám              |
|                                      | Az SQL Server Reporting Services (SSRS) támogatja a méretezést                                 | Igen       | Nincs              |
|                                      | A telemetria-adatokat átviszik a felhőbe                                                   | Igen       | Nincs              |
| Készletgazdálkodás                 |                                                                                           | Igen       | Igen             |
| Lifecycle Services                   |                                                                                           | Igen       | Igen             |
|                                      | Konfigurálható üzleti folyamatok                                                           | Igen       | Nincs              |
| Honosítások                        |                                                                                           | Igen       | Igen             |
| Gyártás                        |                                                                                           | Igen       | Igen             |
| Alaptervezés és előrejelzés      |                                                                                           | Igen       | Igen             |
| Mobilalkalmazás, munkaterületek és platform |                                                                                           | Igen       | Igen             |
| Office-integráció                   |                                                                                           | Igen       | Igen             |
| Szervezeti adminisztráció          |                                                                                           | Igen       | Igen             |
| Beszerzés és forrás             |                                                                                           | Igen       | Igen             |
|                                      | Kiadás külső katalógusba beszerzési igénylésből                                   | Igen       | Szám              |
|                                      | Beszerzési és ráfordítási elemzés Power BI jelentések                                                  | Igen       | Szám              |
| Termékinformációk kezelése       |                                                                                           | Igen       | Igen             |
| Alaptermékadatok                  |                                                                                           | Igen       | Igen             |
| Termelés                           |                                                                                           | Igen       | Igen             |
|                                      | Termelési teljesítmény Power BI jelentések                                                   | Igen       | Szám              |
| Projektvezetés és könyvelés    |                                                                                           | Igen       | Igen             |
| Értékesítés                                |                                                                                           | Igen       | Igen             |
|                                      | Értékesítési és jövedelmezőségi teljesítmény Power BI jelentések                                      | Igen       | Szám              |
| Biztonság                             |                                                                                           | Igen       | Igen             |
| Szolgáltatáskezelés                   |                                                                                           | Igen       | Igen             |
| Ellátásilánc-kezelés              |                                                                                           | Igen       | Igen             |
| Szállításkezelés            |                                                                                           | Igen       | Igen             |
| Szállítói együttműködés                 |                                                                                           | Igen       | Nincs              |
| Raktárkezelés                 |                                                                                           | Igen       | Igen             |
|                                      | Raktári mobilalkalmazás                                                                      | Igen       | Igen             |
|                                      | Raktárkezelés Power BI jelentések                                                              | Igen       | Szám              |
| Webes ügyfél                           |                                                                                           | Igen       | Igen             |
|                                      | Feladatrögzítő – Feladatrögzítések mentése vagy betöltése a BPM-tárból                         | Igen       | Nincs              |
| Támogatás                              |                                                                                           | Igen       | Igen             |
|                                      | A Súgó és támogatás menüvel hozzáférés a támogatáshoz                                             | Igen       | Nem              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Helyszíni telepítéseknél rendelkezésre álló lehetőségek listájának megtekintéséhez kattintson ide: [A helyszíni telepítéseknél rendelkezésre álló kereskedelmi lehetőségek](../../../retail/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Terület**         | **Szolgáltatás**         | **Felhőbeli** | **Helyszíni** |
|------------------|---------------------|-----------|-----------------|
| Összes Emberi erőforrások-terület | Összes Emberi erőforrások-funkció | Igen       | Nem              |

## <a name="development-and-administration-features"></a>Fejlesztési és adminisztrációs funkciók

| **Terület**                   | **Szolgáltatás**                               | **Felhőbeli** | **Helyszíni** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Felépítés és tesztelés             |                                           | Igen       | Igen             |
| Bővíthetőség              |                                           | Igen       | Igen             |
| Megfigyelés és telemetria   |                                           | Igen       | Igen             |
| Platform kompatibilitása     |                                           | Igen       | Igen             |
| Karbantartás                  |                                           | Igen       | Igen             |
|                            | Szolgáltatási környezetek                    | Igen       | Nincs              |
| Trace Parser és PerfTimer |                                           | Igen       | Nincs              |
| Frissítés                    |                                           | Igen       | Igen             |
|                            | Frissítés                                   | Igen       | Szám              |
|                            | Frissítés és a korábbi verziók támogatása | Igen       | Nem              |
| Visual Studio fejlesztés  |                                           | Igen       | Igen             |

