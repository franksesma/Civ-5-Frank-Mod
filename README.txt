CHANGE LOGS:
    * No longer receives +3 science from great works after adopting Artistic Genius in Aesthetics
    * Silk Roads in Commerce now gives a +100% production bonus instead of +50% production bonus towards Markets, Banks, and Stock Exchnages
    * Humanism in Rationalism now gives a +100% production bonus towards science buildings instead of +50% production.
    * Finishing Honor now grants a free spy. 
    * Adopting Rationalism or Aesthetics now officially blocks you from adopting the other. 

FILES THAT CONTAIN THE CHANGES DESCRIBED IN THE CHANGE LOGS:
    - To Enable Custom Civs: Set Playable and AIPlayable for Civilizations to default="true"

CHANGES TO CIV5Units_Mongol.xml:

    Add text label for when Ratonalism or Aesthetics is unlocked near TXT_KEY_POLICY_BRANCH_CANNOT_UNLOCK_RELIGION:
    <Replace Tag="TXT_KEY_POLICY_BRANCH_CANNOT_UNLOCK_AESTHETICS_OR_RATIONALISM"> 
        <Text>
            [COLOR_WARNING_TEXT]This branch is now locked because {1_BranchNameString:textkey} has been opened.[ENDCOLOR]
        </Text>
    </Replace>

    Add to <Text> for for TXT_KEY_POLICY_BRANCH_HONOR_HELP: Gain 1 additional [ICON_SPY]

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

CHANGES TO CIV5Units.xml:

    Change <ExtraSpies> to 1 for <Type>BUILDING_HONOR_FINISHER</Type> 

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
