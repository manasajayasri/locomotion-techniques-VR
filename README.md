# Locomotion Techniques
In virtual reality (VR), locomotion techniques are crucial for navigating virtual environments, balancing immersion with user comfort to prevent motion sickness. Popular methods include teleportation, where users instantly move to a targeted location, and smooth locomotion, which involves continuous movement controlled by a joystick. These techniques help mitigate the mismatch between visual inputs and physical motion, reducing the risk of discomfort.

More immersive options include room-scale movement, which allows users to physically walk within their space, and arm-swinging, where arm movements simulate walking. Advanced methods like redirected walking can cleverly adjust user paths to enhance spatial immersion without requiring large physical spaces. Each VR locomotion technique offers different levels of immersion and comfort, tailored to suit various user preferences and application needs.

Group member 1 name: Amogha Manjunatha Kuruvadi

Group member 1 email: kuruvadi@uwm.edu

Group member 2 name: Manasa Thambabathula

Group member 2 email: thambab2@uwm.edu

Group member 3 name: Sheetal Saju

Group member 3 email: ssaju@uwm.edu

#### Third party assets: 
- [godot-xr-tools](https://github.com/GodotVR/godot-xr-tools) 
- [kaykit-dungeon-remastered ](https://kaylousberg.itch.io/kaykit-dungeon-remastered)
- [Godot XR Hand Pose Detector](https://godotengine.org/asset-library/asset/3097)

#### References for Various Locomotion Techniques: 
- https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10108834
- https://faculty.washington.edu/wobbrock/pubs/assets-23.02.pdf
  
### Project Recap 
High-level summary of our project.

#### Answer

> [!NOTE]
> Eco-Runner VR: A Race to Save the Planet is an immersive virtual reality game designed to entertain and educate users about environmental conservation. Players navigate through various natural settings—land, water, forest, and sky—collecting eco-friendly items and avoiding hazards linked to pollution and environmental degradation. The game leverages physical activity, requiring players to bend, jump, and fetch items, enhancing both the immersion and interactivity of the experience. The main goals of Eco-Runner VR are to provide an engaging gaming experience that also raises awareness about sustainability issues. As players progress, they witness the direct impact of their actions through the Restoration Meter, which visually transforms the polluted environments into clean and vibrant ecosystems as they collect items. This visual feedback loop not only rewards players but also educates them on the importance of sustainable practices.
The minimal viable product (MVP) focuses on one playable world with full VR controls for movement, an obstacle avoidance mechanic, a working Restoration Meter, and a basic scoring system. These elements are designed to meet the dual goals of entertainment and education, ensuring players feel both challenged and motivated to learn about environmental issues.
Overall, Eco-Runner VR aims to combine fun gameplay with educational content, creating a compelling experience that encourages players to think about their environmental footprint while providing an enjoyable and physically engaging VR game.

### Identified Locomotion Tasks

#### Answer

> [!NOTE]
> 1) Triggered Forward Movement
> 2) Precise Short-Distance Movement

#### 1) Triggered Forward Movement
The player needs to move forward along the path by performing a specific action, such as a hand-swinging motion or a grabbing gesture. Movement is not continuous but triggered by deliberate actions from the player, adding an interactive element to the gameplay.

#### 2) Precise Short-Distance Movement
The player needs to perform deliberate movements to dodge obstacles (e.g., fallen trees, mud puddles) or position themselves closer to collectible items like seeds and water. Movement is controlled by specific actions, such as short hand-swing gestures or grabbing motions, to ensure precision.

#### Possible techniques:
 - Continuous movement with velocity-dependent FOV restriction \*
 - Continuous movement with time-dependent FOV restriction \*
 - Walking-in-place using hand swinging movement
 - Translation-gain-based techniques (i.e. "Seven League Boots") \*\*
 - Teleportation with final direction specification
 - Teleportation with rapid transition (rather than instantaneous transition)
 - World-in-Miniature with the abiilty to manipulate the user's point of view
 - Single-point or Dual-point world manipulation
 - A hybrid of any of the listed techniques

*\* Continuous movement can be implemented using either view-directed steering, hand-directed steering, or the "human joystick" method*

*\*\* The total physical environment size requirements cannot exceed 4 meters by 4 meters*

### Identified Technique Options

#### Answer

> [!NOTE]
> i) Walking-in-place Using Hand Swinging Movement
> 
> ii) Grab and Pull Movement [From above research articles referenced]
> 
> iii) Teleportation with Final Direction Specification
> 
> iv) Climbing Mechanism
> 
> v) Walking-in-place Using Hand Swinging Movement
> 
> vi) Teleportation with Rapid Transition

