## URDF Extensions

Unfortunately the official URDF specification does not provide any facility to clearly define "extensions" to the URDF, i.e. XML code that is defined inline in URDF XML, but that is not part of the official tags defined in the spec, as for example is done in SDF: http://sdformat.org/tutorials?tut=custom_elements_attributes_proposal&ver=1.7&cat=pose_semantics_docs& . 

However, there are a bunch of URDF parsers that define their own extensions to add some functionalities. What is happening when a URDF parser does not support a given extension, as nothing is specified in the extension, is the extension is simply ignored. 

Extensions:


### `urdf-ext-gazebo`

The `<gazebo>` tags: This is an element that is originated as way to embed Gazebo-specific extensions in URDF, but despite the name of the tag the related code is contained in the `sdformat` library. 



Documentation: https://classic.gazebosim.org/tutorials?tut=ros_urdf .
Code: https://github.com/gazebosim/sdformat/blob/4ebe022c231b6b46ee56ad46ecbabc8f3e9aa534/src/parser.cc#L1353 .

##### Closed loop support

Among the different features supported, this extensions also permits to specify closed loops, see for example https://classic.gazebosim.org/tutorials?tut=kinematic_loop&cat=#Split4-barlinkageinURDFwithanSDFormatfixedjoint : 

~~~xml
 <gazebo>
    <joint name="joint_E" type="fixed">
      <pose>-0.1 -0.01 0 0 0 0</pose>
      <parent>link_BE</parent>
      <child>link_EC</child>
    </joint>
  </gazebo>
</robot>
~~~

 
> [!WARNING]  
> The `joint` element that is contained inside the `<gazebo>` tag is an SDF `joint` element, not a URDF one. The equivalent URDF joint would be:
> ~~~xml
> <joint name="joint_E" type="fixed">
>   <parent link="link_BE"/>
>   <child link="link_EC"/>
>   <origin xyz="-0.1 -0.01 0" rpy="0 0 0"/>
> </joint>
> ~~~

### `urdf-ext-idyntree`

The `idyntree` multibody dynamics library URDF loader support loading sensor information from `<sensor>` tag. The used semantics and attributes is similar (but with some difference) with the one described in http://wiki.ros.org/urdf/XML/sensor .

Documentation: https://github.com/robotology/idyntree/blob/v13.1.1/doc/model_loading.md#sensor-extensions . 
Code: https://github.com/robotology/idyntree/blob/v13.1.1/src/model_io/codecs/src/SensorElement.cpp .

### `urdf-ext-drake`

The `drake` library URDF loader supports various extension to set in URDF some drake-specific parameters

Documentation: https://drake.mit.edu/doxygen_cxx/group__multibody__parsing.html#multibody_parsing_drake_extensions .
Code: https://github.com/RobotLocomotion/drake/tree/v1.35.0/multibody/parsing

### `urdf-ext-mujoco`

The `mujoco` library URDF loader supports various extension to set in URDF some mujoco-specific parameters

Documentation: https://mujoco.readthedocs.io/en/stable/modeling.html#curdf
Code: https://github.com/google-deepmind/mujoco/blob/3.2.5/src/xml/xml_urdf.cc

### `urdf-ext-mit-biomimetics` 

The Biomimetic Robotics Lab at MIT define its own extensions that they call `URDF+`, that permits to define closed loops in URDF. From the code point of view, they developed a fork on the official libraries `urdfdom_headers` and `urdfdom`.

Documentation: `URDF+` paper at Humanoids 2024, not sure if it is public.
Code: https://github.com/mit-biomimetics/urdfdom_headers, https://github.com/mit-biomimetics/urdfdom


##### Closed loop support

The main point of the MIT Biomimetic lab extension is indeed the definition of closed loop joints, that can be defined as:

~~~xml
 <gazebo>
    <joint name="joint_E" type="fixed">
      <pose>-0.1 -0.01 0 0 0 0</pose>
      <parent>link_BE</parent>
      <child>link_EC</child>
    </joint>
  </gazebo>
</robot>
~~~
