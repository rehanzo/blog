---
layout: post
title:  "Tiling WM Workspace Management Sucks"
categories: tech
permalink: tiling-wm-ws-management-sucks
---
{: .first-image}
![Tiling WM Abstract](/assets/tiling-wm-abstract.png)

Tiling WM workspace management sucks.

I have been using tiling window managers since 2019, first starting out with BSPWM, eventually moving onto Sway, and now use Hyprland. The workspace management for these, and the majority of other window managers feel as though they are made for robots, rather than humans.

These window managers use a system that ties numbers to workspaces; there are other ways they can be used, but this is generally the default. Pressing the windows key, along with any of the keys 0-9 will open its respective workspace (besides 0, which opens workspace 10). So, windows+1 opens the first, windows+2 opens the second, etc. Generally, adding the shift key to the key combination moves a window; windows+Shift+1 moves the active window to workspace 1, windows+Shift+2 moves the active window to workspace 2, etc.

Before delving deeper, I'd like to point out that there are particular workflows that this system of workspace management lends itself well to. For example, you might have specific workspaces hold a specific application and only that specific application. If you hold your terminals in workspace 1, your browser in workspace 2, and your music player in workspace 3, then it works great. The reason being is that you think of it not as workspace 1, 2, or 3, but as the terminal workspace, the browser workspace, and the music workspace, respectively. Your muscle memory links to this, your mind basically ignoring the numbers. 

However, I, and I suspect many others, do not use this workflow. Instead, we use a more dynamic workflow, opening and closing workspaces on the fly for various tasks. With this more dynamic workflow, where different workspaces hold different groups of windows at different times, you end up associating the workspaces with their respective numbers. This then requires you to keep track of these numbers to move around and manipulate workspaces. Having to dedicate focus to this bureaucratic task of keeping track of these numbers demands certain level of attention, pulling you away from actually using your computer.

Another issue I had with this style of workspace management was that it limits the way you styled your status bar. My optimal styling represents workspaces as dots. I also like it minimal, which entails representing just the occupied workspaces. Using both design elements at once is basically not possible. If you do, you won't know which number is tied to which workspace, which is essential. So its either I have dots representing the workspaces, but have all workspaces 1-10 present in the bar at all times, or have numbers represent them in the bar. I got fed up with this and ended up modifying the Waybar source code and making a [PR](https://github.com/Alexays/Waybar/pull/2617), adding a feature to show all workspaces prior to the last active or occupied workspace. This worked in ameliorating this particular qualm, but the rest of the downsides remained.

A substantially better workflow, and one that I employ currently with the help of a certain program, is a spatially focused one. Instead of workspaces tightly bound to numbers, they instead exist relative to eachother. To go to another workspace, I move in its direction, left or right. If a workspace becomes empty in between two others, this workspace is closed and ignored, moving the currently occupied workspaces beside eachother. I've found that his workflow requires significantly less attention to handle, allowing me to basically forget about its management, and I'm able to spend more attention and focus on actually using my computer.

The tool I use is called hyprnome, created by someone who seemed to share my thought process. This is how discovered that gnome has a similar workflow to the one I have currently. I have open PRs that add features to this program, one of which is the ability to create workspaces inbetween others. I'll likely write another post detailing the implementation of that. Shout out to the author of the plugin. You can find hyprnome 
[here](https://github.com/donovanglover/hyprnome) and the authors personal website [here](https://donovan.is).
