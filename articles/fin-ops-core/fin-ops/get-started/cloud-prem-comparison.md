---
title: Felhőalapú és helyszíni szolgáltatások összehasonlítása
description: A cikk bemutatja, hogy mely funkciók támogatottak a felhőben és a létesítményben.
author: sericks007
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: e3b200186096a49f800d5b650ac81a45fe5e9e30
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644141"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Felhőalapú és helyszíni szolgáltatások összehasonlítása

[!include [banner](../includes/banner.md)]

Ez a cikk a következő alkalmazásoknál a felhőben elérhető funkciók és a létesítményben elérhető funkciók összehasonlítását mutatja be:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

A [fejlesztési és adminisztrációs szolgáltatásokkal](cloud-prem-comparison.md#development-and-administration-features) kapcsolatos információk is itt érhetők el.

A következő táblázatokban az alkalmazási területek listája található. A felhő és helyszíni támogatás a szolgáltatás egészére nézve van felsorolva. Ha bizonyos szolgáltatások eltérnek az általános területtől, ezek a szolgáltatások külön sorban jelennek meg a szolgáltatás oszlopban.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Terület**             | **Funkció**                | **Felhőbeli** | **Helyszíni** |
|---------------------|-----------------------------|-----------|-----------------|
| Megfelelés és tanúsítványok        |                                                                                           | Igen       | Igen             |
|                                      | SOC 1 1. típusú tanúsítvány                                                                | Igen       | Nem              |
| Adatok integrálása és kezelése      |                                                                                           | Igen       | Igen             |
|                                      | Adatok exportálása a saját adatraktárba                                                    | Igen       | Igen             |
|                                      | Növekményes frissítések exportálásának engedélyezése egy adatentitásba                                 | Igen       | Igen             |
|                                      | Adatintegrálások                                                                         | Igen       | Igen             |
| Dokumentumkezelés                  |                                                                                           | Igen       | Igen             |
| Pénzgazdálkodás                 |                                                                                           | Igen       | Igen             |
| Súgó                                 |                                                                                           | Igen       | Nem              |
| Emberi erőforrások                      |                                                                                           | Igen       | Igen             |
| Intelligencia                         |                                                                                           | Igen       | Igen             |
|                                      | Elektronikus jelentés (EJ)                                                                 | Igen       | Igen             |
|                                      | ER: Integráció az LCS rendszerrel                                                                  | Igen       | Nem              |
|                                      | ER: Integráció a SharePoint szolgáltatással                                                           | Igen       | Nem              |
|                                      | ER: Integráció a Regulatory Configuration Service (RCS) szolgáltatással                              | Igen       | Nem              |
|                                      | ER: Helyi fájlrendszer használata ER konfigurációk tárhelyeként, amelyeket ER tárházakon keresztül lehet elérni | Nem        | Igen             |
|                                      | PowerBI.com integrálása                                                              | Igen       | Nem              |
|                                      | PowerBI Desktop integrálása                                                          | Nem        | Igen             |
|                                      | Elemzési munkaterületek                                                                     | Igen       | Nem              |
|                                      | Intelligens üzleti folyamat: ajánlások                                             | Igen       | Nem              |
|                                      | Power BI jelentések készítése az OData segítségével a Power BI asztal vagy az Excel PowerQuery eszközök használatával    | Igen       | Nem              |
|                                      | Az SQL Server Reporting Services (SSRS) támogatja a méretezést                                 | Igen       | Igen             |
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
|                                      | Feladatrögzítő – Feladatrögzítések mentése vagy betöltése a BPM-tárból                         | Igen       | Nem              |
| Támogatás                              |                                                                                           | Igen       | Igen             |
|                                      | A Súgó és támogatás menüvel hozzáférés a támogatáshoz                                             | Igen       | Nem              |
|                                      | Üzleti események                                                                           | Igen       | Igen (vagy internetkapcsolat szükséges, vagy egyéni végpontokat kell megvalósítani az intraneten belüli üzleti események küldéséhez és fogadásához)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Terület**                | **Funkció**             | **Felhőbeli** | **Helyszíni** |
|-------------------------|-------------------|-----------|-----------------|
| Eszközkezelés                     |                                                                                           | Igen       | Igen             |
| Megfelelés és tanúsítványok        |                                                                                           | Igen       | Igen             |
|                                      | SOC 1 1. típusú tanúsítvány                                                                | Igen       | Nem              |
| Költségkönyvelés                      |                                                                                           | Igen       | Igen             |
|                                      | Költségkönyvelés tartalomcsomag Power BI szolgáltatáshoz                                                 | Igen       | Nem              |
|                                      | Költségkönyvelés munkaterülete mobil alkalmazáshoz                                                  | Igen       | Nem              |
| Költségkezelés                      |                                                                                           | Igen       | Igen             |
|                                      | Költségkezelési tartalomcsomag Power BI-hez                                                 | Igen       | Nem              |
| Adatok integrálása és kezelése      |                                                                                           | Igen       | Igen             |
|                                      | Konfigurációs alapú kiterjesztés                                                            | Igen       | Nem              |
|                                      | Adatok exportálása a saját adatraktárba                                                    | Igen       | Igen             |
|                                      | Növekményes frissítések exportálásának engedélyezése egy adatentitásba                                 | Igen       | Igen             |
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
|                                      | PowerBI Desktop integrálása                                                          | Nem        | Igen             |
|                                      | Elemzési munkaterületek                                                                     | Igen       | Nem              |
|                                      | Intelligens üzleti folyamat: ajánlások                                             | Igen       | Nem              |
|                                      | Power BI jelentések készítése az OData segítségével a Power BI asztal vagy az Excel PowerQuery eszközök használatával    | Igen       | Nem              |
|                                      | Az SQL Server Reporting Services (SSRS) támogatja a méretezést                                 | Igen       | Igen             |
|                                      | A telemetria-adatokat átviszik a felhőbe                                                   | Igen       | Nem              |
| Készletgazdálkodás                 |                                                                                           | Igen       | Igen             |
| Lifecycle Services                   |                                                                                           | Igen       | Igen             |
|                                      | Konfigurálható üzleti folyamatok                                                           | Igen       | Nem              |
| Honosítások                        |                                                                                           | Igen       | Igen             |
| Gyártás                        |                                                                                           | Igen       | Igen             |
| Alaptervezés és előrejelzés      |                                                                                           | Igen       | Igen             |
|                                      | Tervezési optimalizálás                                                                     | Igen       | Nem              |
|                                      | Igény-előrejelzés                                                                        | Igen       | Nem              |
| Mobilalkalmazás, munkaterületek és platform |                                                                                           | Igen       | Igen             |
| Office-integráció                   |                                                                                           | Igen       | Igen             |
| Szervezeti adminisztráció          |                                                                                           | Igen       | Igen             |
| Beszerzés és forrás             |                                                                                           | Igen       | Igen             |
|                                      | Kiadás külső katalógusba beszerzési igénylésből                                   | Igen       | Nem              |
|                                      | Beszerzési és ráfordítási elemzés Power BI jelentések                                                  | Igen       | Nem              |
| Termékinformációk kezelése       |                                                                                           | Igen       | Igen             |
| Alaptermékadatok                  |                                                                                           | Igen       | Igen             |
| Termelés                           |                                                                                           | Igen       | Igen             |
|                                      | Termelési teljesítmény Power BI jelentések                                                   | Igen       | Nem              |
| Projektvezetés és könyvelés    |                                                                                           | Igen       | Igen             |
| Értékesítés                                |                                                                                           | Igen       | Igen             |
|                                      | Értékesítési és jövedelmezőségi teljesítmény Power BI jelentések                                      | Igen       | Nem              |
| Biztonság                             |                                                                                           | Igen       | Igen             |
| Szolgáltatáskezelés                   |                                                                                           | Igen       | Igen             |
| Ellátásilánc-kezelés              |                                                                                           | Igen       | Igen             |
| Szállításkezelés            |                                                                                           | Igen       | Igen             |
| Szállítói együttműködés                 |                                                                                           | Igen       | Nem              |
| Raktárkezelés                 |                                                                                           | Igen       | Igen             |
|                                      | Raktári mobilalkalmazás                                                                      | Igen       | Igen             |
|                                      | Raktárkezelés Power BI jelentések                                                              | Igen       | Nem              |
| Webes ügyfél                           |                                                                                           | Igen       | Igen             |
|                                      | Feladatrögzítő – Feladatrögzítések mentése vagy betöltése a BPM-tárból                         | Igen       | Nem              |
| Támogatás                              |                                                                                           | Igen       | Igen             |
|                                      | A Súgó és támogatás menüvel hozzáférés a támogatáshoz                                             | Igen       | Nem              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Helyszíni telepítéseknél rendelkezésre álló lehetőségek listájának megtekintéséhez kattintson ide: [A helyszíni telepítéseknél rendelkezésre álló kereskedelmi lehetőségek](../../../commerce/retail-onprem.md).

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
|                            | Szolgáltatási környezetek                    | Igen       | Nem              |
| Trace Parser               |                                           | Igen       | Igen             |
| PerfTimer                  |                                           | Igen       | Igen\*           |
| Frissítés                    |                                           | Igen       | Igen             |
|                            | Frissítés                                   | Igen       | Nem              |
|                            | Frissítés és a korábbi verziók támogatása | Igen       | Nem              |
| Visual Studio fejlesztés  |                                           | Igen       | Igen             |

\* A helyszíni környezetekben a PerfTimer csak az ügyfél számára jeleníti meg az eredményeket.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
