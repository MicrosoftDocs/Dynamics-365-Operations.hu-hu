<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="cost.md" target-language="hu-HU">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>cost.4e88df.80e7a033467c3d94d55f06daa05f99bd27e19a29.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>80e7a033467c3d94d55f06daa05f99bd27e19a29</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\cost.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Cost configuration for distributed order management (DOM)</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A felosztott rendeléskezelés (DOM) költségkonfigurációja</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes cost configuration for the distributed order management (DOM) functionality in Microsoft Dynamics 365 for Retail.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ez a témakör a Microsoft Dynamics 365 for Retail felosztott rendeléskezelés (DOM) funkciójára vonatkozó költségkonfigurációt részletezi.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Cost configuration for distributed order management (DOM)</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">A felosztott rendeléskezelés (DOM) költségkonfigurációja</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A szervezeteknek számos költségösszetevőt kell figyelembe venniük annak meghatározására, hogy melyik a rendelés teljesítésének szempontjából optimális helyszín.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Some of these cost components are shipping cost, handling cost, and packaging cost.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ezen költségösszetevők közé tartozik például a szállítási költség, a kezelési költség és a csomagolási költség.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>A combination of these costs is calculated to determine the fulfillment location.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ezeknek a költségeknek a kombinációját ki kell számítani a teljesítési helyszín meghatározása céljából.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>When the first iteration of distributed order management (DOM) in Microsoft Dynamics 365 for Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A Microsoft Dynamics 365 for Retail szolgáltatásban a felosztott rendeléskezelés (DOM) első ismétlésekor sor került a megrendelések teljesítési helyszínekhez való hozzárendelésének optimalizálására, a rendszer csak a távolságot vette figyelembe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Although distance can be correlated with cost, it isn't the same as cost.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ugyan a távolság korrelálható a költséggel, ez nem egyezik meg a költséggel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Például egy 24 órán belüli szállítási módszer többe kerül, mint a háromnapos szállítás vagy a hétnapos szállítás ugyanakkora távolságra.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A költségkonfiguráció funkció segítségével a kiskereskedők meghatározhatják és konfigurálhatják a további költségösszetevőket, amelyeket az rendelési sorok teljesítése céljából optimális helyszín meghatározása céljából ki kell számítani és figyelembe kell venni.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ha be van állítva a költségösszetevők konfigurálása, a DOM-feloldó csak ezeket a költségmeghatározásokat használja a rendelés teljesítése szempontjából optimális helyszín meghatározásakor.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>It doesn't consider the distance component as a cost.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Nem veszi figyelembe a távolság-összetevőt költségként.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Azonban ha nincs beállítva a költségösszetevők konfigurálása, a DOM-feloldó használja a távolság-összetevőt költségként a rendelés teljesítése szempontjából optimális helyszín meghatározásakor.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Set up cost components</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Költségösszetevők beállítása</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Two major cost component types can be defined in the system: <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Other<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">A rendszerben két fő költségösszetevő-típus határozható meg: <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Egyéb<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Both cost component types support multiple calculation bases, as shown in the following table.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Mindkét típusú költségösszetevő több számítási alapot is támogat, ahogy az alábbi táblázatban látható.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Cost component type</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Költségösszetevő típusa</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Calculation basis</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Számítás alapja</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Shipping</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Szállítás</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Simple</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Egyszerű</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Tiered</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Rétegzett</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Other</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Egyéb</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Sales order</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Értékesítési rendelés</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Sales line</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Értékesítési sor</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Location</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Helyszín</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Shipping cost component type</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Szállítási költségösszetevő típusa</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>This section explains how to set up each combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and a calculation basis for shipping costs.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Ez a szakasz bemutatja, hogy hogyan lehet beállítani a <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> költségösszetevő-típus és a számítási alap egyes kombinációit a szállítási költségekhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>It also explains how the DOM solver uses each combination.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Cost component type = Shipping and Calculation basis = Simple</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Költségösszetevő típusa = Szállítási és Számítási alap = Egyszerű</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>If a combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Simple<ept id="p2">**</ept> calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha a <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> költségösszetevő-típus és az <bpt id="p2">**</bpt>Egyszerű<ept id="p2">**</ept> számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>You must set up the following fields for this combination:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ehhez a kombinációhoz a következő mezőket kell beállítani:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Költségtényező<ept id="p1">**</ept> – Adja meg a költségtényező egyedi azonosítóját.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source><target logoport:matchpercent="78" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Leírás<ept id="p1">**</ept> – Adja meg a költségtényező nevét és leírását.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Kezdő dátum<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Záró dátum<ept id="p2">**</ept> – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Aktív<ept id="p1">**</ept> – Azt jelzi, hogy a költségtényező aktív-e.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>Company<ept id="p1">**</ept> – Specify the legal entity that the cost factor is configured for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Vállalat<ept id="p1">**</ept> – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>All lines of the calculation criteria must be for the same legal entity.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source><bpt id="p1">**</bpt>Modes of delivery<ept id="p1">**</ept> – Specify the modes of delivery that the cost is configured for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Szállítási módok<ept id="p1">**</ept> – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source><bpt id="p1">**</bpt>Calculation type<ept id="p1">**</ept> – Specify how the cost should be calculated for a specific mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Számítási típus<ept id="p1">**</ept> – Adja meg a költség számításának módját egy megadott szállítási mód esetén.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Two calculation types are supported:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A szolgáltatásban két számítási típus támogatott:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source><bpt id="p1">**</bpt>Fixed<ept id="p1">**</ept> – A flat cost is used for the mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Rögzített<ept id="p1">**</ept> – Állandó költség, amely az adott szállítási módhoz használatos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>If you select this calculation type, the <bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> field defines the flat cost.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha ezt a számítási típust választja, akkor a <bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> mező adja meg az állandó költséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source><bpt id="p1">**</bpt>Per-distance unit<ept id="p1">**</ept> – The cost for the mode of delivery is calculated as the cost value that is specified in the <bpt id="p2">**</bpt>Cost<ept id="p2">**</ept> field times the distance between the delivery address and the locations.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Távolságegység szerint<ept id="p1">**</ept> – A szállítási mód költségét a rendszer úgy számítja ki, hogy a <bpt id="p2">**</bpt>Költség<ept id="p2">**</ept> mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value that is used in conjunction with the <bpt id="p2">**</bpt>Calculation type<ept id="p2">**</ept> field to compute the cost for a mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> – Megadja a <bpt id="p2">**</bpt>Számítási típus<ept id="p2">**</ept> mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Cost component type = Shipping and Calculation basis = Tiered</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Költségösszetevő típusa = Szállítási és Számítási alap = Rétegzett</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>If a combination of the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Tiered<ept id="p2">**</ept> calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</source><target logoport:matchpercent="95" state="translated" state-qualifier="fuzzy-match">Ha a <bpt id="p1">**</bpt>Szállítási<ept id="p1">**</ept> költségösszetevő-típus és a <bpt id="p2">**</bpt>Rétegzett<ept id="p2">**</ept> számítási alap kombinációját alkalmazzák, akkor a szállítási módhoz tartozó szállítási költség egy állandó költségen vagy távolságon alapul.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>However, in this combination, the distance is based on a tiered range of distances.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ebben a kombinációban a távolság több távolság rétegzett tartományán alapul.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ehhez a kombinációhoz a következő mezőket kell beállítani:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Költségtényező<ept id="p1">**</ept> – Adja meg a költségtényező egyedi azonosítóját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Leírás<ept id="p1">**</ept> – Adja meg a költségtényező nevét és leírását.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source><bpt id="p1">**</bpt>Default cost<ept id="p1">**</ept> – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Alapértelmezett költség<ept id="p1">**</ept> – Adja meg a szállítási módhoz használt költséget, ha a szállítási cím és a helyszín közti távolság nem esik a szállítási módhoz meghatározott rétegzett távolságok egyikébe sem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Kezdő dátum<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Záró dátum<ept id="p2">**</ept> – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktív<ept id="p1">**</ept> – Azt jelzi, hogy a költségtényező aktív-e.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source><bpt id="p1">**</bpt>Company<ept id="p1">**</ept> – Specify the legal entity that the cost factor is configured for.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Vállalat<ept id="p1">**</ept> – Adja meg azt a jogi személyt, amelyre vonatkozóan konfigurálja a költségtényezőt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>All lines of the calculation criteria must be for the same legal entity.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A számítási feltétel minden sorának ugyanarra a jogi személyre kell vonatkoznia.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">**</bpt>Modes of delivery<ept id="p1">**</ept> – Specify the modes of delivery that the cost is configured for.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Szállítási módok<ept id="p1">**</ept> – Adja meg azokat a szállítási módokat, amelyhez kapcsolódóan konfigurálja a költséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source><bpt id="p1">**</bpt>Distance type<ept id="p1">**</ept> – Specify whether the tiered distance definition is an aerial distance or a road distance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Távolság típusa<ept id="p1">**</ept> – Adja meg, hogy a rétegzett távolság meghatározása légi vagy közúti távolságra utal-e.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">**</bpt>Distance units<ept id="p1">**</ept> – Specify the unit that the tiered distance is measured in.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Távolságegységek<ept id="p1">**</ept> – Adja meg az egységet, amelyben a rétegzett távolság mérése történjen.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source><bpt id="p1">**</bpt>Distance from<ept id="p1">**</ept> – Specify the start range for the tiered distance.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Távolság – alsó határ<ept id="p1">**</ept> – Adja meg a rétegzett távolság tartományának alsó határát.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source><bpt id="p1">**</bpt>Distance to<ept id="p1">**</ept> – Specify the end range for the tiered distance.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Távolság – felső határ<ept id="p1">**</ept> – Adja meg a rétegzett távolság tartományának felső határát.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source><bpt id="p1">**</bpt>Calculation type<ept id="p1">**</ept> – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Számítási típus<ept id="p1">**</ept> – Adja meg a költség számításának módját egy megadott szállítási mód és rétegzett távolság esetén.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Two calculation types are supported:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A szolgáltatásban két számítási típus támogatott:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source><bpt id="p1">**</bpt>Fixed<ept id="p1">**</ept> – A flat cost is used for the mode of delivery.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Rögzített<ept id="p1">**</ept> – Állandó költség, amely az adott szállítási módhoz használatos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>If you select this calculation type, the <bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> field defines the flat cost.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ha ezt a számítási típust választja, akkor a <bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> mező adja meg az állandó költséget.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source><bpt id="p1">**</bpt>Per distance unit<ept id="p1">**</ept> – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the <bpt id="p2">**</bpt>Cost<ept id="p2">**</ept> field times the distance between the delivery address and the locations.</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Távolságegység szerint<ept id="p1">**</ept> – A szállítási mód és a rétegzett távolság költségét a rendszer úgy számítja ki, hogy a <bpt id="p2">**</bpt>Költség<ept id="p2">**</ept> mezőben megadott költségértéket megszorozza a szállítási cím és a helyszínek közti távolsággal.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value that is used in conjunction with the <bpt id="p2">**</bpt>Calculation type<ept id="p2">**</ept> field to compute the cost for a mode of delivery.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> – Megadja a <bpt id="p2">**</bpt>Számítási típus<ept id="p2">**</ept> mezővel kapcsolatban használt költségértéket, amellyel kiszámítható a szállítási mód költsége.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>When you define tiered distances, the system validates that there are no missing or overlapping distances.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A rétegzett távolságok meghatározása során a rendszer ellenőrzi, hogy nincsenek-e hiányzó vagy egymást átfedő távolságok.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>The distance type that is used for a mode of delivery must be the same across all the tiered distances.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A szállítási módhoz használt távolságtípusnak az összes rétegzett távolság esetén meg kell egyeznie.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Other cost component type</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Egyéb költségösszetevő-típus</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>This section explains how to set up each combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and an other cost type for non-shipping costs.</source><target logoport:matchpercent="80" state="translated" state-qualifier="fuzzy-match">Ez a szakasz bemutatja, hogy hogyan lehet beállítani az <bpt id="p1">**</bpt>Egyéb<ept id="p1">**</ept> költségösszetevő-típus és az egyéb költségtípus egyes kombinációit a nem szállítási költségekhez.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>It also explains how the DOM solver uses each combination.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Bemutatja azt is, hogy a DOM-feloldó miként alkalmazza az egyes kombinációkat.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Cost component type = Other and Other cost type = Sales order</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési rendelés</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Sales order<ept id="p2">**</ept> other cost type is used to define non-shipping costs at the sales order level.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Az <bpt id="p1">**</bpt>Egyéb<ept id="p1">**</ept> költségösszetevő és az <bpt id="p2">**</bpt>Értékesítési rendelés<ept id="p2">**</ept> egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelés szintjén.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ehhez a kombinációhoz a következő mezőket kell beállítani:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Költségtényező<ept id="p1">**</ept> – Adja meg a költségtényező egyedi azonosítóját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Leírás<ept id="p1">**</ept> – Adja meg a költségtényező nevét és leírását.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Kezdő dátum<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Záró dátum<ept id="p2">**</ept> – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktív<ept id="p1">**</ept> – Azt jelzi, hogy a költségtényező aktív-e.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the sales order level.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> – Adja meg a nem szállítási költségek értékesítési rendelés szintjén vett költségértékét.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Cost component type = Other and Other cost type = Sales line</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Értékesítési sor</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Sales line<ept id="p2">**</ept> other cost type is used to define non-shipping costs at the sales order line level.</source><target logoport:matchpercent="93" state="translated" state-qualifier="fuzzy-match">Az <bpt id="p1">**</bpt>Egyéb<ept id="p1">**</ept> költségösszetevő és az <bpt id="p2">**</bpt>Értékesítési sor<ept id="p2">**</ept> egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos az értékesítési rendelési sor szintjén.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ehhez a kombinációhoz a következő mezőket kell beállítani:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Költségtényező<ept id="p1">**</ept> – Adja meg a költségtényező egyedi azonosítóját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Leírás<ept id="p1">**</ept> – Adja meg a költségtényező nevét és leírását.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Kezdő dátum<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Záró dátum<ept id="p2">**</ept> – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktív<ept id="p1">**</ept> – Azt jelzi, hogy a költségtényező aktív-e.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the sales order line level.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> – Adja meg a nem szállítási költségek értékesítési rendelési sor szintjén vett költségértékét.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Cost component type = Other and Other cost type = Location</source><target logoport:matchpercent="83" state="translated" state-qualifier="fuzzy-match">Költségösszetevő típusa = Egyéb és Egyéb költségtípus = Helyszín</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>A combination of the <bpt id="p1">**</bpt>Other<ept id="p1">**</ept> cost component type and the <bpt id="p2">**</bpt>Location<ept id="p2">**</ept> other cost type is used to define non-shipping costs for a group of locations or an individual location.</source><target logoport:matchpercent="68" state="translated" state-qualifier="fuzzy-match">Az <bpt id="p1">**</bpt>Egyéb<ept id="p1">**</ept> költségösszetevő és a <bpt id="p2">**</bpt>Helyszín<ept id="p2">**</ept> egyéb költségtípus kombinációja a nem szállítási költségek meghatározására használatos helyszínek csoportjára vagy egy egyéni helyszínre vonatkozóan.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>You must set up the following fields for this combination:</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ehhez a kombinációhoz a következő mezőket kell beállítani:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source><bpt id="p1">**</bpt>Cost factor<ept id="p1">**</ept> – Enter a unique identifier for the cost factor.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Költségtényező<ept id="p1">**</ept> – Adja meg a költségtényező egyedi azonosítóját.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source><bpt id="p1">**</bpt>Description<ept id="p1">**</ept> – Enter the name and description of the cost factor.</source>
        <target logoport:matchpercent="78" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Leírás<ept id="p1">**</ept> – Adja meg a költségtényező nevét és leírását.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source><bpt id="p1">**</bpt>Start date<ept id="p1">**</ept> and <bpt id="p2">**</bpt>End date<ept id="p2">**</ept> – You can use these fields to limit the cost factor for a specific date range.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Kezdő dátum<ept id="p1">**</ept> és <bpt id="p2">**</bpt>Záró dátum<ept id="p2">**</ept> – Ezekkel a mezőkkel a költségtényezőt egy megadott dátumtartományra korlátozhatja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>If you leave these fields blank, the cost factor is valid for an indefinite period.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Ha üresen hagyja ezeket a mezőket, akkor a költségtényező határozatlan időre érvényes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source><bpt id="p1">**</bpt>Active<ept id="p1">**</ept> – Indicate whether the cost factor is active.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited"><bpt id="p1">**</bpt>Aktív<ept id="p1">**</ept> – Azt jelzi, hogy a költségtényező aktív-e.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The DOM considers only active cost factors that are associated with the fulfillment profile.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">A DOM csak az aktív, teljesítési profilhoz társított költségtényezőket veszi figyelembe.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source><bpt id="p1">**</bpt>Fulfillment group<ept id="p1">**</ept> – Specify the group of locations that the non-shipping cost is defined for.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>Teljesítési csoport<ept id="p1">**</ept> – Adja meg a helyszíncsoportot, amellyel kapcsolatban meghatározza a nem szállítási költséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source><bpt id="p1">**</bpt>Fulfillment location<ept id="p1">**</ept> – Specify the location that the non-shipping cost is defined for.</source><target logoport:matchpercent="81" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Teljesítési helyszín<ept id="p1">**</ept> – Adja meg a helyszínt, amellyel kapcsolatban meghatározza a nem szállítási költséget.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Nem adható meg teljesítési csoport és teljesítési helyszín ugyanabban a sorban helyszínalapú számítási feltétel esetén.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source><bpt id="p1">**</bpt>Cost<ept id="p1">**</ept> – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</source><target logoport:matchpercent="70" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Költség<ept id="p1">**</ept> – Adja meg a nem szállítási költségek teljesítési csoport szintjén vagy teljesítési helyszín szintjén vett költségértékét.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Ha azt szeretné, hogy a DOM futtatáskor figyelembe vegye ezeket a költségeket, hozzá kell adnia a költségtényezőt a megfelelő teljesítési profilhoz.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>