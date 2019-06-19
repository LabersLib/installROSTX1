# installROSTX1
Install Robot Operating System (ROS) on NVIDIA Jetson TX1

These scripts will install Robot Operating System (ROS) on the NVIDIA Jetson TX1 development kit.

For L4T 28.2 (JetPack 3.2)

See releases or tags for earlier versions.

The script is based on the Ubuntu ARM install of ROS Kinetic: http://wiki.ros.org/kinetic/Installation/Ubuntu

Maintainer of ARM builds for ROS is http://answers.ros.org/users/1034/ahendrix/

There are two scripts:

<strong>installROS.sh</strong>
<pre>
Usage: ./installROS.sh  [[-p package] | [-h]]
 -p | --package &lt;packagename&gt;  ROS package to install
                               Multiple Usage allowed
                               The first package should be a base package. One of the following:
                                 ros-kinetic-ros-base
                                 ros-kinetic-desktop
                                 ros-kinetic-desktop-full
 </pre>
 
Default is ros-kinetic-ros-base if no packages are specified.

Example Usage:

$ ./installROS.sh -p ros-kinetic-desktop -p ros-kinetic-rgbd-launch

This script installs a baseline ROS environment. There are several tasks:

<ul>
<li>Enable repositories universe, multiverse, and restricted</li>
<li>Adds the ROS sources list</li>
<li>Sets the needed keys</li>
<li>Loads specified ROS packages, defaults to ros-kinetic-base-ros if none specified</li>
<li>Initializes rosdep</li>
</ul>

You can edit this file to add the ROS packages for your application. 

<strong>setupCatkinWorkspace.sh</strong>
Usage:

$ ./setupCatkinWorkspace.sh [optionalWorkspaceName]

where optionalWorkspaceName is the name of the workspace to be used. The default workspace name is catkin_ws. This script also sets up some ROS environment variables. Refer to the script for details.

<em><b>Note:</b> On June 7, 2019 the GPG key for ROS was changed due to security issues. If you have ROS installed on your system before this, you should delete the GPG key:</em>
 
<pre>
$ sudo apt-key del 421C365BD9FF1F717815A3895523BAEEB01FA116
</pre> 


## Release Notes
<strong>June 2019</strong>
* L4T 28.2 (JetPack 3.2)
* Update ROS GPG key

<strong>April 2018</strong>
* -vL4T28.2
* L4T 28.2 (JetPack 3.2)
* Unify with Jetson TX2 release

<strong>October 2016</strong>
* Initial Release 
* vL4T24.2.1
* L4T 24.2.1 (JetPack 3.0)

## License
MIT License

Copyright (c) 2017-2018 Jetsonhacks

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
 
