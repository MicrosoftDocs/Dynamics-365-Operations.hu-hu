<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="trace-execution-er-troubleshoot-perf.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>trace-execution-er-troubleshoot-perf.773b92.aa71db2752889bc905c22bab1cf2fa46d7ee07c7.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>aa71db2752889bc905c22bab1cf2fa46d7ee07c7</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>67d00b95952faf0db580d341249d4e50be59119c</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\dev-itpro\analytics\trace-execution-er-troubleshoot-perf.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Trace execution of ER format to troubleshoot performance issues</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ER-formátum végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides information about how to use the performance trace feature in Electronic reporting (ER) to troubleshoot performance issues.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a témakör azt mutatja be, hogyan kell használni az Elektronikus jelentéskészítés (ER) teljesítményfigyelő funkcióját a teljesítménnyel kapcsolatos problémák elhárításához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Trace the execution of ER formats to troubleshoot performance issues</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match">Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárításához</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of Microsoft Dynamics 365 for Finance and Operations and enter it in the output that is generated.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az Elektronikus jelentéskészítés (ER) elektronikus dokumentumok létrehozására használatos konfigurációinak tervezési folyamatának részeként meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le a Microsoft Dynamics 365 for Finance and Operations szolgáltatásból, majd a létrehozott kimeneti fájlba illesztheti őket.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A ER teljesítmény-nyomonkövetési funkciója segítségével jelentősen csökkenthető az idő és költség, amely az ER-formátum végrehajtásához kapcsolódó részletes adatok gyűjtésére és az adatok teljesítményi problémák hibajavítására való felhasználására fordítandó.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>This tutorial provides guidelines about how to take performance traces for executed ER formats in Finance and Operations, and how to use the information from these traces to help improve performance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez az oktatóanyag bemutatja, hogy hogyan lehet elvégezni a teljesítmény nyomon követését a végrehajtott ER formátumokhoz a Finance and Operations modulban, valamint hogy hogyan lehet felhasználáni a nyomon követésből származó információkat a teljesítmény javítására.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Prerequisites</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Előfeltételek</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>To complete the examples in this tutorial, you must have the following access:</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">A jelen oktatóanyagban szereplő példák elvégzéséhez a következő hozzáférésekkel kell rendelkeznie:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Access to Finance and Operations for one of the following roles:</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Hozzáférés a Finance and Operations alkalmazáshoz a következő szerepkörök egyikével:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Electronic reporting developer</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elektronikus jelentések fejlesztője</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Electronic reporting functional consultant</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Elektronikus jelentések funkcióival foglalkozó konzulens</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>System administrator</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Rendszergazda</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as Finance and Operations, for one of the following roles:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Hozzáférés a Regulatory Configuration Service (RCS) példányához, amelyet ugyanarra a bérlőre telepítettek, mint a Finance and Operations szolgáltatást, a következő szerepkörök egyikéhez:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Electronic reporting developer</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Elektronikus jelentések fejlesztője</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Electronic reporting functional consultant</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Elektronikus jelentések funkcióival foglalkozó konzulens</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>System administrator</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Rendszergazda</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>You must also download and locally store the following files.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A következő fájlokat is le kell töltenie és helyben tárolnia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>File</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Fájl</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Content</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Tartalom</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Performance trace model.version.1</source><target logoport:matchpercent="0" state="translated">Teljesítmény-nyomonkövetési modell.verzió.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source><bpt id="p1">[</bpt>Sample ER data model configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="76" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt>Minta ER-adatmodell konfigurációja<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Performance trace metadata.version.1</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Teljesítmény-nyomonkövetési metaadat.verzió.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source><bpt id="p1">[</bpt>Sample ER metadata configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="76" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt>Minta ER-metaadat konfigurációja<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Performance trace mapping.version.1.1</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Teljesítmény-nyomonkövetési leképezés.verzió.1.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">[</bpt>Sample ER model mapping configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt>Minta ER-adatmodell leképezési konfigurációja<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Performance trace format.version.1.1</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">Teljesítmény-nyomonkövetési formátum.verzió.1.1</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source><bpt id="p1">[</bpt>Sample ER format configuration<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">[</bpt>Minta ER-formátum konfigurációja<ept id="p1">](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Configure ER parameters</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">ER-paraméterek konfigurálása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Each ER performance trace that is generated in Finance and Operations is stored as an attachment of the execution log record.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Minden egyes, a Finance and Operations szolgáltatásban létrehozott ER teljesítmény-nyomonkövetést a rendszer a végrehajtási naplórekord mellékleteként tárolja.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>The Document management (DM) framework of Finance and Operations is used to manage these attachments.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Finance and Operations szolgáltatás Dokumentumkezelés (DM) keretrendszerével kezelhetők ezek a mellékletek.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ER-paramétereket előre be kell állítania a teljesítmény-nyomkövetéshez használandó DM-dokumentumtípus meghatározásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>In Finance and Operation, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Finance and Operations modulban az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés<ept id="p1">**</ept> munkaterületen válassza az <bpt id="p2">**</bpt>Elektronikus jelentéskészítés paraméterei<ept id="p2">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Then, on the <bpt id="p1">**</bpt>Electronic reporting parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Attachments<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Others<ept id="p3">**</ept> field, select the DM document type to use for performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezután az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés paraméterei<ept id="p1">**</ept> oldalon, a <bpt id="p2">**</bpt>Mellékletek<ept id="p2">**</ept> lap <bpt id="p3">**</bpt>Egyéb<ept id="p3">**</ept> mezőjében válassza ki a teljesítmény-nyomkövetéshez használandó DM-dokumentum típusát.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Electronic reporting parameters page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Elektronikus jelentéskészítés paraméterei lap a Finance and Operations modulban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>To be available in the <bpt id="p1">**</bpt>Others<ept id="p1">**</ept> lookup field, a DM document type must be configured in the following manner on the <bpt id="p2">**</bpt>Document types<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Document management <ph id="ph2">\&gt;</ph> Document types<ept id="p3">**</ept>):</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ahhoz, hogy elérhető legyen az <bpt id="p1">**</bpt>Egyebek<ept id="p1">**</ept> keresési mezőben, a DM-dokumentumtípust a következő módon kell konfigurálni a <bpt id="p2">**</bpt>Dokumentumtípusok<ept id="p2">**</ept> oldalon (<bpt id="p3">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Dokumentumkezelés <ph id="ph2">\&gt;</ph>Dokumentumtípusok<ept id="p3">**</ept>):</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>Class:<ept id="p1">**</ept> Attach file</source><target logoport:matchpercent="66" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Osztály:<ept id="p1">**</ept> Fájl csatolása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>Group:<ept id="p1">**</ept> File</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Csoport:<ept id="p1">**</ept> Fájl</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Document types page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dokumentumtípusok oldal a Finance and Operations modulban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>The selected document type must be available in every company of the current Finance and Operations instance, because DM attachments are company-specific.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A kiválasztott dokumentumtípusnak az aktuális Finance and Operations-példány minden vállalatában elérhetőnek kell lennie, mivel a DM-mellékletek vállalatspecifikusak.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Configure RCS parameters</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">RCS-paraméterek konfigurálása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>ER performance traces that are generated in Finance and Operations will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Finance and Operations modulban létrehozott ER teljesítmény-nyomkövetéseket a rendszer elemzési célból az RCS szolgáltatásba importálja az ER-formátumtervező és az ER-leképezéstervező használatával.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Mivel a rendszer az ER teljesítmény-nyomkövetéseket az adott ER-formátumhoz kapcsolódó végrehajtási naplórekord mellékleteként tárolja, előre be kell állítania az RCS-paramétereket a teljesítmény-nyomkövetések csatolására használandó DM-dokumentumtípus meghatározása érdekében.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>In the instance of RCS that has been provisioned for your company, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A vállalat számára rendelkezésre bocsátott RCS-példányban, az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés<ept id="p1">**</ept> munkaterületen válassza az <bpt id="p2">**</bpt>Elektronikus jelentéskészítés paraméterei<ept id="p2">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Then, on the <bpt id="p1">**</bpt>Electronic reporting parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Attachments<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Others<ept id="p3">**</ept> field, select the DM document type to use for performance traces.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ezután az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés paraméterei<ept id="p1">**</ept> oldalon, a <bpt id="p2">**</bpt>Mellékletek<ept id="p2">**</ept> lap <bpt id="p3">**</bpt>Egyéb<ept id="p3">**</ept> mezőjében válassza ki a teljesítmény-nyomkövetéshez használandó DM-dokumentum típusát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Electronic reporting parameters page in RCS</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match">Elektronikus jelentéskészítés paraméterei lap az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>To be available in the <bpt id="p1">**</bpt>Others<ept id="p1">**</ept> lookup field, a DM document type must be configured in the following manner on the <bpt id="p2">**</bpt>Document types<ept id="p2">**</ept> page (<bpt id="p3">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Document management <ph id="ph2">\&gt;</ph> Document types<ept id="p3">**</ept>):</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ahhoz, hogy elérhető legyen az <bpt id="p1">**</bpt>Egyebek<ept id="p1">**</ept> keresési mezőben, a DM-dokumentumtípust a következő módon kell konfigurálni a <bpt id="p2">**</bpt>Dokumentumtípusok<ept id="p2">**</ept> oldalon (<bpt id="p3">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Dokumentumkezelés <ph id="ph2">\&gt;</ph>Dokumentumtípusok<ept id="p3">**</ept>):</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source><bpt id="p1">**</bpt>Class:<ept id="p1">**</ept> Attach file</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match"><bpt id="p1">**</bpt>Osztály:<ept id="p1">**</ept> Fájl csatolása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">**</bpt>Group:<ept id="p1">**</ept> File</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match"><bpt id="p1">**</bpt>Csoport:<ept id="p1">**</ept> Fájl</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Design an ER solution</source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match">ER-megoldás tervezése</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Tegyük fel, hogy egy új ER-megoldást tervez, amellyel szállítói tranzakciókat bemutató új jelentést hozhat létre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Currently, you can find the transactions for a selected vendor on the <bpt id="p1">**</bpt>Vendor transactions<ept id="p1">**</ept> page (go to <bpt id="p2">**</bpt>Account payable <ph id="ph1">\&gt;</ph> Vendors <ph id="ph2">\&gt;</ph> All vendors<ept id="p2">**</ept>, select a vendor, and then, on the Action Pane, on the <bpt id="p3">**</bpt>Vendor<ept id="p3">**</ept> tab, in the <bpt id="p4">**</bpt>Transactions<ept id="p4">**</ept> group, select <bpt id="p5">**</bpt>Transactions<ept id="p5">**</ept>).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Jelenleg a kiválasztott szállítóhoz tartozó tranzakciókat a <bpt id="p1">**</bpt>Szállítói tranzakciók<ept id="p1">**</ept> oldalon találja (lépjen a <bpt id="p2">**</bpt>Kötelezettségek <ph id="ph1">\&gt;</ph> Szállítók <ph id="ph2">\&gt;</ph> Minden szállító<ept id="p2">**</ept> pontra, válasszon a szállítók közül, majd a Műveleti ablaktábla <bpt id="p3">**</bpt>Szállító lapján<ept id="p3">**</ept>, a <bpt id="p4">**</bpt>Tranzakciók<ept id="p4">**</ept> csoportban válassza a <bpt id="p5">**</bpt>Tranzakciók<ept id="p5">**</ept> elemet).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>However, you want to have all vendor transaction at the same time in one electronic document in XML format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Önnek azonban az összes szállítói tranzakció megjelenítésére van szükség, ugyanabban a pillanatban, egyetlen elektronikus dokumentumban, XML formátumban.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a megoldás több olyan ER-konfigurációt is magában foglal, amelyek a szükséges adatmodell-, metaadat-, modell-hozzárendelési és formátum-összetevőket tartalmazzák.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Sign in to the instance of RCS that has been provisioned for your company.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Jelentkezzen be a vállalata részére biztosított RCS-példányba.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>In this tutorial, you will create and modify configurations for the <bpt id="p1">**</bpt>Litware, Inc.<ept id="p1">**</ept> sample company.</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match">Ebben az oktatóanyagban létrehozzuk és módosítjuk a konfigurációkat a <bpt id="p1">**</bpt>Litware, Inc.<ept id="p1">**</ept> mintavállalatra vonatkozóan.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Therefore, make sure that this configuration provider has been added to RCS and selected as active.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezért győződjön meg róla, hogy ezt a konfigurációszolgáltatót hozzáadták az RCS-szolgáltatáshoz, és aktívként kijelölték.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>For instructions, see the <bpt id="p1">[</bpt>Create configuration providers and mark them as active<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11)</ept> procedure.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">További útmutatásért tekintse át a <bpt id="p1">[</bpt>Konfigurációszolgáltatók létrehozása és megjelölése aktívként<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11)</ept> eljárást.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>In the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select the <bpt id="p2">**</bpt>Reporting configurations<ept id="p2">**</ept> tile.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés<ept id="p1">**</ept> munkaterületen válassza ki a <bpt id="p2">**</bpt>Jelentéskészítési konfiguráció<ept id="p2">**</ept> csempét.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> lapon importálja az előfeltételként az RCS-be letöltött ER-konfigurációkat, a következő sorrendben: adatmodell, metaadat, modell-hozzárendelés, formátum.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>For each configuration, follow these steps:</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">Minden konfiguráció esetén hajtsa végre az alábbi lépéseket:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Exchange <ph id="ph1">\&gt;</ph> Load from XML file<ept id="p1">**</ept>.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">A Műveleti ablaktáblában válassza az <bpt id="p1">**</bpt>Átváltás <ph id="ph1">\&gt;</ph> Betöltés XML-fájlból<ept id="p1">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Select <bpt id="p1">**</bpt>Browse<ept id="p1">**</ept> to select the appropriate file for the required ER configuration in XML format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Tallózás<ept id="p1">**</ept> gombra kattintva válassza ki a megfelelő, XML-formátumú fájlt a szükséges ER-konfigurációhoz.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza ki az <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Configurations page in RCS</source><target logoport:matchpercent="84" state="translated" state-qualifier="fuzzy-match">Konfigurációk oldal az RCS-ben</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Run the ER solution to trace execution</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ER-megoldás futtatása a végrehajtás nyomon követéséhez</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Assume that you've finished designing the first version of the ER solution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Tegyük fel, hogy befejezte az ER-megoldás első verziójának tervezését.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>You now want to test it in your Finance and Operations instance and analyze execution performance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezt követően tesztelni szeretné a Finance and Operations példányában, és elemezni a végrehajtás teljesítményét.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source><bpt id="p1">&lt;a id='import-configuration'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Import an ER configuration from RCS into Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">&lt;a id='import-configuration'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>ER-konfiguráció importálása az RCS szolgáltatásból a Finance and Operations modulba</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Sign in to your Finance and Operations instance.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Jelentkezzen be a Finance and Operations példányába.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your Finance and Operations instance (where you test and finally use them).</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ebben az oktatóanyagban konfigurációkat importálunk az RCS-példányból (ahol az ER-összetevőket tervezzük) a Finance and Operations-példányba (ahol teszteljük és használjuk majd őket).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Therefore, you must make sure that all the required artifacts have been prepared.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezért győződjön meg arról, hogy az összes szükséges műterméket előkészítette.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>For instructions, see the <bpt id="p1">[</bpt>Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)<ept id="p1">](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations)</ept> procedure.</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">További útmutatásért tekintse át az <bpt id="p1">[</bpt>Elektronikus jelentéskészítési (ER) konfigurációk importálása a Regulatory Configuration Service (RCS)<ept id="p1">](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations)</ept> eljárást.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Follow these steps to import the configurations from RCS into Finance and Operations:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A következő lépések végrehajtásával importálhatja a konfigurációkat az RCS szolgáltatásból a Finance and Operations modulba:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>In the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, on the tile for the <bpt id="p2">**</bpt>Litware, Inc.<ept id="p2">**</ept> configuration provider, select <bpt id="p3">**</bpt>Repositories<ept id="p3">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés<ept id="p1">**</ept> munkaterületen, a <bpt id="p2">**</bpt>Litware, Inc.<ept id="p2">**</ept> konfigurációszolgáltató csempéjén válassza ki a <bpt id="p3">**</bpt>Tárházak<ept id="p3">**</ept>elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>On the <bpt id="p1">**</bpt>Configuration repository<ept id="p1">**</ept> page, select the repository of the <bpt id="p2">**</bpt>RCS<ept id="p2">**</ept> type, and then select <bpt id="p3">**</bpt>Open<ept id="p3">**</ept>.</source><target logoport:matchpercent="73" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Konfigurációs tárházak<ept id="p1">**</ept> lapon válassza ki az <bpt id="p2">**</bpt>RCS<ept id="p2">**</ept> típusú tárházat, majd válassza a <bpt id="p3">**</bpt>Megnyitás<ept id="p3">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> FastTab, select the <bpt id="p2">**</bpt>Performance trace format<ept id="p2">**</ept> configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> gyorslapon válassza ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés formátuma<ept id="p2">**</ept> konfigurációt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>On the <bpt id="p1">**</bpt>Versions<ept id="p1">**</ept> FastTab, select version <bpt id="p2">**</bpt>1.1<ept id="p2">**</ept> of the selected configuration, and then select <bpt id="p3">**</bpt>Import<ept id="p3">**</ept>.</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Verziók<ept id="p1">**</ept> gyorslapon válassza ki a kiválasztott konfiguráció <bpt id="p2">**</bpt>1.1<ept id="p2">**</ept> verzióját, majd az <bpt id="p3">**</bpt>Importálás<ept id="p3">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Configuration repository page in Finance and Operations</source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match">Finance and Operations Konfigurációs tárházak oldala</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az adatmodell- és modell-hozzárendelési konfigurációk megfelelő verzióit a rendszer automatikusan importálja az importált ER-formátumkonfiguráció előfeltételeként.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Turn on the ER performance trace</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ER teljesítmény-nyomkövetésének bekapcsolása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">A Finance and Operations alkalmazásban nyissa meg a <bpt id="p1">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Elektronikus jelentéskészítés <ph id="ph2">\&gt;</ph> Konfigurációk<ept id="p1">**</ept> menüt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the Action Pane, on the <bpt id="p2">**</bpt>Configurations<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Advanced settings<ept id="p3">**</ept> group, select <bpt id="p4">**</bpt>User parameters<ept id="p4">**</ept>.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> oldal műveleti ablaktábláján, a <bpt id="p2">**</bpt>Konfigurációk<ept id="p2">**</ept> lapon, a <bpt id="p3">**</bpt>Speciális beállítások<ept id="p3">**</ept> csoportban válassza a <bpt id="p4">**</bpt>Felhasználói paraméterek<ept id="p4">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>In the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Execution tracing<ept id="p2">**</ept> section, follow these steps:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Felhasználói paraméterek<ept id="p1">**</ept> párbeszédablakban a <bpt id="p2">**</bpt>Végrehajtás nyomon követése<ept id="p2">**</ept> szakaszban kövesse az alábbi lépéseket:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>In the <bpt id="p1">**</bpt>Execution trace format<ept id="p1">**</ept> field, select <bpt id="p2">**</bpt>Debug trace format<ept id="p2">**</ept> to start to collect the details of ER format execution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Végrehajtási nyomkövetés formátuma<ept id="p1">**</ept> mezőben válassza a <bpt id="p2">**</bpt>Nyomkövetési formátum hibakeresése<ept id="p2">**</ept> elemet, amellyel megkezdheti az ER-formátum végrehajtásához tartozó adatok gyűjtését.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>When this value is selected, the performance trace will collect information about the time that is spent on the following actions:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha az érték ki van jelölve, akkor a teljesítmény-nyomkövetés adatokat gyűjt az időről, amelyet a következő műveletekre fordít:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Running each data source in the model mapping that is called to get data</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Minden adatforrás futtatása a modell-hozzárendelésben, amelyet az adatok lekéréséhez behív a rendszer</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Processing each format item to enter data in the output that is generated</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Minden egyes formátumelem feldolgozása a létrejövő kimeneti fájlba való adatbevitel érdekében</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>You use the <bpt id="p1">**</bpt>Execution trace format<ept id="p1">**</ept> field to specify the format of the generated performance trace that the execution details are stored in for ER format and mapping elements.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Végrehajtás nyomkövetésének formátuma<ept id="p1">**</ept> mező használatával meghatározhatja a létrejövő teljesítmény-nyomkövetés formátumát, amelyben a végrehajtás részleteit tárolják az ER-formátumhoz és leképezési elemekhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>By selecting <bpt id="p1">**</bpt>Debug trace format<ept id="p1">**</ept> as the value, you will be able to analyze the content of the trace in ER Operation designer, and see the ER format or mapping elements that are mentioned in the trace.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Hibakeresési nyomkövetés formátuma<ept id="p1">**</ept> értékként történő kiválasztásával lehetősége nyílik a nyomkövetés tartalmának elemzésére az ER Művelettervezőben, és megtekintheti a nyomkövetésben említett ER-formátum vagy leképezés elemeit.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Set the following options to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to collect specific details of the execution of the ER model mapping and ER format components:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha a következő beállításokat <bpt id="p1">**</bpt>Igen<ept id="p1">**</ept> értékre állítja, akkor specifikus adatokat gyűjthet az ER modell-hozzárendelés és az ER-formátum összetevőinek végrehajtásáról:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Collect query statistics<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect the following information:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Lekérdezési statisztikák gyűjtése<ept id="p1">**</ept> – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a következő adatokat fogja gyűjteni:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>The number of database calls that were made by data sources</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az adatforrások által végzett adatbázishívások száma</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The number of duplicate calls to the database</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">Az ismétlődő hívások száma az adatbázisban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Details of the SQL statements that were used to make database calls</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az SQL-utasítások részleteit, amelyekkel az adatbázishívásokat végezték</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source><bpt id="p1">**</bpt>Trace access of caching<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Gyorsítótárazás hozzáférésének nyomon követése<ept id="p1">**</ept> – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés adatokat gyűjt az ER modell-hozzárendelés gyorsítótár-használatáról.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source><bpt id="p1">**</bpt>Trace data access<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Nyomkövetési adatok hozzáférése<ept id="p1">**</ept> – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a rekordlista típusú végrehajtott adatforrásokhoz tartozó, adatbázisba intézett hívások számával kapcsolatos adatokat gyűjt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source><bpt id="p1">**</bpt>Trace list enumeration<ept id="p1">**</ept> – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Nyomkövetési lista felsorolása<ept id="p1">**</ept> – Ha ez a beállítás be van kapcsolva, a teljesítmény-nyomkövetés a rekordlista típusú végrehajtott adatforrásokból lekért rekordok számával kapcsolatos adatokat gyűjt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>The parameters in the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box are specific to the user and the current company.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Felhasználói paraméterek<ept id="p1">**</ept> párbeszédpanel paraméterei a felhasználóra és az aktuális vállalatra jellemzőek.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>User parameters dialog box in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A felhasználói paraméterek párbeszédpanel a Finance and Operations modulban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">&lt;a id='run-format'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Run the ER format</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">&lt;a id='run-format'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Az ER-formátum futtatása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>In Finance and Operations, select the <bpt id="p1">**</bpt>DEMF<ept id="p1">**</ept> company.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A Finance and Operations szolgáltatásban válassza a <bpt id="p1">**</bpt>DEMF<ept id="p1">**</ept> vállalatot.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Nyissa meg a következőt: <bpt id="p1">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Elektronikus jelentéskészítés <ph id="ph2">\&gt;</ph> Konfigurációk<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, select the <bpt id="p2">**</bpt>Performance trace format<ept id="p2">**</ept> item.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> oldalon található konfigurációs fában válassza ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés formátuma<ept id="p2">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Run<ept id="p1">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A Műveleti ablaktáblán kattintson a <bpt id="p1">**</bpt>Futtatás<ept id="p1">**</ept> elemre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Notice that the file that is generated presents information about 265 transactions for six vendors.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Figyelje meg, hogy a létrejövő forrásfájl hat szállító 265 tranzakcióját jeleníti meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>Review the execution trace</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A végrehajtás nyomkövetésének áttekintése</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source><bpt id="p1">&lt;a id='export-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Export the generated trace from Finance and Operations</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">&lt;a id='export-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>A létrejövő nyomkövetés exportálása Finance and Operations szolgáltatásból</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A teljesítmény-nyomkövetéseket leválaszthatja az ER forrásformátumából, és szerializálhatja egy külső zip-fájlba.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configuration debug logs<ept id="p1">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A Finance and Operations alkalmazásban nyissa meg a <bpt id="p1">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Elektronikus jelentéskészítés <ph id="ph2">\&gt;</ph> Konfigurációk hibakeresési naplói<ept id="p1">**</ept> menüt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Electronic reporting run logs<ept id="p1">**</ept> page, in the left pane, in the <bpt id="p2">**</bpt>Configuration name<ept id="p2">**</ept> field, select <bpt id="p3">**</bpt>Performance trace format<ept id="p3">**</ept> to find the log records that have been generated by the execution of the <bpt id="p4">**</bpt>Performance trace format<ept id="p4">**</ept> configuration.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés futtatási naplói<ept id="p1">**</ept> oldalon a bal oldali panelen, a <bpt id="p2">**</bpt>Konfiguráció neve<ept id="p2">**</ept> mezőben válassza a <bpt id="p3">**</bpt>Teljesítmény-nyomkövetés formátuma<ept id="p3">**</ept> lehetőséget, amellyel megtalálhatja a <bpt id="p4">**</bpt>Teljesítmény-nyomkövetés formátuma<ept id="p4">**</ept> végrehajtásával létrehozott naplórekordokat.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Select the <bpt id="p1">**</bpt>Attachments<ept id="p1">**</ept> button (the paper clip symbol) in the upper-right corner of the page, or press <bpt id="p2">**</bpt>Ctrl+Shift+A<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Válassza a <bpt id="p1">**</bpt>Mellékletek<ept id="p1">**</ept> gombot (kapocs jel) az oldal jobb felső sarkában, vagy nyomja meg a <bpt id="p2">**</bpt>Ctrl+Shift+A<ept id="p2">**</ept> billentyűkombinációt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Attachments button on the Electronic reporting run logs page in Finance and Operations</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Mellékletek gomb az Elektronikus jelentéskészítés futtatási naplói oldalon a Finance and Operations szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>On the <bpt id="p1">**</bpt>Attachments for Electronic reporting run logs<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Open<ept id="p2">**</ept> to get the performance trace as a zip file and store it locally.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés futtatási naplói – Mellékletek<ept id="p1">**</ept> oldalon a Műveleti ablaktáblán válassza a <bpt id="p2">**</bpt>Megnyitás<ept id="p2">**</ept> lehetőséget a teljesítmény-nyomkövetés zip-fájlként való lehívásához és helyi tárolásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Attachments for Electronic reporting run logs page in Finance and Operations</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Mellékletek az Elektronikus jelentéskészítés futtatási naplói oldalhoz a Finance and Operations szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The trace that is generated has a reference to the source ER report via a unique report identifier in <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept> format only.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A létrehozott nyomkövetés referenciával rendelkezik a kiindulási ER-jelentésre egy egyedi, csak <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept> formátumban létező jelentésazonosítón keresztül.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>The version numbering of the format isn't considered.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A formátum verziószámát a rendszer nem veszi figyelembe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Megfigyelhető, hogy végrehajtott ER-formátumhoz létrehozott teljesítmény-nyomkövetés és az ER-modell-hozzárendelés közti társítás a használt gyökérszintű leírón és a közös adatmodellen alapul.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>The version numbering of the format and model mapping isn't considered.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">A formátum és a modell-hozzárendelés verziószámát a rendszer nem veszi figyelembe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>The setting of the <bpt id="p1">**</bpt>Default for model mapping<ept id="p1">**</ept> flag for the model mapping also isn't considered.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Alapértelmezett a modell-hozzárendeléshez<ept id="p1">**</ept> jelölő modell-hozzárendeléshez tartozó beállítását szintén figyelmen kívül hagyja.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source><bpt id="p1">&lt;a id='import-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Import the generated trace into RCS</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">&lt;a id='import-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>A létrejövő nyomkövetés importálása az RCS szolgáltatásba</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>In RCS, in the <bpt id="p1">**</bpt>Electronic reporting<ept id="p1">**</ept> workspace, select the <bpt id="p2">**</bpt>Reporting configurations<ept id="p2">**</ept> tile.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match">Az RCS szolgáltatásban az <bpt id="p1">**</bpt>Elektronikus jelentéskészítés<ept id="p1">**</ept> munkaterületen válassza ki a <bpt id="p2">**</bpt>Jelentéskészítési konfiguráció<ept id="p2">**</ept> csempét.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, expand the <bpt id="p2">**</bpt>Performance trace model<ept id="p2">**</ept> item, and select the <bpt id="p3">**</bpt>Performance trace format<ept id="p3">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> lapon található konfigurációs fában bontsa ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetési modell<ept id="p2">**</ept> elemet, és válassza a <bpt id="p3">**</bpt>Teljesítmény-nyomkövetés formátuma<ept id="p3">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">A Műveleti ablaktáblán kattintson a <bpt id="p1">**</bpt>Tervező<ept id="p1">**</ept> elemre.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>On the <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Formátumtervező<ept id="p1">**</ept> lapon a Műveleti ablaktáblában válassza ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés<ept id="p2">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>In the <bpt id="p1">**</bpt>Performance trace result settings<ept id="p1">**</ept> dialog box, select <bpt id="p2">**</bpt>Import performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Teljesítmény-nyomkövetési eredmény beállításai<ept id="p1">**</ept> párbeszédpanelen válassza a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés importálása<ept id="p2">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Select <bpt id="p1">**</bpt>Browse<ept id="p1">**</ept> to select the zip file that you exported from Finance and Operations earlier.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Tallózás<ept id="p1">**</ept> gombra kattintva kiválaszthatja azt a zip-fájlt, amelyet korábban exportált a Finance and Operations modulból.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza ki az <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Performance trace result settings dialog box in RCS</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A teljesítmény-nyomkövetési eredmények beállításai párbeszédpanel az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>Use the performance trace for analysis in RCS – Format execution</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Formátum-végrehajtás</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>In RCS, on the <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page, select <bpt id="p2">**</bpt>Expand/collapse<ept id="p2">**</ept> to expand the content of all format items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az RCS szolgáltatás <bpt id="p1">**</bpt>Formátumtervező<ept id="p1">**</ept> lapján válassza a <bpt id="p2">**</bpt>Kibontás/összecsukás<ept id="p2">**</ept> elemre az összes formátumelem tartalmának kibontásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>Notice that additional information is shown for some items of the current format:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Megfigyelheti, hogy az aktuális formátum bizonyos elemeinél további információk is megjelennek:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>The actual time that was spent entering data in the generated output by using the format item</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az adatok a létrejövő kimeneti fájlba történő bevitelére fordított tényleges idő a formátumelem használatával</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>The same time expressed as a percentage of the total time that was spent generating the whole output</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ugyanez az időtartam a teljes kimeneti fájl létrehozására fordított összes idő százalékaként kifejezve</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>Format designer page in RCS</source><target logoport:matchpercent="84" state="translated" state-qualifier="fuzzy-match">Formátumtervező oldal az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>Close <bpt id="p1">**</bpt>Format designer<ept id="p1">**</ept> page.</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Zárja be a <bpt id="p1">**</bpt>Formátumtervező<ept id="p1">**</ept> lapot.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source><bpt id="p1">&lt;a id='use-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>Use the performance trace for analysis in RCS – Model mapping</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">&lt;a id='use-trace'&gt;</bpt><ept id="p1">&lt;/a&gt;</ept>A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>In RCS, on the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, in the configuration tree, select the <bpt id="p2">**</bpt>Performance trace mapping<ept id="p2">**</ept> item.</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">Az RCS szolgáltatásban a <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> oldalon található konfigurációs fában válassza ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés hozzárendelése<ept id="p2">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>On the Action Pane, select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="85" state="translated" state-qualifier="leveraged-inherited">A Műveleti ablaktáblán kattintson a <bpt id="p1">**</bpt>Tervező<ept id="p1">**</ept> elemre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>Select <bpt id="p1">**</bpt>Designer<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza a <bpt id="p1">**</bpt>Tervező<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>On the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page, on the Action Pane, select <bpt id="p2">**</bpt>Performance trace<ept id="p2">**</ept>.</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Modell-hozzárendelési tervező<ept id="p1">**</ept> lapon a Műveleti ablaktáblában válassza ki a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés<ept id="p2">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>Select the trace that you imported earlier.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Válassza ki a korábban importált nyomkövetést.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza ki az <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>Notice that new information becomes available for some data source items of the current model mapping:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Megfigyelheti, hogy az aktuális modell-hozzárendelés bizonyos adatforráselemeihez új információk jelennek meg:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>The actual time that was spent getting data by using the data source</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az adatforrás által az adatok lekérésére fordított tényleges idő</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>The same time expressed as a percentage of the total time that was spent running the whole model mapping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ugyanez az időtartam a teljes modell-hozzárendelés lefuttatására fordított összes idő százalékaként kifejezve</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum data source is run.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Megfigyelheti, hogy az ER tájékoztatja Önt arról, hogy az aktuális modell-hozzárendelés megkettőzi az adatbázis-kérelmeket a VendTable/<ph id="ph1">\&lt;</ph>Kapcsolatok/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum adatforrás futása során.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ez az ismétlődés azért fordul elő, mert a szállítói tranzakciók listájának lekérése minden ismétlődő szállítói rekordnál két alkalommal történik:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>One call is made to enter details of each transaction in the data model, based on configured bindings.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az egyik lehívás annak érdekében történik, hogy az egyes tranzakciók részleteit bevigyék az adatmodellbe a konfigurált kötések alapján.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>One call is made to enter the calculated number of transactions per vendor in the data model.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Egy lehívás pedig annak érdekében történik, hogy a szállítónkénti tranzakciók kiszámított mennyiségét bevigyék az adatmodellbe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Message about duplicate database requests on the Model mapping designer page in RCS</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ismétlődő adatbázis-kérelmekkel kapcsolatos üzenet a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:530<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum data source.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:530<ph id="ph2">\]</ph><ept id="p1">**</ept> érték azt jelzi, hogy a VendTrans táblát a rendszer 530 alkalommal hívta le annak érdekében, hogy egy rekordot visszaadjon az adott táblából a VendTable/<ph id="ph3">\&lt;</ph>Kapcsolatok/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum adatforrásba.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>530<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the VendTable/<ph id="ph3">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az <bpt id="p1">**</bpt><ph id="ph1">\[</ph>530<ph id="ph2">\]</ph><ept id="p1">**</ept> érték azt jelzik, hogy a VendTable/<ph id="ph3">\&lt;</ph>Kapcsolatok/VendTrans.VendTable<ph id="ph4">\_</ph>AccountNum adatforrást 530 alkalommal hívta le a rendszer annak érdekében, hogy egy rekordot visszaadjon az adott adatforrásból, és az ebből származó részletes adatokat bevigye az adatmodellbe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>We recommend that you use caching for the VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Javasoljuk a gyorsítótárazás használatát a VendTable/<ph id="ph1">\&lt;</ph>Relations/VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum adatforráshoz a lehívások számának csökkentése érdekében, amelyek a 265 tranzakció adatainak lehívásához szükséges, valamint a modell-hozzzárendelés teljesítményének javítása érdekében.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A LedgerTransTypeList-adatforrásra vonatkozó lehívások számának csökkentéséhez is hasznos lehet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>This data source is used to associate each value of the <bpt id="p1">**</bpt>LedgerTransType<ept id="p1">**</ept> enumeration with its label.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ezzel az adatforrással lehetséges a <bpt id="p1">**</bpt>LedgerTransType<ept id="p1">**</ept> felsorolás minden egyes értékének saját címkéjéhez társítása.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az adatforrás használatával megkeresheti a megfelelő címkét, és megadhatja az egyes szállítói tranzakciókhoz tartozó adatmodellben.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>The current number of calls to this data source (9,027) is quite high for 265 transactions.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az adatforráshoz intézett lehívások jelenlegi száma (9027) elég magas a 265 tranzakcióra vonatkoztatva.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>Model mapping designer page in RCS, showing 9,027 calls to the data source</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Modell-hozzárendelési tervező lapja az RCS szolgáltatásban, amely 9027 lehívást jelez az adatforráshoz</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>Improve the model mapping based on information from the execution trace</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A modell-hozzárendelés javítása a végrehajtási nyomkövetésből származó információk alapján</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>Modify the logic of the model mapping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A modell-hozzárendelés logikájának módosítása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>Follow these steps to use caching, to help prevent duplicate calls to the database:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Hajtsa végre a következő lépéseket a gyorsítótárazás használatához az adatbázishoz intézett ismétlődő hívások megakadályozása érdekében:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>In RCS, on the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page, in the <bpt id="p2">**</bpt>Data sources<ept id="p2">**</ept> pane, select the <bpt id="p3">**</bpt>VendTable<ept id="p3">**</ept> item.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az RCS <bpt id="p1">**</bpt>Modell-hozzárendelési tervező<ept id="p1">**</ept> oldalán az <bpt id="p2">**</bpt>Adatforrások<ept id="p2">**</ept> panelen válassza ki a <bpt id="p3">**</bpt>VendTable<ept id="p3">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Válassza a <bpt id="p1">**</bpt>Gyorsítótárazás<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Expand the <bpt id="p1">**</bpt>VendTable<ept id="p1">**</ept> item, expand the list of one-to-many relations for the VendTable data source (the <bpt id="p2">**</bpt><ph id="ph1">\&lt;</ph>Relations<ept id="p2">**</ept> item), and select the <bpt id="p3">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p3">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Bontsa ki a <bpt id="p1">**</bpt>VendTable<ept id="p1">**</ept> elemet, bontsa ki a VendTable adatforráshoz tartozó egy a többhöz kapcsolatos listáját (a <bpt id="p2">**</bpt><ph id="ph1">\&lt;</ph>Kapcsolatok<ept id="p2">**</ept> elemet), és válassza a <bpt id="p3">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p3">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Válassza a <bpt id="p1">**</bpt>Gyorsítótárazás<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Caching setup to help prevent duplicate calls</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Gyorsítótár-beállítás az ismétlődő lehívások megelőzése érdekében</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Hajtsa végre az alábbi lépéseket, hogy a LedgerTransTypeList-adatforrás a VendTable-adatforrás hatókörébe kerüljön:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>In the <bpt id="p1">**</bpt>Data source types<ept id="p1">**</ept> pane, expand the <bpt id="p2">**</bpt>Functions<ept id="p2">**</ept> item, and select the <bpt id="p3">**</bpt>Calculated field<ept id="p3">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Adatforrástípusok<ept id="p1">**</ept> panelen bontsa ki a <bpt id="p2">**</bpt>Funkciók<ept id="p2">**</ept> elemet, és válassza a <bpt id="p3">**</bpt>Számított mező<ept id="p3">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>In the <bpt id="p1">**</bpt>Data sources<ept id="p1">**</ept> pane, select the <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Adatforrások<ept id="p1">**</ept> panelen válassza a <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>Select <bpt id="p1">**</bpt>Add<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza a <bpt id="p1">**</bpt>Hozzáadás<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>In the <bpt id="p1">**</bpt>Name<ept id="p1">**</ept> field, enter <bpt id="p2">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p2">**</ept>.</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Név<ept id="p1">**</ept> mezőbe írja be a <bpt id="p2">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p2">**</ept> szót.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Select <bpt id="p1">**</bpt>Edit formula<ept id="p1">**</ept>.</source><target logoport:matchpercent="66" state="translated" state-qualifier="fuzzy-match">Válassza a <bpt id="p1">**</bpt>Képlet szerkesztése<ept id="p1">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, enter <bpt id="p2">**</bpt>LedgerTransTypeList<ept id="p2">**</ept>.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Képlet<ept id="p1">**</ept> mezőbe írja be a következőt: <bpt id="p2">**</bpt>LedgerTransTypeList<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza a <bpt id="p1">**</bpt>Mentés<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>Close the <bpt id="p1">**</bpt>Formula editor<ept id="p1">**</ept> page.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Zárja be a <bpt id="p1">**</bpt>Képletszerkesztő<ept id="p1">**</ept> lapot.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>Click <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Kattintson az <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> gombra.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Follow these steps to do caching of the <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> field:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Hajtsa végre a következő lépéseket a <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> mező gyorsítótárazásának végrehajtásához:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>Select the <bpt id="p1">**</bpt>LedgerTransTypeList<ept id="p1">**</ept> item.</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Válassza ki a <bpt id="p1">**</bpt>LedgerTransTypeList<ept id="p1">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Válassza a <bpt id="p1">**</bpt>Gyorsítótárazás<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>Select the <bpt id="p1">**</bpt>VendTable.<ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Válassza ki a <bpt id="p1">**</bpt>a VendTable.<ph id="ph1">\$</ph>TransType<ept id="p1">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source>Select <bpt id="p1">**</bpt>Cache<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Válassza a <bpt id="p1">**</bpt>Gyorsítótárazás<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>Caching setup for the $TransType field</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A $TransType mező gyorsítótárazásának beállítása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>Follow these steps to change the <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransTypeRecord<ept id="p1">**</ept> field so that it starts to use the cached <bpt id="p2">**</bpt><ph id="ph2">\$</ph>TransType<ept id="p2">**</ept> field:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Hajtsa végre az alábbi lépéseket a <bpt id="p1">**</bpt><ph id="ph1">\$</ph>TransTypeRecord<ept id="p1">**</ept> mező módosításához, hogy az a gyorsítótárazott <bpt id="p2">**</bpt><ph id="ph2">\$</ph>TransType<ept id="p2">**</ept> mezőt használja:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>In the <bpt id="p1">**</bpt>Data sources<ept id="p1">**</ept> pane, expand the <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> item, expand the <bpt id="p3">**</bpt><ph id="ph1">\&lt;</ph>Relations<ept id="p3">**</ept> item, expand the <bpt id="p4">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p4">**</ept> item, and select the <bpt id="p5">**</bpt>VendTable. VendTrans.VendTable<ph id="ph3">\_</ph>AccountNum.<ph id="ph4">\$</ph>TransTypeRecord<ept id="p5">**</ept> item.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Adatforrások<ept id="p1">**</ept> panelen bontsa ki a <bpt id="p2">**</bpt>VendTable<ept id="p2">**</ept> elemet, bontsa ki a <bpt id="p3">**</bpt><ph id="ph1">\&lt;</ph>Kapcsolatok<ept id="p3">**</ept> elemet, bontsa ki a <bpt id="p4">**</bpt>VendTrans.VendTable<ph id="ph2">\_</ph>AccountNum<ept id="p4">**</ept> elemet, majd válassza a <bpt id="p5">**</bpt>VendTable. VendTrans.VendTable<ph id="ph3">\_</ph>AccountNum.<ph id="ph4">\$</ph>TransTypeRecord<ept id="p5">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>Select <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza ki a <bpt id="p1">**</bpt>Szerkesztés<ept id="p1">**</ept> opciót.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>Select <bpt id="p1">**</bpt>Edit formula<ept id="p1">**</ept>.</source><target logoport:matchpercent="100" state="translated" state-qualifier="exact-match">Válassza a <bpt id="p1">**</bpt>Képlet szerkesztése<ept id="p1">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, find the following expression:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Képlet<ept id="p1">**</ept> mezőben keresse meg a következő kifejezést:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = <ph id="ph1">\@</ph>.TransType))</source><target logoport:matchpercent="0" state="translated">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = <ph id="ph1">\@</ph>.TransType))</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>In the <bpt id="p1">**</bpt>Formula<ept id="p1">**</ept> field, enter the following expression:</source><target logoport:matchpercent="86" state="translated" state-qualifier="fuzzy-match">A <bpt id="p1">**</bpt>Képlet<ept id="p1">**</ept> mezőben adja meg a következő kifejezést:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source>FIRSTORNULL (WHERE (VendTable.'<ph id="ph1">\$</ph>TransType', VendTable.'<ph id="ph2">\$</ph>TransType'.Enum = <ph id="ph3">\@</ph>.TransType)).</source><target logoport:matchpercent="0" state="translated">FIRSTORNULL (WHERE (VendTable.'<ph id="ph1">\$</ph>TransType', VendTable.'<ph id="ph2">\$</ph>TransType'.Enum = <ph id="ph3">\@</ph>.TransType)).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="291">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza a <bpt id="p1">**</bpt>Mentés<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="292">
          <source>Close the <bpt id="p1">**</bpt>Formula editor<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Zárja be a <bpt id="p1">**</bpt>Képletszerkesztő<ept id="p1">**</ept> lapot.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="293">
          <source>Select <bpt id="p1">**</bpt>OK<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza ki az <bpt id="p1">**</bpt>OK<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="294">
          <source>Select <bpt id="p1">**</bpt>Save<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Válassza a <bpt id="p1">**</bpt>Mentés<ept id="p1">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="295">
          <source>Close the <bpt id="p1">**</bpt>Model mapping designer<ept id="p1">**</ept> page.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">Zárja be a <bpt id="p1">**</bpt>Modell-hozzárendelési tervező<ept id="p1">**</ept> lapot.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="296">
          <source>Close the <bpt id="p1">**</bpt>Model mappings<ept id="p1">**</ept> page.</source><target logoport:matchpercent="73" state="translated" state-qualifier="fuzzy-match">Zárja be a <bpt id="p1">**</bpt>Modell-hozzárendelések<ept id="p1">**</ept> lapot.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="297">
          <source>Complete the modified version of the ER model mapping</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az ER-modell-hozzárendelés módosított verziójának elvégzése</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="298">
          <source>In RCS, on the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Versions<ept id="p2">**</ept> FastTab, select version <bpt id="p3">**</bpt>1.2<ept id="p3">**</ept> of the <bpt id="p4">**</bpt>Performance trace mapping<ept id="p4">**</ept> configuration.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az RCS <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> lapjának <bpt id="p2">**</bpt>Verziók<ept id="p2">**</ept> gyorslapján válassza ki az <bpt id="p3">**</bpt>1.2<ept id="p3">**</ept>-es verziót a <bpt id="p4">**</bpt>Teljesítmény-nyomkövetés<ept id="p4">**</ept> konfigurációhoz.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="299">
          <source>Select <bpt id="p1">**</bpt>Change status<ept id="p1">**</ept>.</source><target logoport:matchpercent="66" state="translated" state-qualifier="fuzzy-match">Válassza az <bpt id="p1">**</bpt>Állapot módosítása<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="300">
          <source>Select <bpt id="p1">**</bpt>Complete<ept id="p1">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Válassza a <bpt id="p1">**</bpt>Kész<ept id="p1">**</ept> lehetőséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="301">
          <source>Import the modified ER model mapping configuration from RCS into Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A módosított ER-modell-hozzárendelési konfiguráció importálása az RCS szolgáltatásból a Finance and Operations modulba</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="302">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Import an ER configuration from RCS into Finance and Operations<ept id="p1">](#import-configuration)</ept> section earlier in this topic to import version 1.2 of the <bpt id="p2">**</bpt>Performance trace mapping<ept id="p2">**</ept> configuration into Finance and Operations.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>ER-konfiguráció importálása az RCS szolgáltatásból a Finance and Operations modulba<ept id="p1">](#import-configuration)</ept> című szakasz lépéseit a <bpt id="p2">**</bpt>Teljesítmény-nyomkövetés hozzárendelése<ept id="p2">**</ept> konfiguráció 1.2-es verziójának Finance and Operations modulba történő importálásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="303">
          <source>Run the modified ER solution to trace execution</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A módosított ER-megoldás futtatása a végrehajtás nyomon követéséhez</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="304">
          <source>Run the ER format</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Az ER-formátum futtatása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="305">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Run the ER format<ept id="p1">](#run-format)</ept> section earlier in this topic to generate a new performance trace.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>ER-formátum futtatása<ept id="p1">](#run-format)</ept> szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="306">
          <source>Review the execution trace</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">A végrehajtás nyomkövetésének áttekintése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="307">
          <source>Export the generated trace from Finance and Operations</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A létrejövő nyomkövetés exportálása Finance and Operations szolgáltatásból</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="308">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Export the generated trace from Finance and Operations<ept id="p1">](#export-trace)</ept> section earlier in this topic to save a new performance trace locally.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>A létrejövő nyomkövetés exportálása Finance and Operations szolgáltatásból<ept id="p1">](#export-trace)</ept> szakasz lépéseit az új teljesítmény-nyomkövetés helyi mentéséhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="309">
          <source>Import the generated trace into RCS</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A létrejövő nyomkövetés importálása az RCS szolgáltatásba</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="310">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Import the generated trace into RCS<ept id="p1">](#import-trace)</ept> section earlier in this topic to import the new performance trace into RCS.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>A létrejövő nyomkövetés importálása az RCS szolgáltatásba<ept id="p1">](#import-trace)</ept> szakasz lépéseit az új teljesítmény-nyomkövetés RCS szolgáltatásba történő importálásához.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="311">
          <source>Use the performance trace for analysis in RCS – Model mapping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="312">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Use the performance trace for analysis in RCS – Model mapping<ept id="p1">](#use-trace)</ept> section earlier in this topic to analyze the latest performance trace.</source><target logoport:matchpercent="60" state="translated" state-qualifier="fuzzy-match">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>AA teljesítmény-nyomkövetés alkalmazása elemzési célokra az RCS szolgáltatásban – Modell-hozzárendelés<ept id="p1">](#use-trace)</ept> című szakasz lépéseit a legutóbbi teljesítmény-nyomkövetés elemzéséhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="313">
          <source>Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Megfigyelheti, hogy az Ön által a modell-hozzárendelésen végzett kiigazításokkal megszüntette az adatbázisba intézett ismétlődő lekérdezéseket.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="314">
          <source>The number of calls to database tables and data sources for this model mapping has been also reduced.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az adott modellhozzárendeléshez tartozó, adatbázistáblákba és adatforrásokba küldött lehívások száma is csökkent.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="315">
          <source>Therefore, the performance of the whole ER solution has improved.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezáltal a teljes ER-megoldás teljesítménye javult.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="316">
          <source>Trace information for the VendTable data source on the Model mapping designer page in RCS</source><target logoport:matchpercent="74" state="translated" state-qualifier="fuzzy-match">A VendTable adatforrás információinak nyomon követése a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="317">
          <source>In the trace information, the value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>12<ph id="ph2">\]</ph><ept id="p1">**</ept> for the VendTable data source indicates that this data source was called 12 times.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A nyomkövetési adatok között szereplő <bpt id="p1">**</bpt><ph id="ph1">\[</ph>12<ph id="ph2">\]</ph><ept id="p1">**</ept> érték azt jelzi, hogy az adatforrást 12 alkalommal hívták le.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="318">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:6<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that six calls were translated to database calls to the VendTable table.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt><ph id="ph1">\[</ph>Q:6<ph id="ph2">\]</ph><ept id="p1">**</ept> érték azt jelzi, hogy hat hívást fordított le a rendszer a VendTable táblába irányuló adatbázishívásként.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="319">
          <source>The value <bpt id="p1">**</bpt><ph id="ph1">\[</ph>C:6<ph id="ph2">\]</ph><ept id="p1">**</ept> indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt><ph id="ph1">\[</ph>C:6<ph id="ph2">\]</ph><ept id="p1">**</ept> érték azt jelzik, hogy az adatbázisból lehívott rekordokat gyorsítótárazták, és 6 további hívást a gyorsítótár használatával dolgoztak fel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="320">
          <source>Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Megfigyelheti, hogy a LedgerTransTypeList adatforrásba indított hívások száma 9027-ről 240-re csökkent.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="321">
          <source>Trace information for the LedgerTransTypeList data source on the Model mapping designer page in RCS</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">A LedgerTransTypeList adatforrás információinak nyomon követése a Modell-hozzárendelési tervező oldalon az RCS szolgáltatásban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="322">
          <source>Review the execution trace in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A végrehajtás nyomon követésének áttekintése a Finance and Operations modulban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="323">
          <source>In addition to RCS, some versions of Finance and Operations might offer capabilities for an ER framework designer experience.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az RCS szolgáltatás mellett a Finance and Operations egyes verziói is kínálhatnak ER-keretrendszer tervezői élményére vonatkozó lehetőségeket.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="324">
          <source>These versions of Finance and Operations have an <bpt id="p1">**</bpt>Enable design mode<ept id="p1">**</ept> option that can be turned on.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A Finance and Operations ezen verziói rendelkeznek a <bpt id="p1">**</bpt>Tervezői mód engedélyezése<ept id="p1">**</ept> lehetőséggel, amelyet be lehet kapcsolni.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="325">
          <source>You can find this option on the <bpt id="p1">**</bpt>General<ept id="p1">**</ept> tab of the <bpt id="p2">**</bpt>Electronic reporting parameters<ept id="p2">**</ept> page, which you can open from the <bpt id="p3">**</bpt>Electronic reporting<ept id="p3">**</ept> workspace.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a beállítás az <bpt id="p2">**</bpt>Elektronikus jelentéskészítés paraméterei<ept id="p2">**</ept> oldal <bpt id="p1">**</bpt>Általános<ept id="p1">**</ept> lapján található, amelyet az <bpt id="p3">**</bpt>Elektronikus jelentéskészítés<ept id="p3">**</ept> munkaterületről nyithat meg.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="326">
          <source>Enable design mode option on the Electronic reporting parameters page in Finance and Operations</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A tervezői mód lehetőség engedélyezése az Elektronikus jelentéskészítés paraméterei oldalon a Finance and Operations modulban</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="327">
          <source>If you use one of these versions of Finance and Operations, you can analyze the details of generated performance traces directly in Finance and Operations.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha a Finance and Operations ezen verzióinak egyikét használja, akkor közvetlenül a Finance and Operations modulban elemezheti a létrehozott teljesítmény-nyomkövetés részleteit.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="328">
          <source>You don't have to export them from Finance and Operation and import them into RCS.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezeket nem kell exportálnia a Finance and Operations modulból, és importálnia az RCS szolgáltatásba.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="329">
          <source>Review the execution trace by using external tools</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A végrehajtási nyomkövetés áttekintése külső eszközök használatával</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="330">
          <source>Configure user parameters</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Felhasználói paraméterek konfigurálása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="331">
          <source>In Finance and Operations, go to <bpt id="p1">**</bpt>Organization administration <ph id="ph1">\&gt;</ph> Electronic reporting <ph id="ph2">\&gt;</ph> Configurations<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="72" state="translated" state-qualifier="leveraged-inherited">A Finance and Operations alkalmazásban nyissa meg a <bpt id="p1">**</bpt>Szervezeti adminisztráció <ph id="ph1">\&gt;</ph> Elektronikus jelentéskészítés <ph id="ph2">\&gt;</ph> Konfigurációk<ept id="p1">**</ept> menüt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="332">
          <source>On the <bpt id="p1">**</bpt>Configurations<ept id="p1">**</ept> page, on the Action Pane, on the <bpt id="p2">**</bpt>Configurations<ept id="p2">**</ept> tab, in the <bpt id="p3">**</bpt>Advanced settings<ept id="p3">**</ept> group, select <bpt id="p4">**</bpt>User parameters<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="72" state="translated" state-qualifier="leveraged-inherited">A <bpt id="p1">**</bpt>Konfigurációk<ept id="p1">**</ept> oldal műveleti ablaktábláján, a <bpt id="p2">**</bpt>Konfigurációk<ept id="p2">**</ept> lapon, a <bpt id="p3">**</bpt>Speciális beállítások<ept id="p3">**</ept> csoportban válassza a <bpt id="p4">**</bpt>Felhasználói paraméterek<ept id="p4">**</ept> lehetőséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="333">
          <source>In the <bpt id="p1">**</bpt>User parameters<ept id="p1">**</ept> dialog box, in the <bpt id="p2">**</bpt>Execution tracing<ept id="p2">**</ept> section, in the <bpt id="p3">**</bpt>Execution trace format<ept id="p3">**</ept> field, select <bpt id="p4">**</bpt>PerfView XML<ept id="p4">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A <bpt id="p1">**</bpt>Felhasználói paraméterek<ept id="p1">**</ept> párbeszédpanel <bpt id="p2">**</bpt>Végrehajtás nyomkövetése<ept id="p2">**</ept> szakaszának <bpt id="p3">**</bpt>Végrehajtási nyomkövetés formátuma<ept id="p3">**</ept> mezőjében válassza a <bpt id="p4">**</bpt>PerfView XML<ept id="p4">**</ept> elemet.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="334">
          <source>Run the ER format</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Az ER-formátum futtatása</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="335">
          <source>Repeat the steps in the <bpt id="p1">[</bpt>Run the ER format<ept id="p1">](#run-format)</ept> section earlier in this topic to generate a new performance trace.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Ismételje meg a jelen témakörben korábban ismertetett, <bpt id="p1">[</bpt>ER-formátum futtatása<ept id="p1">](#run-format)</ept> szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="336">
          <source>Notice that the web browser offers a zip file for download.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Megfigyelheti, hogy az internetböngésző felajánlja a zip-fájl letöltését.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="337">
          <source>This file contains the performance trace in PerfView format.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ez a fájl a teljesítmény-nyomkövetést PerfView formátumban tartalmazza.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="338">
          <source>You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ezután használhatja a PerfView teljesítményelemzési eszközt az ER-formátum végrehajtás részleteinek elemzésére.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>