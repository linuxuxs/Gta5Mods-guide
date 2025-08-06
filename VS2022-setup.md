In order to create mods, you will need to have:  
* the Class Library (.NET Framework) project template in VS2022.
* GTA5   
* C# and programming experience 

After creating the project in VS2022, in the **Solution Explorer** right-click **References**, and add a new reference.  

Go inside Browse, and click on the Browse button, the one next to OK and Cancel. Navigate to your GTA5 main directory, and find the ScriptHookVDotNet2.dll file, and select it.  

Then, click on Assemblies -> Framework -> and search for **System.Windows.Forms**.    

Here are some useful documentation:  

[The Microsoft key codes and modifiers](https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.keys?view=netframework-4.8)  
[The RAGE mp native functions](https://cdn.rage.mp/public/natives/)  
[.NET System API Reference](https://learn.microsoft.com/en-us/dotnet/api/system?view=net-9.0)  
[The ScriptHookVDotNet repo](https://github.com/scripthookvdotnet/scripthookvdotnet)    
[Native Reference Docs](https://docs.fivem.net/natives/#_0x132F52BBA570FE92)    

Done, then inside the file:  

```
using System;
using System.Windows.Forms;
using GTA;
using GTA.Native;
using GTA.Math;

namespace test
{
    public class Main : Script
    {
        public Main() {
            Tick += onTick;
            KeyDown += onKeyDown;
        }

        private void onTick(object sender, EventArgs e) {

        }

        private void onKeyDown(object sender, KeyEventArgs e) {

        }
    }
}

```

Lets expalin the code a bit!
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
Tick += onTick;
```
```
private void onTick(object sender, EventArgs e) {}
```
----

Whenever the player presses a key, onKeyDown is triggered.
```
KeyDown += onKeyDown;
```
```
private void onKeyDown(object sender, KeyEventArgs e) {}
```
-----

Now you can start creating your own mods!
