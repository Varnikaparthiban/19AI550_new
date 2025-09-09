# Ex.No: 6  Implementation of Jumping  behaviour- Unity
### DATE:  01.09.25                                                                        
### REGISTER NUMBER : 212223240170
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```
###
**Program **
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
          //  isGrounded = false;
        }
    }

   
}
```
### Output:

<img width="1480" height="990" alt="Screenshot 2025-09-09 134635" src="https://github.com/user-attachments/assets/50701f51-65f3-48c8-81ec-ee3660d11264" />

<img width="1489" height="1001" alt="Screenshot 2025-09-09 134650" src="https://github.com/user-attachments/assets/9b2eb3bd-7c59-4b5e-91df-a863b671a814" />


### Result:
Thus the simple jumping behavior was implemented successfully.
