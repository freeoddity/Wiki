---
title: Database Function Tables
permalink: /functions/
nav_order: 5
---
[**Thanks to T6 for allowing me to reuse the UD wiki!**](https://twitter.com/ThievingSix) 

[**Be sure to check out his new Dokkan Wiki**](https://dokkan.wiki/)

Thanks to the goats [**Goheezy**](https://twitter.com/GoheezyDokkan), [**Merged**](https://twitter.com/UDMerged), [**Luke**](https://twitter.com/LukeNienteData), and [**Ener**](https://twitter.com/_Energizz)

#### Causality Types
`skill_causalities` table


| Causality ID | Name | Description | cau_val1 | cau_val2 | cau_val3 |
|:------------:|-------------------------------|--------------------------------------------------------|------------------------------------|---------------------|----------|
| 0 | isNoneRule | Nothing |  |  |  |
| 1 | isOverHpRate | HP is above percent | HP Percent |  |  |
| 2 | isUnderHpRate | HP is below percent | HP Percent |  |  |
| 3 | isOverEnergy | Ki is above a number | Ki Amount |  |  |
| 4 | isUnderEnergy | Ki is below a number | Ki Amount |  |  |
| 5 | isElapsedTurn | Battle has past turn number | Turn |  |  |
| 6 | isPartyRaceType | Checks if entire deck has a certain link skill | Link Skill ID |  |  |
| 7 | isEnemyRaceType | Checks if enemy has certain link skill | Link Skill ID |  |  |
| 8 | isOverFightingPower | Checks current attack and defense is over a number | Attack | Defense |  |
| 9 | isUnderFightingPower | Checks current attack and defense is under a number | Attack | Defense |  |
| 10 | isOverHpRateOverEnergy | HP is above percent, Ki is above number | HP Percent | Ki Amount |  |
| 11 | isOverHpRateUnderEnergy | HP is above percent, Ki is below number | HP Percent | Ki Amount |  |
| 12 | isUnderHpRateOverEnergy | HP is below percent, Ki is above number | HP Percent | Ki Amount |  |
| 13 | isUnderHpRateUnderEnergy | HP is below percent, Ki is below number | HP Percent | Ki Amount |  |
| 14 | isFirstAttack | Card is in first slot |  |  |  |
| 15 | isOverTargetNum | More than a number of enemies | Number of Enemies |  |  |
| 16 | isUnderTargetNum | Less than a number of enemies | Number of Enemies |  |  |
| 17 | isOverTargetHpRate | Enemy target HP above a percent | HP Percent |  |  |
| 18 | isUnderTargetHpRate | Enemy target HP below a percent | HP Percent |  |  |
| 19 | isAttackOrder | Checks card slot position | Slot (0, 1, 2) |  |  |
| 20 | isOverEnergyCondition | Ki is above percent | Ki Percent |  |  |
| 21 | isUnderEnergyCondition | Ki is below percent | Ki Percent |  |  |
| 22 | isPartyExistChara | Check if character is present in deck | Card Unique Info ID |  |  |
| 23 | isLinkNum | Check if at number of links or greater are active | Number of links |  |  |
| 24 | isHitDamaged | Activates upon being attacked |  |  |  |
| 25 | isTargetKill | Activates when target is killed |  |  |  |
| 26 | isOverHpRateEnableSpecial | HP is above percent, card has enough ki to super | HP Percent |  |  |
| 27 | isUnderHpRateEnableSpecial | HP is below percent, card has enough ki to super | HP Percent |  |  |
| 28 | isSlotElementType | Checks if any cards on rotation are a certain element | Element Type |  |  |
| 29 | isEnemyExistChara | Check if character is an enemy | Card Unique Info ID |  |  |
| 30 | isGuardSuccess | Check if card is guarding |  |  |  |
| 31 | isCombinationAttack | Activates if there are three enemy attacks |  |  |  |
| 32 | isChangeEnergyBallColor | Checks if there is a ki of a certain type on the board | Ki Type |  |  |
| 33 | isBetweenHpRate | Checks if card HP percent is between two numbers | HP Percent Lower | HP Percent Higher |  |
| 34 | isOverTeamCategoryNum | Check if category card is present | 0 for deck; 1 for enemy | Category ID | Unknown |
| 35 | hasAllElementBitpatternCards | Checks if deck has all types of an element bitset | Element Bitset |  |  |
| 36 | isOverHpRateAndElapsedTurn | HP is above percent, battle has past turn number | HP Percent | Turn |  |
| 37 | isUnderHpRateAndElapsedTurn | HP is below percent, battle has past turn number | HP Percent | Turn |  |
| 38 | isTargetEnemyCondition | Enemy has required status effects | Status Effect Flags (see footnote) | Unknown |  |
| 39 | isTargetElementTypeBitPattern | Check if enemy element matches element bitset | Element Bitset |  |  |
| 40 | isSpecialAttack | Activates if card has used a special attack |  |  |  |
| 41 | isOverTeamUniqueCardNum | Activates if deck has card with name | Unknown | Card Unique Info ID | Unknown |
| 42 | isEnergyBallGetNum | Activates if card gets more then specified Ki amount | Unknown | Ki Amount |  |
| 43 | isDodgeSuccess | Activates if card has evaded an attack | Unknown | Unknown | Unknown |
| 44 | isCountUp | Unknown | Unknown | Unknown | Unknown |
| 45 | isContainsCardByCategoryAndUniqueInfo | Activates if card is in target, category and unique info relations | Target (team, turn, enemy...) | Category (id, not sub target) | card\_unique\_info\_set\_relations |



<br />

##### Causality #38 - isTargetEnemyCondition Status Flags

| Status Mask | Description |
|:-----------:|---------------------------|
| 1 | Unknown |
| 2 | Unknown |
| 4 | Unknown |
| 8 | Unknown |
| 16 | ATK Down |
| 32 | DEF Down |
| 64 | Unknown |
| 128 | Unknown |
| 256 | Efficacy Type 9 |
| 512 | Efficacy Type 47 |
| 1024 | Sealed (Efficacy Type 48) |
| 2048 | Efficacy Type 8 |
| 4096 | Unknown |
| 8192 | Efficacy Type 53 |
| 16384 | Efficacy Type 75 |
| 32768 | Efficacy Type 94 |
| 65536 | Efficacy Type 96 |
| 131072 | Unknown |
| 262144 | Unknown |
| 524288 | Efficacy Type 100 |
| 1048576 | Efficacy Type 101 |

<br /><br />

#### Calc Options
Applies to all skills tables & `support_items`


| Calc Option 	| Description        	|
|:-------------:|--------------------	|
| 0           	| Calc Plus          	|
| 1           	| Calc Minus         	|
| 2           	| Calc Percent Plus  	|
| 3           	| Calc Percent Minus 	|
| 4           	| Calc Equal         	|



<br /><br />

#### Efficacy Types


|ID  | Description                                                                                                               | eff_value1                                 | eff_value2                        | eff_value3                                                                                                                                                          |
|----|---------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Change Atk Param                                                                                                          | Atk Value                                  |                                   |                                                                                                                                                                     |
| 2  | Change Def Param                                                                                                          | Def Value                                  |                                   |                                                                                                                                                                     |
| 3  | Change Atk Def Param                                                                                                      | Atk Value                                  | Def Value                         |                                                                                                                                                                     |
| 4  | Change Heal HP                                                                                                            | Hp Value                                   |                                   |                                                                                                                                                                     |
| 5  | Change Enegy Param                                                                                                        | Ki Value                                   |                                   |                                                                                                                                                                     |
| 8  | Change Condition Delay                                                                                                    | Leave all 3 eff values at 0                | Use probability for chance        | Always use target enemy or all enemys                                                                                                                               |
| 9  | Change Condition Stun                                                                                                     | Leave all 3 eff values at 0                | Use probability for chance        | Always use target enemy or all enemys                                                                                                                               |
| 11 | Change Attack Order                                                                                                       |                                            |                                   |                                                                                                                                                                     |
| 12 | Change Pain Attack                                                                                                        |                                            |                                   |                                                                                                                                                                     |
| 13 | Change Resist Damage                                                                                                      | 100-Reduction Value (%)                    |                                   |                                                                                                                                                                     |
| 16 | Change Element Type Atk                                                                                                   | ATK (Element) Value                        |                                   |                                                                                                                                                                     |
| 17 | Change Element Type Def                                                                                                   | DEF (Element) Value                        |                                   |                                                                                                                                                                     |
| 18 | Change Element Type Atk Def                                                                                               | ATK (Element) Value                        | DEF (Element) Value               |                                                                                                                                                                     |
| 19 | Change Element Type Hp Param                                                                                              | HP (Element) Value                         |                                   |                                                                                                                                                                     |
| 20 | Change Element Type Enegy Param                                                                                           | KI (Element) Value                         |                                   |                                                                                                                                                                     |
| 21 | Change Recovery                                                                                                           |                                            |                                   |                                                                                                                                                                     |
| 22 | Change Condition Heal                                                                                                     |                                            |                                   |                                                                                                                                                                     |
| 24 | Change Guard Break                                                                                                        | Leave all 3 eff values at 0                | Use probability for chance        | Always use target enemy or all enemys                                                                                                                               |
| 26 | Change Absorb Special Energy                                                                                              |                                            |                                   |                                                                                                                                                                     |
| 27 | Change Resist Special Damage                                                                                              |                                            |                                   |                                                                                                                                                                     |
| 28 | Change Absorb Deal Damage                                                                                                 | Recovery Value (%)                         |                                   |                                                                                                                                                                     |
| 34 | Change Dokkan Gauge Bonus                                                                                                 |                                            |                                   |                                                                                                                                                                     |
| 35 | Change Heal Bonus                                                                                                         |                                            |                                   |                                                                                                                                                                     |
| 36 | Change Special Bonus                                                                                                      |                                            |                                   |                                                                                                                                                                     |
| 37 | Change Energy Bonus                                                                                                       |                                            |                                   |                                                                                                                                                                     |
| 38 | Change Link Skill Bonus                                                                                                   | Link Effect Value Boost (%)                |                                   |                                                                                                                                                                     |
| 39 | Change Element Type Energy Bonus                                                                                          |                                            |                                   |                                                                                                                                                                     |
| 40 | Change Element Type Linkage Bonus                                                                                         |                                            |                                   |                                                                                                                                                                     |
| 43 | Change Hp Atk                                                                                                             |                                            |                                   |                                                                                                                                                                     |
| 44 | Change Element Type Hp Atk                                                                                                |                                            |                                   |                                                                                                                                                                     |
| 46 | Change Passive Probability Bonus                                                                                          |                                            |                                   |                                                                                                                                                                     |
| 47 | Change Condition Psychic                                                                                                  | Leave all 3 eff values at 0                | Use probability for chance        | Always use target enemy or all enemys                                                                                                                               |
| 48 | Change Condition Seal                                                                                                     | Leave all 3 eff values at 0                | Use probability for chance        | Always use target enemy or all enemys                                                                                                                               |
| 50 | Change Invalid Bad Condition                                                                                              | Leave all 3 eff values at 0                | Use probability for chance        | Always use target private or all allies                                                                                                                             |
| 51 | Change Energy Ball Color                                                                                                  | Change KI Orb (use element id)             | Target KI Orb (use element id)    |                                                                                                                                                                     |
| 52 | Change Resurrection                                                                                                       | Leave all 3 eff values at 0                | Use probability for chance        | Always use target private or all allies                                                                                                                             |
| 53 | Ignore Enemy Defense                                                                                                      | Leave all 3 eff values at 0                | Use probability for chance        | Always use target private or all allies                                                                                                                             |
| 54 | Change Invalid Combination Attack Bonus                                                                                   |                                            |                                   |                                                                                                                                                                     |
| 55 | Change Target Def And Self Atk                                                                                            |                                            |                                   |                                                                                                                                                                     |
| 56 | Change Target Def And Self Def                                                                                            |                                            |                                   |                                                                                                                                                                     |
| 57 | Change Target Def And Self Energy                                                                                         |                                            |                                   |                                                                                                                                                                     |
| 58 | Change Energy Ball Heal                                                                                                   |                                            |                                   |                                                                                                                                                                     |
| 59 | Change Energy Ball Proportional Atk                                                                                       | ATK Value                                  |                                   |                                                                                                                                                                     |
| 60 | Change Energy Ball Proportional Def                                                                                       | DEF Value                                  |                                   |                                                                                                                                                                     |
| 61 | Change Energy Ball Proportional Atk Def                                                                                   | ATK Value                                  | DEF Value                         |                                                                                                                                                                     |
| 63 | Change Special Energy Cost                                                                                                |                                            |                                   |                                                                                                                                                                     |
| 64 | Change Element Type Energy Ball Proportional Atk                                                                          | Element Value (0-4)                        | ATK Boost Value (%)               | Element Value (0-4)                                                                                                                                                 |
| 65 | Change Element Type Energy Ball Proportional Def                                                                          | Element Value (0-4)                        | DEF Boost Value (%)               | Element Value (0-4)                                                                                                                                                 |
| 66 | Change Element Type Energy Ball Proportional Atk Def                                                                      | Element Value (0-4)                        | ATK & DEF Boost Value (%)         | Element Value (0-4)                                                                                                                                                 |
| 67 | Change Energy Ball Color Bitpattern                                                                                       | Insert 31                                  | Insert 32                         |                                                                                                                                                                     |
| 68 | Change Energy Ball Proportional Bitpattern                                                                                | Insert 32                                  | Insert 2                          | HP Value                                                                                                                                                            |
| 69 | Change Energy Ball Color Specify Random                                                                                   | Changes All orbs into (Element ID)         | Insert 1                          | Insert 1                                                                                                                                                            |
| 70 | Change Energy Ball Color Specify Random Without Obstacles                                                                 |                                            |                                   |                                                                                                                                                                     |
| 71 | Change Hp Range Atk                                                                                                       | ATK Boost At MIN HP (%)                    | ATK Boost At MAX HP (%)           | Always 1100                                                                                                                                                         |
| 72 | Change Hp Range Def                                                                                                       | DEF Boost At MIN HP (%)                    | DEF Boost At MAX HP (%)           | Always 1100                                                                                                                                                         |
| 73 | Change Hp Range Atk Def                                                                                                   | ATK & DEF Boost At MIN HP (%)              | ATK & DEF Boost At MAX HP (%)     | Always 1100                                                                                                                                                         |
| 74 | Change Hp Range Ball Heal                                                                                                 |                                            |                                   |                                                                                                                                                                     |
| 75 | Change Condition Disable Swap                                                                                             |                                            |                                   |                                                                                                                                                                     |
| 76 | Change Condition Super Effective Atk                                                                                      | Leave all 3 eff values at 0                | Use probability for chance        | Always use Target Private, Unless You Want All Allies To Be Affected                                                                                                |
| 77 | Change Reset Ball Color                                                                                                   |                                            |                                   |                                                                                                                                                                     |
| 78 | Guard Against All Attacks                                                                                                 | Leave all 3 eff values at 0                | Use probability for chance        | Always use Target Private, Unless You Want All Allies To Be Affected                                                                                                |
| 79 | Metamorphic Transformation (Full Rotation Transformation eg. Rage, Giant Ape, Metal Cooler Core, etc.) | Transform Card Id| Links to battle_params param_no for Set #1 | Links to battle_params param_no for Set #2 (Conventionally 1 Number Above The ID Of Set #1 eg. Set#1 ID is 601, Set#2 ID Would Usually Be 602)                                                          |
| 80 | Change Counter Attack                                                                                                     | Damage Reduction(%)(Optional)              | Counter Multiplier                | Lua Script # From Folder [lua] > [ab_script] > [attack_counter] > cXXXX.lua (the number you put is whatever is in XXXX, excluding the first 2 or 3 zeroes before the number) |
| 81 | Change Extra Attack                                                                                                       |                                            | Probability Attack                | Probability Super Attack                                                                                                                                            |
| 82 | Change Element Type Hp Atk Def                                                                                            |                                            |                                   |                                                                                                                                                                     |
| 83 | Change Element Type Energy Bitpattern                                                                                     |                                            |                                   |                                                                                                                                                                     |
| 84 | Change Suicide Attack                                                                                                     |                                            |                                   |                                                                                                                                                                     |
| 85 | Change Step Extra Attack                                                                                                  |                                            |                                   |                                                                                                                                                                     |
| 86 | Change Special Atk Rate                                                                                                   |                                            |                                   |                                                                                                                                                                     |
| 87 | Change Element Type Attack Coef                                                                                           |                                            |                                   |                                                                                                                                                                     |
| 88 | Change Element Type Defense Coef                                                                                          |                                            |                                   |                                                                                                                                                                     |
| 89 | Change Element Type Attack Defense Coef                                                                                   |                                            |                                   |                                                                                                                                                                     |
| 90 | Change Critical Attack                                                                                                    | Probability                                |                                   |                                                                                                                                                                     |
| 91 | Change Dodge                                                                                                              | Probability                                |                                   |                                                                                                                                                                     |
| 92 | Change Always Hit                                                                                                         |                                            |                                   |                                                                                                                                                                     |
| 93 | Change Element Type Bitpattern Hp                                                                                         |                                            |                                   |                                                                                                                                                                     |
| 94 | Change Invalidate Stun                                                                                                    |                                            |                                   |                                                                                                                                                                     |
| 95 | Change Dodge Counter Attack                                                                                               | Links to battle_params param_no            | Counter Multiplier                | Lua Script #                                                                                                                                                        |
| 96 | Change Energy Ball Additional Point                                                                                       | Insert 63                                  | Ki Value                          |                                                                                                                                                                     |
| 97 | Change Absorb Special                                                                                                     | Recover HP %?                              | Special Category Raw Attribute    | Animation id [lua] > [ab_script] > [ab_sys] > as(nullification id).lua                                                                                              |
| 98 | Change Incremental Param                                                                                                  | Increase ATK/DEF/Ki Value                  | Maximum ATK/DEF/Ki Value          | 0 = Atk, 1 = Def, 2 = Critical Chance, 3 = Dodge, 4 = Damage Reduction, 5 = Ki Gain                                                                                 |
| 99 | Change Invalidate Status Down                                                                                             |                                            |                                   |                                                                                                                                                                     |
| 100| Change Invalidate Astute                                                                                                  |                                            |                                   |                                                                                                                                                                     |
| 101| Change Prediction                                                                                                         | Leave all 3 eff values at 0                | Use probability for chance        | Always use Target Private                                                                                                                                           |
| 102| Change Metamorphic Probability Count Limit                                                                                |                                            |                                   |                                                                                                                                                                     |
| 103| Transformation                                                                                                            | Transform Card Id                          | Turn Requirement                  | Links to battle_params param_no                                                                                                                                     |
| 104| Change HP Atk Def                                                                                                         | HP Value                                   | ATK Value                         | DEF Value                                                                                                                                                           |     
| 109| Revival Skill                                                                                                             | HP% to heal                                | effect_pack Row                   | BGM ID                                                                                                                                                              |
| 110| Passive Reset?                                                                                                            | Insert 2                                   | Passive Skill id                  | 0                                                                                                                                                                   |
| 111| Disable Action                                                                                                            | 0 (use probability for chance)             | 0                                 | 0                                                                                                                                                                   |


<br /><br />

#### Target Types



| Target Type 	| Description                     	|
|:-------------:|---------------------------------	|
| 0           	| None                            	|
| 1           	| Self                            	|
| 2           	| Party All                       	|
| 3           	| Enemy                           	|
| 4           	| Enemy All                       	|
| 5           	| Self And Target                 	|
| 6           	| Party Race Type                 	|
| 7           	| Party Exist Chara               	|
| 8           	| Target Excepct                  	|
| 9           	| Target Party Enemy Attack Order 	|
| 10          	| Slot Attacker                   	|
| 11          	| Party Slot Random               	|
| 12          	| Party Super Class                 |
| 13          	| Party Extreme Class               |
| 14          	| Enemy Super Class                 |
| 15          	| Enemy Extreme Class               |



<br /><br />

#### Influence Types


| Influence Type 	| Description 	|
|:----------------:	|-------------	|
| 0              	| None        	|
| 1              	| Both Ends   	|
| 2              	| Left        	|
| 3              	| Right       	|
| 4              	| Jump Left   	|
| 5              	| Jump Right  	|



<br /><br />

#### Exec Timing


| Exec Timing | Description         |ef|
|:-----------:|---------------------|--|
|      1      | Start Round         |ef|
|      2      | Link Skills         |ef|
|      3      | Your Turn           |ef|
|      4      | On Player Attack    |ef|
|      5      | Enemy Turn          |ef|
|      6      | Before Player Hit   |ef|
|      7      | After Player Hit    |ef|
|      8      | Battle Result Phase |ef|
|      9      | End Round           |ef|
|      10     | Unknown             |ef|
|      11     | End of Puzzle Phase |ef|



<br /><br />

#### Type Bitsets



|     Type      |    Value   |
|:-------------:|------------|
|  AGL          |  1         |
|  TEQ          |  2         |
|  INT          |  4         |
|  STR          |  8         |
|  PHY          |  16        |
|  Super        |  32        |
|  Extreme      |  64        |
|  Unknown      |  128       |
|  Unknown      |  256       |
|  Unknown      |  512       |
|  Unknown      |  1024      |
|  Unknown      |  2048      |                  
|  Super AGL    |  4096      |
|  Super TEQ    |  8192      |
|  Super INT    |  16384     |
|  Super STR    |  32768     |
|  Super PHY    |  65536     |
|  Extreme AGL  |  131072    |
|  Extreme TEQ  |  262144    |
|  Extreme INT  |  524288    |
|  Extreme STR  |  1048576   |
|  Extreme PHY  |  2097512   |
|  Unknown      |  4194304   |
|  Unknown      |  8388608   |
|  Unknown      |  16777216  |



<br /><br />

#### Effect Pack Category



| Effect Pack Category | Animation Path |
|----------------------|-----------------------------------|
| 0 | comic_text/ja/%s/%s.lwf |
| 1 | ingame/battle/effect/%s/%s.lwf |
| 2 | ingame/sugoroku/effect/%s/%s.lwf |
| 3 | outgame/effect/%s/%s.lwf |
| 4 | ingame/battle/sp_effect/%s/%s/%s.lwf |
| 5 | ingame/battle/sp_effect/%s/%s.lwf |



<br /> <br />

#### Link Check Types



| Link Check Type | Name | Description |
|:-:|-|-|
| 0 | isLinkCheckType | Unknown |
| 1 | isLinkCheckSlotChara | Unknown |
| 2 | isLinkCheckUnderHprate | Unknown |
| 3 | isLinkCheckExistChara | Unknown |
| 4 | isLinkCheckPercentage | Unknown |
| 5 | isLinkCheckSpecialConsecutive | Unknown |


