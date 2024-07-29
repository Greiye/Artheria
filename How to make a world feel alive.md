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