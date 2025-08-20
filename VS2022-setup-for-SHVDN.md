In order to create mods, you will need to have:  
* the Class Library (.NET Framework) project template in VS2022.
* GTA5   
* C# and programming experience
* SHVDN v2 OR SHVDN v3
---------

After creating the project in VS2022, in the **Solution Explorer** right-click **References**, and add a new reference.

# SHVDN v2:
 Go inside Browse, and click on the Browse button, the one next to OK and Cancel. Navigate to your GTA5 main directory, and find the ScriptHookVDotNet2.dll file, and select it. 

# SHVDN v3:
Go inside Browse, and click on the Browse button, the one next to OK and Cancel. Navigate to your GTA5 main directory, and find the ScriptHookVDotNet3.dll file, and select it.   

----
Then, click on Assemblies -> Framework -> and search for **System.Windows.Forms**.    
After youre done, click OK.


Then the code:  

```
using System;
using GTA;

namespace test {

  public class Main : Script {

    public Main(){
      Tick += onTickFuncName;
      KeyDown += onKeyDownName;
      KeyUp += onKeyUpName;
     }

     private void onTickFuncName(object sender, EventArgs e){
      //do stuff every tick
     }

     private void onKeyDownName(object sender, GTA.KeyEventArgs e){
      //do stuff when any key pressed down
     }

     private void onKeyUpName(object sender, GTA.KeyEventArgs e){
      //do stuff when any key is released
     }

  }
}

```

Lets explain the code a bit!
----

Youre creating a class that is inherited from the GTA's Script class. It is required to make the mod run.  
```
 public class Main : Script {}
```  
----
**Main()** is the constructor, it runs once the mod loads.
```
public Main() {}
```
----
Every game frame, your onTick function will be called.
```
Tick += onTickFuncName;
```
Whenever the player presses a key, onKeyDown is triggered.
```
KeyDown += onKeyDownName;
```
Whenever the player releases a key, onKeyUpName is triggered.
```
 KeyUp += onKeyUpName;
```
----

You can name the tick func and the key pressed func however you want.

----
Now you can start creating your own mods!

