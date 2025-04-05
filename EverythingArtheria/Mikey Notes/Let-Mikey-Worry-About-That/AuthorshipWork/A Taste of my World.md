# What is this world?
Super convoluted. It's Cyberpunk, DnD, Shadowrun, Lancer, all in one. There's tons of items on a spreadsheet.

This is Artheria, but not the side that Jason and friends know. It's about life on the other side. More Cyberpunk.



# What's the point of this world?
For my amusement. This is my own setting.
I play a lot of games. Might as well turn it into something more permanent.

Inspirations












Magic
	Spells
Technology
	Implants
	Hacking
Mechs
Vehicles
Different Types of Tech

So close to each other that at times they're indiscernible

How it starts
Conflict - Being hunted by loansharks
Be about 16 years old. Young. Got some skills but not much.
Fall in a place
It's a hideout
There's so much stuff
	Old broken mechs. Cars, cybernetics. Books. 
How do I turn it into money?
Goal: Handle the Loansharks.
Character Creation
Do Screamsheets




Super Complex
Can be solo played

Includes Magic, Robots, Cyberpunk, Salvage
Like GURPS.

Takes place on multiple worlds and pocket dimensions




- based on Lancer and Salvage Union
- Assume DnD 5e Character Rules until out of rough draft.

Character Creation
Race - Has a tag. Tag is used for DM to construct better dialogue.
Accessories, Paint, Visible Tattoos, etc. - Each has a tag for the same reason.
Armor - tag as well. 

Background has a tag. Celebrity Lvl 1-5, 1 being a 1-4 chance of being known. Starstruck means advantage for player with anything until NPC feels taken advantage of. and etc. for other tags.

NPC's have random tags.  This would make celeb recognition with advantage.

Triggers, Saving Throws? same thing? Actions?


Mech
Frames
Size
Armor
Mounts


Frames have core systems.

Hull is armor.

Agility, dependent on mech type.

Systems, like combat or hacking systems.

Engineering, doing well with what your mech has.

This tabletop system is about several systems stacked on top of each other.

Each session is missions

Hub - Campship or Camp.

Pilot Gear, Hardsuits, etc.

Several Mech Brands
Normal Tech
Magic Tech
Alien Tech
Oddity Tech
Abomination Tech
Solarpunk Tech

## DreamGame
Simple, but complex.
Complex things are hooked up to API's. So it's as simple as you want it to be.
Can be played on mobile.
All my close friends can play it.
Family API. The one with all our family member's stories.

Preferrably smallest size possible.
3D background, 2d Sprites.

Whatever we do in this game, is solidified in our group's fiction works.

No direct inserts from another lore.
Point of sharing the same fictional universe is respecting other's genuine desire to tell their unique story.

Otherwise you have a character who is based off their mother getting killed by sonic the hedgehog, who is severus snape's mother.

Based off of real world events, but not actually real world events.

Attention to culture. Clothing, architecture, food and traditions.


Hacking
If Magic, Runic Flow

Magic, the Weave, is just another medium like water or electricity. The difference is that it is as organic as it is inorganic. Someone tapped into it and learned how to cancel it out. The human body is a system, the magic can be a network program. It means the brain can be hacked.

Netrunning

## Say the game is done, what then?
I hope to enjoy it when I'm 80 and immobile.
Use it to relive my younger days.


# Soloplay



# How to make a world feel alive (code)

Closed system.
On a grand scale, there's 100 Entities.
Each entity is trying to absorb.
Every 1-2 Sessions, there's a change. +- 1.
The current session story is just that one change.

This is global scale.
I wonder if there's a simulator for these changes?

Your open-world system idea sounds interesting! Here's a possible structure for simulating change in a closed ecosystem with 100 entities:


## World Constant Change
### 1. **Entities**
- **Types**: Forests, Armies, Towns, etc.
- **Attributes**: Each entity type can have specific attributes such as:
  - **Forests**: Size, density, health
  - **Armies**: Strength, size, morale
  - **Towns**: Population, resources, defense

### 2. **Transitions**
- **Rules**: Define clear rules for how entities transition from one state to another.
  - **Forest to Town**: If a forest is burned down, it transitions into a town.
  - **Town to Ruins**: If a town is attacked by an army and loses, it transitions into ruins.
  - **Army to Forest**: If an army disbands or is defeated in a forest, the area might revert to a forest over time.

### 3. **Interactions**
- **Events**: Random or triggered events that cause changes in the ecosystem.
  - **Natural Events**: Fires, floods, growth cycles
  - **Human Events**: Battles, migrations, constructions
- **Conditions**: Specific conditions under which transitions occur.
  - **Burning Down a Forest**: Requires an event such as a fire or an army attack.
  - **Building a Town**: Requires resources and population.

