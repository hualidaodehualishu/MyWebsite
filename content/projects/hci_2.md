+++
title = "Roll Ball Game"
date = "2023-01-30"
description = "This is a simple and fun game. In this game,we need roll the ball, then touch to eliminate the blocks, after all the blocks are eliminated, the game is over"
+++
 
# Scene building
   After opening Unity we will see some windows in the operator interface. Here is a brief description.
The scene window is used to display all the game objects we have created, right now there is only a small camera and a small sun. The camera is equivalent to our player's point of view. The sun is a simulation of the real sun emitting light, which can apply the effect of light and shadow to objects.
The game window is used to preview the game screen. When we click on the play button located at the top of the window, we can play the game in this window just like the player, and clicking on the play button again returns us to the editing screen.
The hierarchy window is for all the game scenes we have created, including maps, characters, modules, etc.
The project window is used to store the scripts we have written, the properties of the scene (colors and other physical properties). The largest window on the far right is the one that shows the details of what we have currently selected. For example, if you select a .cs file, then this window will show the source code of this cs file, and if you select an object, then this window will show the various properties of this object. This window is also the place where we operate more.
First I create a plane, click Create -> 3D -> Plane in the Hierarchy window, then a white plane appears in the self window, and we have successfully created the plane.
Next I need to add color to this ground, create a Material folder in the project window to store our material files. Create a new material in this folder, right-click on the folder, select create, material, create a material, and choose a color of your choice. Then click and hold the material and drag it directly onto the ground created in the hierarchy. Next all items in the scene are created in this way.
Here is the created scene：
![截屏2023-01-30 04.11.41.png](https://s2.loli.net/2023/01/30/qHQS5TgV6Cu2eBE.png)
# Project Script
## Player Script
public class PlayerController : MonoBehaviour {
    public float speed;
    public Rigidbody rb;
    void Start () {
        rb = GetComponent<Rigidbody>();
    }
    void FixedUpdate()
    {
        float moveHorizontal = Input.GetAxis("Horizontal");
        float moveVertical = Input.GetAxis("Vertical");
 
 
        Vector3 movement = new Vector3(moveHorizontal,0.0f,moveVertical);
 
 
        rb.AddForce(movement * speed);
    }
}
## CameraController Script
public class CameraController : MonoBehaviour {
 
    public GameObject player;
 
    private Vector3 offset;
 
    void Start()
    {
        offset = transform.position - player.transform.position;
    }
 
    void LateUpdate()
    {
        transform.position = player.transform.position + offset;
    }
}
## Pick Up Script
public class Rotator : MonoBehaviour {
 
    
    // Update is called once per frame
    void Update () {
        transform.Rotate(new Vector3(15, 30, 45) * Time.deltaTime);
    }
}
## OnTriggerEnter Script
private void OnTriggerEnter(Collider other)
    {
        if(other.gameObject.CompareTag("Pick Up"))
        {
            other.gameObject.SetActive(false);
        }
    }
##SetCountText Script
public class PlayerController : MonoBehaviour {
    public float speed;
    public Rigidbody rb;
    public Text CountText;
    public Text WinText;
    private int count;
    // Use this for initialization
    void Start () {
        rb = GetComponent<Rigidbody>();
        count = 0;
        SetCountText();
        WinText.text = "";
 
 
    }
    private void FixedUpdate()
    {
        float moveHorizontal = Input.GetAxis("Horizontal");
        float moveVertical = Input.GetAxis("Vertical");
 
 
        Vector3 movement = new Vector3(moveHorizontal,0.0f,moveVertical);
 
 
        rb.AddForce(movement * speed);
    }
    private void OnTriggerEnter(Collider other)
    {
        if(other.gameObject.CompareTag("Pick Up"))
        {
            other.gameObject.SetActive(false);
            count = count + 1;
            SetCountText();
        }
    }
    void SetCountText()
    {
        CountText.text = "Count:" + count.ToString();
        if(count >= 9)
        {
            WinText.text = "You Win!";
        }
    }
}

These scripts can support the implementation of all the functions of our game。
