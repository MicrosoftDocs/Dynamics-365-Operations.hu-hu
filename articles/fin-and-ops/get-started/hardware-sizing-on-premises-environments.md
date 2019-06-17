<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="hardware-sizing-on-premises-environments.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>hardware-sizing-on-premises-environments.e242d0.4832a056a99e0f7521e022982b7db7b16d7064a3.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4832a056a99e0f7521e022982b7db7b16d7064a3</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>574d4dda83dcab94728a3d35fc53ee7e2b90feb0</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/22/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\fin-and-ops\get-started\hardware-sizing-on-premises-environments.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Hardware sizing requirements for on-premises environments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hardverméretezési követelmények helyszíni környezetekben</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic lists the hardware sizing requirements for an on-premises environment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a témakör a hardverméretezési követelményekkel foglalkozik helyszíni környezetekben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Hardware sizing requirements for on-premises environments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Hardverméretezési követelmények helyszíni környezetekben</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Before you begin the hardware and infrastructure sizing process for an on-premises environment, familiarize yourself with the <bpt id="p1">[</bpt>System requirements<ept id="p1">](system-requirements.md)</ept> and <bpt id="p2">[</bpt>Setup and deployment instructions<ept id="p2">](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)</ept> to gain a solid understanding off the underlying infrastructure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mielőtt elkezdi a hardver és infrastruktúra helyszíni környezetekben való méretezésének folyamatát, ismerkedjen meg ezzel: <bpt id="p1">[</bpt>Rendszerkövetelmények<ept id="p1">](system-requirements.md)</ept> és ezzel: <bpt id="p2">[</bpt>Beállítási és telepítési útmutató<ept id="p2">](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md)</ept>, hogy kellőképpen ismerje a mögöttes infrastruktúrát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Pay close attention to the system setup best practices for optimum performance.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alaposan figyeljen oda a rendszerbeállítás ajánlott eljárásaira az optimális teljesítmény érdekében.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>After you have reviewed the documentation, you can start the process of estimating your transactional and concurrent user volume and sizing your environment based on the average core throughput.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A dokumentáció áttekintése után megkezdheti a tranzakciós és egyidejű felhasználói terjedelem becslését, illetve a környezet méretezését az átlagos processzormagonkénti teljesítmény alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Factors that affect sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A méretezést befolyásoló tényezők</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>All the factors shown in the following illustration contribute to sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A következő ábrán látható összes tényező befolyásolja a méretezést.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The more detailed information that is collected, the more precisely you can determine sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Minél részletesebb a begyűjtött információ, ön annál pontosabban tudja megállapítani a méretezést.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Hardware sizing, without supporting data, is likely to be inaccurate.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A támogató adatok nélküli hardverméretezés valószínűleg pontatlan.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The absolute minimum requirement for necessary data is the peak transaction line load per hour.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az abszolút minimális szükséges adat a tranzakció óránkénti sorsebesség-terhelés csúcspontja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Hardware sizing for on-premises environments<ept id="p1">](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">[</bpt><ph id="ph1">![</ph>Hardverméretezés helyszíni környezetekhez<ept id="p1">](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Viewed from left to right, the first and most important factor needed to accurately estimate sizing is a transaction profile or a transaction characterization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Balról jobbra haladva az első és az egyik legfontosabb tényező, ami a méretezés pontos becsléséhez szükséges, a tranzakció profil vagy a tranzakció jellemzés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>It's important to always find the peak transactional volume per hour.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fontos, hogy mindig megtalálja a tranzakciós terjedelem óránkénti csúcspontját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If there are multiple peak periods, then these periods need to be accurately defined.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ha több csúcspont időszak van, akkor ezeket az időszakokat pontosan meg kell határozni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>As you understand the load that impacts your infrastructure, you also need to understand more detail about these factors:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az infrastruktúrára hatással lévő terhelés megértése mellett ezeket a tényezőket is részletesen tanulmányoznia kell:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source><bpt id="p1">**</bpt>Transactions<ept id="p1">**</ept> – Typically transactions have certain peaks throughout the day/week.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Tranzakciók<ept id="p1">**</ept> – általában a tranzakciók egy adott csúcsponttal rendelkeznek, ami nem változik a nap/hét során.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>This mostly depends on the transaction type.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez elsősorban a tranzakció típusától függ.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Time and expense entries usually show peaks once per week, whereas Sales order entries often come in bulk via integration or trickle in during the day.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az idő- és kiadási tételek általában hetente egyszer érik el a csúcspontot, míg az értékesítési rendelési tételek gyakran tömegesen, integráció vagy szivárgás által érkeznek be a nap folyamán.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>Number of concurrent users<ept id="p1">**</ept> – The number of concurrent users is the second most important sizing factor.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Egyidejű felhasználók száma<ept id="p1">**</ept> – Az egyidejű felhasználók száma a második legfontosabb méretezési tényező.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>You cannot reliably get sizing estimates based on the number of concurrent users, so if this is the only data you have available, estimate an approximate number, and then revisit this when you have more data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az egyidejű felhasználók száma alapján nem juthat megbízható méretezési becslésekhez, így ha ez az egyetlen rendelkezésre álló adata, akkor becsüljön meg egy hozzávetőleges számot, és térjen vissza, ha további adatok is rendelkezésére állnak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>An accurate concurrent user definition means that:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Egy pontos egyidejű felhasználó definíció azt jelenti, hogy:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Named users are not concurrent users.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A névvel rendelkező felhasználók nem egyidejű felhasználók.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Concurrent users are always a subset of named users.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az egyidejű felhasználók mindig részhalmazai a névvel rendelkező felhasználóknak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Peak workload defines the maximum concurrency for sizing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A terhelés csúcspontja határozza meg a méretezésre vonatkozó maximális egyidejűséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Criteria for concurrent users is that the user meets all the following criteria:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Egy felhasználó akkor egyidejű felhasználó, ha megfelel a következő feltételeknek:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Logged on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bejelentkezett.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Working transactions/inquiries at the time of counting.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Működő tranzakciók/lekérdezések a leltározás idején.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Not an idle session.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nem tétlen állapotú munkamenet.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">**</bpt>Data composition<ept id="p1">**</ept> – This is mostly about how your system will be set up and configured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Adatok összetétele<ept id="p1">**</ept> – Ez elsősorban a rendszere beállításának és konfigurációjának módját jelenti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>For example, how many legal entities you will have, how many items, how many BOM levels, and how complex your security setup will be.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Például azt, hogy hány jogi személlyel, cikkel , és anyajegyzék-szinttel rendelkezik, illetve milyen összetettek a biztonsági beállítások.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Each of those factors may have a small impact on performance, so these factors can be offset by using smart choices when it comes to infrastructure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezen tényezők közül valamennyi kis hatással lehet a teljesítményre, így ezek kiegyenlítésére intelligens választási lehetőségek használata ajánlott az infrastruktúra esetén.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source><bpt id="p1">**</bpt>Extensions<ept id="p1">**</ept> – Customizations can be simple or complex.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Bővítmények<ept id="p1">**</ept> – A testreszabások egyszerűek vagy összetettek lehetnek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The number of customizations and the nature of complexity and usage has a varied impact on the size of the infrastructure needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A testreszabások száma, összetettsége és használati jellege különféle hatással vannak a szükséges infrastruktúra méretére.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>For complex customizations, it's advised to conduct performance evaluations to ensure that they are not only tested for efficiency but also help understand the infrastructure needs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Összetett testreszabások esetén teljesítményértékeléseket ajánlott végezni annak biztosítása érdekében, hogy azok nem csak hatékonyak, de az infrastruktúra szükségeinek megértésében is segítenek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>This is even more critical when the extensions are not coded according to best practices for performance and scalability.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez még inkább elengedhetetlen akkor, ha a bővítmények nem a teljesítményre és skálázhatóságra vonatkozó ajánlott eljárások alapján vannak kódolva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>Reporting and analytics<ept id="p1">**</ept> – These factors typically include running heavy queries against the various databases in the Finance and Operations database systems.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Jelentés és analitika<ept id="p1">**</ept> – Ezekhez a tényezőkhöz rendszerint a nehéz lekérdezések futtatása tartozik a Finance and Operations adatbázis rendszereken található adatbázisok számára.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Understanding and reducing the frequency when expensive reports run will help you understand the impact of them.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A gyakoriság megértése és csökkentése erőforrás-igényes jelentések futtatásakor segíthet önnek a hatásuk megértésében.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Third-party solutions<ept id="p1">**</ept> – These solutions, like ISVs, have the same implications and recommendations as extensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Harmadik felektől származó megoldások<ept id="p1">**</ept> – Ezek a megoldások, mint például az ISV-k, ugyanazokkal a következményekkel és ajánlásokkal rendelkeznek, mint a bővítmények.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Sizing your Finance and Operations environment</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az ön Finance and Operations környezetének méretezése</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>To understand your sizing requirements, you need to know the peak volume of transactions that you need to process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A méretezési követelmények megértése érdekében ismernie kell az ön által feldolgozandó tranzakciók terjedelmi csúcspontját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Most auxiliary systems, like Management Reporter or SSRS, are less mission critical.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A legtöbb kiegészítő rendszer, mint például a felügyeleti jelentéskészítő vagy az SSRS, kisebb létfontosságú.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>As a result, this document focuses mostly on AOS and SQL Server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Emiatt ez a dokumentum elsősorban az AOS-szel és az SQL Server-rel foglalkozik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In general, the compute tiers scale out and should be set up in an N+1 fashion, meaning if you estimate three AOS, add a fourth AOS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A számítási szintek általában felskálázódnak, és N+1 módon kell őket beállítani, ami azt jelenti, hogy ha három AOS-t becsült , akkor adjon hozzá egy negyedik AOS-t.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>The database tier should be set up in an Always On highly-available setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az adatbázis-szintet Always-On módban, magas rendelkezésre állással kell beállítani.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>SQL Server (OLTP)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SQL Server (OLTP)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Méretezés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>3K to 15K transaction lines per hour per core on DB server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">3000-15000 óránkénti tranzakciós sorsebesség processzormagonként az adatbázis-kiszolgálón.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Typical AOS-to-SQL core ratio 3:1 for the primary SQL Server.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A tipikus AOS-SQL processzormag arány az elsődleges SQL Server számára 3:1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Additional cores are required based on the chosen high availability configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szükség lehet további processzormagokra a választott magas rendelkezésre állású konfiguráció alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Processing database-heavy operations may regress this to 2:1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az adatbázisokra támaszkodó műveletek ezt 2:1 arányra csökkenthetik.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The following factors influence variations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A változatokat a következő tényezők befolyásolják:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Parameter settings in use.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A használt paraméter-beállítások.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>Levels of extensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Bővítmény szintek.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>Usage of additional functionality, such as database log and alerts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">További funkciók használata, mint például az adatbázisnapló és a figyelmeztetések.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Extreme database logging will further reduce throughput per hour per core below 3K lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az extrém adatbázis-naplózás tovább csökkenti a teljesítményt, óránként és processzormagonként 3000 alatti sorsebességre.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>Complexity of data composition – A simple chart of accounts versus a detailed fine-grained chart of accounts has implications on throughput (as an example).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Adatösszetétel összetettsége – Egy egyszerű számlatükör és egy részletes számlatükör különböző módon befolyásolják a teljesítményt (egy példaként).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Transaction characterization.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tranzakció jellemzése.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>2 GB to 16 GB memory for each core.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">2 GB-tól 16 GB-ig terjedő memória minden egyes processzormag számára.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Auxiliary databases on DB server such as Management reporter and SSRS databases.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kiegészítő adatbázisok az adatbázis-kiszolgálón, mint például a felügyeleti jelentéskészítő és az SSRS-adatbázisok.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>Temp DB = 15% of DB size, with as many files as physical processors.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ideiglenes adatbázis = az adatbázis méretének 15%-a, annyi fájllal, amennyi tényleges processzor van.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>SAN size and throughput based on total concurrent transaction volume/usage.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SAN mérete és teljesítménye a teljes egyidejű tranzakciós terjedelem/felhasználás alapján.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>High availability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Magas rendelkezésre állás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>We recommend always utilizing SQL Server in either a cluster or mirroring setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mindig ajánlott az SQL Server használata egy fürtben vagy egy tükrözött beállításban.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>The second SQL node should have the same number of cores as the primary node.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A második SQL-csomópontnak ugyanannyi processzormaggal kell rendelkeznie, mint az elsődleges csomópont.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Active Directory Federation Services (AD FS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Active Directory Federation Services (AD FS)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>For AD FS sizing, see the <bpt id="p1">[</bpt>AD FS Server Capacity documentation<ept id="p1">](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az AD FS méretezéséhez lásd: <bpt id="p1">[</bpt>AD FS kiszolgálói kapacitás dokumentáció<ept id="p1">](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>A <bpt id="p1">[</bpt>sizing spreadsheet<ept id="p1">](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)</ept> is available for planning the number of instances in your deployment.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elérhető egy <bpt id="p1">[</bpt>méretezési táblázat<ept id="p1">](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx)</ept> a telepítésében található példányok számának tervezéséhez.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>AOS (Online and batch)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">AOS (Online és kötegelt)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Sizing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Méretezés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Sizing by transaction volume/usage</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tranzakciós terjedelem/használat szerinti méretezés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>2K to 6K lines per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">2000-6000 sorsebesség processzormagonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>16 GB per instance</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">16 GB példányonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Standard box – 4 to 24 cores</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Szokásos mező – 4-24 processzormag</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>10 to 15 Enterprise users per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">10-15 vállalati felhasználó processzormagonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>15 to 25 Activity users per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">15-25 Activity felhasználó processzormagonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>25 to 50 Team members per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">25-50 csapattag processzormagonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Batch</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Köteg</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>1 to 4 batch threads per core</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">1–4 Kötegszál processzormagonként</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Size based on batch window characterization</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A kötegfeldolgozási ablak jellemzésétől függő méret</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Note that the AOS, Data Management, and Batch are on the same role in the Service Fabric.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ne feledje, hogy az AOS, az adatkezelő és a köteg ugyanahhoz a Service Fabric szerepkörhöz tartoznak.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>You need to size for these three workloads combined, and not separate these like in Microsoft Dynamics AX 2012.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezen három terhelést kombináltan méretezze, és ne válassza szét őket úgy, mint a Microsoft Dynamics AX 2012-ben.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>The same variability factors for SQL Server apply here.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ugyanazok az SQL Server változtathatósági tényezők érvényesek itt is.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>High availability</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Magas rendelkezésre állás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Ensure that you have at least 1 to 2 more AOS available than you estimate.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg róla, hogy legalább 1-2-vel több AOS érhető el, mint az ön becslése.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Ensure that you have at least 3 to 4 virtual hosts available.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg róla, hogy van legalább 3–4 elérhető virtuális állomása.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Management reporter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Felügyeleti Jelentéskészítő</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>In most cases, unless used extensively, the recommended minimum requirements using two nodes should work well.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A legtöbb esetben a két csomópontot használó ajánlott minimális követelmények betartása elég a működéshez,kivéve ha a használat kiterjedt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>Only in cases where there is heavy use will you need more than two nodes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Csak abban az esetben kell kettőnél több csomópont, ha a használat jelentős fokú.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Please scale as needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Kérjük, skálázzon szükség szerint.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>SQL Server Reporting Services</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">SQL Server Reporting Services szolgáltatás</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>For the general availability release, only one SSRS node can be deployed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az általános elérhetőségű verzió esetén csak egy SSRS-csomópontot lehet telepíteni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Monitor your SSRS node while testing and increase the number of cores available for SSRS on a need basis.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Figyelje az SSRS-csomópontját tesztelés közben, és szükség szerint emelje az SSRS számára elérhető processzormagok számát.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>Make sure that you have a preconfigured secondary node available on a virtual host that is different than the SSRS VM.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Győződjön meg arról, hogy rendelkezik a virtuális állomáson olyan előre konfigurált másodlagos csomóponttal, amely eltér az SSRS virtuális géptől.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>This is important if there is an issue with the virtual machine that hosts SSRS or the virtual host.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez akkor fontos, ha probléma van az SSRS-t tároló virtuális géppel vagy a virtuális állomással.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>If this the case, they would need to be replaced.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez esetben ki kellene őket cserélni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Environment Orchestrator</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Környezeti szervező</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>The Orchestrator service is the service that manages your deployment and the related communication with LCS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A szervező szolgáltatás kezeli az ön telepítését és az ehhez kapcsolódó LCS-szel való kommunikációt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>This service is deployed as the primary Service Fabric service and requires at least three VMs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a szolgáltatás az elsődleges Service Fabric szolgáltatásként van telepítve, és legalább három virtuális gépet igényel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>This service is co-located with the Service Fabric orchestration services.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ez a szolgáltatás egy helyen található a Service Fabric szervezési szolgáltatásokkal.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>This and should be sized to the peak load of the cluster.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ezt a fürt terhelési csúcspontja alapján kell méretezni.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>For more information, see <bpt id="p1">[</bpt>Service Fabric cluster capacity planning considerations<ept id="p1">](/azure/service-fabric/service-fabric-cluster-capacity)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">További információkért lásd: <bpt id="p1">[</bpt>Service Fabric fürt kapacitástervezési szempontok<ept id="p1">](/azure/service-fabric/service-fabric-cluster-capacity)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>Virtualization and oversubscription</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Virtualizáció és túljegyzés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Mission critical services like the AOS should be hosted on Virtual hosts that have dedicated resources – cores, memory, and disk.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Az olyan létfontosságú szolgáltatásokat, mint az AOS, dedikált erőforrásokkal rendelkező virtuális gépeken kell tárolni. Ilyen erőforrások a processzormagok, a memória, és a lemez.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>