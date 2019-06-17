<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="set-up-external-catalog-for-punchout.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>set-up-external-catalog-for-punchout.474d96.39baa331120d765543c3cf662ce53d2bcfe404ab.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>39baa331120d765543c3cf662ce53d2bcfe404ab</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>574d4dda83dcab94728a3d35fc53ee7e2b90feb0</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/22/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\supply-chain\procurement\set-up-external-catalog-for-punchout.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Set up an external catalog for PunchOut eProcurement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítson be külső katalógust a PunchOut e-beszerzés számára</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the use of an  external catalog or punchout catalog to collect quote information from a vendor and add it to a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a témakör egy külső katalógus (punchout-katalógus) használatát mutatja be, amelynek révén információt gyűjt egy szállítótól, hozzáadja egy igényléshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Set up an external catalog for PunchOut eProcurement</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítson be külső katalógust a PunchOut e-beszerzés számára</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>By using the external catalog, you can ensure that the product and price information that you subsequently process in Dynamics 365 for Finance and Operations July 2017 is accurate and up to date.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógus segítségével biztosítható, hogy a Dynamics 365 for Finance and Operations 2017. júliusi verziójában feldolgozott termék- és árinformációk pontosak és naprakészek legyenek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The requisition can then be approved and converted to a purchase order and an order can be placed at the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az igénylés ezután jóváhagyható és beszerzési rendeléssé alakítható át, valamint leadhat egy rendelést a szállítónál.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>When the external catalog is set up and an employee is preparing a requisition, there will be an option to redirect to an external site, the external catalog, and return the shopping basket that was created at the external site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Amikor a külső katalógus be van állítva, és egy alkalmazott egy igénylést készít elő, a rendszer felajánlja, hogy átirányítja egy külső webhelyre, egy külső katalógushoz, majd visszairányítja a külső webhelyen létrehozott bevásárlókosarat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>This communication is based on the cXML protocol and it has to be set up between the systems of the buying and the selling organization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a kommunikáció cXML-protokollon alapul, amelyet be kell állítani a vásárló és az értékesítő szervezetek rendszerei között.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>To set up the communication, your vendor has to provide pieces of information for you to use in the configuraiton of the external catalog such as Identity, domain of the buyers company, for example, "DUNS" and "DUNS number", credentials, and the URL to reach the vendors catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kommunikáció beállításához a szállítójának bizonyos információkat kell megadnia annak érdekében, hogy ezeket a külső katalógus konfigurációjában felhasználhassa, többek között a következőket: Azonosító, a vevő vállalatának tartománya, például a DUNS és a DUNS-szám, hitelesítő adatok, valamint a szállító katalógusának URL-címe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Setting up an external catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Külső katalógus beállítása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>The external catalog should enable an employee who enters a purchase requisition to be redirected to an external site to select products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógusnak lehetővé kell tennie, hogy a beszerzési igénylésbe belépő alkalmazottat átirányítsa egy külső webhelyre a termék kiválasztása érdekében.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The products that the employee selects from the external catalog are returned to Dynamics 365 for Finance and Operations with up-to-date price information and from here, they can be added to the purchase requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alkalmazott által a külső katalógusből kiválasztott termékeket a rendszer visszairányítja a Dynamics 365 for Finance and Operations rendszerébe naprakész árinformációkkal, és innen hozzáadhatók a beszerzési igényléshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The intention is not to enable employees to place an order on the external site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szándék nem az, hogy az alkalmazottak egy külső webhelyről rendelhessenek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>When setting up the external catalog, you need to make sure that the purpose of the site that can be accessed by the external catalog is to collect quote information and not to place a real order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógus beállításakor győződjön meg arról, hogy a külső katalógus által hozzáférhető webhely célja az információgyűjtés, nem pedig valódi megrendelés leadása.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>To set up an external vendor catalog, complete the following tasks:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Külső szállítói katalógus beállításához a következő feladatokat kell elvégeznie:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Set up a procurement category hierarchy.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Beszerzési kategóriahierarchia beállítása.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>For more information, see <bpt id="p1">[</bpt>Set up policies for procurement category hierarchies<ept id="p1">](tasks/set-up-policies-procurement-category-hierarchies.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">További információkért lásd: <bpt id="p1">[</bpt>Beszerzésikategória-hierarchiák irányelveinek beállítása<ept id="p1">](tasks/set-up-policies-procurement-category-hierarchies.md)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Register the vendor in Finance and Operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Regisztrálja a szállítót a Finance and Operations rendszerben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Before you can set up configurations to access an external vendor’s catalog, you must set up the vendor and the vendor contact in Microsoft Dynamics 365.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mielőtt beállíthatná a külső gyártó katalógusához szükséges konfigurációkat, be kell állítania a szállítót és a szállítói kapcsolattartót a Microsoft Dynamics 365 rendszerben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The external catalog’s vendor must also be added to the selected procurement category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógus szállítóját is hozzá kell adni a kiválasztott beszerzési kategóriához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For more information about registering vendors in Microsoft Dynamics 365, see <bpt id="p1">[</bpt>Manage vendor collaboration users<ept id="p1">](manage-vendor-collaboration-users.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállítók Microsoft Dynamics 365 rendszerben történő regisztrálásával kapcsolatos további tudnivalókat lásd: <bpt id="p1">[</bpt>Szállítói együttműködés felhasználóinak kezelése<ept id="p1">](manage-vendor-collaboration-users.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>For information about how to assign vendors to a procurement category, see <bpt id="p1">[</bpt>Approve vendors for specific procurement categories<ept id="p1">](tasks/approve-vendors-specific-procurement-categories.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállítónak a beszerzési kategóriához való hozzárendelésével kapcsolatos további tudnivalókat lásd: <bpt id="p1">[</bpt>Szállítók jóváhagyása konkrét beszerzési kategóriákra vonatkozóan<ept id="p1">](tasks/approve-vendors-specific-procurement-categories.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Make sure that the units of measure and the currency that the vendor uses are set up.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg arról, hogy a mértékegységek és a szállító által használt pénznem be van beállítva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>For information about how to create a unit of measure, see <bpt id="p1">[</bpt>Manage units of measure<ept id="p1">](../pim/tasks/manage-unit-measure.md)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A mértékegység létrehozásával kapcsolatos további tudnivalókat lásd: <bpt id="p1">[</bpt>Mértékegységek kezelése<ept id="p1">](../pim/tasks/manage-unit-measure.md)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Configure the external vendor catalog by using the requirements for your vendor’s external catalog site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítsa be a külső szállítói katalógust a szállító külső katalógusának webhelye által előírt követelmények használatával.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>For more details about this task, see <bpt id="p1">[</bpt>Configure the external vendor catalog<ept id="p1">](#configure-the-external-vendor-catalog)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A feladattal kapcsolatos további tudnivalókról lásd: <bpt id="p1">[</bpt>A külső szállítói katalógus konfigurálása<ept id="p1">](#configure-the-external-vendor-catalog)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Test the vendor’s external catalog configurations to verify that the settings are valid and that you can access the vendor’s external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tesztelje a szállító külső katalógusának konfigurációit, hogy biztosítsa a beállítások érvényességét, valamint hogy hozzáférhet a szállítói külső katalógushoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Use the <bpt id="p1">**</bpt>Validate settings<ept id="p1">**</ept> action to validate the request setup message that you’ve defined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Használja a <bpt id="p1">**</bpt>Beállítások ellenőrzése<ept id="p1">**</ept> műveletet az ön által beállított beállításkérési üzenet ellenőrzéséhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>This message should cause the vendors external catalog site to be opened in a browser window.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az üzenet következményeként a szállítók külső katalóguswebhelyének meg kell nyílnia egy böngészőablakban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>During validation, you can’t order items and services from the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az ellenőrzés során nem rendelhet cikkeket és szolgáltatásokat a szállítótól.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>To order items and services, you must access the vendor’s catalog from a purchase requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cikkek és szolgáltatások rendeléséhez egy beszerzési igénylésből kell hozzáférnie a szállítói katalógushoz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Activate the external catalog by using the <bpt id="p1">**</bpt>Activate catalog<ept id="p1">**</ept> button on the <bpt id="p2">**</bpt>External catalogs<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Aktiválja a külső katalógust a <bpt id="p1">**</bpt>Katalógus aktiválása<ept id="p1">**</ept> gombra kattintva a <bpt id="p2">**</bpt>Külső katalógusok<ept id="p2">**</ept> lapon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>The external catalog must be activated before employees can use it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógust aktiválni kell, mielőtt az alkalmazottak használni kezdenék.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>You can inactivate the external catalog at any time.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső katalógust bármikor inaktiválhatja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Configure the external vendor catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső szállítói katalógus konfigurálása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>This section gives more details about task 4 in the preceding section.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben a szakaszban további tájékoztatást talál az előző szakasz 4. feladatával kapcsolatban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Enter a name and description for the vendor’s external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Adjon egy nevet és leírást a szállító külső katalógusának.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The name that you enter will appear on the cart that represents the external catalog that is shown to employees who creates a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A beírt név megjelenik a külső katalógust jelölő bevásárlókocsiban, amely az igénylést létrehozó alkalmazottaknak megjelenik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Employees can click on the cart to open the catalog on the vendor’s external catalog site.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alkalmazottak kattinthatnak a bevásárlókocsira a katalógusnak a szállító külső katalóguswebhelyén történő megnyitásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Add an image by using the<bpt id="p1"> **</bpt>External catalog image<ept id="p1">**</ept> action.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Adjon hozzá képet a<bpt id="p1"> **</bpt>Külső katalógusbeli kép<ept id="p1">**</ept> művelettel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>The image will appear on the cart that represents the external catalog that is shown to employees who create a requisition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kép megjelenik a külső katalógust jelölő bevásárlókocsiban, amely az igénylést létrehozó alkalmazottaknak megjelenik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>Note that the image’s width and height must be equal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vegye figyelembe, hogy a kép szélességének és magasságának meg kell egyeznie.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Otherwise the image won’t be displayed correctly.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ellenkező esetben a kép nem megfelelően jelenik meg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Select whether the vendor’s external catalog website should appear in the same browser window as the one where the employee has created the requisition, or if it should open in a new window.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Válassza ki, hogy a szállító külső katalóguswebhelye ugyanabban a böngészőablak jelenjen-e meg, mint amelyikben az alkalmazott az igénylést létrehozta, vagy pedig új ablakban nyíljon meg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Select the vendor for the catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Válassza ki a katalógushoz tartozó szállítót.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In the <bpt id="p1">**</bpt>Legal entities<ept id="p1">**</ept> list, there is a row for each legal entity where the vendor is set up.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A <bpt id="p1">**</bpt>Jogi személyek<ept id="p1">**</ept> listában minden egyes jogi személyhez tartozik egy sor, ahol a szállító be van állítva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>To allow users to request products directly from the vendor’s catalog in some legal entities but not others, you can use the <bpt id="p1">**</bpt>Prevent access<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Allow access<ept id="p2">**</ept> button for each legal entity where you want the catalog to be or not to be available.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Annak érdekében, hogy a felhasználók csak bizonyos jogi személyek esetében igényelhessék közvetlenül a termékeket a szállítói katalógusból, másokban pedig nem, használhatja a <bpt id="p1">**</bpt>Hozzáférés megakadályozása<ept id="p1">**</ept> vagy a <bpt id="p2">**</bpt>Hozzáférés engedélyezése<ept id="p2">**</ept> gombot minden olyan jogi személy esetében, amelynél szeretné beállítani a katalógus elérhetőségét.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the <bpt id="p1">**</bpt>Default expiration (Days)<ept id="p1">**</ept> field, enter the number of days that a quotation received from the external catalog is valid and can be used to purchase from the external vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az <bpt id="p1">**</bpt>Alapértelmezett lejárat (nap)<ept id="p1">**</ept> mezőben adja meg azon napok számát, amíg a külső katalógusból kapott árajánlatok érvényesek és használhatók maradnak a külső szállítótól történő beszerzéshez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>When a quotation is created and retrieved from the vendor’s external catalog site, the quotation is valid as of the current system date and remains valid for the number of days that you enter in this field.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Amikor létrehoz és lekér egy árajánlatot a szállító külső katalóguswebhelyéről, az árajánlat az aktuális rendszerdátumtól kezdve az ebben a mezőben megadott számú napig marad érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Click the <bpt id="p1">**</bpt>Add<ept id="p1">**</ept> button to start mapping the procurement categories to the external catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kattintson a <bpt id="p1">**</bpt>Hozzáadás<ept id="p1">**</ept> gombra a beszerzési kategóriák külső katalógusnak történő megfeleltetésének elkezdéséhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source> Then, in the Category name list, select a category.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> Ezután a Kategória neve listából válasszon egy kategóriát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>The list of categories is a superset of procurement categories that the vendor has been mapped to in all the legal entities that are set up for the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kategóriák listája olyan beszerzési kategóriaszabvány, amelynek a szállítót megfeleltette a rendszer a szállítóhoz tartozó minden jogi személy esetében.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>Procurement policies are used to allow or restrict access to categories for the buying legal entity or receiving operating unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A beszerzési irányelvek segítségével engedélyezheti vagy korlátozhatja a vevő jogi személyre vagy a fogadó üzemi egységre vonatkozó kategóriák hozzáférhetőségét.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source> Punchout to an external catalog requires that access be allowed to at least one of the procurement categories that is mapped to the catalog.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> A külső katalógushoz történő kilépés megköveteli, hogy legalább egy olyan beszerzési kategóriához létezzen hozzáférési jogosultság, amely a katalógushoz van rendelve.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Set up the cXML setup request message that will be sent to the vendor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Állítsa be a szállítónak küldendő cXML beállításkérési üzenetet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>The automatically generated message format is the minimal template that is required in order to start a session.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az automatikusan generált üzenetformátum a munkamenet elindításához szükséges minimális sablon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Fill in values for the tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Töltse ki a címkék értékeit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>At any time, you can reload the system-generated message template by clicking <bpt id="p1">**</bpt>Restore message format<ept id="p1">**</ept>.<ph id="ph1"> </ph></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bármikor újra betöltheti be a rendszer által generált üzenetsablont az <bpt id="p1">**</bpt>Üzenetformátum visszaállítása lehetőségre<ept id="p1">**</ept> kattintva.<ph id="ph1"> </ph></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Note that if you restore the message format, the current message will be replaced by the automatically generated message format, which has empty tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vegye figyelembe, hogy az üzenetformátum visszaállításával az aktuális üzenetet az automatikusan generált üzenetformátum írja felül, amely üres címkéket tartalmaz.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>cXML setup message</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">cXML beállítási üzenet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Below you can find a description of the tags that are included in the template:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az alábbiakban megtalálja a sablonban szereplő címkék leírását:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Field</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mező</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Leírás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>&lt; Header &gt;&lt; From &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; From &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>The domain of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő vállalatának tartománya.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>&lt; Header &gt;&lt; From &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; From &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>The identity of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő vállalatának azonosítója.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>&lt; Header &gt;&lt; To &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; To &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>The domain of the vendor’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállító vállalatának tartománya.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>&lt; Header &gt;&lt; To &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; To &gt;&lt; Credential&gt;&lt; Identity &gt;&lt; /Identity&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>The identity of the vendor’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállító vállalatának azonosítója.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>The domain of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő vállalatának tartománya.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; Identity &gt;&lt; /Identity&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; Identity &gt;&lt; /Identity&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>The identity of the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő vállalatának azonosítója.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; SharedSecret &gt;&lt; /SharedSecret &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Header &gt;&lt; Sender &gt;&lt; Credential &gt;&lt; SharedSecret &gt;&lt; /SharedSecret &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>The shared secret for the buyer’s company.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A vevő vállalatának közös titkos kulcsa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>&lt; Request deploymentMode=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Request deploymentMode=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The test or production deployment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A teszt vagy az éles telepítés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>&lt; Request &gt;&lt; PunchOutSetupRequest &gt;&lt; SupplierSetup &gt;&lt; URL &gt;&lt; /URL&gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; Request &gt;&lt; PunchOutSetupRequest &gt;&lt; SupplierSetup &gt;&lt; URL &gt;&lt; /URL&gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>The URL of the vendor’s punchout endpoint.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szállító külső katalógus végpontjának URL-címe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Extrinsic elements</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Külső elemek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>An extrinsic element is additional information, such as a user name that is based on a user that punches out. The extrinsic element is set when the punchout occurs and it can be sent in the request setup message.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső elem további információt jelent, például egy olyan felhasználónév, amely a külső katalógust használó felhasználónak felel meg. A külső elem beállítása a külső katalógus használatakor történik, és elküldhető a beállításkérési üzenetben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Your vendor could have a requirement for receiving an extrinsic element in the setup request.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Megtörténhet, hogy a szállítónál követelmény áll fenn egy a beállítási kérelemben levő külső elem fogadása tekintetében.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>In that case, you should add the extrinsic element to the list of extrinsic elements in the <bpt id="p1">**</bpt>Message format<ept id="p1">**</ept> section of the <bpt id="p2">**</bpt>External catalog<ept id="p2">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ebben az esetben hozzá kell adni a külső elemet a külső elemek listájához az <bpt id="p1">**</bpt>Üzenetformátum<ept id="p1">**</ept> részben a <bpt id="p2">**</bpt>Külső katalógus<ept id="p2">**</ept> lapon.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Specify a name for the extrinsic element that the vendor can recognize and map it to a value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Olyan nevet adjon a külső elemnek, amelyet a szállító felismer, és meg tudja feleltetni egy értéknek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>The options for values are: User name, User email, or Random value.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">A lehetséges értékek a következők: Felhasználónév, Felhasználói e-mail vagy Véletlenszerű érték.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>For more information about the cXML protocol, see the <bpt id="p1">[</bpt>cXML.org website<ept id="p1">](http://cxml.org/)</ept>.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">A cXML-protokollal kapcsolatos további tudnivalókat lásd: <bpt id="p1">[</bpt>cXML.org website<ept id="p1">](http://cxml.org/)</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Post back message</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Visszajelzési üzenet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>The post back message is the message that is received from the vendor when the user checks out from the external site and returns to Finance and Operations.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">A visszajelzési üzenet a szállítótól kapott üzenet, amikor a felhasználó kilép a külső webhelyről, és visszatér a Finance and Operations rendszerbe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Post back messages can’t be configured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A visszajelzési üzenetek nem konfigurálhatók.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>The messages are based on the cXML protocol definition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az üzenetek a cXML-protokoll definícióján alapulnak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source> Here is the information that can be part of the post back message that is received on a requisition line:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"> Itt látható az a szöveg, amely az igénylési soron beérkező visszajelzési üzenet része lehet:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Message received from vendor</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szállítótól kapott üzenet</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Copied to requisition line in Finance and Operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Másolva a Finance and Operations rendszer igénylési sorába</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>&lt; ItemIn quantity=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemIn quantity=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Quantity</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mennyiség</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>&lt; ItemIn&gt;&lt; ItemID &gt;&lt; SupplierPartID &gt;&lt; /SupplierPartID &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemIn&gt;&lt; ItemID &gt;&lt; SupplierPartID &gt;&lt; /SupplierPartID &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>External item ID</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Külső cikkazonosító</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>&lt; ItemDetail&gt;&lt; UnitPrice &gt;&lt; Money currency=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail&gt;&lt; UnitPrice &gt;&lt; Money currency=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>Currency</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pénznem</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>&lt; ItemDetail &gt;&lt; UnitPrice &gt;&lt; Money &gt;&lt; /Money &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; UnitPrice &gt;&lt; Money &gt;&lt; /Money &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Unit price</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Egységár</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>&lt; ItemDetail &gt;&lt; Description ShortName=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Description ShortName=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Product name</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Termék neve</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>&lt; ItemDetail &gt;&lt; Description &gt;&lt; /Description &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Description &gt;&lt; /Description &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>Included in item description; Product name if ShortName is not specified.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szerepel a cikk leírásában; Termék neve, ha nincs megadva a ShortName.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>&lt; ItemDetail &gt;&lt; UnitOfMeasure &gt;&lt; /UnitOfMeasure &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; UnitOfMeasure &gt;&lt; /UnitOfMeasure &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Unit</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Egység</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>&lt; ItemDetail &gt;&lt; Classification &gt;&lt; /Classification &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Classification &gt;&lt; /Classification &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>Included in item description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szerepel a cikk leírásában</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>&lt; ItemDetail &gt;&lt; Classification domain=”” &gt;</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">&lt; ItemDetail &gt;&lt; Classification domain=”” &gt;</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Included in item description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szerepel a cikk leírásában</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>Delete an external catalog</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Külső katalógus törlése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Delete an external catalog with the Delete action on the page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Törölje a külső katalógust a lapon lévő Törlés művelettel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>If a product from the external vendor catalog has been requested, the external vendor catalog cannot be deleted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A külső szállítói katalógus nem törölhető, ha egy terméket kért a külső szállítói katalógusból.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Instead, the status of the external vendor catalog is set to inactive.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ehelyett a külső szállítói katalógus állapota inaktívra vált.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>If you want to remove access to the external vendor’s catalog site, but not delete it, change the external catalog status to Inactive.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha szeretné megszüntetni, de nem szeretné törölni a külső szállítói katalógus webhelyéhez való hozzáférést, állítsa a külső katalógus állapotát inaktívra.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>