# Blunder-addon
# Blunder Add-on for Blender

## Overview

The Blunder Add-on is a custom Blender add-on designed to streamline the process of importing images, setting up scenes, and creating lighting setups. It provides an easy-to-use interface to automate these tasks, making it ideal for artists and developers who need to quickly prepare scenes for rendering or animation.

## Features

- **Clear Scene**: Deletes all objects in the current scene.
- **Import Images as Planes**: Imports images as planes and rotates them for proper orientation.
- **Correct Scale of Planes**: Adjusts the scale of imported planes by a specified factor.
- **Create Preset Cameras**: Adds multiple cameras to the scene with predefined positions and settings.
- **Create Lightbox**: Creates a light-emitting plane to simulate a lightbox effect in the scene.

## Installation

1. Download the add-on script file.
2. Open Blender and go to `Edit` > `Preferences` > `Add-ons`.
3. Click `Install` and select the downloaded add-on script file.
4. Enable the add-on by checking the box next to "Blunder".

## Usage

Once installed and enabled, the Blunder panel will appear in the Sidebar of the 3D Viewport.

### Panel

- **Location**: Sidebar > Blunder
- **Button**: "Create scene" - Executes the main function to set up the scene with imported images, preset cameras, and lightbox.

### Main Function

The main function (`main(context)`) performs the following tasks:
1. Clears the current scene.
2. Imports specified images as planes.
3. Adjusts the scale of the imported planes.
4. Creates preset cameras in the scene.
5. Adds a lightbox to the scene.

### Custom Functions

- **clear_scene()**: Deletes all objects in the current scene.
- **import_images_as_planes(image_paths)**: Imports images from the specified paths and rotates them.
- **correct_scale_of_planes(scale_factor)**: Adjusts the scale of all mesh objects by the given scale factor.
- **create_preset_cameras()**: Adds three cameras to the scene with predefined positions and settings.
- **create_lightbox(location, size, rotation)**: Adds a light-emitting plane to the scene.

## Example

To use the add-on, follow these steps:

1. Ensure the add-on is enabled in Blender.
2. Go to the 3D Viewport and open the Sidebar.
3. Select the "Blunder" tab.
4. Click the "Create scene" button to run the main function and set up your scene.

## Development

### Operators and Panels

- **SimpleOperator**: Operator to execute the main function and set up the scene.
- **VIEW_PT_my_script_panel**: Panel to provide the UI for the add-on in the Sidebar.

### Register and Unregister

The add-on script includes functions to register and unregister the operators and panels:

```python
def register():
    bpy.utils.register_class(SimpleOperator)
    bpy.utils.register_class(VIEW_PT_my_script_panel)
    bpy.types.VIEW3D_MT_object.append(menu_func)

def unregister():
    bpy.utils.unregister_class(SimpleOperator)
    bpy.utils.unregister_class(VIEW_PT_my_script_panel)
    bpy.types.VIEW3D_MT_object.remove(menu_func)
```

## License

This project is licensed under the MIT License.

