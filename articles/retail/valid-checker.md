<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="valid-checker.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>valid-checker.125a66.1fc894206f9d90fce1e2eab292ac241e9d943e23.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>1fc894206f9d90fce1e2eab292ac241e9d943e23</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\valid-checker.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Retail transaction consistency checker</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kiskereskedelmi tranzakció konzisztencia-ellenőrzése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the retail transaction consistency checker functionality in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Retail kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkciójáról.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Retail transaction consistency checker</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kiskereskedelmi tranzakció konzisztencia-ellenőrzése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben a témakörben részletes leírást találhat a Microsoft Dynamics 365 for Finance and Operations 8.1.3 verziójában bemutatott kiskereskedelmi tranzakció konzisztencia-ellenőrzésére használatos funkcióról.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">A konzisztencia-ellenőrző azonosítja és elkülöníti az inkonzisztens tranzakciókat, mielőtt a kimutatásfeladási folyamat kezeli őket.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>When a statement is posted in Microsoft Dynamics 365 for Retail, posting can fail due to inconsistent data in the retail transaction tables.</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">Egy kimutatás feladása során a Microsoft Dynamics 365 for Retail szolgáltatásban a feladás sikertelen lehet, ha inkonzisztens adatok találhatók a kiskereskedelmi tranzakciók táblájában.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The data issue may be caused by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Az adatokkal kapcsolatos problémákat a pénztár (POS) alkalmazás előre nem látható problémái okozhatják, vagy ha a tranzakciók importálása nem megfelelően történt egy külső fél pénztárrendszeréből.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Examples of how these inconsistencies may appear include:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alábbiakban az inkonzisztenciák megjelenésére mutatunk be példákat:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The transaction total on the header table does not match the transaction total on the lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fejléctáblában szereplő tranzakciós végösszeg nem egyezik meg a sorokban található tranzakciók összegével.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>The line count on the header table does not match with the number of lines in the transaction table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fejléctábla sorainak száma nem egyezik meg a tranzakciós tábla sorainak számával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Taxes on the header table do not match the tax amount on the lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A fejléctáblában szereplő adók nem egyeznek meg a sorokban szereplő adó összegével.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a kimutatásfeladási folyamat feldolgozza az inkonzisztens tranzakciókat, akkor inkonzisztens értékesítési számlák és fizetési naplók keletkeznek, és emiatt a teljes kimutatásfeladási folyamat sikertelen lesz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha a kimutatásokat ebből az állapotból szeretné helyreállítani, ahhoz számos tranzakciós táblát érintő, komplex adathelyesbítési művelet szükséges.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>The retail transaction consistency checker prevents such issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kereskedelmi tranzakció konzisztencia-ellenőrzője megelőzi az ehhez hasonló problémák létrejöttét.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>The following chart illustrates the posting process with the transaction consistency checker.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alábbi ábrán a tranzakció konzisztencia-ellenőrzőjével végrehajtott feladási folyamat látható.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source><bpt id="p1">![</bpt>Statement posting process with retail transaction consistency checker<ept id="p1">]</ept><bpt id="p2">(./media/validchecker.png "</bpt>Statement posting process with retail transaction consistency checker<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével<ept id="p1">]</ept><bpt id="p2">(./media/validchecker.png "</bpt>Kimutatásfeladási folyamat kiskereskedelmi tranzakció konzisztencia-ellenőrzőjével<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>The <bpt id="p1">**</bpt>Validate store transactions<ept id="p1">**</ept> batch process checks the consistency of the retail transaction tables for the following scenarios.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Az <bpt id="p1">**</bpt>Üzleti tranzakciók ellenőrzése<ept id="p1">**</ept> kötegfolyamat ellenőrzi a kiskereskedelmi tranzakciós táblázatok konzisztenciáját az alábbi esetekben.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source><bpt id="p1">**</bpt>Customer account<ept id="p1">**</ept> – Validates that the customer account in the retail transaction tables exists in the HQ customer master.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Vevői számla<ept id="p1">**</ept> – Ellenőrzi, hogy a kiskereskedelmi tranzakciós táblában szereplő vevői számla létezik a HQ-ban a vevői alapadatok között.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source><bpt id="p1">**</bpt>Line count<ept id="p1">**</ept> – Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Sorok száma<ept id="p1">**</ept> – Ellenőrzi, hogy a tranzakciós fejléctáblában rögzített sorok száma megegyezik az értékesítési tranzakciók táblájában található sorok számával.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>Price includes tax<ept id="p1">**</ept> – Validates that the <bpt id="p2">**</bpt>Price includes tax<ept id="p2">**</ept> parameter is consistent across transaction lines.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Az ár tartalmazza az adót<ept id="p1">**</ept> – Ellenőrzi, hogy az <bpt id="p2">**</bpt>Az ár tartalmazza az adót<ept id="p2">**</ept> paraméter konzisztens-e a tranzakció soraiban.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source><bpt id="p1">**</bpt>Gross amount<ept id="p1">**</ept> – Validates that the gross amount on the header is the sum of the net amounts on the lines plus the tax amount.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Bruttó összeg<ept id="p1">**</ept> – Ellenőrzi, hogy a fejlécben szereplő bruttó összeg megfelel-e a sorokban található nettó összegek és az adó összegének összesítésével.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source><bpt id="p1">**</bpt>Net amount<ept id="p1">**</ept> – Validates that the net amount on the header is the sum of the net amounts on the lines.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Nettó összeg<ept id="p1">**</ept> – Ellenőrzi, hogy a fejlécben szereplő nettó összeg megfelel-e a sorokban található nettó összegek összesítésével.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source><bpt id="p1">**</bpt>Under / Over payment<ept id="p1">**</ept> – Validates that the difference between the gross amount on the header and the payment amount doesn't exceed the maximum underpayment/overpayment configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Alulfizetés/Túlfizetés<ept id="p1">**</ept> – Ellenőrzi, hogy a fejlécben található bruttó összeg és a kifizetett összeg közti különbség nem haladja meg a maximális alulfizetés/túlfizetés konfigurációját.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Discount amount<ept id="p1">**</ept> – Validates that the discount amount on the discount tables and the discount amount on the retail transaction line tables are consistent, and that the discount amount on the header is the sum of the discount amounts on the lines.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Engedmény összege<ept id="p1">**</ept> – Ellenőrzi, hogy az engedménytáblákban szereplő engedmény összege és a kiskereskedelmi tranzakció sorában szereplő engedmény összege konzisztens-e, és hogy a fejlécben található engedmény összege egyenlő-e a sorok engedményeinek összegével.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">**</bpt>Line discount<ept id="p1">**</ept> – Validates that the line discount on the transaction line is the sum of all the lines in the discount table that corresponds to the transaction line.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Sorengedmény<ept id="p1">**</ept> – Ellenőrzi, hogy a tranzakciós sorban található sorengedmény megegyezik-e az adott tranzakciós sorhoz kapcsolódó engedménytábla összes sorának összegével.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source><bpt id="p1">**</bpt>Gift card item<ept id="p1">**</ept> – Retail doesn't support the return of gift card items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Ajándékutalvány-cikk<ept id="p1">**</ept> – A Retail alkalmazás nem támogatja az ajándékutalvány-cikkek visszaküldését.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>However, the balance on a gift card can be cashed out. Any gift card item that is processed as a return line instead of a cash-out line fails the statement posting process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Azonban az ajándékutalvány egyenlegét ki lehet fizetni készpénzben. Ha az ajándékutalványcikket visszárusorként dolgozzák fel készpénzes kifizetési sor helyett, akkor a kimutatás feladási folyamata sikertelen lesz.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>The validation process for gift card items helps guarantee that the only return gift card line items on the retail transaction tables are gift card cash-out lines.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ajándékutalvány-cikkek ellenőrzési folyamata segítségével garantálható, hogy a kiskereskedelmi tranzakciós táblákban szereplő, ajándékutalvány-cikkek visszaküldésére vonatkozó sorok ajándékutalvány készpénzes kifizetési sorok legyenek.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source><bpt id="p1">**</bpt>Negative price<ept id="p1">**</ept> – Validates that there are no negative price transaction lines.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Negatív ár<ept id="p1">**</ept> – Ellenőrzi, hogy nincsenek negatív árt tartalmazó tranzakciós sorok.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">**</bpt>Item &amp; Variant<ept id="p1">**</ept> – Validates that items and variants on the transaction lines exist in the item and variant master file.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Cikk és változat<ept id="p1">**</ept> – Ellenőrzi, hogy a tranzakciós sorban szereplő cikkek és változatok léteznek a cikk és a változat törzsadatfájljában.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Set up the consistency checker</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Konzisztencia-ellenőrző beállítása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Configure the "Validate store transactions" batch process, at <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Retail IT <ph id="ph2">\&gt;</ph> POS posting<ept id="p1">**</ept>, for periodic runs.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Konfigurálja az „Üzleti tranzakciók ellenőrzése” kötegfolyamatot időszakos futás esetén a <bpt id="p1">**</bpt>Kiskereskedelem <ph id="ph1">\&gt;</ph> Kiskereskedelem IT <ph id="ph2">\&gt;</ph> pénztárfeladás<ept id="p1">**</ept> menüpontban.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kötegelt feladat az üzlet szervezeti hierarchiája alapján ütemezhető, hasonlóan a „Kimutatások kötegelt kiszámítása” és a „Kimutatások kötegelt feladása” folyamatok beállításához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Javasoljuk, hogy úgy konfigurálja ezt a kötegfolyamatot, hogy az naponta többször fusson, és úgy ütemezze, hogy minden P-feladat végrehajtása végén fusson.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Results of validation process</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ellenőrzési folyamat eredményei</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>The results of the validation check by the batch process are tagged on the appropriate retail transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kötegfolyamat által végzett ellenőrzés eredményeit a rendszer felcímkézi a megfelelő kiskereskedelmi tranzakcióra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The <bpt id="p1">**</bpt>Validation status<ept id="p1">**</ept> field on the retail transaction record is either set to <bpt id="p2">**</bpt>Successful<ept id="p2">**</ept> or <bpt id="p3">**</bpt>Error<ept id="p3">**</ept>, and the date of the last validation run appears on the <bpt id="p4">**</bpt>Last validation time<ept id="p4">**</ept> field.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kiskereskedelmi tranzakció rekordján található <bpt id="p1">**</bpt>Ellenőrzés állapota<ept id="p1">**</ept> mező vagy <bpt id="p2">**</bpt>Sikeres<ept id="p2">**</ept> vagy <bpt id="p3">**</bpt>Hiba<ept id="p3">**</ept> értékre van beállítva, és az utolsó ellenőrzés futásának dátuma a <bpt id="p4">**</bpt>Legutóbbi ellenőrzés időpontja<ept id="p4">**</ept> mezőben látható.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the <bpt id="p1">**</bpt>Validation errors<ept id="p1">**</ept> button.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha további, ellenőrzési hibához kapcsolódó leíróbb jellegű hibaüzenetet szeretne megtekinteni, válassza ki a megfelelő kiskereskedelmi üzlet tranzakciós rekordját, majd kattintson az <bpt id="p1">**</bpt>Ellenőrzési hibák<ept id="p1">**</ept> gombra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Azokat a tranzakciókat, amelyek nem feleltek meg az ellenőrzésen, valamint a még nem ellenőrzött tranzakciókat a rendszer nem szerepelteti a kimutatásokban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A „Kimutatás számítása” folyamat során a felhasználók értesítést kapnak, ha olyan tranzakciók találhatók, amelyeknek szerepelniük kellett volna a kimutatásban, de mégsem szerepeltek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>If a validation error is found, the only way to fix the error is to contact Microsoft Support.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha ellenőrzési probléma merül fel, a hiba javítása csak a Microsoft ügyfélszolgálata segítségével lehetséges.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In a future release, capability will be added so that users can fix the records that failed through the user interface.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A jövőbeli kiadások egyikében hozzáadásra kerül majd a lehetőség, amely segítségével a felhasználók maguk is kijavíthatják a rekordokat a felhasználói felületen, amelyek sikertelenek voltak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Logging and auditing capabilities will also be made available to trace the history of the modifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A később hozzáférhetővé váló naplózási és auditálási lehetőségek segítségével a módosítások előzményei is nyomon követhetők lesznek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Additional validation rules to support more scenarios will be added in a future release.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A jövőbeli kiadásokban olyan további ellenőrzési szabályokat adunk hozzá, amellyel még több eset ellenőrzése válik lehetővé.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>