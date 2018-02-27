# Unity-2017.2-click-on-models-when-using-Vuforia-6.5
Unity 2017.2 click on models when using Vuforia 6.5

To show all videos and download  all unity pagackes for free must be Subscriber youtube channel 
https://www.youtube.com/channel/UCNJVG9_IebHe-NF-K_Y8Grw?sub_confirmation=1

[![Watch the video](https://img.youtube.com/vi/HlQOrpsiWI0/0.jpg)](http://youtu.be/HlQOrpsiWI0)


using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Vuforia;
using System.IO;

public class Clicks : MonoBehaviour {

    public GameObject Button, Buttoncube, cube;
	// Use this for initialization
	void Start () {
        Button = GameObject.Find("Button");
        Buttoncube = GameObject.Find("Buttoncube");
        cube = GameObject.Find("Cube");

        Button.SetActive(true);
        Buttoncube.SetActive(false);
        cube.SetActive(false);
    }
	
	// Update is called once per frame
	void Update () {

        if (Input.GetMouseButtonDown(0))
        {
            Ray ray = Camera.main.ScreenPointToRay(Input.mousePosition);
            RaycastHit hit;
            if (Physics.Raycast(ray, out hit))
            {
                if (hit.collider.tag == "Buttonone")
                {
                    Button.SetActive(false);
                    Buttoncube.SetActive(true);
                    cube.SetActive(true);
                }

                if (hit.collider.tag == "Buttontow")
                {
                    Button.SetActive(true);
                    Buttoncube.SetActive(false);
                    cube.SetActive(false);
                }
            }
        }
	}
}

