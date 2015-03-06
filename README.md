## Installing the Unity Plugin ##
1. Import the MightyIO Package (MightyIO-Unity.unitypackage)
2. From the Unity Window menu item select MightyIO.
3. Enter your Auth Token which can be found inside the MightyIO dashboard (create an acount if you haven't already).
4. Make sure your Bundle Identifier matches a promotion in the MightyIO dashboard.
5. Verify that an In-App purchase matching the Product Identifier from the MightyIO exists in your game.
6. Implement the MightyIO.ShowRibbon(), MightyIO.purchaseSuccessful, MightyIO.purchaseFailed, MightyIO.modalShown, MightyIO.modalClosed methods into your script as seen in the MightyIODemo.cs.
6. Build your game to iOS 7.0 or greater and run your game from xcode.


Methods
-----

**MightyIO.ShowRibbon()**
This method will display the ribbon to your players, allowing them to enter the MightyIO Pop Up Shop where they may unlock your MightyItem.

---
**MightyIO.finishedLoading**
This method will display the ribbon to your players, allowing them to enter the MightyIO Pop Up Shop where they may unlock your MightyItem.

**returns:**
string: A message giving the status of the MightyIO authentication.

---

**MightyIO.purchaseSuccessful**
This method will run when I successful purchase has been made inside the pop up shop. Implement this inside your OnEnable function and inside place code to unloack the item for your player.

**returns:**
string: The product that was purchased from the Pop Up Shop

---

**MightyIO.purchaseFailed**
This method will run if a purchase is not properly completed.

**returns:**
string: The purchase error.

---

**MightyIO.modalShown**
This method runs when the Shop is being displayed.  Using this function you could pause game play while your player is buying the Mighty Item.

**returns:**
string: 

---

**MightyIO.modalClosed**
This method runs when the Pop Up Shop is closed.  Here you could restart your paused game play.

**returns:**
string: 

---



**example:**
```c#
    using UnityEngine;
using System.Collections;

public class MightyIODemo : MonoBehaviour {

	// Use this for initialization
	void Start () {
		
	}

	void OnEnable(){
		MightyIO.ShowRibbon();

		MightyIO.finishedLoading += alertFinishedLoading;
		MightyIO.purchaseSuccessful += alertSuccess;
		MightyIO.purchaseFailed += alertFailure;
        MightyIO.modalShown += alertShown;
        MightyIO.modalClosed += alertClosed;
	}

	void OnDisable(){
		MightyIO.HideRibbon();
	
		MightyIO.finishedLoading -= alertFinishedLoading;
		MightyIO.purchaseSuccessful -= alertSuccess;
		MightyIO.purchaseFailed -= alertFailure;
        MightyIO.modalShown -= alertShown;
        MightyIO.modalClosed -= alertClosed;
	}

	void alertFinishedLoading(string msg)
	{
		Debug.Log("Finished Loading: " + msg);
	}

	void alertSuccess(string msg)
	{
		Debug.Log("Alert Success: " + msg);
	}

	void alertFailure(string msg)
	{
		Debug.Log ("Alert Fail: " + msg);
	}

    void alertShown(string msg)
    {
        Debug.Log ("Modal Shown: " + msg);
    }

    void alertClosed(string msg)
    {
        Debug.Log ("Modal Closed: " + msg);
    }
}
```

___
