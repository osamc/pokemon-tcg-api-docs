---
sidebar_position: 1
---

# The card object

## Attributes

### **id** *string*

Unique identifier for the object.

---

### **name** *string*

The name of the card.

---

### **supertype** *string*

The supertype of the card, such as Pokémon, Energy, or Trainer.

---

### **subtypes** *list(string)*

A list of subtypes, such as Basic, EX, Mega, Rapid Strike, etc.

---

### **level** *string*

The level of the card. This only pertains to cards from older sets and those of supertype Pokémon.

---

### **hp** *integer*

The hit points of the card.

---

### **types** *list(string)*

The energy types for a card, such as Fire, Water, Grass, etc.

---

### **evolvesFrom** *string*

Which Pokémon this card evolves from.

---

### **evolvesTo** *list(string)*

Which Pokémon this card evolves to. Can be multiple, for example, Eevee.

---

### **rules** *list(string)*

Any rules associated with the card. For example, VMAX rules, Mega rules, or various trainer rules.

---

### **ancientTrait** *hash*

The ancient trait for a given card. An ancient trait has the following fields:

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **name** *string*        | The name of the ancient trait                       |
| **text** *string* | The text value of the ancient trait |

---

### **abilities** *list(hash)*

One or more abilities for a given card. An ability has the following fields:

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **name** *string*        | The name of the ability                      |
| **text** *string* | The text value of the ability |
| **type** *string* | The type of the ability, such as Ability or Pokémon-Power |

---

### **attacks** *list(hash)*

One or more attacks for a given card. An attack has the following fields:

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **cost** *list(string)*        | The cost of the attack represented by a list of energy types.                     |
| **name** *string* | The name of the attack |
| **text** *string* | The text or description associated with the attack |
| **damage** *string* | The damage amount of the attack |
| **convertedEnergyCost** *integer* | The total cost of the attack. For example, if it costs 2 fire energy, the converted energy cost is simply 2. |

---

### **weaknesses** *list(hash)*

One or more weaknesses for a given card. A weakness has the following fields:

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **type** *string*        | The type of weakness, such as Fire or Water.                     |
| **value** *string* | The value of the weakness |

---

### **resistances** *list(hash)*

One or more resistances for a given card. A resistance has the following fields:

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **type** *string*        | The type of resistance, such as Fire or Water.                     |
| **value** *string* | The value of the resistance |

---

### **retreatCost** *list(string)*

A list of costs it takes to retreat and return the card to your bench. Each cost is an energy type, such as Water or Fire.

---

### **convertedRetreatCost** *integer*

The converted retreat cost for a card is the count of energy types found within the retreatCost field. For example, ["Fire", "Water"] has a
converted retreat cost of 2.

---

### **set** *hash*

The set details embedded into the card. See the set object for more details.

---

### **number** *string*

The number of the card.

---

### **artist** *string*

The artist of the card.

---

### **rarity** *string*

The rarity of the card, such as "Common" or "Rare Rainbow".

---

### **flavorText** *string*

The flavor text of the card. This is the text that can be found on some Pokémon cards that is usually italicized near the bottom of the card.

---

### **nationalPokedexNumbers** *list(integer)*

The national pokedex numbers associated with any Pokémon featured on a given card.

---

### **legalities** *hash*

The legalities for a given card. A legality will not be present in the hash if it is not legal. If it is legal or banned, it will be present.

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **standard** *string*        | The legality ruling for Standard. Can be either Legal, Banned, or not present.                     |
| **expanded** *string* | The legality ruling for Expanded. Can be either Legal, Banned, or not present. |
| **unlimited** *string* | The legality ruling for Unlimited. Can be either Legal, Banned, or not present.|

---

### **images** *hash*

The images for a card.

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **small** *string*        | A smaller, lower-res image for a card. This is a URL.                 |
| **large** *string* | A larger, higher-res image for a card. This is a URL. |

---

### **tcgplayer** *hash*

The TCGPlayer information for a given card.

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **url** *string*        | The URL to the TCGPlayer store page to purchase this card.                 |
| **updatedAt** *string* | A date that the price was last updated. In the format of YYYY/MM/DD |
| **prices** *hash* | A hash of price types. See below for possible values. |

The following price types are available:

normal, holofoil, reverseHolofoil, 1stEditionHolofoil and 1stEditionNormal.

Each price type can have the following fields (all provided via TCGPlayer):

| Property       | Description                        |
|--------------------------|----------------------------------------------------------------|
| **low** *decimal*        | The low price of the card                |
| **mid** *decimal* | The mid price of the card |
| **high** *decimal* | The high price of the card |
| **market** *decimal* | The market value of the card. This is usually the best representation of what people are willing to pay. |
| **directLow** *decimal* | The direct low price of the card |

---

## Sample JSON

```json
{
  "id": "swsh4-25",
  "name": "Charizard",
  "supertype": "Pokémon",
  "subtypes": [
    "Stage 2"
  ],
  "hp": "170",
  "types": [
    "Fire"
  ],
  "evolvesFrom": "Charmeleon",
  "abilities": [
    {
      "name": "Battle Sense",
      "text": "Once during your turn, you may look at the top 3 cards of your deck and put 1 of them into your hand. Discard the other cards.",
      "type": "Ability"
    }
  ],
  "attacks": [
    {
      "name": "Royal Blaze",
      "cost": [
        "Fire",
        "Fire"
      ],
      "convertedEnergyCost": 2,
      "damage": "100+",
      "text": "This attack does 50 more damage for each Leon card in your discard pile."
    }
  ],
  "weaknesses": [
    {
      "type": "Water",
      "value": "×2"
    }
  ],
  "retreatCost": [
    "Colorless",
    "Colorless",
    "Colorless"
  ],
  "convertedRetreatCost": 3,
  "set": {
    "id": "swsh4",
    "name": "Vivid Voltage",
    "series": "Sword & Shield",
    "printedTotal": 185,
    "total": 203,
    "legalities": {
      "unlimited": "Legal",
      "standard": "Legal",
      "expanded": "Legal"
    },
    "ptcgoCode": "VIV",
    "releaseDate": "2020/11/13",
    "updatedAt": "2020/11/13 16:20:00",
    "images": {
      "symbol": "https://images.pokemontcg.io/swsh4/symbol.png",
      "logo": "https://images.pokemontcg.io/swsh4/logo.png"
    }
  },
  "number": "25",
  "artist": "Ryuta Fuse",
  "rarity": "Rare",
  "flavorText": "It spits fire that is hot enough to melt boulders. It may cause forest fires by blowing flames.",
  "nationalPokedexNumbers": [
    6
  ],
  "legalities": {
    "unlimited": "Legal",
    "standard": "Legal",
    "expanded": "Legal"
  },
  "images": {
    "small": "https://images.pokemontcg.io/swsh4/25.png",
    "large": "https://images.pokemontcg.io/swsh4/25_hires.png"
  },
  "tcgplayer": {
    "url": "https://prices.pokemontcg.io/tcgplayer/swsh4-25",
    "updatedAt": "2021/07/09",
    "prices": {
      "reverseHolofoil": {
        "low": 2.58,
        "mid": 7.37,
        "high": 100.0,
        "market": 3.61,
        "directLow": 2.55
      },
      "normal": {
        "low": 1.0,
        "mid": 3.99,
        "high": 49.99,
        "market": 2.81,
        "directLow": 2.12
      }
    }
  }
}
```