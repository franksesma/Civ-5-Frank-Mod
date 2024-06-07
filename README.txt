CHANGE LOGS:
v1.3
- Rationalism can now be adopted in medieval era 
- Mercenary Army in Commerce now allows you to purchase Units at a -25% reduced gold cost.
- Added Enlightenment Era mod
- Added Ethnic Units mod
- Spy from finishing Honor has been removed
- Cultural Centers in Aesthetics now gives +50% production towards culture buildings instead of 100%.
- Fine Arts in Aesthetics no longer provides a free Scriptorium, Gallery, and Conservatory.

v1.2
- Artistic Genius in Aesthetics no longer provides +3 science from great works.
- Silk Roads in Commerce now gives a +100% production bonus instead of +50% production bonus towards Markets, Banks, and Stock Exchnages
- Humanism in Rationalism now gives a +100% production bonus towards science buildings instead of +50% production.
- Adopting Rationalism or Aesthetics now officially blocks you from adopting the other. 
- Anti-Tank rifle now has 40 combat strength instead of 30.
- Bomb Shelters have been moved from Telecommunications to Nuclear Fission.
- Crossbow class as a whole has been nerfed 2 combat strength, regular crossbow are down from 13 combat strength to 11 combat strength (Longbowmen have been reduced by 2 from 12 to 10. Saethwyr have been reduced by 2 from 15 to 13). 
- Canals have been brought back.

=====================================================================================================
To create another mod pack compatible with this:
1. Start up Civ 5, go to Mods, select the mods you want to compile into a modpack along with the "Multiplayer Mod Work Around" enabled. 
2. Once in game, start up Firetuner and run the command CreateMP()
3. In the MP_MODSPACK folder, navigate to Override and copy all of the XML files over into the Frank Mod "Override" folder.
4. In the MP_MODSPACK folder, navigate to UI and open InGame.lua. Copy the "ContextPtr:LoadNewContext()" methods at the end of the script that are missing from the InGame.lua from the Frank Mod "UI" folder.
5. In the MP_MODSPACK folder, navigate to Mods and copy all of the mod folders over into the Frank Mod "Mods" folder.
6. Ready to distribute.

=====================================================================================================

FILES THAT CONTAIN THE CHANGES DESCRIBED IN THE CHANGE LOGS:

CHANGES TO FOLDER:

- To Enable Custom Civs: Set Playable and AIPlayable for Civilizations to default="true"
- Added the SocialPolicyPopup.lua file to the UI folder

CHANGES TO CIV5Units_Mongol.xml:
    Update Fine Arts label:
    <Replace Tag="TXT_KEY_POLICY_FINE_ARTS_HELP"> 
    <Text>
        [COLOR_POSITIVE_TEXT]Fine Arts[ENDCOLOR][NEWLINE][COLOR_POSITIVE_TEXT]Amphitheaters[ENDCOLOR], [COLOR_POSITIVE_TEXT]Opera Houses[ENDCOLOR], [COLOR_POSITIVE_TEXT]Museums[ENDCOLOR], and [COLOR_POSITIVE_TEXT]Broadcast Towers[ENDCOLOR] increase city [ICON_TOURISM] Tourism output by 20%.
    </Text>

    Update Mercenary Army label:
    <Replace Tag="TXT_KEY_POLICY_TRADE_UNIONS_HELP"> 
    <Text>
        [COLOR_POSITIVE_TEXT]Mercenary Army[ENDCOLOR][NEWLINE]Allows the purchasing of [COLOR_YELLOW]Landsknechts[ENDCOLOR] at [COLOR_CYAN]Civil Service[ENDCOLOR] and [COLOR_YELLOW]Foreign Legions[ENDCOLOR] at [COLOR_CYAN]Replaceable Parts[ENDCOLOR]. Purchasing units with Gold [ICON_GOLD] costs 25% less than normal.
    </Text>

    Add text label for when Ratonalism or Aesthetics is unlocked near TXT_KEY_POLICY_BRANCH_CANNOT_UNLOCK_RELIGION:
    <Replace Tag="TXT_KEY_POLICY_BRANCH_CANNOT_UNLOCK_AESTHETICS_OR_RATIONALISM"> 
        <Text>
            [COLOR_WARNING_TEXT]This branch is now locked because {1_BranchNameString:textkey} has been opened.[ENDCOLOR]
        </Text>
    </Replace>

    Change Production boost label for Silk Road to say 100%:
    <Replace Tag="TXT_KEY_POLICY_CARAVANS_HELP"> 
        <Text>
            [COLOR_POSITIVE_TEXT]Silk Road[ENDCOLOR][NEWLINE]+100% [ICON_PRODUCTION] Production bonus towards [COLOR_POSITIVE_TEXT]Markets[ENDCOLOR], [COLOR_POSITIVE_TEXT]Banks[ENDCOLOR], and [COLOR_POSITIVE_TEXT]Stock Exchanges[ENDCOLOR]
        </Text>
    </Replace>

    Change Production boost label for Humanism to say 100%:
    <Replace Tag="TXT_KEY_POLICY_HUMANISM_HELP"> 
        <Text>
            [COLOR_POSITIVE_TEXT]Humanism[ENDCOLOR][NEWLINE]+100% [ICON_PRODUCTION] Production towards [COLOR_POSITIVE_TEXT]Libraries[ENDCOLOR], [COLOR_POSITIVE_TEXT]Universities[ENDCOLOR], [COLOR_POSITIVE_TEXT]Observatories[ENDCOLOR], [COLOR_POSITIVE_TEXT]Public Schools[ENDCOLOR], and [COLOR_POSITIVE_TEXT]Research Labs[ENDCOLOR].
        </Text>
    </Replace>

    Change Lekmod Titles: Frank's lekmod v##.#

    Change Artistic Genius label to not mention the +3 science from Great works
    <Replace Tag="TXT_KEY_POLICY_ARTISTIC_GENIUS_HELP"> 
        <Text>
            [COLOR_POSITIVE_TEXT]Artistic Genius[ENDCOLOR][NEWLINE]A [ICON_GREAT_ARTIST] Great Artist appears. [COLOR_POSITIVE_TEXT]Amphitheaters[ENDCOLOR], [COLOR_POSITIVE_TEXT]Opera Houses[ENDCOLOR], [COLOR_POSITIVE_TEXT]Museums[ENDCOLOR], and [COLOR_POSITIVE_TEXT]Broadcast Towers[ENDCOLOR] provide +1 [ICON_RESEARCH] Science. Every [COLOR_POSITIVE_TEXT]Festival[ENDCOLOR] yields +2 [ICON_RESEARCH] Science.
        </Text>
    </Replace>

    Change Bomb Shelters to be available at Nuclear Fission instead of Telecommunications:
    <ID>124</ID> 
        <Type>BUILDING_BOMB_SHELTER</Type> 
        <PrereqTech>TECH_NUCLEAR_FISSION</PrereqTech> 

    Changed Freedom, Order, and Autocracy labels to Democracy, Communism, and Fascism.

