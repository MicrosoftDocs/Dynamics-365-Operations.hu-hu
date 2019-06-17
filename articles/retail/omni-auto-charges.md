<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Többcsatornás speciális automatikus költségek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a témakör a Retail csatorna rendeléseihez kapcsolódó kiegészítő rendelési költségek automatikus költségfunkciók használatával való kezelésére vonatkozó lehetőségeket írja le.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Többcsatornás speciális automatikus költségek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a témakör tájékoztatást nyújt a speciális automatikus költségek funkció konfigurációjáról és telepítéséről, amely rendelkezésre áll a Dynamics 365 for Retail 10.0-s verziójában.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a speciális automatikus költségek funkciók engedélyezve vannak, akkor az összes támogatott Retail csatornában (pénztár (POS), hívásközpont, és az interneten keresztül) kihasználhatja az <bpt id="p1">[</bpt>automatikus költségek<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> konfigurációk előnyeit, amelyeket a fejléc- és sorszintű kapcsolódó költségekre vonatkozóan meghatároztak az ERP alkalmazásban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A Dynamics 365 for Retail 10.0 verzió előtti kiadásokban az <bpt id="p1">[</bpt>automatikus költség<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> konfigurációi csak az elektronikus kereskedelmi és a hívásközponti csatornákban létrehozott rendelések számára hozzáférhetők.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A 10.0 és a későbbi verziókban a pénztár által létrehozott rendelések is kihasználhatják az automatikus költségek konfigurációit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezzel a módszerrel a további vegyes költségek szisztematikusan hozzáadhatók az értékesítési tranzakciókhoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A 10.0-s verzió előtti kiadások használata esetén a pénztárfelhasználót a rendszer felkéri arra, hogy manuálisan adja meg a szállítási díjat egy „összes szállítása” vagy „kiválasztottak szállítása” pénztártranzakció létrehozása során.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Míg az alkalmazás vegyes költségekre vonatkozó lehetőségei a költségek rendelésben való leírásával kapcsolatban használhatók, ezek nem nyújtanak szisztematikus számítást – a számítás a felhasználó által beírt adatokon alapul a költségek értékek meghatározásakor.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A költségeket csak egyszeri „szállítással” kapcsolatos költségkóddal lehet hozzáadni, és a létrehozás után nem lehet egyszerűen szerkeszteni és módosítani őket a pénztárban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szállítási költségek hozzáadására a kézi beavatkozások használata továbbra is elérhető a 10.0 és újabb verziókban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a szervezet nem engedélyezi a <bpt id="p1">**</bpt>Speciális automatikus költségek<ept id="p1">**</ept> paramétert, a pénztár felkérései a költségek manuális bevitelére változatlanok maradnak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A speciális automatikus költségek funkcióval a POS-felhasználó számításokat végezhet bármely meghatározott vegyes költséggel az automatikus költségek beállítási táblái alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezenkívül a felhasználók képesek lesznek további költségek és díjak korlátlan mennyiségének hozzáadására vagy szerkesztésére bármelyi pénztári értékesítési tranzakcióhoz fejléc- vagy sorszinten (átvétel és fizetés helyben vagy vevői rendelés esetén).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Speciális automatikus költségek engedélyezése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">A <bpt id="p1">**</bpt>Kiskereskedelem <ph id="ph1">\&gt;</ph> Központ beállítása <ph id="ph2">\&gt;</ph> Paraméterek <ph id="ph3">\&gt;</ph> Kiskereskedelmi paraméterek<ept id="p1">**</ept> oldalon lépjen a <bpt id="p2">**</bpt>Vevői rendelések<ept id="p2">**</ept> lapra. A <bpt id="p3">**</bpt>Költségek<ept id="p3">**</ept> gyorslapon állítsa a <bpt id="p4">**</bpt>Speciális automatikus költségek használata<ept id="p4">**</ept> beállítást <bpt id="p5">**</bpt>Igen<ept id="p5">**</ept> értékre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Speciális automatikus költségek paraméter</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a speciális automatikus költségek engedélyezve vannak, a felhasználókat már nem szólítja fel a rendszer, hogy manuálisan adja meg a POS terminálon a szállítási költséget összes szállítása vagy kiválasztottak szállítása típusú vevői rendelés létrehozásakor.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A pénztár rendelési költségeket a rendszer szisztematikusan kiszámítja és hozzáadja a pénztártranzakcióhoz (ha megtalálható a megfelelő automatikus költségek tábla, amely megfelel a létrehozott rendelés feltételének).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A felhasználók hozzáadhatnak vagy karbantarthatnak fejléc- vagy sorszintű költségeket manuálisan az újonnan hozzáadott pénztárműveleteken keresztül, amelyeket hozzá lehet adni a pénztár képernyő-elrendezésekhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha speciális automatikus költségek engedélyezve vannak, a meglévő <bpt id="p1">**</bpt>Kiskereskedelmi paraméterek<ept id="p1">**</ept>, amelyek a <bpt id="p2">**</bpt>Szállítási költségek kódja<ept id="p2">**</ept> és <bpt id="p3">**</bpt>Szállítási költségek visszatérítése<ept id="p3">**</ept> pontokhoz tartoznak, nem használatosak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezek a paraméterek csak akkor érvényesek, ha a <bpt id="p1">**</bpt>Speciális automatikus költségek használata<ept id="p1">**</ept> paraméter értéke <bpt id="p2">**</bpt>Nem<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mielőtt engedélyezi ezt a funkciót, győződjön meg róla, hogy tesztelte és képezte az alkalmazottakat, mivel ez megváltoztatja a szállítási és egyéb költségek kiszámításának és a pénztár értékesítési rendeléseinek hozzáadásának folyamatát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ellenőrizze, hogy megérti a folyamat hatását a tranzakciók létrehozására a pénztárból.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hívásközpontból származó és e-kereskedelmi rendelések esetén a speciális automatikus költségek engedélyezésének hatása minimális.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hívásközpont és az elektronikus kereskedelmi alkalmazások továbbra is ugyanúgy viselkednek majd, ahogy korábban tették az automatikus költségekre vonatkozó táblákhoz kapcsolódó további rendelési díjak kiszámításához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hívásközpont csatorna felhasználói továbbra is manuálisan szerkeszthetik a rendszer által kiszámított automatikus költségeket a fejléc vagy sorok szintjén, vagy manuális hozzáadhatnak a további vegyes költségeket a fejléc vagy sorok szintjén.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">További pénztárműveletek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ahhoz, hogy a speciális automatikus költségek megfelelően működjenek a pénztáralkalmazás környezetében, új pénztárműveleteket adtunk hozzá.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezeket a műveleteket hozzá kell adnia a <bpt id="p1">[</bpt>Pénztár képernyő-elrendezései<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> részhez, és telepítenie kell a pénztár eszközeihez a speciális automatikus költségek telepítésével együtt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha ezek a műveletek hozzáadása nem történik meg, a felhasználók nem tudják majd kezelni vagy karbantartani a vegyes költségeket a pénztártranzakciókon, és nem lesz lehetőségük kiigazítani vagy módosítani a rendszer által számított, automatikus költségek konfiguráción alapuló költségértékeket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Legalább ajánlott, hogy telepítse a <bpt id="p1">**</bpt>Költségek kezelése<ept id="p1">**</ept> műveletet a pénztár elrendezéséhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Az új műveletek alább láthatók.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>142 – Költségek kezelése<ept id="p1">**</ept> – Használja ezt a műveletet arra, hogy engedélyezze a pénztár felhasználóknak a vegyes költségek megjelenítését és szerkesztését a pénztártranzakcióknál, amelyeket vagy kézzel vagy rendszer által kerültek hozzáadásra automatikus költségek számításain keresztül.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>141 – Fejlécköltségek hozzáadása<ept id="p1">**</ept> – Használja ezt a műveletet arra, hogy lehetőséget adjon a felhasználónak a fejléc szintű vegyes költségek manuális hozzáadására a pénztár értékesítési tranzakcióhoz (és válassza ki a használandó költségkódot).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>140 – Sorköltségek hozzáadása<ept id="p1">**</ept> – Használja ezt a műveletet arra, hogy lehetőséget adjon a felhasználónak a sorszintű vegyes költségek manuális hozzáadására a pénztár értékesítési tranzakció sorához (és válassza ki a használandó költségkódot).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>143 – Költségek újraszámolása<ept id="p1">**</ept> – A művelet segítségével az értékesítési tranzakcióhoz a költségek teljes ismételt számítását végrehajthatja.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bármely korábbi felhasználó által felülbírált automatikus költségek újra lesznek számítva a bevásárlókocsi aktuális konfigurációja alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mint minden pénztárműveletnál, a biztonsági konfigurációk beállíthatók úgy, hogy vezetői jóváhagyást igényeljenek a művelet végrehajtásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fontos megjegyezni, hogy a fent felsorolt POS-műveletek a POS-elrendezés akkor is hozzáadhatók, ha a <bpt id="p1">**</bpt>Speciális automatikus költségek használat<ept id="p1">**</ept> paraméter le van tiltva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben az esetben a szervezetek még további előnyöket élvezhetnek, azáltal hogy a manuálisan hozzáadott díjakat megtekinthetik és szerkesztheti a <bpt id="p1">**</bpt>Költségek kezelése<ept id="p1">**</ept> művelettel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Felhasználók használhatják a <bpt id="p1">**</bpt>Fejlécköltségek hozzáadása<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Sorköltségek hozzáadása<ept id="p2">**</ept> műveleteket POS-tranzakciókhoz, még akkor is, ha a <bpt id="p3">**</bpt>Speciális automatikus költségek használata<ept id="p3">**</ept> paraméter le van tiltva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Költségek újraszámolása<ept id="p1">**</ept> művelet kevesebb funkcióval rendelkezik, ha a <bpt id="p2">**</bpt>Speciális automatikus költésgek használata<ept id="p2">**</ept> le van tiltva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben a szituációban semmi nem lesz újraszámítva, és a manuálisan hozzáadott díjak a tranzakcióhoz visszaállnak $0.00 értékre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használati eset példái</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben a szakaszban használati eseteket mutatunk be, amellyel jobban megértheti az automatikus költségek és vegyes költségek beállítását és használatát a Kiskereskedelmi csatorna rendelései vonatkozásában.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alábbi példák bemutatják az alkalmazás működését, amikor a <bpt id="p1">**</bpt>Speciális automatikus díjak használata<ept id="p1">**</ept> paraméter engedélyezve van.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Automatikus költségek fejlécköltségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használati eset forgatókönyve</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő szeretne automatikusan költségeket hozzáadni a szállításhoz a bármely kiskereskedelmi csatornában létrehozott tranzakciók esetén, ahol a termékeket el kell szállítani a vevőhöz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő kínál 2 szállítási módot: földi és légi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a vevő a Földi szállítást választja és a rendelés értéke kisebb, mint 100 USD, a kiskereskedő 10 USD fuvardíjat akar a vevőre terhelni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a rendelés értéke több mint 100 USD, és a vevő a földi szállítás mellet dönt, a vevőnek nem számolnak fel további szállítási díjakat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a vevő légi módot választ az összes megrendeléshez, összértékétől függetlenül, 20 USD szállítási díjat kell felszámítani.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beállítás és konfigurálás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben az esetben a két automatikus költségekre vonatkozó tábla konfigurációja szükséges.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ugorjon a <bpt id="p1">**</bpt>Kinnlevőségek <ph id="ph1">\&gt;</ph> Költségek beállítása <ph id="ph2">\&gt;</ph> Automatikus költségek<ept id="p1">**</ept> pontra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Két különböző fejléc szintű automatikus költséget konfiguráljon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítson be egyet a „földi szállítási módhoz” és egyet a „légi szállítási módhoz”</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben az esetben azokat az "Összes vevő" használatára kell konfigurálni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A földi szállítási költségekhez az <bpt id="p1">**</bpt>Automatikus költségek<ept id="p1">**</ept> oldal sorokat tartalmazó szakaszában határozza meg a költséget 10 USD-nak, amelyeket a 0,01 és 100 dollár közti rendelésekhez alkalmaz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hozzon létre egy másik költségek sort, ahol jelzi, hogy a 100,01 USD feletti rendeléseknek nincs költsége.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Automatikus költségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A légi szállítási költségekhez az Automatikus költségek képernyő sorokat tartalmazó szakaszában határozza meg a költséget 20 USD-nak, amelyeket mindent rendeléshez alkalmaz (0,01 és 9°999°999 USD közti érték esetén)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Küldje el a módosításokat a Retail Server/csatorna-adatbázishoz, hogy a pénztár használhassa őket a <bpt id="p1">**</bpt>1040 elosztási ütemezés<ept id="p1">**</ept> feladat futtatásával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Értékesítés feldolgozása ebben az esetben</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fenti konfigurációs lépések végrehajtása és a módosítások csatorna-adatbázisra alkalmazása után, bármely vevői rendelés vagy értékesítési tranzakció, amelyet a pénztárban, hívásközpontban, vagy elektronikus kereskedelmi csatornákban hoztak létre, amelyeknél a fejlécben beállították a földi vagy légi szállítási módot, használja ezeket a költségeket és automatikusan hozzáadja őket az értékesítéshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ekkor minden olyan értékesítési tranzakcióra vonatkoznak a költségek, amelyeket a szállítási módokat használó jogi személyen belül létrehoztak, mivel nincs olyan funkció, amellyel az automatikus költségek konfigurációt csak egy adott értékesítési csatornára alkalmazzanak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A POS és az elektronikus kereskedelem eseteiben,mivel ezeketn a rendeléseken nincs pontosan meghatározott „fejléc”, a fejléc szintű költségek csak akkor érvényesek, ha a tranzakció összes értékesítési sorához pontosan ugyanaz a szállítási mód van beállítva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a pénztár vagy elektronikus kereskedelem által létrehozott tranzakciók esetén „vegyes teljesítési módok” vannak, csak sorszintű automatikus díjakat fog a rendszer figyelembe venni és alkalmazni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A hívásközpont helyzeteinél a felhasználó rendelkezik hatalommal a szállítási mód beállítására a rendelés fejlécében, ezért fejléc szintű költségek vonatkoznak ezekre a rendelésekre, akkor is, ha az egyes értékesítési sorok különböző szállítási mód használatára vannak beállítva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A hívásközpont rendelések fejléc szintű költségei mindig a szállítási mód alapján történik, amely az értékesítési rendelés fejlécének szintjén meg van határozva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Automatikus költségek sorköltségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használati eset forgatókönyve</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő szeretne hozzáadni egy további díjat a vevőnek a beállítási díjakra, amikor a vevő egy bizonyos típusú számítógépet szerez be.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezen a számítógépen további nem választható beállítási műveletre van szükség, amelyet a kiskereskedő hajt végre a vevőnek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő tájékoztatta vevőket, hogy ezért a beállításért járulékos díj lesz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő a díjjal kapcsolatos költségeket a termék eladási árától külön kívánja kezelni pénzügyi jelentési célok miatt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezen számítógép bármely kiskereskedelmi csatornán való megvásárlásakor a vevőnek 19,99 USD beállítási díjat kell fizetnie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beállítás és konfigurálás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben az esetben egy sorszintű automatikus költségekre vonatkozó tábla konfigurációja szükséges.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ugorjon a <bpt id="p1">**</bpt>Kinnlevőségek <ph id="ph1">\&gt;</ph> Költségek beállítása <ph id="ph2">\&gt;</ph> Automatikus költségek<ept id="p1">**</ept> pontra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítsa a <bpt id="p1">**</bpt>Szint<ept id="p1">**</ept> legördülő menüt <bpt id="p2">**</bpt>Sor<ept id="p2">**</ept> értékre, és hozzon létre egy új automatikus költségek rekordot az összes vevőre és az adott termékre vagy termékcsoportra vonatkozóan, ahol a beállítási díjakat kell fizetnie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Automatikus költségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Küldje el a költségeket a Retail Server/csatorna-adatbázishoz, hogy a pénztár használhassa őket a <bpt id="p1">**</bpt>1040 elosztási ütemezés<ept id="p1">**</ept> feladat futtatásával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Értékesítés feldolgozása ebben az esetben</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fenti konfigurációs lépések végrehajtása és a módosítások csatorna-adatbázisra alkalmazása után, bármely vevői rendelés vagy értékesítési tranzakció, amelyet a pénztárban, hívásközpontban, vagy elektronikus kereskedelmi csatornákban hoztak létre, amelyeknél az adott cikk szerepel a rendelésben, egy sorszintű költség rendelés végösszegéhez való szisztematikus hozzáadását kezdeményezi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ekkor a költségek minden olyan értékesítési sorra vonatkoznak a költségek, amely megfelel az adott jogi személyen belül a sorszintű automatikus költségek konfigurációjának, mivel nincs olyan funkció, amellyel a sorszintű automatikus költségeknek csak egy bizonyos értékesítési csatornára való alkalmazását szabályozzák.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuális fejlécköltségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használati eset forgatókönyv leírása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő kivételt tett a jellemző folyamatokban, amikor termékek speciális házhozszállítását ajánlotta a vevőknek, aki termékeket rendelt az áruházban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő és a vevő megállapodtak, hogy a vevő kifizet további 25 USD kezelési díjat erre a szolgáltatásra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A rendelés átvevőjének hozzá kell adnia ezt a díjat a tranzakcióhoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mivel a díj egy általános díj, és nem kapcsolódik egyetlen termékhez sem a rendelésen, fejlécköltséget használnak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beállítás és konfigurálás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg róla, hogy az ebben az esetben használandó költségkód megfelelően van beállítva: nyissa meg a <bpt id="p1">**</bpt>Kinnlevőségek <ph id="ph1">\&gt;</ph> Költségek beállítása <ph id="ph2">\&gt;</ph> Költségek<ept id="p1">**</ept> lapot az esethez megfelelő költségkód meghatározásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Költségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Ha a költséget „szállításhoz” kapcsolódó költségként kell figyelembe venni, szállítási engedmény vagy promóció céljából, a költségkód <bpt id="p1">**</bpt>Szállítási költség<ept id="p1">**</ept> beállítását állítsa <bpt id="p2">**</bpt>Igen<ept id="p2">**</ept> értékre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha ezt a költséget jogosult a pénztáralkalmazásban a rendszer egy visszáru-tranzakció feldolgozása során szisztematikusan visszatéríteni, állítsa a <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> beállítást <bpt id="p2">**</bpt>Igen<ept id="p2">**</ept> értékre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> jelző csak akkor alkalmazható, amikor a <bpt id="p2">**</bpt>Speciális automatikus költségek használata<ept id="p2">**</ept> paraméter értéke <bpt id="p3">**</bpt>Igen<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Küldje el a költségeket a Retail Server/csatorna-adatbázishoz, hogy a pénztár használhassa őket a <bpt id="p1">**</bpt>1040 elosztási ütemezés<ept id="p1">**</ept> feladat futtatásával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Fejlécdíj hozzáadása<ept id="p1">**</ept> műveletet meg kell adni a <bpt id="p2">[</bpt>POS képernyő-elrendezés<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> részben úgy, hogy a felhasználó számára a pénztárból elérhető gomb lehívható ez a művelet (141-es művelet).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A képernyő-elrendezés módosításait meg kell osztani a kiskereskedelmi csatornán, valamint az elosztási ütemezés funkción.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuális fejlécköltségek értékesítési feldolgozása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A forgatókönyv végrehajtásához a pénztár alkalmazásban a pénztár felhasználónak létre kell hoznia szokásos módon az értékesítési tranzakciót, a termékek és egyéb konfigurációk hozzáadásával az értékesítéshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fizetés begyűjtése előtt a felhasználónak végre kell hajtania a <bpt id="p1">**</bpt>Fejlécköltség hozzáadása<ept id="p1">**</ept> műveletet, amely figyelmezteti a felhasználót a költségkód kiválasztására és a költségértékek megadására.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a felhasználó befejezi a folyamatot, a költség hozzáadódik az értékesítési rendeléshez fejléc szintű díjként.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a folyamat alkalmazható a hívásközpontban a meglévő <bpt id="p1">**</bpt>Költségek<ept id="p1">**</ept> funkcióval, amely az <bpt id="p2">**</bpt>Értékesítés<ept id="p2">**</ept> lapon található az eszköztáron.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Költségek karbantartása<ept id="p1">**</ept> oldalon a felhasználó hozzáadhat egy új költségsort a rendelés fejlécéhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuális sorköltségek példa</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használati eset forgatókönyve</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő kérte, hogy az értékelési rendelésen 2 cikk az 5-ből kapjon ajándékcsomagolást.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedő ezt a nem kötelező szolgáltatást cikkenként 2 USD díjért nyújtja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A rendelés átvevőjének hozzá kell adnia ezeket a díjat az ajándékcsomagolást kapó cikkekhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beállítás és konfigurálás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg róla, hogy az ebben az esetben használandó költségkód megfelelően van beállítva: nyissa meg a <bpt id="p1">**</bpt>Kinnlevőségek <ph id="ph1">\&gt;</ph> Költségek beállítása <ph id="ph2">\&gt;</ph> Költségek<ept id="p1">**</ept> lapot az esethez megfelelő költségkód meghatározásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a költséget „szállításhoz” kapcsolódó költségként kell figyelembe venni, szállítási engedmény vagy promóció céljából, a költségkód <bpt id="p1">**</bpt>Szállítási költség<ept id="p1">**</ept> beállítását állítsa <bpt id="p2">**</bpt>Igen<ept id="p2">**</ept> értékre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha ezt a költséget jogosult a pénztáralkalmazásban a rendszer egy visszáru-tranzakció feldolgozása során szisztematikusan visszatéríteni, állítsa a <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> beállítást <bpt id="p2">**</bpt>Igen<ept id="p2">**</ept> értékre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> jelző csak akkor alkalmazható, amikor a <bpt id="p2">**</bpt>Speciális automatikus költségek használata<ept id="p2">**</ept> paraméter értéke <bpt id="p3">**</bpt>Igen<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Küldje el a költségeket a Retail Server/csatorna-adatbázishoz, hogy a pénztár használhassa őket a <bpt id="p1">**</bpt>1040 elosztási ütemezés<ept id="p1">**</ept> feladat futtatásával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Sorköltség hozzáadása<ept id="p1">**</ept> műveletet meg kell adni a <bpt id="p2">[</bpt>POS képernyő-elrendezés<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> részben úgy, hogy a felhasználó számára a pénztárból elérhető gomb lehívható ez a művelet (140-es művelet).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A képernyő-elrendezés módosításait meg kell osztani a kiskereskedelmi csatornán, valamint az elosztási ütemezés funkción.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Manuális sorköltségek értékesítési feldolgozása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A forgatókönyv végrehajtásához a pénztár alkalmazásban a pénztár felhasználónak létre kell hoznia szokásos módon az értékesítési tranzakciót, a termékek és egyéb konfigurációk hozzáadásával az értékesítéshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fizetés begyűjtése előtt a felhasználónak ki kell választania a meghatározott sort a pénztárcikkek megjelenített listájából, amire a költségek vonatkoznak, és végre kell hajtania a <bpt id="p1">**</bpt>Sorköltség hozzáadása<ept id="p1">**</ept> műveletet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A felhasználót a program kéri, hogy válassza ki a költségkódot, és adja meg a költségek értékét.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a felhasználó befejezi a folyamatot, a költség hozzákapcsolódik a sorhoz, és hozzáadódik az értékesítési rendeléshez sor szintű költségként.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A felhasználó szükség esetén megismételheti a folyamatot, és a tranzakció többi cikkének sorához is hozzáadhat sorköltségeket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ugyanezt az eljárást lehet alkalmazni a hívásközpontban a „költségek karbantartása” funkcióval, amely a <bpt id="p1">**</bpt>Pénzügyek<ept id="p1">**</ept> legördülő menü alatt található az <bpt id="p2">**</bpt>Értékesítésirendelés-sorok<ept id="p2">**</ept> szakaszban az <bpt id="p3">**</bpt>Értékesítési rendelés<ept id="p3">**</ept> lapon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ennek hatására megnyílik a <bpt id="p1">**</bpt>Költségek karbantartása<ept id="p1">**</ept> lap, amelyen a felhasználó hozzáadhat egy új sorspecifikus költséget a tranzakcióhoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">További szolgáltatások</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Költségek szerkesztése a pénztár értékesítési tranzakcióin</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Költségek kezelése<ept id="p1">**</ept> műveletet (142) hozzá kell adni a <bpt id="p2">[</bpt>POS képernyő-elrendezés<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> részhez, így a felhasználó megtekintheti és módosíthatja, vagy felülbírálhatja a rendszer által kiszámított vagy manuálisan létrehozott fejléc vagy sor szintű költségeket.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha nem adják hozzá a műveletet, a felhasználók nem tudják módosítani a költségek értékét a pénztártranzakción, és nem tudják majd megtekinteni a költségek részleteit, például a költséghez kapcsolt költségkód típusát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Költségek kezelése<ept id="p1">**</ept> lapon a pénztárban a felhasználó megtekintheti a fejléc és a sor szintű költségek részleteit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A felhasználó használhatja az ezen a lapon elérhető <bpt id="p1">**</bpt>Szerkesztés<ept id="p1">**</ept> funkciót, amellyel módosíthatja a meghatározott költségsorban felszámított összeget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Amikor egy költségsort manuálisan felülbíráltak, a rendszer nem számítja újra szisztematikusan, kivéve, ha a felhasználó elindítja a <bpt id="p1">**</bpt>Költségek újraszámolása<ept id="p1">**</ept> műveletet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a <bpt id="p1">**</bpt>Költség-felülbírálás okkódja<ept id="p1">**</ept> úgy van beállítva a <bpt id="p2">**</bpt>Kiskereskedelmi paraméterek<ept id="p2">**</ept> beállító oldalon, akkor a rendszer kéri a felhasználót egy okkód megadására, amikor a kölrségek módosulnak a pénztáralkalmazásban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha az okkódot rögzítették a felülírt költségekre, új jelentés érthető el, a felülbírálások áttekintésére és ellenőrzésére.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A jelentés itt található: <bpt id="p1">**</bpt>Kiskereskedelem <ph id="ph1">\&gt;</ph> Lekérdezések és jelentések <ph id="ph2">\&gt;</ph> Költség-felülbírálás előzményei<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Költségek visszatérítése pénztár visszáru-tranzakciójában</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a <bpt id="p1">**</bpt>Speciális automatikus költségek használata<ept id="p1">**</ept> paraméter értéke <bpt id="p2">**</bpt>Igen<ept id="p2">**</ept>, a meglévő <bpt id="p3">**</bpt>Szállítási költségek visszatérítése<ept id="p3">**</ept> kiskereskedelmi paraméter már nem érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Annak jelzésére, hogy a speciális automatikus költségek alkalmazása esetén mely költségeket kell szisztematikusan visszatéríteni a vevőnek, győződjön meg arról, hogy a kapcsolódó költségkódot <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> értékkel konfigurálta a <bpt id="p2">**</bpt>Költségkód<ept id="p2">**</ept> beállító oldalon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg arról, hogy a beállításokat szinkronizálta a kiskereskedelmi csatorna-adatbázisokkal az elosztási ütemezés feldolgozásán keresztül.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Költségek visszatérítése visszárurendelési tranzakcióban</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A költségeket nem térítik vissza szisztematikusan a Retail szolgáltatásban létrehozott <bpt id="p1">**</bpt>Visszárurendelések<ept id="p1">**</ept> esetén.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A felhasználóknak ki kell jelölniük a <bpt id="p1">**</bpt>Költségek másolása<ept id="p1">**</ept> lehetőséget a <bpt id="p2">**</bpt>Visszárurendelés<ept id="p2">**</ept> létrehozásakor.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a <bpt id="p1">**</bpt>Költségek másolása<ept id="p1">**</ept> nincs bejelölve, az eredeti értékesítési tranzakció költségeit nem téríti vissza automatikusan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a <bpt id="p1">**</bpt>Költségek másolása<ept id="p1">**</ept> ki van választva, a rendszer az összes költséget átmásolja a visszárurendelésre, és a felhasználó manuálisan módosíthatja vagy törölheti azokat, amelyeket nem szeretne visszatéríteni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A hívásközpont visszáru-rendelési folyamata jelenleg nem támogat a <bpt id="p1">**</bpt>Visszatéríthető<ept id="p1">**</ept> a jelzőt a <bpt id="p2">**</bpt>Költségkód<ept id="p2">**</ept> beállításakor.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pénztárnyugták konfigurálása a költségek mutatására</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">A következő nyugtaelemeket hozzáadta a rendszer a nyugta sorához és láblécéhez a speciális automatikus költségek funkció támogatásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Sor szállítási költségei<ept id="p1">**</ept> – Ez a sorszintű elem az olyan specifikus költségkódok összefoglalására használatos, amelyeket az értékesítési sorra alkalmaztak.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Itt csak az olyan költségkódok jelennek meg, amelyet <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> költségként jelöltek meg a <bpt id="p2">**</bpt>Költségkód<ept id="p2">**</ept> oldalon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Sor egyéb költségei<ept id="p1">**</ept> – Ez a sorszintű elem az olyan nem szállításspecifikus költségkódok összefoglalására használatos, amelyeket az értékesítési sorra alkalmaztak.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Ezek azok a költségkódok, ahol a <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> jelző a <bpt id="p2">**</bpt>Költségkód<ept id="p2">**</ept> lapon nincs engedélyezve.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Megrendelés szállítási költségeinek részletei<ept id="p1">**</ept> – Ez a láblécszintű elem megjeleníti a rendelésre alkalmazott költségkódok leírásait, amelyeket <bpt id="p2">**</bpt>Szállítási<ept id="p2">**</ept> költségként jelöltek meg a <bpt id="p3">**</bpt>Költségkód<ept id="p3">**</ept> beállító oldalon.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Rendelés szállítási költségei<ept id="p1">**</ept> – Ezzel a lábléc szintű elemmel a szállítással kapcsolatos költségek dollárértékét jeleníti meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Megrendelés egyéb költségeinek részletei<ept id="p1">**</ept> – Ez a láblécszintű elem megjeleníti a rendelésre alkalmazott költségkódok leírásait, amelyeket nem szállítással kapcsolatos költségként jelöltek meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Rendelés egyéb költségei<ept id="p1">**</ept> – Ezzel a lábléc szintű elemmel a nem szállítással kapcsolatos költségek dollárértékét jeleníti meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Azt ajánljuk, hogy a szervezet szabadszöveges mezőket is adjon hozzá a nyugta láblécéhez annak érdekében, hogy meghatározza azokat a területeket, ahol a költségeket összefoglalják.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Megakadályozza, hogy a költségeket kiszámítsák a pénztárrendelés befejezéséig</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Előfordulhat, hogy egyes szervezetek szívesebben várnak, amíg a felhasználó befejezte az összes értékesítés hozzáadását a pénztártranzakcióhoz a költségek számítása előtt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Annak megakadályozására, hogy a költségek számítását cikkekként hozzáadják a pénztártranzakciókhoz, kapcsolja be a <bpt id="p1">**</bpt>Manuális költségszámítás<ept id="p1">**</ept> paramétert az üzlet által használt <bpt id="p2">**</bpt>Funkcióprofil<ept id="p2">**</ept> oldalán.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a paraméter engedélyezése arra kötelezi a pénztárfelhasználót, hogy a <bpt id="p1">**</bpt>Teljes összeg kiszámítása<ept id="p1">**</ept> műveletet használja, amikor a termékek hozzáadása a pénztártranzakcióhoz befejeződött.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Teljes összeg kiszámítása<ept id="p1">**</ept> művelet majd elindítja a rendelés fejlécére vagy megfelelő sorokra vonatkozó automatikus díjak számítását.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Költség-felülbírálási jelentések</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha felhasználó manuálisan felülírja a számított költségeket vagy manuálisan ad hozzá költséget a tranzakcióhoz, ez az adatot lesz elérhető ellenőrzésre a <bpt id="p1">**</bpt>Költség-felülbírálás előzményei<ept id="p1">**</ept> jelentésben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A jelentés itt érhető el: <bpt id="p1">**</bpt>Kiskereskedelem <ph id="ph1">\&gt;</ph> Lekérdezések és jelentések <ph id="ph2">\&gt;</ph> Költség-felülbírálás előzményei<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fontos megjegyezni, hogy a jelentéshez szükséges adatokat importálása a csatorna-adatbázisból történik a központba „P” elosztási munkaütemezésen keresztül.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Emiatt a POS-ban végrehajtott felülbírálások adatait nem lesznek azonnal elérhetők a jelentésben mindaddig, amíg a feladat fel nincs töltve az üzlet tranzakciós adatokaiba a központban.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>