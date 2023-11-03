# Awesome URDF [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

> A curated list of Unified Robot Description Format (URDF) libraries, tools and resources.

Unified Robot Description Format (URDF) is an XML format for representing some aspects of a robot model, that was initially proposed as part of the [Robot Operating System (ROS)](https://www.ros.org/), but it is now used in several robotics-related tools and software.

See the [official ROS documentation page on URDF](http://wiki.ros.org/urdf) for the official specification and more information about URDF.

## Contents

- [URDF](#urdf)
  - [Libraries](#libraries)
    - [C++](#c)
    - [Python](#python)
    - [MATLAB/Simulink](#matlabsimulink)
    - [Rust](#rust)
    - [Julia](#julia)
  - [Resources](#resources)
  - [Tools](#tools)
- [Community](#community)


## URDF

There is no versioned specification of the URDF format. The main reference for the URDF format are the [ROS wiki docs on URDF](http://wiki.ros.org/urdf).

### Libraries

Libraries to import, export and manipulate URDF files.

#### C++
- [urdfdom](https://github.com/ros/urdfdom) - Reference C++ URDF parser implementation mantained by OpenRobotics. [BSD]
- [sdformat](http://sdformat.org/) - Reference C++ implementation of the SDFormat (Simulation Description Format), used in Gazebo and Ignition libraries that includes a converter (based on `urdfdom`) from URDF to SDF. [APACHE2]
- [iDynTree](https://github.com/robotology/idyntree) - Library for kinematics and dynamics computation of free-floating robot model, with support for import and export of URDF files. It includes Python and MATLAB bindings. [BSD]

#### Python
- [urdf_parser_py](https://github.com/ros/urdf_parser_py) - Reference Python URDF parser mantained by OpenRobotics. [BSD]
- [odio_urdf](https://github.com/hauptmech/odio_urdf) - Library for building URDF files using Python. [MIT]

#### MATLAB/Simulink
- [Simscape Multibody URDF Import](https://mathworks.com/help/physmod/sm/ug/urdf-import.html) - Simscape Multibody is the Multibody simulation environment of MATLAB, that supports importing URDFs. MATLAB docs contain also a useful [URDF primer](https://mathworks.com/help/physmod/sm/ug/urdf-model-import.html) documentation. [Commercial]

#### Rust
- [urdf-rs](https://github.com/openrr/urdf-rs) - URDF parser using [serde-xml-rs](https://github.com/RReverser/serde-xml-rs) for Rust. [APACHE2]

#### Julia
- [MeshCatMechanisms.jl](https://github.com/JuliaRobotics/MeshCatMechanisms.jl) - 3D Visualization of mechanisms and URDFs using [MeshCat.jl](https://github.com/rdeits/MeshCat.jl) and [RigidBodyDynamics.jl](https://github.com/JuliaRobotics/RigidBodyDynamics.jl) . [MIT]

### Resources

- [Awesome Robot Descriptions](https://github.com/robot-descriptions/awesome-robot-descriptions#readme) - A curated list of awesome robot descriptions, most in URDF or Xacro formats.

### Tools

- [xacro](https://github.com/ros/xacro) - Xacro is an XML macro language. With xacro, you can construct shorter and more readable XML files by using macros that expand to larger XML expressions. Xacro is frequently used to mantain URDF models. [BSD]
- [blender-robotics-utils](https://github.com/robotology/blender-robotics-utils) - Set of utilities for exporting/controlling your robot in [Blender](https://www.blender.org/). It includes a URDF to Blender model converter. [BSD]
- [Unity-Technologies/URDF-Importer](https://github.com/Unity-Technologies/URDF-Importer) - URDF Importer allows you to import a robot defined in URDF format in a [Unity scene](https://unity.com). [APACHE]
- [yourdfpy](https://github.com/clemense/yourdfpy) - Library and command-line tool to load, visualize, manipulate, validate and save URDF files.
- [urdf-viz](https://github.com/openrr/urdf-viz) - Visualize URDF/XACRO file, URDF Viewer works on Windows/MacOS/Linux. [APACHE2]
- [Foxglove Studio](https://foxglove.dev/urdf) - Visualization app for web or desktop, supports URDFs as well as arbitrary bag or [MCAP](https://mcap.dev) data. [MPL-2.0]

## Community


- [Robotics StackExchange](https://robotics.stackexchange.com/?tags=urdf) - Questions related to URDF in Robotics StackExchange. 
- [ROS Answers](https://answers.ros.org/questions/scope%3Aall/sort%3Aactivity-desc/tags%3Aurdf/) - Questions related to URDF in ROS.
- [Foxglove Slack community](https://foxglove.dev/slack) - Questions and discussion related to robitics data visualization

## Contribute

Contributions are welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.


## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](http://creativecommons.org/publicdomain/zero/1.0)
