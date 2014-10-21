## Installing the Unity Plugin ##
1. Import the SuperMighty Package (MightyIO-Unity.unitypackage)
2. From the MightyIO folder in the 'Project' window of your game, find the SMPlugin Prefab
3. Select the scene you wish to add SM to from the MightyIO folder, drag the SMRibbon Prefab onto your stage
4. Create a new Layer: "SMRibbon"
5. Set SMPlugin to be on the layer (allow all children to change to this layer as well), SMRibbon
6. Click on the SMRibbon Prefab in your scene, change 'Auth Token' to your auth token (found in your user dashboard).
7. Set SuperMightyCam > Culling Mask to 'SMRibbon'
8. Switch to iOS Platform for your build
9. Open Player Settings, set the 'Target Xcode Version' to '6.0' or greater and set your bundle identifier.
10. Build the iOS version!

