# Unreal-Snow-Deformation
Snow Deformation BluePrint for Unreal Engine 4

Code Roy Massaad

License MIT 


**Description:**

This is a BluePrint system i put in together in 2016 to enable snow deformation

Last tested and still working on Unreal Engine 4.25.3


**What is in the repository:**

-Sample Project with 1 level using a third person game controller


**Features of Snow blueprint:**

-Supports flat and curved surfaces

-Supports multiple objects deforming the snow surface objects



**How to test it:**

-Clone the repository and open it with Unreal engine, it has all needed files


**What should i look for to figure out how it works:**

-The 2 different blueprint classes of the surfaces and objects affecting them, in addition to the textures, render targets and materials used by them. ( 1 BP for the character, 2 for 2 spheres + 3 for 3 snow surfaces)


**How does the snow deformation system work ?**

-Some objects can deform snow, some objects act as snow surfaces 

-Both objects that can deform and the snow surfaces that can be deformed have different Blueprints that defines them as such allow them to do this

-The snow surfaces material have a dynamic depth normal map that can be edited by other other objects with bluerpints (texture, material, material instance)

-Under each objects that deform snow, there is camera underneath that is tracking their depth shape from underneath (feet, ball bottom..) and it saves this data in a render target

-The objects that can deform snow emits a trace line that goes down, if it hits a snow surface, it can affect its height map by calculating where the UV hit collided, then it draws/merges the camera's render target depth image on the snow surface material in the exact hit location with proper orientation and scaling, effectively editing its depth normal map dynamically

-The blueprints expose variable properties that help tune this, such as strength of impact depth+snow normal merger, length of tracing beam..


**What needs to be improved:**

-Smoother deformation (i tried to blend it with another material, but just barely smoothed it)

-Testing performance on a large scene

-The BP code hasnt been updated since 2016, it needs to be revised and improved

-Better Snow material, i did a quick one for this test

-Maybe its best to do this in C++ instead of BP










