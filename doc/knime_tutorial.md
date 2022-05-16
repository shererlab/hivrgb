KNIME Image processing tutorial
===

## 1. Download and install KNIME

Visit www.knime.com and download KNIME for your platform (Windows, MacOS and Linux are supported).

![KNIME Homepage](images/00_knime_website.png)

## 2. Launch KNIME

Launch KNIME and setup up your workspace directory. This directory will store the workflow associated files.

![KNIME Workspace](images/01a_knime_workspace.png)

KNIME will open with several side panels along with a  welcome screen. How to use each of these panels is beyond the scope of this tutorial. For more information on editing/developing workflows please visit the [KNIME development documentation](https://www.knime.com/learning). In this tutorial we will use the `KNIME Explorer` side panel to select and load a workflow.

![First launch](images/01_knime_welcome.png)

## 3. Load a workflow

You can load the NR-SAT the workflow by visiting the KNIME hub at [hub.knime.com](https://hub.knime.com) and search for `NR-SAT`. Then using the "Drag Workflow" feature to drag the workflow into the `KNIME Explorer` side panel. Alternatively you can access the NR-SAT from the HIV RGB GitHub repository at [github.com/shererlab/hivrgb](https://github.com/shererlab/hivrgb). The NR-SAT workflow and sample data (Supplementary Data File 2 and 3 respectively) are also included with the the HIV RGB publication. The workflow can also be downloaded and directly imported into KNIME (**File** > **Import KNIME Workflow...**).

Once the workflow as been added to the KNIME workspace, double click the workflow to open and load it.

![KNIME imported workflow](images/02b_knime_explorer.png)

Before you can begin using the NR-SAT workflow, several dependencies need to be resolved. Click `Yes` to automatically install most of the required extensions.

![Missing extensions](images/02_knime_extensions.png)


A new window will display which packages are being installed and their associated details.

![Install dependencies](images/02a_install_dependencies.png)

After installing the `KNIME Image Processing` extensions you may receive a "Restart KNIME" notification. Click `Restart Now` and continue the tutorial after KNIME has successfully started again.

![Reboot](images/02c_knime_reboot.png)

```
Note that you may receive an error indicating that ImageJ Macro was not found. Click OK and continue with the tutorial. The ImageJ integration steps below will resolve this issue.
```

![Missing extensions error](images/03_knime_extensions_error.png)

Before you can run the NR-SAT workflow, ImageJ integration must be manually enabled. Click **Help** > **Install New Software...** to open the software management window.

![Install new software](images/04_1_knime_add_software.png)

Next click the **Manage...** (red arrow) to open the software sources management window.

![Add software](images/04_knime_add_software.png)

Click the check box next to the `KNIME Community Extensions (Experimental)` software site (red arrow). To accept this settings click **Apply and Close**.

![Community extensions](images/05_knime_community_extensions.png)

Back in the "Available Software" window select `--All Available Sites--` in the `Work with:` pull down menu. 

![Available sites pulldown](images/06a_knime_pulldown.png)

Next search for `imagej` in the search bar and select the `KNIME Image Processing - ImageJ Integration (Beta)` and install the software package by clicking **Next** and **Finish** after accepting the software licenses. You may be prompted again to restart KNIME.

![ImageJ integration](images/06_knime_imagej_integration.png)

## 4. Load data into the workflow

To load data into the workflow, right click the first node `Initialize workflow` in the "Folder selection" box and click **Configure...**.

![Folder configuration](images/08_knime_folder_config.png)

Enter the path to the **folder** containing your data then click **OK**.

```
Note: The data file needs to be in its own folder. The NR-SAT workflow will fail to run if you select the image file itself.
```

![Folder selection](images/09_knime_folder_selection.png)

The workflow is now ready to run.

## 5. Running the workflow

To run workflows click either the single green play button (runs only the selected node and the nodes before the selected node) or the double green play button (runs all nodes in the workflow).

![KNIME run buttons](images/11_knime_run_buttons.png)

Once your workflow has completed, each node should have a green status. If an error has occurred, look for red nodes with an error icon.

![KNIME complete workflow](images/12_knime_complete_workflow.png)

If you are unable to get any output data, check the last two output nodes. If they are red they need to be configured with the correct output directory.

![KNIME output nodes](images/13_knime_output_nodes.png)


## 5. Viewing the workflow progress

With most nodes you can view the current state of the data by right clicking the node and selecting **View: Image Viewer**. This will open up a window with the image data and its current processing state (_e.g._ a binary image). You can also utilize the viewers at the bottom of the workflow to check the input data (before any processing is done), the cytoplasmic segmentation and nuclear segmentation.

![KNIME Viewers](images/14_viewers.png)

Right click one of the viewers and select **View: Interactive Segmentation View**.

![KNIME Viewer 2](images/14a_viewer.png)

In the interactive segmentation view, double click on either the `Image` or `Labeling` category to open the image inspection window.

![KNIME interactive seg view](images/14b_viewers.png)

![KNIME seg result](images/14c_viewers.png)