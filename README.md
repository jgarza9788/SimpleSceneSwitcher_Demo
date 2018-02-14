SimpleSceneSwitcher
-------------------------------------
[Asset Store Link](http://u3d.as/169e)  
© 2017 Justin Garza

PLEASE LEAVE A REVIEW OR RATE THE PACKAGE IF YOU FIND IT USEFUL!
Enjoy! :)

## Table of Contents

* [Contact](#Contact)
* [Description/Features](#Description-Features)
* [Terms of Use](#Terms-of-Use)
* [Overview/Setup](#Overview/Setup)
* [Scripts](#Scripts)
	* [GoToSceneButton.cs](#GoToSceneButton.cs)
	* [SceneSwitcher.cs](#SceneSwitcher.cs)
	* [SceneSwitcherAdvanced.cs](#SceneSwitcherAdvanced.cs)
	* [SnapShotCamera.cs](#SnapShotCamera.cs)
	* [Other Scripts](#Other-Scripts)
* [Shaders](#Shaders)
	* [Custom/ScreenSnapShot](#Custom/ScreenSnapShot)
* [Known Issues](#Known-Issues)
	* [UI not showing up in snapshot](#UI-not-showing-up-in-snapshot)


## Contact  

Questions, suggestions, help needed?  
Contact me at:  
Email: jgarza9788@gmail.com  
Cell: 1-818-251-0647  
Contact Info: [justingarza.info/contact](http://justingarza.info/contact/)

## Description Features

Switch between one scene and another with a little animation.
A great starting point for your own custom animation.

* Easily customizable effect. Just edit some animation files!
* Easy to use ...just use a few lines of code.
* Unity Free friendly.
* Fully commented C# code.


## Terms of Use

You are free to add this asset to any game you’d like
However:  
please put my name in the credits, or in the special thanks section. :)  
please do not re-distribute.  

## Overview/Setup 

This asset works my blocking the screen, changing the scene, then animating out.
In some cases, a snapshot of the current scene is used to block the scene.

[YouTube Video!](https://www.youtube.com/watch?v=Ow5RD1gCmoM)

![Imgur](https://i.imgur.com/LYhX9En.gif)
![Imgur](https://i.imgur.com/jC0GdkW.gif)
![Imgur](https://i.imgur.com/tD5Qn3j.gif)
![Imgur](https://i.imgur.com/lR62x93.gif)

## Scripts 

### GoToSceneButton.cs

```cs
/*
GoToSceneButton.cs
a demo of how to trigger the SceneSwitcher
*/


using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

[RequireComponent(typeof(Button))]
public class GoToSceneButton : MonoBehaviour 
{
    /// <summary>
    /// The name of the next scene.
    /// </summary>
	public string SceneName;

	// add method to execute on button click
	void Awake() 
	{
		GetComponent<Button>().onClick.AddListener(ClickButton);
	}
	
    // method to switch scene
	void ClickButton()
	{
        //get mouse position
        Vector3 pos = Input.mousePosition; 
        SceneSwitcher.Instance.ChangeScene(SceneName,pos);

	}
}
```

### SceneSwitcher.cs
This script manages the animation before and after the scene switchs.

**Image:**  
the UI image that will be used to blockout the scene.

**Animation Speed:**  
Speed of Animation

**Switch at Middle:**  
If true, the scene will switch in the middle of the animation.  
If false, the scene will switch at the begining of the animation.

**Save PP Before Switch:**  
if true, saves the player prefs before the switch.

![Imgur](https://i.imgur.com/0fjc6lVm.png)

### SceneSwitcherAdvanced.cs
This script manages the animation before and after the scene switchs.  
Extends from the SceneSwitcher.cs

...The only difference is that it tells the SnapShotCamera to get a snapshot before animating.

### SnapShotCamera.cs
Save an image of the screen to _ScreenShot (where any shader can use).  
...Sorry the screen shot doesn't currently support the UI Layer.

![Imgur](https://i.imgur.com/UsMurZMm.png)

### Other Scripts
The Other scripts are basically just used for the Demos.  
They are commented, but please let me know if you have a question.


## Shaders 

### Custom/ScreenSnapShot  
This shader uses the image taken by the SnapShotCamera.cs


## Known Issues 

### UI not showing up in snapshot
The SnapShotCamera.cs doesn't capture the UI.  
I'll be trying to work on this issue.