#### Task 1: Triggered Forward Movement

i) Walking-in-place Using Hand Swinging Movement
This technique mimics natural walking, requiring the player to swing their arms in place to initiate movement. This provides a strong sense of immersion and minimizes motion sickness by aligning body movement with virtual movement.

ii) Grab and Pull Movement
The player grabs a virtual object in front of them and pulls themselves forward. This provides fine-grained control over movement and works well for short-distance traversal or precise navigation.

iii) Teleportation with Final Direction Specification
Players point to a destination and are teleported there, specifying the direction they face upon arrival. This technique eliminates motion sickness entirely and is ideal for navigating longer distances.

#### Task 2: Precise Short-Distance Movement
i) Climbing Mechanism
The player grabs objects or surfaces to pull themselves up or across. This technique provides tactile interaction and enhances immersion while offering precise control over movement.

ii) Walking-in-place Using Hand Swinging Movement
Similar to Task 1, this technique works for shorter distances, allowing players to maintain immersion while navigating obstacles or collecting items.

iii) Teleportation with Rapid Transition
This technique enables quick relocation to a designated spot, useful for avoiding obstacles or reaching precise positions.

### Selected Techniques

#### Answer
> [!NOTE]
> Group Size: 3

#### 1) Walking-in-place Using Hand Swinging Movement
The user moves forward in the game by mimicking a walking motion using their hand controllers. Swinging the controllers up and down alternately simulates a natural walking movement.
This task allows the user to navigate the virtual environment, such as traversing the forest world or exploring different sections of the game. The hand-swinging gesture provides an intuitive and immersive way to locomote without relying on physical walking.

**Additional Context:**
This technique minimizes the risk of motion sickness often associated with traditional VR locomotion methods and makes movement feel more natural and engaging.

#### 2) Grab and Pull for Precise Movement
The user can grab virtual points or objects within the environment using the controller and "pull" themselves toward that point. This could be implemented for tasks like climbing or moving short distances with precision. This task provides precise control for navigating obstacles, moving to specific areas, or interacting with objects that are slightly out of reach.

**Additional Context:**
Grab-and-pull is particularly useful for tasks requiring accuracy, such as dodging abandoned vehicles or navigating tight spaces. It complements the walking-in-place motion by providing a secondary movement option.

#### 3) Teleportation with Final Direction Specification
The user moves to a specific point in the virtual environment by pointing to a desired location using their VR controller and clicking the selection button. The player can also specify their final facing direction upon arrival by adjusting the controller orientation before confirming the teleport.

**Additional Context:**
This technique virtually eliminates motion sickness by avoiding continuous movement and instead relying on instantaneous or smooth transitions. It is particularly useful in scenarios requiring precise positioning or when rapid navigation is needed, such as moving to collect seeds or water in the forest world or reaching safe zones during gameplay. It also provides accessibility for players who may find other locomotion techniques physically demanding.

#### 4) Climbing Mechanism (Additional technique)
The user interacts with climbable objects in the virtual environment using their VR controllers. By grabbing surfaces like tree branches, ropes, or ledges and performing a pulling motion, the user simulates climbing. This mechanism allows vertical navigation in the environment.

**Additional Context:**
The climbing mechanism requires precise hand-eye coordination and adds an engaging layer of interactivity to the game. It minimizes motion sickness because the user's viewpoint changes are directly tied to their physical actions, maintaining spatial awareness. This technique is particularly effective for encouraging active participation, making the game more dynamic and physically engaging.

#### Instructions

