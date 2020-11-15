**This is a custom fork of Harmony used by the Stardew Valley community.** It's bundled with
[SMAPI](https://github.com/Pathoschild/SMAPI) automatically. See
[pardeike/Harmony](https://github.com/pardeike/Harmony) for documentation and usage.

This fork is identical to Harmony 1.2.0.1, except for two changes. First generated method names
include the original type and the patching Harmony IDs to help troubleshoot error logs:
```c#
// with original Harmony
   at resetLocalState_Patch1(Object )
   at StardewValley.GameLocation.<resetForPlayerEntry>b__219_0()
   ...

// with fork
   at StardewValley.Farm.resetLocalState_PatchedBy<Pathoschild.SmallBeachFarm>(Object )
   at StardewValley.GameLocation.<resetForPlayerEntry>b__219_0()
   ...
```

Second `WriteJump()` supports ARM64/AArch64 using jump code from [MonoMod.Common](https://github.com/MonoMod/MonoMod.Common/blob/acfe156306ef8a47630660345013fc222ccf8657/RuntimeDetour/Platforms/Native/DetourNativeARMPlatform.cs#L129-L144), and a copy of the RuntimeInformation
library to detect the processor architecture in older frameworks.

Here's a [list of changes](https://github.com/Pathoschild/Harmony/compare/v1.2.0.1...fork) in the
forked version.
