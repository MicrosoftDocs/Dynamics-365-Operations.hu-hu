---
title: Fizetési ellenőrző fájlok beállítása és létrehozása
description: Ez a témakör ismerteti az ellenőrzött fizetések beállítását és az ellenőrzött fizetési fájlok létrehozását.
author: panolte
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0984710220171f36a520e471c6c55bf12d97675b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972027"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Fizetési ellenőrző fájlok beállítása és létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti az ellenőrzött fizetések beállítását és az ellenőrzött fizetési fájlok létrehozását. 

A fizetési ellenőrzés beállítása elektronikus csekklista generálásához, amely a banknak elküldhető. Ezután, amikor egy csekket bemutatnak a banknak a bank összehasonlítja azt a csekklistával. Ha a csekk megfelel a listában szereplő csekkel a bank törli azt. Ha a csekk nem egyezik meg a listában szereplő csekkel, akkor a bank bent tartja ellenőrzésre.

## <a name="security-for-positive-pay-files"></a>A fizetési ellenőrző fájlok biztonsága
Az ellenőrzött fizetési fájlok bizalmas információt tartalmazhatnak a kedvezményezettekről és a csekk-összegekről. Ezért győződjön meg róla, hogy a megfelelő biztonsági intézkedéseket használja attól az időponttól, hogy a fájlok létrejönnek addig, amíg a bank meg nem kapja őket. A fizetési ellenőrző fájlok a webböngészője által megadott helyre lesznek letöltve. Mivel a fizetési ellenőrző fájlok bizalmas adatokat is tartalmazhatnak, fontos, hogy csak engedéllyel rendelkező felhasználók férjenek hozzá ezen információk létrehozásához és megtekintéséhez a Microsoft Dynamics 365 Finance rendszerben. A következő táblázat segítségével határozza meg a szükséges jogosultságokkal.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feladat</th>
<th>Jogosultság</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fizetési ellenőrző fájlok létrehozása a <strong>Bankszámlák</strong> listaoldalon vagy a <strong>Bankszámlák</strong> lapon.</td>
<td><ul>
<li><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Ellenőrzött fizetési fájlok létrehozása több jogi személyhez és bankszámlához a <strong>Fizetési ellenőrző fájl létrehozása</strong> oldalon.</td>
<td><ul>
<li><strong>Banki ellenőrzött fizetési információk karbantartása</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Fizetési ellenőrző fájlok megtekintése a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Banki ellenőrzött fizetési információk megtekintése több jogi személynél</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Fizetési ellenőrző fájlok visszaigazolása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Fizetési ellenőrző fájl visszaigazolása</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Fizetési ellenőrző fájlok visszahívása a <strong>Fizetési ellenőrző fájl összegzése</strong> oldalon.</td>
<td><strong>Fizetési ellenőrző fájl visszahívása</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Ellenőrzött fizetési formátum beállítása
Az ellenőrzött fizetési fájlok adatentitások használatával jönnek létre. Mielőtt készíthetne egy fizetési ellenőrző fájlt, be kell állítania egy átalakítási bemeneti formátumot, amely ahhoz lesz használatos, hogy a csekk információit olyan formátumra fordítsa, amely képes kommunikálni a bankkal. Az **Ellenőrzött fizetési formátum** lapon létrehozhat egy fájlformátum-azonosítót és egy leírást. Az átalakítási bemeneti formátumnak XML típusúnak kell lennie. Az adott formátum az Ön által használt átalakító fájltól függ. Vegyük például a bővíthető stíluslap-nyelv transzformációt (XSLT) fájlt, amelyhez meg van adva, hogy az **XML-elem** formátumot használja. Használja az **Az átalakításhoz használt fájl feltöltése** műveletet hogy megadja az átalakítási fájl helyét azon formátumhoz, amelyet a bankja igényel.

## <a name="example-xslt-file-for-positive-pay-file"></a>Példa: XSLT-fájl az ellenőrzött fizetési fájlhoz.

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
  <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:value-of select="'
'" />
    <Document>
      <xsl:value-of select="'
'" />
      <!--Header Begin-->
      <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
      <xsl:value-of select="'
'" />
      <!--Header End-->
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
        <!--Cheque Detail begin-->
        <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
            <xsl:value-of select='string("Yes")'/>
          </xsl:when>
          <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
            <xsl:value-of select='string("No")'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='string(" ")'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("Payment")'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='CHEQUENUM/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='AMOUNTCUR/text()'/>
        <xsl:value-of select="','" />
        <xsl:value-of select='string("BOA-#1812")'/>
        <xsl:value-of select="','" />
        <xsl:choose>
          <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
            <xsl:value-of select='VENDGROUP/text()'/>
          </xsl:when>
          <xsl:otherwise>
            <xsl:value-of select='CUSTGROUP/text()'/>
          </xsl:otherwise>
        </xsl:choose>
        <xsl:value-of select="','" />
        <xsl:value-of select='TRANSDATE/text()'/>
        <xsl:value-of select="'
