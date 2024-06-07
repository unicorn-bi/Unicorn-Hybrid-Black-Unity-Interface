# Documentation
This section provides structural descriptions of the BCI system in unity. Each prefab provided is designed to facilitate various aspects of BCI integration and visualization in Unity projects. For beginners, it is recommended to design your BCI application with the help of provided prefabs.

## BCI System Design Hierarchy


### Overview
The BCI system is structured to provide a flexible and modular approach for integrating various brain-computer interaction components. The hierarchy is designed to accommodate a single device to configure and process multiple pipelines, enableing users to tailor the system to their specific needs. 

### Hierarchy Diagram
<p align="center">
<img src="../Img/BCIsystemDesign4.png" alt="drawing" width="800"/><br/>
</p>

### Description
The diagram above illustrates the hierarchical structure of the BCI system. Here is a breakdown of each component and its role withint the hierarchy.

- **BCI Base / BCI Visual ERP 3D**: This is the root component that serves as the foundation of the entire BCI system. 
    > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\BCI`
    - **UI Bar**: A user interface element that provides control display options for the BCI system.
    - **Device**: The core component responsible for managing the connection to the **Unicorn Hybrid Black** device.
        > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Device`
        - **Pipelines**: The container for all processing pipelines. Users can add multiple pipelines under this node.
            - **Signal Qaulity Pipeline**: Process the quality of the EEG signal received from the unicorn hybrid black.
                > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\SignalQuality`
                - **Signal Quality UI**: Displays the signal quality information on the game UI.
            - **EEGData Pipeline**: Get the raw datastream / re-processed EEG datastream at defined update rate.
                > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\EEGData`
            - **ERP Pipeline**: Processes event related potentials.
                > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\ERP`
                - **ERP Pipeline UI**: A UI for displaying the training result.
                - **ERP Paradigm**: Manage the ERP Pipeline configuration, used in conjunction with ERP Pipeline.
                    - **ERP Tags**: The container for gameobjects used within ERP Paradigm for presenting the stimuli.
                        - **ERP Flash Object**: An object used for presenting stimulation.
                            > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\ERP`
                            -**ERP Feedback tag**: A game object with a defined feedback system for visualizing the BCI command in realtime.
                                > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\ERP\ERPFeedbackTags`
                    - **ERP Paradigm UI**: A UI for controlling the start / stop of the ERPPipeline.
                        > Prefab Reference Location: `Assets\gtec\Unity Interface\Prefabs\Pipelines\ERP\ERPTags`
                

        - **Device UI**: The user interface for interacting with the unicorn hybrid black device