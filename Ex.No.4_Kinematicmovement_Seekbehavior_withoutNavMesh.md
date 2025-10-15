# Ex.No: 4  Implementation of Kinematic movement -seek and Flee behavior in Unity
### DATE:  15.10.2025                                                                          
### REGISTER NUMBER : 212223240117
### AIM: 
To write a program to simulate the process of seek and Flee behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12.  Write a script for flee behavior and attach it to target
13.  Run the game
14. Stop the program
    
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class seekScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (target.position - transform.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class fleeScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (transform.position-target.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
### Output:
<img width="1591" height="793" alt="Screenshot 2024-05-15 192358" src="https://github.com/user-attachments/assets/67c82599-19dc-4180-94ae-6c5cf9f914ad" />
<img width="1017" height="535" alt="Screenshot 2025-10-15 085354" src="https://github.com/user-attachments/assets/7ce98a34-2409-4254-8c43-e85e01da4153" />
<img width="1014" height="549" alt="Screenshot 2025-10-15 085411" src="https://github.com/user-attachments/assets/a63f83f6-41dd-4ab9-9c83-2a0a626eba33" />
<img width="1022" height="546" alt="Screenshot 2025-10-15 085420" src="https://github.com/user-attachments/assets/6ebc2b6f-96d1-43a1-9398-172235fd7632" />













### Result:
Thus the simple seek behavior was implemented successfully.
