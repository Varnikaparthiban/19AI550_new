# Ex.No: 10  Implementation of 2D/3D game Player Movement and Jumping in Unity
### DATE: 27-10-2025                                                                          
### REGISTER NUMBER : 212223240170
### AIM: 
To design and implement a 2D game character in Unity that can move left, right, and jump using C# scripting and Rigidbody2D physics.
### Algorithm:
```
1.Start
2.Initialize Components:
    Get the Rigidbody2D component of the player character.
    Set initial values for moveSpeed, jumpForce, and isGrounded = false.
3.Take Player Input:
    Read horizontal movement input using Input.GetAxis("Horizontal").
    Read jump input using Input.GetButtonDown("Jump").
4.Apply Horizontal Movement:
    Multiply the horizontal input by moveSpeed.
    Update the Rigidbody2D’s velocity in the X-axis while keeping the Y-axis velocity unchanged.
5.Check for Jump:
   If the jump key (Spacebar) is pressed and the player is on the ground (isGrounded == true):
   Apply upward velocity equal to jumpForce.
   Set isGrounded = false.
6.Detect Collision with Platform:
   When the player collides with an object tagged as “Platform” or “Untagged”:
   If the player’s vertical velocity ≤ 0 (falling down):
   Set isGrounded = true.
   Repeat Steps 3–6 continuously in every frame (Update() method).
7.Stop when the game ends or player object is destroyed.
```  
### Program:
```
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float moveSpeed = 5f;
    public float jumpForce = 10f;
    private Rigidbody2D rb;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        float horizontalInput = Input.GetAxis("Horizontal");
        rb.linearVelocity = new Vector2(horizontalInput * moveSpeed, rb.linearVelocity.y);

        if (Input.GetButtonDown("Jump") && isGrounded)
        {
            rb.linearVelocity = new Vector2(rb.linearVelocity.x, jumpForce);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter2D(Collision2D collision)
    {
        if (collision.gameObject.CompareTag("Platform") || collision.gameObject.CompareTag("Untagged"))
        {
            if (rb.linearVelocity.y <= 0)
            {
                isGrounded = true;
            }
        }
    }
}

```
### Output:

<img width="940" height="578" alt="image" src="https://github.com/user-attachments/assets/bba472e5-e36a-4f2a-b1e9-cb44b188986a" />
<img width="781" height="561" alt="image" src="https://github.com/user-attachments/assets/7c82f3b8-4dde-48be-ad03-a7a2e70def1c" />


### Result:
Thus, the game was developed using Unity and adopted 2D Physics and Artificial Intelligence (AI) for character control and movement detection technology.
