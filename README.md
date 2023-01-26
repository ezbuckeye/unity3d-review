# Unity Review

This repo contains my study notes and learning projects contained in the course [Complete C# Unity Game Developer 3D](https://www.udemy.com/course/unitycourse2/)

## Projects Overview

![PlayAroundLab](./PlayAround.png)

## Unity Notes

### PlayAroundLab

- press `alt + left mouse button` to look around the scene
- press `f` to focus on an object / a group of objects
- use `Command + D` to make a quick copy of the game object
- drag the game object to Assets to create its Prefabs
- use `Q`(View), `W`(Move), `E`(Rotate), `R`(Scale), `T`(Rect), `Y`(Transform) to switch the functionality of the cursor

### ObstacleGame

- ```
  public class Mover : MonoBehaviour
  {
      // Start is called before the first frame update
      void Start()
      {
        transform.Translate(1, 0, 0); // the object would only move once
      }

      // Update is called once per frame
      void Update()
      {
          transform.Translate(0.01f, 0f, 0f); // the object would keep moving along x axis
      }
  }
  ```

- `[SerializeField] float x = 0.1f;` => could edit the x field more easily in Unity Editor
- ```
  float xValue = Input.GetAxis("Horizontal");  // (old Input System) could use xValue/yValue to do transform
  float yValue = Input.GetAxis("Vertical");
  ```
- `Time.deltaTime` => frame rate independent
- use Cinemachine to follow an object
  1. Install Cinimachine from Package Manager
  2. Add Cinimachine Brain component to camera
  3. Add Virtual Camera and rename
  4. Point the Virtual Camera to follow the player (set Body->Framing Transposer, set Follow->target object)
  5. Tune distance
- Basic Collision
  1. check the Box Collider option for items that need to handle collision
  2. add Rigidbody component to Player object
  3. add some constraints on position/rotation to the rigid body of player object
