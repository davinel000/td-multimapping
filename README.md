# TD-Multimapping Module

TD-Multimapping is a TouchDesigner module designed for advanced keystoning and warping of images across multiple projectors. It extends the functionality of the **Stoner** plugin from the Palette (2022+ versions), offering enhanced mapping capabilities and efficient externalization of mapping settings. By using this module, you can:

- Save and load mapping projects, reducing storage requirements for UV-maps.
- Overlay masks and alignment grids for precise image adjustments.
- Apply additional shift and scaling transformations.

Currently, **hard-edge blending** is supported for edge alignment. **Soft-edge blending** is planned for a future version, either as an update to this module or a higher-level implementation. The module will also migrate to a unified Python script and extensions structure in upcoming updates.

### Use Cases
TD-Multimapping was developed for **Urbanscreen GmbH & Co.** and is actively used in mapping solutions for events and institutional installations.

---

## Setting up the Multibeamer Module

The Multibeamer module consolidates all settings needed for a projector setup. It extends Stoner functionality with optimized tools for storing external projections, applying multiple keystones, and previewing results.

### Steps to Set Up

1. **Add the Tox File and Connect Inputs:**
   - Add the provided `.tox` file to your TouchDesigner project.
   - Connect your **TOP** containing the full image (to be split across projectors) to the input of the Multibeamer module.

2. **Open the Multibeamer Parameters Window:**
   - Use the default hotkey `Ctrl+Shift+M` to open the parameters window.

3. **Creating a Mapping Project:**
   - Navigate to the **"New"** tab.
   - Enter the project name and specify the number of projectors used in your setup.
   - Click **Create**. A new folder will be generated in the `/mapping_settings` directory with all necessary configuration files. The message "Project is ready to use" will confirm the successful setup.
  
![New tab](./screenshots/multimapping%20(1).png)

4. **Setting Resolution and Beamer Layout:**
   - Open the **"Res"** tab and configure:
     - **Fit to Resolution:** Matches your content's width and height to the projector layout. Ensure your content resolution aligns with this setting.
     - **Beamers in a Row:** For a single line, set the total number of projectors. For grids, specify the number of projectors per row (e.g., 3 for a 3x2 grid).
     - **Beamer Resolution:** Specify the overall resolution of your layout. For example:
       - A line of 6 FHD projectors = `11520x1080`.
       - A 3x2 grid = `5760x2160`.
     - **Justify Horizontal/Vertical:** Aligns content based on your system's screen configuration. By default, it's **Right Top**, so ensure your control screen is positioned left (and lower, if applicable) relative to your layout.

![Res tab](./screenshots/multimapping%20(2).png)

5. **Mask, Settings, Calibration:**
   - Open the **"General"** tab:
     - View project info: Number of projectors, project name, and resolution.
     - Toggle mapping/warping and apply custom masks (ensure mask resolution matches your content).
     - Activate **Show Calibration** preview for color adjustments.
     - Use the lower module area to view the projector layout, with optional **Show Numbers** for alignment verification.
     - Add a full grid (visible on all screens) or Stoner grid (visible while using Stoner) for fine-tuning image corrections.

![General tab](./screenshots/multimapping%20(5).png)

6. **Keystoning:**
   - Access the tabs for each projector (e.g., **B1**, **B2**, ..., **BN**).
   - Adjust:     
     - Open the **Stoner** interface for keystone and warp adjustments using a mouse or keyboard for precision.
     - Save settings after finishing adjustments for each projector.
     - Disable calibration, grids, or numbers once setup is complete.
     - **Premapping Transform:** Useful for strongly overlapping projectors; manually set scale, translation, and rotation.
    
![Beamer tab](./screenshots/multimapping%20(4).png)

7. **Opening Previously Saved Mapping:**
   - Go to the **"Open"** tab, click the **+** button, and select a saved project folder. Ensure it contains all necessary projector folders (e.g., `Beamer1`, `Beamer2`, ...). Press **Load**. The message "Project is ready to use" confirms successful loading.

![Open tab](./screenshots/multimapping%20(3).png)

---

## Notes on Beamer Layout Setup

1. **Configure Screen Grid:**
   - Use Windows Display Settings or Nvidia Device Manager for layout setup (linear or grid).
   - Carefully set relative positions of the screens to prevent display misalignment or clipping.

2. **Control Screen Placement:**
   - Position the control screen **to the left** of all projection screens. By default, projections are justified **Right Top**, but this can be adjusted in the Multibeamer settings.

3. **Stabilization (Optional):**
   - If using Nvidia Quadro or similar cards, enable **EDID profiles** for higher stability during projector use.

---

## Current Limitations and Roadmap

- **Soft-edge blending** is not yet supported but is planned for future implementation.
- A major update will migrate the module to a unified **Python extensions** framework for enhanced flexibility and maintainability.

---

## Contact

For inquiries or issues, reach out at **[davinel000@gmail.com](mailto:davinel000@gmail.com)**.
