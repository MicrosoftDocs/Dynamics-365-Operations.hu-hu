---
title: Nyomtató ER céltípusa
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy nyomtatót célhelyként a kimenő dokumentumok létrehozásához konfigurált elektronikus jelentési (ER) formátumú fájlok MAPPA vagy FÁJL összetevőihez PDF vagy Microsoft Office-formátumokban (Excel/Word).
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 148da191ce4ea99c237895c40ec007a1aa0cd537
ms.sourcegitcommit: 0d9ca44b48fb2e33d8160faccc1e6bd932e58934
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150792"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Nyomtató célhely

[!include [banner](../includes/banner.md)]

A létrejövő dokumentumokat közvetlenül egy hálózati nyomtatóra lehet küldeni közvetlen nyomtatásra.

## <a name="prerequisites"></a>Előfeltételek

Először telepítenie és konfigurálnia kell a dokumentumirányítási ügynököt, majd regisztrálnia kell a hálózati nyomtatókat. További információkért lásd: [A Dokumentumirányítási ügynök telepítése a hálózati nyomtatás engedélyezéséhez](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).

## <a name="make-the-printer-destination-available"></a>A nyomtató célhelyének elérhetővé tétele

Ahhoz, hogy a **Nyomtató** célhelyet elérhetővé tegye a Microsoft Dynamics 365 Finance aktuális példányában, lépjen a **Funkció kezelése** munkaterületre, majd kapcsolja be az alábbi funkciókat, ebben a sorrendben:

1. A kimenő Elektronikus jelentéskészítési dokumentumok konvertálásának engedélyezése Microsoft Office formátumokról PDF-fájllá
2. Dokumentumirányítási ügynök az Elektronikus jelentéskészítés céljaként a kimenő dokumentumok esetében

[![Az ER nyomtatócélhely funkció beállítása a Funkció kezelése munkaterületen](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Alkalmazhatóság

A **Nyomtató** célhely csak olyan fájlösszetevőkhöz konfigurálható, amelyek nyomtatható PDF-formátumban (PDF Merger vagy PDF fájlformátumú elemekben) vagy Microsoft Office Excel/Word formátumban (Excel-fájl) generálják a kimenetet. Amikor a rendszer létrehozza a PDF formátumú kimenetet, elküldi azt a nyomtatónak. Amikor Microsoft Office-formátumú kimenetet generál, a rendszer azt automatikusan PDF-formátumba konvertálja, majd elküldi a nyomtatónak.

### <a name="limitations"></a>Korlátozások

Ez a funkció egy előnézeti funkció, azok a felhasználási feltételek vonatkoznak rá, amelyek itt olvashatók: [Kiegészítő felhasználási feltételek a Microsoft Dynamics 365 előnézetek esetén](https://go.microsoft.com/fwlink/?linkid=2105274).

A **Nyomtató** célhely csak felhőalapú telepítések esetén van a rendszerben.

### <a name="use-the-printer-destination"></a>A Nyomtató célhely használata

1. Az **Engedélyezve** beállítást az **Igen** értékre állítva a létrejövő dokumentumokat elküldi a nyomtatónak.
2. A **Nyomtató neve** mezőben válassza ki a kívánt hálózati nyomtatót.
3. Állítsa **Menti a nyomtatási archívumba?** lehetőséget **Igen** értékre, és a létrejövő kimenetet a nyomtatási archívumban tárolhatja, így az további nyomtatás céljából elérhetővé válik. Ha később szeretné elérni az archivált kimenetet, nyissa meg a **Szervezeti adminisztráció** \> **Lekérdezések és jelentések** \> **Jelentésarchívum** elemét.

[![A Nyomtató célhely használata](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> A **Nyomtató** célhely konfigurálása során nem kell bekapcsolni a **Konvertálás PDF-fájllá** beállítást. A PDF-konverzió nyomtatás céljából akkor is megtörténhet, ha a beállítás ki van kapcsolva.

Ha egy adott [oldaltájolást](electronic-reporting-destinations.md#SelectPdfPageOrientation) szeretne használni a kimenő dokumentumok Excel-formátumba történő nyomtatásakor, akkor be kell kapcsolnia a **Konvertálás PDF-fájllá** beállítást. Ha a **Konvertálás PDF-fájllá** beállítást **Igen** értékre állítja az **Oldaltájolás** mező elérhetővé válik. A **Lap tájolása** mezőben kiválaszthat egy oldaltájolást.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