'" />
      </xsl:for-each>
    </Document>
  </xsl:template>
</xsl:stylesheet>
```

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Az ellenőrzött fizetési formátum hozzárendelése egy bankszámlához
Minden egyes bankszámlához, amelyhez szeretne létrehozni ellenőrzött fizetési információt, hozzá kell rendelnie az előző szakaszban megadott ellenőrzött fizetési formátumot. A **Bankszámlák** oldalon válassza ki azt az ellenőrzött fizetési formátumot, amely megfelel a bankszámlájának. Az **Ellenőrzött fizetés kezdő dátuma** mezőbe írja be az ellenőrzött fizetési fájlok létrehozásának kezdő dátumát. Fontos, hogy megadjon egy dátumot ebben a mezőben. Ellenkező esetben az első fizetési ellenőrző fájl, amit létrehoz tartalmazni fogja az összes csekket, amit valaha létrehoztak ehhez a bankszámlához.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Számsorozat hozzárendelése az ellenőrzött fizetési fájlokhoz
Minden ellenőrzött fizetési fájlnak rendelkeznie kell egy egyedi számmal. Használja a **Számsorozatok** lapot a **Készpénz- és bankkezelési paraméterek** oldalon, hogy számsorozatokat hozzon létre az ellenőrzött fizetési fájlokhoz.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Ellenőrzött fizetési fájl létrehozása egyetlen bankszámlához
Létrehozhat egy ellenőrzött fizetési fájlt egyetlen jogi személyhez és egyetlen bankszámlához. További információért arról, hogy hogyan hozhat létre ellenőrzött fizetési fájlokat egyszerre több jogi személyhez és bankszámlához lásd a következő részt. Ellenőrzött fizetési fájl létrehozásához, egyetlen jogi személyhez és egyetlen bankszámlához, nyissa meg a **Fizetési ellenőrző fájl létrehozása** párbeszédablakot a **Bankszámlák** oldalon. A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát. Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Ellenőrzött fizetési fájl létrehozása több bankszámlához
Ellenőrzött fizetési fájlok létrehozásához több bankszámlához használja a **Fizetési ellenőrző fájl létrehozása** ismétlődő feladatot. Válassza ki az ellenőrzött fizetés fájlformátumát és adja meg, hogy minden jogi személyhez létrejöjjön-e a fájl, vagy csak egy kijelölt jogi személyhez. Létrehozhatja továbbá a fájlt minden bankszámlához, amely az adott ellenőrzött fizetési formátumot használja, vagy egy kijelölt bankszámlához. A **Fordulónap dátuma** mezőben adja meg a fizetési ellenőrző fájlban használni kívánt utolsó csekk dátumát. Minden olyan csekk, amely nem került bele az ellenőrzött fizetési fájlba ezen csekkdátum végéig bekerül a fájlba.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Az ellenőrzött fizetési fájl létrehozásának eredményeinek megtekintése
Miután a fizetési ellenőrző fájl létrejött, megtekintheti az eredmények a **Fizetési ellenőrző fájl összegzése** lapon. Az egyes csekkek részleteinek megtekintéséhez használja a **Fizetési ellenőrző fájl** részletes lapját.

## <a name="confirm-a-positive-pay-file"></a>A fizetési ellenőrző fájl visszaigazolása
Miután kifizetésre kerültek a fizetési ellenőrző fájlban felsorolt csekkek, a bank visszaigazolási számot küld róla. Ezt követően visszaigazolhatja a fizetési ellenőrző fájlt. A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszaigazolás beírása** művelet. Amikor visszaigazol egy ellenőrzött fizetési fájlt, akkor a banktól kapott visszaigazolási szám rögzítésre kerül.

## <a name="recall-a-positive-pay-file"></a>Fizetési ellenőrző fájl visszahívása
Ha módosítania kell valamit a fizetési ellenőrző fájlban, akkor vissza tudja hívni. A **Fizetési ellenőrző fájl összegzése** lapon, válasszon ki egy ellenőrzött fizetést, amelynek állapota **Létrehozva**, majd válassza ki a **Visszahívás** művelet. Minden csekkhez a mező, amely a fizetési ellenőrző fájlban azt jelöli, hogy a csekk szerepel-e egy fizetési ellenőrző fájlban visszaállításra kerül. Ezt követően létrehozhat egy új ellenőrzött fizetési fájlt, amely tartalmazza a visszavont csekket.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]