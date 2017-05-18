# Fitboard Reference

This file is for ReGameVR's Unity development for the FITBoard project.

**Contents**

1. [Device Connection Architecture Diagram](Device-Connection-Architecture)
2. [Unity Device Interface](Unity-Device-Interface)

## Device Connection Architecture

// TODO

## Unity Device Interface

```c#
public class FitboardInput
{
	/// <summary>
	/// Gets if key was pressed down this frame.
	/// </summary>
	/// <remarks>
	/// Key was not pressed in last frame but is in this frame
	/// </remarks>
	/// <returns><c>true</c>, if key was pressed down this frame, <c>false</c> otherwise.</returns>
	/// <param name="keyName">Key Name.</param>
	public static bool GetKeyDown (string keyName);

	/// <summary>
	/// Gets if key is pressed this frame.
	/// </summary>
	/// <remarks>
	/// Key was pressed in last frame and still is in this frame
	/// </remarks>
	/// <returns><c>true</c>, if key is pressed in this frame, <c>false</c> otherwise.</returns>
	/// <param name="keyName">Key Name.</param>
	public static bool GetKeyPressed (string keyName);

	/// <summary>
	/// Gets if the key was released this frame.
	/// </summary>
	/// <returns><c>true</c>, if key was released this frame, <c>false</c> otherwise.</returns>
	/// <param name="keyName">Key Name.</param>
	public static bool GetKeyUp (string keyName);

	/// <summary>
	/// Gets any key was pressed down this frame.
	/// </summary>
	/// <remarks>
	/// Key was not pressed in last frame but is in this frame
	/// </remarks>
	/// <returns><c>true</c>, if any key down was gotten, <c>false</c> otherwise.</returns>
	public static bool GetAnyKeyDown ();

	/// <summary>
	/// Gets any key pressed this frame.
	/// </summary>
	/// <remarks>
	/// Key was pressed in last frame and still is in this frame
	/// </remarks>
	/// <returns><c>true</c>, if any key pressed was gotten, <c>false</c> otherwise.</returns>
	public static bool GetAnyKeyPressed ();

	/// <summary>
	/// Gets any key released this frame.
	/// </summary>
	/// <returns><c>true</c>, if any key up was gotten, <c>false</c> otherwise.</returns>
	public static bool GetAnyKeyUp ();
}
```
