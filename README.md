# Align Characters to the Underground in UE4

## Introduction
Embedded in an example project you will find a method that aligns the player-character to the underground/the surface he walks on. So if the player walks up a ramp, the character will be accordingly tilted.
![A screenshot of the tilted character in Unreal Editor](http://i.imgur.com/PjJDX3q.jpg)

## Technical overview
To get the desired effect, a line will be traced downwards from the players position, upon the hit event the character gets aligned to the normal vector of the surface he is standing on.

## Usage
For using the method, it has to be bound to a event. In case of the example, it is called every framed via the Tick-Event, but it can also get assigned to a buton input or collision events:

1. Navigate to ActorAlignment\Source\ActorAlignment and open the ActorAlignmentCharacter.cpp.
2. In Line 136 you'll find the method Tick, which is called every frame an aligns the character.
  - every frame, a SingleLineTrace is performed
  - from the following hit event, the normmal vector of the underground gets picked
  - via CrossProduct we get the new vectors
  - the character receives a vector transformation which aligns him to the underground
3. As mentioned above, the method can be bound to other events like OnTouchBegin or OnActorBeginOverlap.

![A screenshot of the tilted character in Unreal Editor](http://i.imgur.com/xK43YyH.jpg)