> [!NOTE]
> Scene 1: Walking-in-place Using Hand Swinging Movement
> Scene 2: Teleportation with Final Direction Specification
> Scene 3: Grab and Pull Mechanism
> Scene 4: Climbing Mechanism

#### Scene 1: Walking-in-place Using Hand Swinging Movement
1. Equip the VR headset and start the scene for walking-in-place movement.
2. Swing your hand controllers alternately up and down to simulate walking.
3. Observe the character moving forward in the environment based on the motion of the hand controllers.
4. Movement is proportional to the intensity and rhythm of the hand-swinging motion.
5. A green pillar is present in the environment, and if you press the grip button, you will initiate the climbing mechanic to ascend the pillar.
   
**Additional Notes:**
Tried to implement another layer below the static body to ensure the player falls off and resets if they move beyond the boundaries of the stage. While I attempted to add another layer to enhance the resetting mechanism, I couldn’t fully implement it due to time constraints. This technique still showcases smooth locomotion and provides an intuitive way for players to navigate without physical walking.

**Demo:** https://panthers-my.sharepoint.com/:v:/g/personal/thambab2_uwm_edu/EUX7C1CNi1FDpBPpQKHYG7IB_Xg9Iof-OKP3T7oG8daVWw

[YT: https://www.youtube.com/shorts/XewZZKzecsM]

#### Scene 2: Teleportation with Final Direction Specification
Begin the teleportation scene and equip the VR headset.
1. Activating the Teleportation Beam: Use the trigger button on the left controller to activate the teleportation beam.
2. Selecting a Location and Direction:
- Point the beam at the desired location within the environment.
- Use the primary thumbstick on the left controller to set the final direction:
   * Push the thumbstick right to rotate the direction clockwise.
   * Push the thumbstick left to rotate the direction anticlockwise.
3. Teleporting: Release the trigger button to teleport to the selected location and orientation.

After teleportation, the player's orientation will automatically align with the beam's final direction, enabling smooth navigation and interaction within the environment.

**Demo:** https://panthers-my.sharepoint.com/:v:/g/personal/thambab2_uwm_edu/ES9JLr8dOedDjZvCpSHilTsBjvFP7VhyIgBYzEB-IeYE9A

[YT: https://www.youtube.com/shorts/5GZPWYo_yUw]

#### Scene 3: Grab and Pull Mechanism
1. Initiate the scene featuring the grab and pull locomotion technique.
2. Put on the VR headset and simulate the action of grabbing and pulling an imaginary rope to experience locomotion.
3. Utilize the joysticks on the Right Controller to adjust the viewport as needed. Pull the virtual object toward yourself to simulate moving forward.

**Additional Notes:**
This locomotion method is inspired by research outlined in our previously referenced papers, which explore the effectiveness and user engagement of the grab and pull technique in virtual environments.

**Demo:** https://panthers-my.sharepoint.com/:v:/g/personal/thambab2_uwm_edu/EfBmnSMphPNBp_TUvw88sdYBKhsCD_T4T_ZAlK7eBxMrbw

[YT: https://www.youtube.com/shorts/Vi6APQ-UHZA]

#### Scene 4: Climbing Mechanism
1. Start the climbing mechanism scene and equip the VR headset.
2. Approach climbable objects like ledges or vertical surfaces in the environment.
3. Use the grip button on the controller to grab onto the surface.
4. Perform pulling motions with the controller to climb upwards or sideways.
5. Reach the top or move laterally to navigate elevated or obstacle-laden areas.

**Additional Notes:**
This technique provides vertical navigation and enhances immersion through realistic physical interactions with the environment. The climbing mechanism integrates multiple interactive components including:
- Movement (using controllers)
- Jump
- Object pickup
- Climbing
- Flight mechanism (use B/Y and left joystick)

**Demo:** https://panthers-my.sharepoint.com/:v:/g/personal/thambab2_uwm_edu/EZ632cbRHkNAvB461w48kcQBo5Bb1F0jmo0p6pqR4twwHA

[YT: https://youtube.com/shorts/S0KN4hIDuzo]
