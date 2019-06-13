<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="batch.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>batch.e70006.4456fc3d5bc4547fa8211642b11ca6df455fa187.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4456fc3d5bc4547fa8211642b11ca6df455fa187</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\batch.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Improved handling of batch-tracked items</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the improvements that have been made to the handling of batches for batch-tracked items during the Retail statement posting process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a témakör azt mutatja be, hogy milyen fejlesztéseket vezettek be a kötegek kezelésével kapcsolatban a kötegelt nyomkövetésű cikkek esetén a kiskereskedelmi kimutatások feladási folyamata során.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Improved handling of batch-tracked items</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Microsoft Dynamics 365 for Retail pénztár (POS) alkalmazásban a kötegelt nyomkövetésű cikkek kötegszámai nem rögzíthetők az értékesítés pillanatában.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Bizonyos konfigurációk esetén azonban amikor az értékesítéseket a központban vevői rendeléseken vagy kimutatásfeladáson keresztül adják fel, a Microsoft Dynamics-rendszer arra számít, hogy a kötegelt nyomkövetésű cikkekhez léteznek érvényes kötegszámok, és ezeket használják majd a számlázási folyamat során.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha a termékekhez léteznek érvényes kötegszámok, a rendszer ezeket használja a vevői rendelések számlázási folyamata és a kimutatásfeladásból származó értékesítési rendelés számlázási folyamata során.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ellenkező esetben a vevői rendelés számlázási folyamata nem képes a feladásra, és a pénztárfelhasználó számára hibaüzenet jelenik meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Statement posting then goes into an error state.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A kimutatásfeladás pedig hibás állapotba kerül.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>This error state occurs even when negative inventory has been turned on for the products.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a hibás állapot akkor fordulhat elő, ha negatív készlet van bekapcsolva a termékekhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Microsoft Dynamics for Retail 10.0.4-es és újabb verzióiban végzett fejlesztések segítségével garantálható, hogy amikor a kötegelt nyomkövetésű cikkekhez negatív készlet van bekapcsolva, a vevői rendelés és az értékesítési rendelés kimutatásfeladáson keresztül történő számlázása nincs zárolva az adott cikkekhez, ha a készlet 0 (nulla) vagy ha nincs elérhető kötegszám.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az új funkció alapértelmezett kötegazonosítót használ az értékesítési sorokhoz, ha nem találhatók kötegszámok.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To define the default batch ID that is used for customer orders, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Order<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A vevői rendelésekhez használt alapértelmezett kötegazonosító meghatározásához állítsa be az <bpt id="p1">**</bpt>Alapértelmezett kötegazonosító<ept id="p1">**</ept> mezőt a <bpt id="p2">**</bpt>Kiskereskedelmi paraméterek<ept id="p2">**</ept> lap <bpt id="p3">**</bpt>Vevői rendelések<ept id="p3">**</ept> fülének <bpt id="p4">**</bpt>Rendelés<ept id="p4">**</ept> gyorslapján.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>To define the default batch ID that is used for sales order invoicing through statement posting, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Posting<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Inventory update<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Az értékesítési rendelések kimutatásfeladáson keresztül történő számlázásához használt alapértelmezett kötegazonosító meghatározásához állítsa be az <bpt id="p1">**</bpt>Alapértelmezett kötegazonosító<ept id="p1">**</ept> mezőt a <bpt id="p2">**</bpt>Kiskereskedelmi paraméterek<ept id="p2">**</ept> lap <bpt id="p3">**</bpt>Feladás<ept id="p3">**</ept> fülének <bpt id="p4">**</bpt>Készletfrissítés<ept id="p4">**</ept> gyorslapján.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a funkció csak akkor áll rendelkezésre, ha a megadott tárolási raktárhoz és cikkekhez be van kapcsolva a speciális raktárkezelés.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Egy későbbi kiadásban a funkció már olyan esetekben is támogatott lesz, ahol nem használják a speciális raktárkezelést.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>