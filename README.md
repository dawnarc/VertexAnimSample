
# Overview

The reason why I created this project:

The example project [VertexAnimSample - Box.com](https://epicgames.box.com/s/qlzveuyov93p9a00gjbiftim1yy207ew) that was provided by official document ([Baking out vertex animation in editor with AnimToTexture](https://dev.epicgames.com/community/learning/tutorials/daE9/unreal-engine-baking-out-vertex-animation-in-editor-with-animtotexture)) was obsolete, there're some serious issues haven't been addressed, but Epic doesn't update the example, the Editor Utility Wdiget in the origin project can't be run properly.

# Content

This's an UE5 project to demonstrate VAT: Bake bone (SkeletalMesh) animation into Vertex Animation Texture, and play animation using material (the main work is running in vertex shader) of StaticMesh.

# How to run

> [!IMPORTANT]  
> Make sure plugin `AnimToTexture` has been enabled in your project.

1. EUW_VAT_Utils is an Editor Utility Widget bake Vertex Animation Textures automatically, credit to [AnimToTextureHelpers](https://github.com/kromond/AnimToTextureHelpers).  
![01](./img/01.png)
> [!WARNING]  
> The origin EUW_VAT_Utils only works in UE5.1, I fixed some issues to make it workable in UE5.3.

2. Create a replica from your origin assets, because the material will be interpolated by EUW_VAT_Utils automatically.  
![02](./img/02.png)

3. Then locate to the directory of plugin content: /AnimToTexture/Characters/Mannequin/Materials/BoneAnimation/  
![03](./img/03.png)

	Copy the these three nodes below.  
	![04](./img/04.png)

	Paste into your material:  
	![05](./img/05.png)

	Final result:  
	![06](./img/06.png)

4. Change the material's reference of SkeletalMesh asset.  
![07](./img/07.png)  
![08](./img/08.png)

5. Right click EUW_VAT_Utils to run the widget.  
![09](./img/09.png)

	Setup the parameters, and click Do All.  
	![10](./img/10.png)

A moment later, Vertex Animation Textures have been generated.  
![11](./img/11.png)  
![13](./img/13.png)

	And the materials has been tweaked automatically.  
	![12](./img/12.png)  

	Final effect:  
	![14](./img/14.gif)

6. Because we baked multiple animation assets at once before, so we can switch animation by Material Parameter.  
![15](./img/15.png)  
![16](./img/16.gif)

	![17](./img/17.png)  
	![18](./img/18.gif)

	How to get the animation frame length of an animation?  
	check the `Number of Sampled Keys` of AnimSequence.  
	![18](./img/19.png)

# References

AnimToTextureHelpers (EUW_VAT_Utils)  
