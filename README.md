# GVR Soundfield bug example

This repo demonstrates an issue with the GVRAudioSoundfield. It has been observed using the GVR 1.30.0 release with Unity 5.5.2f1 on a Windows 10 x64 system. I have not explored different hardware/version configurations.


There are three scenes included, which all share this heirarchy:

.


+-- "Camera Container" GameObject


|   +-- "Main Camera" GameObject


+-- "Soundfield" GameObject

# Object descriptions:
- Camera Container simply contains the Main Camera, it is not necessary to replicate the bug but is necessary for the workaround.
- Main Camera contains the GVRAudioListener
- Soundfield cotains the GVRAudioSoundfield



| Included Scenes | Descriptions |
| ------ | ------ |
| NoRotation | Soundfield rotation Y is set to 0, Container rotation Y set to 0 |
| 180Rotation | Soundfield rotation Y is set to 180, Container rotation Y set to 0 |
| Workaround-180OnCameraContainer | Soundfield rotation Y is set to 0, Container rotation Y set to 180 |

# Explanation

The *180Rotation* scene and the *Workaround-180OnCameraContainer* scenes are expected to play the audio in the same way, because the relative offset between the listener and soundfield is the same. This does not happen however, the *180Rotation* and the *NoRotation* scenes play audio back in the same way.   
