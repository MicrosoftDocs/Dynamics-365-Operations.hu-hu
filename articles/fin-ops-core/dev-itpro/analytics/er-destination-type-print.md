---
title: Nyomtató ER céltípusa
description: Ez a cikk bemutatja, hogy hogyan konfigurálhatja a célnyomtatót az elektronikus jelentésformátumok (ER) minden mappájához vagy FÁJLösszetevőihez.
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 826455d0901a45ef26755fd323ee2a2737b5eec0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845570"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Nyomtatási cél

[!include [banner](../includes/banner.md)]

A létrejövő dokumentumokat közvetlenül egy hálózati nyomtatóra lehet küldeni közvetlen nyomtatásra.

## <a name="prerequisites"></a>Előfeltételek

Először telepítenie és konfigurálnia kell a dokumentumirányítási ügynököt, majd regisztrálnia kell a hálózati nyomtatókat. További információkért lásd: [A Dokumentumirányítási ügynök telepítése a hálózati nyomtatás engedélyezéséhez](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>A nyomtató célhelyének elérhetővé tétele

Ha **a** Microsoft Dynamics 365 Pénzügy aktuális példányán elérhetővé tenni a célnyomtatót, **használja** a Funkciókezelés munkaterületet, és ebben a sorrendben kapcsolja be a következő funkciókat:

1. A kimenő Elektronikus jelentéskészítési dokumentumok konvertálásának engedélyezése Microsoft Office formátumokról PDF-fájllá
2. Dokumentumirányítási ügynök az Elektronikus jelentéskészítés céljaként a kimenő dokumentumok esetében

[![Az ER nyomtatócélhely funkció beállítása a Funkció kezelése munkaterületen.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Alkalmazhatóság

#### <a name="pdf-printing"></a>PDF-nyomtatás

A Pénzügy rendszer 10.0.18-as verzió előtti verzióiban a célnyomtató csak olyan fájlösszetevőkhöz konfigurálható, **amelyek** nyomtatható PDF-formátumban (**PDF egyesítési vagy PDF-fájlformátum-elemek** **·**) és Word-formátumban (Microsoft Office Excel Excel-fájlformátum-elem **)** generálhatók. Amikor a kimenet PDF formátumú lesz, a rendszer elküldi egy nyomtatóra. Ha a kimenet Office-formátumban **, az Excel** fájlformátumelem használatával jön létre, akkor a program automatikusan PDF-formátumra konvertálja, és elküldi a nyomtatónak.

A 10.0.18-as **·** **verzióban** azonban beállíthatja a közös fájlformátumelem nyomtatási célját. Ez a formátumelem elsősorban a kimenet TXT vagy XML formátumú előállítására használatos. Konfigurálhat olyan ER-formátumot **·** **·**, amely a közös fájlformátum-elemet tartalmazza gyökérformátumelemként, és a bináris tartalom formátumelemeként az alatta található egyetlen beágyazott elemként. Ebben az esetben a **Közös** fájlformátum elem a **Bináris** tartalomformátum elemhez beállított kötés által meghatározott formátumban hoz létre kimenetet. Be lehet állítani például, [hogy](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) ez a [kötés](../../fin-ops/organization-administration/configure-document-management.md) PDF- vagy Office (Excel- vagy Word-) formátumú dokumentumkezelési mellékletek tartalmával töltse ki ezt az elemet. A kimenetet a konfigurált nyomtató céljával **nyomtathatja** ki. 

> [!NOTE]
> Ha a **Nyomtató** cél beállításához a **Közös\\fájl** formátumelemet választja, a tervezés során nem lehet garantálni, hogy a kiválasztott elem PDF-formátumú vagy pdf formátumú kimenetet hoz létre. Ezért a következő figyelmeztető üzenet jelenik meg: "Győződjön meg róla, hogy a kiválasztott formátumösszetevő által létrehozott kimenet konvertálható PDF formátumúvá. Ellenkező esetben törölje a jelet a "KONVERTÁLÁS PDF formátumba" beállításból." Meg kell tenni a szükséges lépéseket a futásidejű problémák megelőzése érdekében, ha futásidőben nem PDF vagy nem PDF formátumú kimenet van rendelkezésre a nyomtatáshoz. Ha arra számít, hogy a kimenet Office (Excel vagy Word) formátumú lesz, **be kell lennie jelölve a Konvertálás PDF formátumba**.
>
> A 10.0.26-os **és újabb verzióban a KONVERTÁLÁS PDF-fájlba** **·** **·** **beállításhoz pdf formátumot kell választania a konfigurált nyomtató cél dokumentumirányítási típus paraméteréhez.**

#### <a name="zpl-printing"></a>ZPL-nyomtatás

A 10.0.26-os és újabb verziókban konfigurálhatja a közös **Közös\\Fájl** **Nyomtató** célját úgy, ·hogy kiválasztja a **ZPL** paramétert a **Dokumentumirányítás típusa** paraméterhez. Ebben az **esetben futásidőben a rendszer figyelmen kívül hagyja a PDF-formátumra** konvertálás beállítást, és a TXT- vagy XML-kimenetet közvetlenül a kiválasztott nyomtatóra küldi a dokumentumirányítási ügynök (DRA [) Programnyelv (ZPL)](install-document-routing-agent.md) szerződésének használatával. Ez a funkció a ZPL II címkeelrendezésnek megfelelő ER-formátumban használható különböző címkék nyomtatására.

[![A Dokumentumirányítás típusa paraméter beállítása a Cél beállításai párbeszédpanelen.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Ezzel a funkcióval kapcsolatos további tudnivalókat [lásd: Új ER-megoldás megtervezése ZPL-címkék nyomtatásához](er-design-zpl-labels.md).

### <a name="limitations"></a>Korlátozások

A **Nyomtató** célhely csak felhőalapú telepítések esetén van a rendszerben.

### <a name="use-the-printer-destination"></a>A Nyomtató célhely használata

1. Az **Engedélyezve** beállítást az **Igen** értékre állítva a létrejövő dokumentumokat elküldi a nyomtatónak.
2. A **Nyomtató neve** mezőben válassza ki a kívánt hálózati nyomtatót.
3. Állítsa **Menti a nyomtatási archívumba?** lehetőséget **Igen** értékre, és a létrejövő kimenetet a nyomtatási archívumban tárolhatja, így az további nyomtatás céljából elérhetővé válik. Ha később szeretné elérni az archivált kimenetet, nyissa meg a **Szervezeti adminisztráció** \> **Lekérdezések és jelentések** \> **Jelentésarchívum** elemét.

[![A Nyomtató célhely használata.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> A **Nyomtató** célhely konfigurálása során nem kell bekapcsolni a **Konvertálás PDF-fájllá** beállítást. A PDF-konverzió nyomtatás céljából akkor is megtörténhet, ha a beállítás ki van kapcsolva.

Ha egy adott [oldaltájolást](electronic-reporting-destinations.md#SelectPdfPageOrientation) szeretne használni a kimenő dokumentumok Excel-formátumba történő nyomtatásakor, akkor be kell kapcsolnia a **Konvertálás PDF-fájllá** beállítást. Ha a **Konvertálás PDF-fájllá** beállítást **Igen** értékre állítja az **Oldaltájolás** mező elérhetővé válik. A **Lap tájolása** mezőben kiválaszthat egy oldaltájolást.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