### 4. **Simulation Cycle**
- **Time Steps**: Define how time progresses in your simulation (e.g., days, months, years).
- **Update Rules**: Each time step, apply the rules and conditions to update the state of the entities.
- **Balance**: Ensure the number of entities remains constant at 100.

### 5. **Example Scenario**
1. **Initial State**: 50 forests, 30 towns, 20 armies.
2. **Event**: An army attacks a forest.
3. **Transition**: Forest is burned down and transitions into a town.
4. **Updated State**: 49 forests, 31 towns, 20 armies.

### 6. **Tracking and Visualization**
- **Data Tracking**: Keep track of each entity's state and changes over time.
- **Visualization**: Create a map or chart to visualize the current state of the world and its changes.

### 7. **Complexity and Variability**
- **Randomness**: Introduce random events to keep the simulation unpredictable.
- **Strategies**: Allow entities to have strategies or goals to add depth (e.g., armies seeking to expand, towns focusing on defense).

### Implementation
This can be implemented in various programming languages or game engines. Python with libraries like Pygame for 2D visualization or Unity for a more complex 3D environment could work well.

### Pseudo-Code Example
```python
class Entity:
    def __init__(self, entity_type, attributes):
        self.entity_type = entity_type
        self.attributes = attributes

class Simulation:
    def __init__(self):
        self.entities = [Entity("Forest", {...}) for _ in range(50)] + \
                        [Entity("Town", {...}) for _ in range(30)] + \
                        [Entity("Army", {...}) for _ in range(20)]
    
    def update(self):
        for entity in self.entities:
            self.apply_events(entity)
    
    def apply_events(self, entity):
        if entity.entity_type == "Forest" and random_event_happens():
            entity.entity_type = "Town"
            entity.attributes = {...}

# Initialize and run the simulation
sim = Simulation()
for _ in range(100):  # Run for 100 time steps
    sim.update()
```

This is a basic framework and can be expanded with more detailed rules, events, and interactions to create a rich and dynamic ecosystem.

WOW.


# Small Scale

on a small scale, NPC's are randomly generated. Settlements have a population range, with different modifiers of more likely races and clothings, etc.

There's a quota of workers/soldiers, smiths, traders, per settlement type. Upon generation, NPC's only have race, age group, job(clothing), main personality and schedule.  

NPC's only develop deeper personalities when players want to get to know them on a deeper level.
Randomly generated NPC's have a schedule depending on their job. It would make sense that a guard would spend their time sleeping in the day, away from the players sight, and only be seen at night while on patrol.

```

import random

# Define constants
RACES = ['Human', 'Elf', 'Dwarf']
AGE_GROUPS = ['Child', 'Adult', 'Elder']
JOBS = ['Worker', 'Soldier', 'Smith', 'Trader']
PERSONALITIES = ['Friendly', 'Hostile', 'Neutral']
SETTLEMENT_TYPES = {
    'village': {'population_range': (20, 50), 'race_weights': [0.7, 0.2, 0.1], 'job_quota': {'Worker': 0.5, 'Soldier': 0.2, 'Smith': 0.1, 'Trader': 0.2}},
    'town': {'population_range': (50, 200), 'race_weights': [0.6, 0.3, 0.1], 'job_quota': {'Worker': 0.4, 'Soldier': 0.3, 'Smith': 0.2, 'Trader': 0.1}}
}

# Define NPC class
class NPC:
    def __init__(self, race, age_group, job, personality, schedule):
        self.race = race
        self.age_group = age_group
        self.job = job
        self.personality = personality
        self.schedule = schedule
        self.deep_personality = None

    def develop_personality(self):
        if not self.deep_personality:
            self.deep_personality = random.choice(PERSONALITIES)

    def __repr__(self):
        return f"NPC(Race: {self.race}, Age: {self.age_group}, Job: {self.job}, Personality: {self.personality}, Schedule: {self.schedule})"

# Function to generate NPCs for a settlement
def generate_npcs(settlement_type):
    settings = SETTLEMENT_TYPES[settlement_type]
    population = random.randint(*settings['population_range'])
    npcs = []

    for _ in range(population):
        race = random.choices(RACES, weights=settings['race_weights'])[0]
        age_group = random.choice(AGE_GROUPS)
        job = random.choices(JOBS, weights=[settings['job_quota'][job] for job in JOBS])[0]
        personality = random.choice(PERSONALITIES)
        schedule = generate_schedule(job)

        npc = NPC(race, age_group, job, personality, schedule)
        npcs.append(npc)

    return npcs

# Function to generate schedules based on job type
def generate_schedule(job):
    if job == 'Soldier':
        return 'Night Patrol, Day Sleep'
    elif job == 'Smith':
        return 'Day Work, Evening Rest'
    elif job == 'Trader':
        return 'Morning Market, Afternoon Rest'
    else:
        return 'Standard Day Work, Evening Rest'

# Example usage
settlement_npcs = generate_npcs('village')
for npc in settlement_npcs:
    print(npc)

# Simulate player interaction with an NPC to develop deeper personality
npc_to_interact = settlement_npcs[0]
npc_to_interact.develop_personality()
print(npc_to_interact)

```