CHANGES TO CIV5Units.xml:
    Removed free Scriptoriums, Galleries, and Conservatories from Fine Arts in Aesthetics
    <NumCitiesFreeAestheticsSchools>20</NumCitiesFreeAestheticsSchools> 

    Reduce cost to purchase units for Mercenary Army in Commerce
    <ID>31</ID> 
        <Type>POLICY_TRADE_UNIONS</Type> 
        <UnitPurchaseCostModifier>-25</UnitPurchaseCostModifier> 

    Allow Rationalism to be adopted in the Medieval era:
    <ID>8</ID> 
        <Type>POLICY_BRANCH_RATIONALISM</Type> 
        <Description>TXT_KEY_POLICY_BRANCH_RATIONALISM</Description> 
        <Help>TXT_KEY_POLICY_BRANCH_RATIONALISM_HELP</Help> 
        <Title>TXT_KEY_RATIONALISM_TITLE</Title> 
        <EraPrereq>ERA_MEDIEVAL</EraPrereq> 

    Change POLICY_CARAVANS ProductionModifier to 100 for the following buildings:
    <Row> 
        <PolicyType>POLICY_CARAVANS</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_MARKET</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_CARAVANS</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_BANK</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_CARAVANS</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_STOCK_EXCHANGE</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>

    Change POLICY_HUMANISM ProductionModifier to 100 for the following buildings:
    <Row> 
        <PolicyType>POLICY_HUMANISM</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_LIBRARY</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_HUMANISM</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_UNIVERSITY</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_HUMANISM</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_OBSERVATORY</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_HUMANISM</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_PUBLIC_SCHOOL</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>
    <Row> 
        <PolicyType>POLICY_HUMANISM</PolicyType> 
        <BuildingClassType>BUILDINGCLASS_LABORATORY</BuildingClassType> 
        <ProductionModifier>100</ProductionModifier> 
    </Row>

    Change POLICY_ARTISTIC_GENIUS to not give Science from Great Works:
    <Row> 
        <PolicyType>POLICY_ARTISTIC_GENIUS</PolicyType> 
        <YieldType>YIELD_SCIENCE</YieldType> 
        <Yield>0</Yield> 
    </Row>

    Change Anti Tank Rifle to 40 Combat Strength:
    <ID>210</ID> 
    <Type>UNIT_ANTI_TANK_RIFLE</Type> 
    <Description>Anti-Tank Rifle</Description> 
    <Civilopedia>TXT_KEY_CIV5_INDUSTRIAL_ANTITANKGUN_TEXT</Civilopedia> 
    <Strategy>TXT_KEY_UNIT_AT_GUN_STRATEGY</Strategy> 
    <Help>TXT_KEY_UNIT_HELP_ANTI_TANK_RIFLE</Help> 
    <Combat>40</Combat> 

    Nerf Crossbow classes down 2 combat strength:
    <Type>UNIT_ENGLISH_LONGBOWMAN</Type> 12->10
    <Type>UNIT_US_LONGBOWMAN</Type> 15->13
    <Type>UNIT_CROSSBOWMAN</Type> 13->11
    <Type>UNIT_CHINESE_CHUKONU</Type> 13->11

    Brought back canals
    <ID>55</ID> 
    <Type>BUILD_CANAL</Type> 
    <ShowInPedia>true</ShowInPedia> 
    <ShowInTechTree>true</ShowInTechTree> 
    <!--
    <Row>
        <UnitType>UNIT_WORKER</UnitType>
        <BuildType>BUILD_CANAL</BuildType>
    </Row>
    <Row>
        <UnitType>UNIT_ARGENTINA_WORKER</UnitType>
        <BuildType>BUILD_CANAL</BuildType>
    </Row>
    <Row>
        <UnitType>UNIT_AUSTRALIA_WORKER</UnitType>
        <BuildType>BUILD_CANAL</BuildType>
    </Row>
    <Row>
        <UnitType>UNIT_FAST_WORKER</UnitType>
        <BuildType>BUILD_CANAL</BuildType>
    </Row>
    -->