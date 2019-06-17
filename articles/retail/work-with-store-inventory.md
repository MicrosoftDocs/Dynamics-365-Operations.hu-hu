<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="work-with-store-inventory.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>work-with-store-inventory.418f90.551a8408aa730bc1916f1c57b7cfd773966ce8bf.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>551a8408aa730bc1916f1c57b7cfd773966ce8bf</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\work-with-store-inventory.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Üzleti árukészlet kezelése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the types of documents that you can use to manage inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A témakör ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Üzleti árukészlet kezelése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>When working with inventory in Dynamics 365 for Retail and using the POS application, it is important to note that POS provides limited support for inventory dimensions and certain inventory item types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Készletek kezelésekor Dynamics 365 for Retail alkalmazásban és a POS alkalmazás használatakor, fontos megjegyezni, hogy POS korlátozott támogatást nyújt készletdimenziókhoz és az egyes készletcikk típusokhoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The POS solution does not support the following item configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A POS-megoldás nem támogatja a következő cikk-konfigurációkat:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>BOM items (except kit products, which utilize some components of the BOM framework)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Anyagjegyzék-cikkek (kivéve a csomagtermékeket, amelyek használják az anyagjegyzék-keretrendszer bizonyos összetevőit)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Catch weight items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tényleges súllyal rendelkező cikkek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Batch-controlled items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kötegvezérelt cikkek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The POS application currently does not support the following tracking dimensions in the POS:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A POS alkalmazás jelenleg nem támogatja a következő nyomon követési dimenziókat a POS-ben:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Batch tracking dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kötegkövetési-dimenzió</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Owner dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tulajdonosi dimenzió</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The POS solution provides limited support for the following dimensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A POS-megoldás a következő dimenziókhoz korlátozott támogatást nyújt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Limited support indicates that the POS may default some of these dimensions into inventory transactions automatically based on warehouse/store setup configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Korlátozott támogatás azt jelzi, hogy a POS esetleg ezen dimenziók némelyikét a automatikusan készlettranzakciókká alakítja a raktár/üzlet a telepítési konfigurációja alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>POS will not fully support the dimensions in the way they are supported if a sales transaction is manually entered into the ERP.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">POS nem teljes mértékben támogatja a dimenziók, olyan módin, mintha az értékesítési tranzakció manuálisan lenne megadva az ERP-ben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source><bpt id="p1">**</bpt>Warehouse Location<ept id="p1">**</ept> – Users will not have the ability to manage the receiving warehouse location for items received into a store warehouse when the store has not been configured to use the warehouse management process.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Raktár helyszíne<ept id="p1">**</ept> – A felhasználók nem lesznek képesek kezelni a fogadó raktár helyét az üzlet raktárába beérkezett cikkekre, amikor az üzlet nincs beállítva a raktárkezelési folyamat használatára.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>A default receiving location defined on the store warehouse will be used for these items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezekhez a cikkekhez az üzlet raktárában megadott alapértelmezett bevételezési hely lesz használatban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>If the warehouse management process has been enabled for the store, limited support that prompts the user to choose a receiving location for the entire receipt will be triggered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a raktárkezelési folyamat engedélyezve van az üzlethez, akkor korlátozott támogatás jelenik meg a felhasználó számára, válasszon egy fogadó helyszínt a teljes nyugtához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Items sold from the store will always be sold out of the default retail location as defined on the store warehouse setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az üzletből eladott cikkek mindig az üzlet alapértelmezett raktárából kerülnek eladásra az üzlet raktárbeállításai szerint.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The location for managing return inventory can be controlled through default return location definition on the store warehouse or based on return reason codes as defined in the return location policy.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">A visszáru-készlet kezelésének helye az üzlet raktárának alapértelmezett visszárurendelés-definícióján keresztül vagy visszaküldés helyére vonatkozó szabályzatban megadott visszaküldési kódok alapján történik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>License plate<ept id="p1">**</ept> – License plates are only applicable when <bpt id="p2">**</bpt>Use warehouse management process<ept id="p2">**</ept> has been enabled on the item and the store warehouse.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Azonosítótábla<ept id="p1">**</ept> – Azonosítótábla csak akkor van használva, ha a <bpt id="p2">**</bpt>Raktárkezelési folyamatok alkalmazása<ept id="p2">**</ept> engedélyezve van a cikkhez és az áruházi raktárban.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In POS, if inventory is received into a store warehouse where the warehouse management process has been enabled, and the location chosen to receive the item into is tied to a location profile that requires license plate control, the POS application will systematically apply a license plate to the receiving line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A pénztárnál abban az esetben, ha a készletet olyan üzletraktárba fogadják, amelyben a raktárkezelési folyamat engedélyezve van, és a tétel beérkezéséhez kiválasztott helyprofil megköveteli az azonosítótábla ellenőrzését, a POS-alkalmazás szisztematikusan azonosítótáblát rendel a fogadó sorhoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Users in POS will not have the ability to change or manage this license plate data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A POS-felhasználók nem tudják módosítani vagy kezelni ezt az azonosítótábla-adatot.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>If full management of license plates is required, it is suggested the store use the WMS mobile application or the back office ERP client to manage the receipt of these items.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Ha szükséges az azonosítótáblák teljes körű kezelése, akkor javasolt, hogy az üzlet a WMS Mobile alkalmazást vagy a back office ERP-ügyfelet használja a cikkek fogadásának kezelésére.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Serial number<ept id="p1">**</ept> – The POS application has limited support for single serial number to be registered on a transaction sales line for orders created in POS with serialized items.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Sorozatszám<ept id="p1">**</ept> – A POS-alkalmazás korlátozottan támogatja egy sorozatszám regisztrálását tranzakciós értékesítési sorhoz, olyan rendelésekhez, amelyek a pénztárban sorszámozott cikkekkel lettek létrehozva.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>This serial number is not validated against registered serial numbers already in inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a sorozatszám nincs ellenőrizve a már készleten lévő regisztrált sorozatszámokkal szemben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>If a sales order is created in the call center channel or fulfilled through the ERP and multiple serial numbers are registered to a single sales line during the fulfillment process in the ERP, these serial numbers will not be able to be applied or validated if a return is processed in POS for these orders.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Ha egy értékesítési rendelést a hívásközpont-csatornában hoztak létre, vagy az ERP-n keresztül van teljesítve, és több sorozatszám lesz regisztrálva egy értékesítési sorhoz az ERP teljesítési folyamata során, akkor ezek a sorozatszámok nem lesznek alkalmazhatók vagy ellenőrizhetők, ha visszárut dolgoznak fel a pénztárban ezekhez a rendelésekhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source><bpt id="p1">**</bpt>Inventory status<ept id="p1">**</ept> – For items that use the warehouse management process and require an inventory status, this status field is not able to be set or modified through the POS application.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Készlet állapota<ept id="p1">**</ept> – A raktárkezelési folyamatot használó cikkek esetében, amelyekhez készletállapot szükséges, ez a mező nem állítható be vagy módosítható a pénztáralkalmazáson keresztül.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>The default inventory status as defined on the store warehouse configuration will be used when items are received into inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A bolt raktárkonfigurátorában megadott készletállapot lesz használva, amikor a cikkek megérkeznek a készletbe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>All organizations must test item configurations through POS in development or test environments before deploying them to production.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az összes szervezetnek tesztelnie kell a cikk-konfigurációkat a fejlesztés alatt álló POS-en tesztelési környezeten keresztül a termelésbe helyezés előtt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Test your items by performing regular cash and carry sales transacting and creating customer orders (if applicable) through the POS with your items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Teszteljék a cikkeket a megszokott készpénzes tranzakciók és ügyfélrendelések létrehozásával (ha van) az elemek a POS-en keresztül a cikkeivel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Testing must include running a full statement posting processes in your test environment and verifying that there are no issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A tesztelésnek tartalmaznia kell teljes nyilatkozatközzétételi folyamatokat a tesztkörnyezetben, és ellenőrizni kell, hogy ne legyenek problémák.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Configuring items in a way that is not supported by the POS application, without proper testing, can result in your statement posting process failing in production without an easy way to correct the issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cikkek konfigurálása oly módon, amelyet POS alkalmazás nem támogat megfelelő tesztelés nélkül, a kimutatás feladási folyamat hibáját okozhatja a termelés során, anélkül, hogy könnyen javítani lehetne a problémákat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Partner or customer customizations to the application may optionally be considered to allow these posting processes to successfully complete.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alkalmazás partneri vagy ügyfél-testreszabásai esetleg megfontolhatók, hogy lehetséges legyen ezen feladási folyamatok sikeres elvégzése.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>If customizations are not needed, the organization must ensure that the product configuration of your products has been done in a way that is supported by the standard POS application/order creation/statement posting process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha nincs szükség testreszabásokra, a szervezetnek biztosítania kell, hogy megtörtént a termékek a termékkonfigurációja oly módon, hogy azt a szokások POS alkalmazás/rendelés létrehozása/kimutatásfeladási folyamat támogassa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Purchase orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beszerzési rendelések</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Purchase orders are created at the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A beszerzési rendeléseket a központi irodában készítik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail through the <bpt id="p1">**</bpt>Picking/Receiving<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha kiskereskedelmi raktár szerepel a beszerzési rendelés fejlécében, akkor a rendelés fogadása az áruháznál történhet a Modern POS (MPOS) vagy a felhőalapú POS segítségével a Microsoft Dynamics 365 for Retail szolgáltatásban a <bpt id="p1">**</bpt>Kitárolás/bevételezés<ept id="p1">**</ept> művelettel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>After the quantities that are received at the store are entered in the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> field in POS for the purchase order document, they can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Miután az üzletben bevételezett mennyiségek beírásra kerülnek a <bpt id="p1">**</bpt>Fogadás most<ept id="p1">**</ept> mezőbe a pénztárban a beszerzési rendelés dokumentumba, lehetséges azok helyi mentése vagy véglegesítése.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Saving this data locally has no effect on in-stock inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezeknek az adatoknak a helyi mentése nem befolyásolja a készleten lévő készletet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and just needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen bizonylat elküldésére a központba, és szüksége van egy megoldásra a korábban megadott <bpt id="p1">**</bpt>Most fogadva<ept id="p1">**</ept> adat tárolására.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a most fogadva adatokat menti helyben a felhasználó csatorna-adatbázisába.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the purchase order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Miután a dokumentumot feldogozta a <bpt id="p1">**</bpt>Véglegesítés<ept id="p1">**</ept> lehetőséggel a <bpt id="p2">**</bpt>Fogadás most<ept id="p2">**</ept> adatokat a program elküldi a központnak és a beszerzési rendelés bizonylata fel lesz adva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Transfer orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Átmozgatási rendelések</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>A transfer order can specify that a particular store is the location that items can be shipped from or the location the inventory will be received into.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az átmozgatási rendelés megadhatja, hogy egy adott üzlet az a hely, ahonnan a cikkeket szállítani lehet, vagy az a hely, ahol fogadják azokat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>If the POS user is the shipping warehouse for a transfer order, they will be able to enter <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a pénztár felhasználója egy átmozgatási rendelés szállítási raktára, akkor a pénztárból meg tudja adni a <bpt id="p1">**</bpt>Szállítás most<ept id="p1">**</ept> mennyiségeket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>The data entered by the shipping store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállító üzlet által megadott adatok helyileg vagy véglegesítve menthetők.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>When saved locally, no updates are made to the transfer order document in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Helyi mentéskor nem történik frissítés a központ átmozgatási rendelési dokumentumában.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Saving should be done only if the user is not ready to post the shipment to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen szállítmány elküldésére a központba, és szüksége van egy megoldásra a korábban megadott <bpt id="p1">**</bpt>Most szállítva<ept id="p1">**</ept> adat tárolására.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>After the store is ready to confirm shipment, the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option should be selected.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Miután az üzlet készen áll a szállítmány jóváhagyására a <bpt id="p1">**</bpt>Véglegesítés<ept id="p1">**</ept> lehetőséget kell választani.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>This posts the shipment of the transfer order in HQ so that the receiving warehouse will now be able to receive against it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez feladja az átmozgatási rendelés kiszállítását a központba, amelyet a fogadó raktár immár képes fogadni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>If the POS user is the receiving warehouse for a transfer order, they will be able to enter the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a pénztár felhasználója egy átmozgatási rendelés fogadó raktára, akkor a pénztárból meg tudja adni a <bpt id="p1">**</bpt>Fogadás most<ept id="p1">**</ept> mennyiségeket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The data entered by the receiving store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fogadó üzlet által megadott adatok helyileg vagy véglegesítve menthetők.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A mentés csak akkor hajtható végre, ha a felhasználó nem áll készen bizonylat elküldésére a központba, és csak szüksége van egy megoldásra a korábban megadott <bpt id="p1">**</bpt>Most fogadva<ept id="p1">**</ept> adat tárolására.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a most fogadva adatokat menti helyben a felhasználó csatorna-adatbázisába.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the transfer order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Miután a dokumentumot feldogozta a <bpt id="p1">**</bpt>Véglegesítés<ept id="p1">**</ept> lehetőséggel a <bpt id="p2">**</bpt>Fogadás most<ept id="p2">**</ept> adatokat a program elküldi a központnak és az átmozgatási rendelés bizonylata fel lesz adva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>It's important to note that the receiving store will be restricted to only being able to commit receive quantities that are equal to or less than shipped quantities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fontos megjegyezni, hogy a fogadó üzletet csak a szállított mennyiséggel megegyező vagy annál kisebb szállított mennyiségeket képes bevételezni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>An attempt to receive quantities on a transfer order that have not previously shipped will result in errors and the receipt will not be confirmed in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A korábban nem leszállított átmozgatási rendelések a mennyiségeinek fogadására tett kísérlet hibákat okoz, és a bizonylat nem lesz megerősítve a központban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Stock counts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Leltárok</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Stock counts can be either scheduled or unscheduled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A leltárok lehetnek ütemezettek és nem tervezettek is.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A tervezett leltárokat a központi irodában kezdeményezik, ami meghatározza, hogy melyik cikkeket kell leltározni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A központi iroda létrehoz egy leltárbizonylatot, amelyet fogadni tudnak az üzletnél, ahol a tényleges készletmennyiségeket rögzítik az MPOS vagy a Cloud POS rendszerben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A nem ütemezett leltárakat az üzlet kezdeményezi, és a frissített tényleges készletmennyiségeket vagy az MPOS, vagy a Cloud POS rendszerben rögzítik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>When a stock count of either type is completed, it is committed and sent to the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Amikor bármely típusú leltár befejeződik vállalásra kerül és a központi irodába küldik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>At the head office, the count is validated and posted as a separate step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A központi irodában a leltárt ellenőrzik és feladják egy külön lépésben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Inventory lookup</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Keresés a készletben</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>The current product quantity on hand for multiple stores and warehouses can be viewed on the <bpt id="p1">**</bpt>Inventory lookup<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A több üzlet és raktár számára elérhető aktuális készleten levő termékmennyiséget a <bpt id="p1">**</bpt>Keresés a készletben<ept id="p1">**</ept> lapon tekintheti meg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az aktuális készleten levő mennyiségen túl az ígérethez rendelkezésre álló (ATP) mennyiségek az egyes üzletek esetében tekinthetők meg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>To do so, select the store that you want to view the ATP for and then click <bpt id="p1">**</bpt>Show store availability<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ehhez válassza ki azt az üzletet, amelyre vonatkozóan meg akarja jeleníteni az ígérethez rendelkezésre álló mennyiséget, és kattintson az <bpt id="p1">**</bpt>Üzlet elérhetőségének megjelenítése<ept id="p1">**</ept> lehetőségre.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>