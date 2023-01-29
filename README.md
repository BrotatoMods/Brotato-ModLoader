# Brotato-ModLoader

**Brotato PCK using the latest version of [ModLoader](https://github.com/GodotModding/godot-mod-loader), v2.0.0.**

## Using Mods

 <details>
 <summary><b>Installation</b></summary>
 
 <br />
 
>  ### ⚙ Installation ⚙
>  
> - Download the latest PCK from the [Releases page](https://github.com/BrotatoMods/Brotato-ModLoader/releases). The PCK will be under "Assets" and have the file etxension ".pck".
>
> - Rename the PCK to `ModLoader.pck`
>
> - Copy the ``ModLoader.pck`` and the ``run.gd`` inside the Brotato game folder   
> ![image](https://user-images.githubusercontent.com/41547570/209873722-64bd0388-1a2b-4c67-88d7-3b83499f7466.png)
>
> - Create a ``mods`` folder at the same location   
> ![image](https://user-images.githubusercontent.com/41547570/209873160-5fed6b66-52d3-4ee8-86d4-f752aa44b89e.png)
> 
> - Inside Steam add the following start options to Brotato   
> ![image](https://user-images.githubusercontent.com/41547570/209873529-0094e4f9-2326-4075-8352-42961c0c2980.png)   
> ![image](https://user-images.githubusercontent.com/41547570/209873571-dba1fbf1-9a30-48af-9d8d-56aee4ef5ccd.png)   
> ``--enable-mods --main-pack ModLoader.pck --script run.gd``
> 
> - Add mod zips to your "mods" folder. There's no need to unzip them, just drop them into "mods".   
>    ![image](https://user-images.githubusercontent.com/41547570/209873887-cd37f093-0bdd-47ca-b21a-6b4f96098df0.png)
>    - Note that some mods have dependencies, eg [Invasion](https://github.com/BrotatoMods/Brotato-Invasion-Mod) depends on [ContentLoader](https://github.com/BrotatoMods/Brotato-ContentLoader).
>    - This just means that to use one, you have to have the other.
>    - You can check dependencies by opening the mod zip, going into "mods-unpacked" then the mod folder name, and checking "\_meta.json"
> 
> 
> - Launch the game 🚀

 </details>
 
 <details>
 <summary><b>Help</b></summary>
   
<br />

> ### :interrobang: Help :interrobang:
>
> If you get stuck you can ask for help in the [Space Potatoes Discord](https://discord.gg/j39jE6k)   
> Make sure to read the **modding-faq** and verify that you read it by clicking the check emote.   
> ![image](https://user-images.githubusercontent.com/41547570/211566790-5611494b-f2f9-4cd3-b7b6-64cd7de3b816.png)   
> ![image](https://user-images.githubusercontent.com/41547570/211566842-0b8c0957-1438-4dfc-8e98-8d7a608bc29b.png)   
> 
> After that go to ``#modding-help`` and ask away :thumbsup:   
> ![image](https://user-images.githubusercontent.com/41547570/211572905-56081f0b-26c9-4fbb-849d-f5f6cd74eb0f.png)

 </details>

## Creating Mods

 <details>
 <summary><b>Documentation</b></summary>
 
 <br />
 
 > - For general information on how to use the Mod Loader check the [Godot Modding Readme](https://github.com/GodotModding/godot-mod-loader).
 > - In the near future we will provide detailed and Brotato specific documentation here.
  
 </details>
 
 <details>
 <summary><b>Help</b></summary>
   
<br />

> We are happy to chat in the [Space Potatoes Discord](https://discord.gg/j39jE6k)   
> Make sure to read the **modding-faq** and verify it by clicking the check emote.   
> ![image](https://user-images.githubusercontent.com/41547570/211566790-5611494b-f2f9-4cd3-b7b6-64cd7de3b816.png)   
> ![image](https://user-images.githubusercontent.com/41547570/211566842-0b8c0957-1438-4dfc-8e98-8d7a608bc29b.png)   
> 
> After that we welcome you in ``#modding-dev`` :thumbsup:   
> ![image](https://user-images.githubusercontent.com/41547570/211591351-a3733080-f952-4165-8ad4-f400ea80e26d.png)


 </details>

### Available Mods

See the main [BrotatoMods GitHub page](https://github.com/BrotatoMods) for the current list of compatible mods.

### Example Mods

Download some example mods from [BrotatoMods/Brotato-Example-Mods](https://github.com/BrotatoMods/Brotato-Example-Mods).

