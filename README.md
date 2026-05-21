<div align="center">

<a href="https://www.sofa-framework.org/">
  <img src="https://www.sofa-framework.org/wp-content/uploads/2013/01/SOFA_LOGO_ORANGE_2-normal.png" alt="SOFA Framework" height="85"/>
</a>
&nbsp;&nbsp;&nbsp;&nbsp;
<a href="https://stereokit.net/">
  <img src="https://github.com/StereoKit/StereoKit/blob/master/tools/img/StereoKitWideBackground.svg" alt="StereoKit" height="85"/>
</a>

# SofaStereoKit

**Real-time multi-physics simulation with SOFA, rendered and interacted with in StereoKit.**

<br/>

[![SOFA](https://img.shields.io/badge/SOFA-simulation-orange.svg)](https://github.com/sofa-framework/sofa)
[![StereoKit](https://img.shields.io/badge/StereoKit-XR-blueviolet.svg)](https://github.com/StereoKit/StereoKit)
[![OpenXR](https://img.shields.io/badge/OpenXR-ready-brightgreen.svg)](https://www.khronos.org/openxr/)
[![Status](https://img.shields.io/badge/status-experimental-orange.svg)]()

</div>

## What is SofaStereoKit

**SofaStereoKit** is a binding layer between [SOFA](https://github.com/sofa-framework/sofa) and [StereoKit](https://github.com/StereoKit/StereoKit).

SOFA provides real-time physics simulation, with an emphasis on medical simulation, robotics, deformable bodies, FEM, constraints, solvers, and collision models.

StereoKit provides a lightweight OpenXR application framework for building mixed reality, virtual reality, and spatial computing experiences in C#.

SofaStereoKit connects both worlds:

- SOFA computes the simulation
- StereoKit renders the scene in XR
- StereoKit input can interact with SOFA objects
- SOFA scenes can become immersive medical and robotic simulations

## Why

SOFA is often used as a standalone simulation tool, but it is also a set of libraries that can be integrated into other projects.

StereoKit is designed for simple, direct XR development.

SofaStereoKit aims to make SOFA simulations visible, interactive, and spatial through StereoKit.

## Minimal example

```csharp
using StereoKit;
using SofaStereoKit;

SK.Initialize();

var sofa = new SofaRuntime();
sofa.LoadScene("scene.scn");

SK.Run(() =>
{
    sofa.Step(Time.Elapsedf);
    sofa.Draw();
});
```

## Repository layout

```text
SofaStereoKit/
├─ src/
│  ├─ native/      # SOFA native bridge
│  ├─ csharp/      # C# bindings for StereoKit
│  └─ interop/     # shared interop types
├─ samples/        # StereoKit samples
├─ docs/           # notes and assets
└─ README.md
```

## Requirements

- [SOFA](https://github.com/sofa-framework/sofa)
- [StereoKit](https://github.com/StereoKit/StereoKit)
- CMake
- C++ compiler
- .NET SDK
- OpenXR runtime

## Build

```bash
git clone https://github.com/YOUR_USERNAME/SofaStereoKit.git
cd SofaStereoKit

cmake -B build -S . -DSOFA_ROOT=/path/to/sofa
cmake --build build --config Release
```

## References

- [SOFA Framework](https://www.sofa-framework.org/)
- [SOFA GitHub](https://github.com/sofa-framework/sofa)
- [SOFA Documentation](https://www.sofa-framework.org/community/doc/)
- [StereoKit Website](https://stereokit.net/)
- [StereoKit GitHub](https://github.com/StereoKit/StereoKit)

## License

This project must define its own license.

SOFA and StereoKit keep their own licenses. Please review their license terms before redistributing binaries or integrating this project into commercial software.

---

<div align="center">

**SofaStereoKit**  
SOFA simulation, StereoKit interaction.

</div>