Wow.

Creating a hybrid tabletop game that integrates a screen and code while preserving the unique elements of TTRPGs involves blending the flexibility of tabletop games with the efficiency and convenience of digital tools. Here are some steps and considerations to guide you through this process:

### Concept and Design
1. **Define the Core Experience:**
   - Identify what makes your game unique and what elements from traditional TTRPGs you want to retain. This might include the freedom of player actions, the social interaction, and the narrative flexibility.

2. **Integrate Digital Tools:**
   - Decide which aspects of the game will benefit from digital integration. Common areas include character management, combat calculations, and inventory tracking.
   - Ensure that the digital elements enhance rather than replace the core tabletop experience.

### Technical Implementation
3. **Platform Selection:**
   - Choose a platform for your digital components. This could be a web-based application, a mobile app, or a software for PCs.
   
4. **Coding and Development:**
   - Develop a user-friendly interface that can be easily navigated by players and the game master.
   - Implement features such as automated dice rolls, real-time stat tracking, and dynamic maps.
   - Ensure the code allows for flexibility and adaptability. For example, players should be able to input custom actions that the software can process or track without strict programming constraints.

### Gameplay Mechanics
5. **Maintain Flexibility:**
   - Keep the narrative and decision-making aspects open-ended. Allow the game master (GM) to override or adjust digital components as needed to respond to player creativity.
   - Implement features for custom rule additions and narrative adjustments.

6. **Balance Between Digital and Analog:**
   - Balance the use of digital tools with physical elements like character sheets, miniatures, and dice to maintain the tactile experience of a tabletop game.
   - Consider using the screen for maps, visuals, and real-time data while keeping role-playing and storytelling in the hands of the players and GM.

### Testing and Feedback
7. **Playtesting:**
   - Conduct extensive playtesting with different groups to identify strengths and weaknesses.
   - Gather feedback on the usability of the digital components and their impact on the overall game experience.

8. **Iterate and Improve:**
   - Based on feedback, make necessary adjustments to both the digital and physical components of the game.
   - Ensure that updates and improvements keep the game balanced and enjoyable.

### Additional Features
9. **Custom Content:**
   - Allow for modding or custom content creation, enabling players to personalize their experience further.
   
10. **Community and Support:**
    - Build a community around your game where players can share tips, modifications, and experiences.
    - Provide continuous support and updates based on community feedback.

### Example Setup
- **Digital Character Sheets:** Use a tablet or laptop to manage character sheets, updating stats and inventory automatically based on actions taken during the game.
- **Interactive Maps:** A large screen displaying dynamic maps that can change based on player actions, with fog of war effects and real-time updates.
- **Automated Calculations:** Simplify combat and skill checks with automated dice rolls and result calculations, allowing the GM to focus on storytelling.
- **Narrative Flexibility:** Ensure the digital system can accommodate freeform actions and GM interventions, allowing the narrative to flow naturally.

By carefully designing the integration between digital tools and traditional tabletop elements, you can create a hybrid game that captures the best of both worlds, maintaining the timeless appeal of TTRPGs while leveraging the advantages of modern technology.

## Setting
Low Orbit Space, from Cyberpunk
Space
Cyberpunk Settlements
Magic Settlements

### Story Junkworld
World has gone to shit
War, Famine, Radiation, Societal Collapse
Inspired by Fallout 4
People have to tinker to get by
Old tech is magic

This is the story of a tinkerer
Known by many names
also inspired by Mad Max



## In memory of you
Cyberpunk Setting
- Woman is on a quest
- She's 50 or so. Great shape.
- Asks for directions at a stop
- Child follows her

- Scars from fights
- Goes into a building
- Goes into a gaming company
- Rigs electricity
- Opens up a pc
- downloads files

- Leaves
- Child appears
- Raiders find them
- Good slaves
- No.

- She fights

- Map
- Brain Dance like company has an X mark
- VR Company is X as well


- She continues her quest everywhere.

- Assembles 3D Modeling Software

- Brings out Cassette Tapes
- Brings out Old Tapes

- Goes to a guy
- the guy used to be a VR game dev
- uses the cassette tapes to make the woman a 3D render of her father
- Father has his voice from the cassette
- Father moves like he does in the old videos

- Large Language Model to simulate things he would say.

- They play games for a bit. Every once in a while, the father says something robotlike.

## Chapter 1: The Beginning

