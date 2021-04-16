---
title: Bejövő dokumentumok elemzése Excel-formátumban
description: Ez a témakör a bejövő Microsoft Excel-fájlok tartalmának elemzéséhez használt elektronikus jelentési (ER) formátumok tervezésével kapcsolatos információkat tartalmaz.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 0c41a062d817307adb2889d3678764f1ea4066e2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755180"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Bejövő dokumentumok elemzése Excel-formátumban

[!include[banner](../includes/banner.md)]

Lehetőség van Elektronikus jelentési (ER) formátumok kialakítására olyan bejövő Microsoft Excel-fájlok elemzésére, amelyek az adatokat Microsoft Excel-munkafüzetekben jelenítik meg (XLSX formátumú fájlok). Az ezekből a fájljokból származó tartalmakat felhasználhatja az alkalmazásadatok frissítésére. Ez hasznos a következő esetekben:

- Egy új modell és formátum kialakítása, amelyet futásidőben akar tesztelni. Ebben az esetben Excel szimulálni fogja az aktuális alkalmazás adatait.
- Az Excelben való alkalmazáson túlmenően is kezelhet adatokat, és meghatározott jelentés benyújtásához importálhatja ezeket az adatokat.

További tudnivalók ezzel a funkcióval kapcsolatban: játssza le a következő feladat útmutatókat **ER adatimportálás Microsoft Excel-fájlból (1. rész: tervezési formátum)** és **ER adatimportálás Microsoft Excel-fájlból** (2. rész: adatok importálása) (megtalálható itt: 7.5.4.3 informatikai szolgáltatási/megoldási összetevők megszerzése/fejlesztése, (10677) üzleti folyamat). Ezek a feladat útmutatók végigvezetik azon, hogy kell a bejövő Excel-fájlt elemezni, amikor az ER formátumot használja adatok importálására a bejövő dokumentumból, illetve ezekkel frissíti az alkalmazásadatokat. A feladat útmutatók fájljait letöltheti itt: [Microsoft letöltőközpont](https://go.microsoft.com/fwlink/?linkid=874684).

A fent említett feladat útmutatók befejezéséhez töltse le a következő fájlokat.

| Tartalom leírása                         | Fájl                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| Bejövő fájl XLSX formátumban - sablon    | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| Bejövő fájl XLSX formátumban - mintaadatok | [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Ha még nem játszotta le a következő feladat útmutatót [ER létrehozása - szükséges konfigurációk a külső fájlból történő adatimportáláshoz](./tasks/er-required-configurations-import-data.md) a jelenlegi Finance and Operations alkalmazásban, töltse le a következő fájlt.

| Tartalom leírása    | Fájl                                                            |
|------------------------|-----------------------------------------------------------------|
| ER modell konfigurációja | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]