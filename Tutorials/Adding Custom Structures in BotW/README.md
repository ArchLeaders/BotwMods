![THUMBNAIL](https://user-images.githubusercontent.com/80713508/147895813-8051d911-5056-428d-91b7-0e79db766c82.png)

# Prerequisites:
- [BCML](https://gamebanana.com/tools/6624)
- [Blender](https://www.blender.org/download/)
- [BotW Modding Toolkit](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333210&authkey=AIvYBLZa9siUSoA) (MTK)
- [Breath of the Wow](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333211&authkey=AOErcELM6eb2RHk) (Memory Editor)
- [HKX2 Blender Addon](https://gitlab.com/HKX2/BlenderAddon/-/raw/main/blenderaddon_hkx2.zip)
- [Switch-Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases) (STB)
- Text Editor (I use [VSCode](https://code.visualstudio.com/))
- WiiU/[Cemu](https://cemu.info/) (MTK does not support switch yet)

# Creating a new mod folder

Open File Explorer and create a new folder named `My New Mod`, or whatever you want your new mods name to be.
I have created a folder in my mods folder named `2022 Sign`.
This folder will be referred to as the `root` folder in the future.

![0001](https://user-images.githubusercontent.com/80713508/147892478-b16a5fce-bf17-4a47-a6ae-b7ad6949602b.png)

In the `root` folder, add two more folders named `Assets` and `Build`.

> The `Assets` folder can hold textures, models, and other files that are not part of the mod.

> The `Build` folder will hold the actual mod files. (content, aoc, logs, etc . . .)

![0002](https://user-images.githubusercontent.com/80713508/147892481-f53267cd-875e-458b-9c18-6ab6ae82a7f1.png)

Next, open MTK in the `root` folder by typing `mtk.exe` in the path box.

![0003](https://user-images.githubusercontent.com/80713508/147892483-2ae02964-ed10-4c9b-927b-3085d835ee5f.png)

MTK will open; you can just ignore that window for now.

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

# Blender and HKX2
> [Download HKX2 Blender Addon](https://gitlab.com/HKX2/BlenderAddon/-/raw/main/blenderaddon_hkx2.zip)

## Install the HKX2 Blender Addon.

This can be done easily in Blender, just go to `Edit` > `Preferences` > `Add-ons` > `Install...`, then browse for `blenderaddon_hkx2.zip`
Now you should have an HKX2 tab in the right pop-out menu.

![0004-0006](https://user-images.githubusercontent.com/80713508/147892637-de4569a9-27e6-4e7d-854e-9d542f5671f4.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Import/create your model.

I have made [this simple model](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333212&authkey=AH2kNfxK6uMQXpM) to use in this tutorial; you may use it as you like.

![0006_ImportFbx](https://user-images.githubusercontent.com/80713508/147892488-44e5dca8-2966-4192-82d3-f9df32319d90.png)

> Blender Tutorials: [Importing Models](https://docs.blender.org/manual/en/latest/files/import_export.html) | [Blender Basics](https://www.youtube.com/watch?v=bpvh-9H8S1g&list=PL8eKBkZzqDiU-qcoaghCz04sMitC1yx6k) | [Blender Guru](https://www.youtube.com/channel/UCOKHwx1VCdgnxwbjyb9Iu1g)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Change the Collision Info

Once you have created/imported your model, you must set the `collision info` for each object.

This is what defines what sounds and effects will be used in game for when Link interacts with it.

To change the collision info of an object, select it in Blender and click `Change collision info` in the HKX2 tab.

![0007](https://user-images.githubusercontent.com/80713508/147892492-b70d5f11-e574-48f4-9b92-ea8597714cde.png)

In the new window, select the material and sub-material, then click `OK`.
> If an error is thrown, just try again. If it is persistent, post it in the [Discord Modding Hub](https://discord.gg/vPzgy5S).

![0008](https://user-images.githubusercontent.com/80713508/147892494-a1902fc4-d6ae-484a-930e-a78fcb6958f1.png)

_If you are confused by all these controls, check out [this](https://github.com/ArchLeaders/Botw-Modding-Toolkit/blob/master/Docs/Info/HKX2BlenderAddon.md) page._

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Exporting a Collision Packfile

Collision in BotW has a few different formats; the one we will be using is HKRB (**H**avo**k** **R**igid-**B**ody)

To export the collision as HKRB, select the objects that are part of the model and click the `Generate BotW packfile` button in the HKRB tab.
Check `Selected Objects` and save the HKRB file in the `root` of your mod; the name will represent the actor name following [these rules](https://github.com/ArchLeaders/Botw-Modding-Toolkit/blob/master/Docs/Info/NamingRules.md#mtk---actor-namimg-rules), so avoid leaving it as `untitled.hkrb`.

![0009](https://user-images.githubusercontent.com/80713508/147892498-1d978747-9e91-47d0-9ee2-1b5464602e81.png)

Confirm that it saved and proceed to exporting your model.

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Exporting the Model

Exporting the model is super easy, but there are a few things you should know before you continue.

1. If you want to use any texture other than the Alb (Color Texture), you need to [duplicate the UV map]().

2. I have noticed that when there is lots of overlapping mesh in the model, it acts oddly in BotW, so try to clean it up as best you can before exporting.

3. Keep your naming consistent; if your actor is named `TwnObj_2022Sign_A_01`, make the name of your materials, textures, etc something like `Mt_2022Sign_ObjectName_A_01_Alb`. See more naming notes [here](https://github.com/ArchLeaders/Botw-Modding-Toolkit/blob/master/Docs/Info/NamingRules.md)

4. When naming the exported FBX, make the name the same as the actor.

To export the model, select all the objects your using, then go to `File` > `Export` > `FBX`.
In the export window, set the scale to `0.01` and check `Selected Objects`, then save it in the `Assets` folder.
If there are (or will be) lots of assets, I recommend making a `Model` sub-folder for the model files.

![0012](https://user-images.githubusercontent.com/80713508/147892506-839474ad-f614-4a8b-88f2-6b5e73de7075.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

# Generating the actor with MTK

Bring the MTK Commander window back into focus and type `a` into the command line.

![0013](https://user-images.githubusercontent.com/80713508/147893488-995b0919-a37d-424e-9685-1572fe6fde78.png)

Press enter and wait for the magic to happen. Do not close MTK Commander when it has finished.

![0014](https://user-images.githubusercontent.com/80713508/147893484-6e94eb13-79e6-4676-b070-701f1a3639c6.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

# Creating the SBFRES

Navigate to `root\Build\content\Model` there will be two new files there, one ending with just `.sbfres` the other, with `.Tex1.sbfres`.
The first file (`.sbfres`) holds the model, the other (`.Tex1.sbfres`) contains the textures.

Open the model SBFRES and drag the `.Tex1` over the opened [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases) window.

_Note: the following image has the wrong file selected in File Explorer, follow the green arrow._

![0015-0016](https://user-images.githubusercontent.com/80713508/147892514-db6f872f-8a37-40ff-a8b5-fc11fedbf537.png)

Before importing the FBX file exported from Blender earlier, there are a few things that need to be done. _(This will hopefully be automated in the future.)_

1. Rename the SBFRES file inside [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases).
The file name you see in File Explorer is not the actual SBFRES name.
To get the correct name for your SBFRES, open the `README.yml` with any [text editor] located in the `root` folder.
The `SBFRES` name will be the `SBFRES Name` entry. Rename both the Model and Tex1 files in [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases) to match that entry.

![0017](https://user-images.githubusercontent.com/80713508/147892516-f151bf0e-6494-48ec-a88c-06385f07219e.png)

_The `SBFRES Model Name` should match that of your FBX file (excluding the `.fbx`) rename the FBX accordingly._

2. Clear the existing textures and models.
In [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases), expand the model entry, right-click the `Models` folder and click `Clear`.
Do the same for the `Textures` folder in the `Tex1` file.

![0018](https://user-images.githubusercontent.com/80713508/147892523-18591393-b58a-4951-ab6f-dd0e741e5609.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Importing the Model

In [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases), right-click the `Model` folder and click `Import`

![0020](https://user-images.githubusercontent.com/80713508/147892528-9a5923e5-2130-4c52-954f-6473d54a62b5.png)

Browse for your `FBX` file and click `Open` then `OK` on the first popup.

On the second popup, check `Enable Vertex Colors`.
Then click the red `(Select Material!)` text box and browse for a BotW Material (`bfmat`).
I will be using [this](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333215&authkey=AAO6WAfmV28JmmI) bfmat file from `TBox_Field_Iron`.

_You can also change the `Game Preset` to `Breath of the Wild` but I have not noticed much of a difference when using this._

![0021](https://user-images.githubusercontent.com/80713508/147892530-aeb30236-1aad-4bd7-860e-1128c01c437c.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Importing Textures

In the `Tex1` file, right-click the `Textures` folder and click `Import`.

![0022](https://user-images.githubusercontent.com/80713508/147892531-e2c5888f-8f20-4f4e-9f38-e59102873729.png)

Browse for your textures and click `Open`; I am using [these](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333213&authkey=AAW9Hj_2-lmiz0s) basic textures.
> If you use PNG (Or any non-encoded format), make sure to set the correct texture format following [this](https://github.com/ArchLeaders/Botw-Modding-Toolkit/blob/master/Docs/Info/TextureFormats.md) guide.

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Assign the Textures

In the `Model` SBFRES, navigate to `Models\YourModelName\Materials` and select a material.

![0023](https://user-images.githubusercontent.com/80713508/147892534-e012ad26-411f-408c-b396-f9e9dfe68cfc.png)

You will see there is a list of textures in the right panel. (Outlined in green.)
Each texture has a `Sampler` value, this is essentially the texture type. E.g. `_a` = `Alb`, `_n` = `Nrm`, `_s` = `Spm`, etc . . .

If you are interested, you can find out what each sampler is [here](https://github.com/ArchLeaders/Botw-Modding-Toolkit/blob/master/Docs/Info/TextureFormats.md)

To change the texture, double-click the name and select a new one from the list.

![0024](https://user-images.githubusercontent.com/80713508/147892536-c24326d6-0ad0-4da1-9af6-c85f6c15effd.png)

You can now remove any unused texture entries in the material by selecting the texture entry and clicking `Remove`.

If you used my textures and material, you should have something like the following:

![0025](https://user-images.githubusercontent.com/80713508/147892538-916e606e-b943-48e6-bad1-6b4b66c35340.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Save the SBFRES

To save the model SBFRES, click the save button in the top left corner of [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases).

Sadly [STB](https://github.com/KillzXGaming/Switch-Toolbox/releases) does not save the `Tex1` as well, so you will need to export it by right-clicking the `Tex1` SBFRES and clicking `Export`.

![0026](https://user-images.githubusercontent.com/80713508/147892540-0838a5df-90bf-4902-9956-cf618ac09447.png)

Overwrite the original `Tex1` file, then accept the prompt to save a `Tex2` file.

![0027](https://user-images.githubusercontent.com/80713508/147892543-aba88f3c-a5fd-4525-bedb-270589e540d3.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Building a BNP with MTK

In the `MTK Commander` window, type `bnp`. (Add any additional switches like `-i` to install the bnp.)

![0028](https://user-images.githubusercontent.com/80713508/147892545-29614881-8a19-4ccb-b16a-2b81d1c610de.png)

Wait for the command to complete. If you did not use `-i`, install the bnp in BCML before running Cemu.

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Testing the Actor

In Cemu, confirm `BCML` is enabled, and `Extended Memory` is disabled, then launch BotW and [Breath of the Wow Memory Editor](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333211&authkey=AOErcELM6eb2RHk).

![0029](https://user-images.githubusercontent.com/80713508/147892548-1393635b-f3ed-4d80-8713-b5403812ea1a.png)

Load a save in BotW and click `Scan Memory` in the [Memory Editor](https://onedrive.live.com/download?cid=74309C0E337BBADE&resid=74309C0E337BBADE%21333211&authkey=AOErcELM6eb2RHk).

![0030](https://user-images.githubusercontent.com/80713508/147892552-0c0484f0-560c-4ff7-a4d0-df29ce335ea0.png)

In the `Weapons` tab, select any weapon, and change the ID to the `New Actor Name`, then click `Update`.

![0031](https://user-images.githubusercontent.com/80713508/147892556-844cb881-d9f1-4ebc-aa08-df6c76eb2b54.png)

Using the D-Pad, slide over to equip the blank item icon. Upon releasing the D-Pad button, the actor should spawn.

![0032](https://user-images.githubusercontent.com/80713508/147892560-49c6fa7a-ad83-484f-a52a-7d618e4fc2c5.png)

Viola! Your actor should be in the game now!

![0033](https://user-images.githubusercontent.com/80713508/147892563-a4000f40-8626-4be3-aa96-b80f2d3e2e7b.png)

But, something is not quite right. The texture I used was purple, but the model is orange.

Luckily I know how to fix this. And with MTK, it is super easy to test changes.

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Fix the glow Color

Open the model SBFRES and select the material that is glowing the wrong color.

With the desired material selected, go to the `Parameters` tab, scroll down, and look for `const_color0`.

Double click that entry to open the `ParamValueDialog`, double click the colored rectangle to change the color.

![0034](https://user-images.githubusercontent.com/80713508/147892567-f2a82bda-a456-4e43-a18a-c78bac3e8ed1.png)

Save the `Model` SBFRES. (No need to save the `Tex1` if it's unchanged.)

Once saved, run the `bnp` command in MTK; if you use the `-i` switch, the existing mod will get updated.

![0036](https://user-images.githubusercontent.com/80713508/147892571-2291fb28-a22b-443e-8502-f90f2118e8d4.png)

Once the command completes, proceed to test just as before.

![0037](https://user-images.githubusercontent.com/80713508/147892573-06c6631e-994c-4c68-99f6-1ac533f7c9e9.png)

![_blank](https://user-images.githubusercontent.com/80713508/147893127-34fe7881-722d-41b6-9ca4-756b8d96a332.png)

## Common Errors

### Black Textures
This is usually caused when either `Vertex Colors` was not checked when importing or the textures are in the wrong format.

### Invisible Model (With Collision)
This is usually caused when the material is broken, re-importing with a different material should fix this.

### Invisble Model (No Collision)
This is usually caused when something in the SBFRES is named incorrectly. Double-check that the names match those in the `README.yml`.