In the neon-drenched sprawl of Neo-Tokyo, a woman in her fifties, still in peak condition with muscles sculpted from a lifetime of combat, moved through the crowded streets. Her name was Mara, and she bore the scars of countless fights. She was on a mission, one that had driven her through the heart of the city's underbelly.
Chapter 2: The Stop

Pausing at a decrepit information kiosk, Mara asked a street urchin for directions. The child, a scrappy girl no older than twelve, watched her with wide, curious eyes. When Mara continued on, she noticed the child trailing her.
Chapter 3: The Building

Ignoring the child's shadow, Mara entered a rundown building, home to a once-famous gaming company now lost to obscurity. She moved with purpose, her fingers expertly rigging the building's failing electrical system. The lights flickered, and Mara opened up a dusty, ancient PC, downloading files with a practiced hand.
Chapter 4: The Encounter

Files secured, Mara exited the building only to be confronted by the child. "Why are you following me?" she asked. Before the girl could answer, a group of raiders emerged, eyes gleaming with malice. "Good slaves," one muttered. "No," Mara replied coldly, fists clenching.
Chapter 5: The Fight

The street erupted into chaos as Mara fought the raiders, her movements a blur of lethal precision. The child watched in awe as Mara dispatched the attackers, her scars a testament to battles won and lost.
Chapter 6: The Map

In the aftermath, the child handed Mara a crumpled map. It showed an X over a Brain Dance company and another over a VR enterprise. These locations held the next clues on her quest. Mara nodded, tucking the map away as they continued their journey together.
Chapter 7: The 3D Modeling Software

Their path led them to a dilapidated warehouse. Inside, Mara assembled an old 3D modeling software, setting up ancient equipment. She carefully placed a series of cassette tapes and old videotapes on a table.
Chapter 8: The Developer

Mara sought out an old acquaintance, a former VR game developer known for his brilliance and eccentricity. He took the tapes and, using the outdated technology, began to create a 3D render of Mara's father. The process was painstaking, but eventually, a lifelike figure emerged, complete with the voice from the cassettes and the movements from the old videos.
Chapter 9: The Reunion

The developer integrated a large language model to simulate Mara's father's speech patterns. The simulation was nearly perfect, though occasionally, the father would say something that betrayed his artificial nature. Mara and her father’s digital ghost spent hours together, playing games and reminiscing.
Chapter 10: The Continuation

Every so often, the father's voice would glitch, revealing the digital underpinnings of his resurrection. Yet, for Mara, these moments of imperfection were a small price to pay for a fleeting touch of the past. With the simulation providing a measure of closure, Mara steeled herself for the next phase of her quest, the neon streets calling her back to the endless journey ahead.
Epilogue

Mara's quest continued through the labyrinthine alleys of Neo-Tokyo, always searching, always moving. The child at her side, a new companion in the cyberpunk odyssey, as they navigated a world where past and future intertwined in a dance of neon and shadows.

Other Side of Poverty
boy is standing by himself at an airport
he's picked up
So. Your old man kicked you out huh?
no.
Shy arent you?
...
This is a family tradition, by the way.
Live like this for a year. 365 days. Wait until the next winter.
Then the fortune is yours.
How old are you?
...16
Best time in your life. You learn a lot at the age.
...I couldn't do it. I stopped at about 6 months?
Then your grandpa died. He didn't have a say in his will after that. bulletproof.
I didn't get the living reward.
But hey, I made it on my own ability.
...
So. yeah. get used to this.
Seattle's a fun town. nothing like New York.
...
## Ch 2 The house.
My room is... small stinky.
Here's your spot.
Small room
Here's the garden.
You're gonna be enrolled in this school. I used to go there.
Paperwork's all done.
Today's friday... so. run around. get used to the place.

## Ch 3. school
It sucks. Cousin makes it better.
What's your career, son?
Take up the tech business like your old man?


## Ch 4. what am I doing here? Why can't we order this?
Lost this. broke my phone. I can't do anything.
Short on cash. Gotta pick up shifts.
You mad?
You don't have to be here. You can go back to your dad.

## Ch 5: My friend
My friend's here. Richboi.

## ch 6: I got lost
Can't depend on rich boi.
What was grandad like?

Hung out with her friends. They're nice. Cool. We're taking a trip out to the foggy mountains.


## 7 Got back in with drugs. Life's good again.
You're going down a road, boy. No one can follow you.

## 8 Lost a tooth. Can't afford to get a new tooth.
## 9 Uncle had a breakthrough. He's doing well in his career.

## chapter 10 Coping

## chapter 11 What's different?

## chapter 12 About to board

## Epilogue 
In my room. A whole year. This room feels... bigger than it should be.
Dad's doing well. He hasn't asked too much about my year. I guess he figured that I'd tell him in one manner or another.

So... Being an electrician huh?