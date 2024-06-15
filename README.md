# Esri ArcGIS Pro Tool: SmartLinxToFeatureClass

SmartLinxToFeatureClass exports LightPoint devices from SmartLinx Core APIs (https://ats-api.smartlinx.tech/api/v2/) to Esri ArcGIS Feature Class format capturing attributes in the name, coords, core, and metering tables from SmartLinx API. In order to run, a cloned Esri ArcGIS Anaconda Python Environment must be created and additionally aiohttp, and asyncio must be installed within this Python Environment. These additional libraries are required to allow optimized asynchronous calls to the SmartLinx API, which will retrieve all LightPoint devices with all attributes in the SmartLinx name, coords, core, and metering tables. Once the information is retrieved from the SmartLinx API, it is then converted into a csv file, and an Esri ArcGIS Feature Class. Using the tool interface provided in Esri ArcGIS Pro, users can enter the SmartLinx API i.e https://ats-api.smartlinx.tech/api/v2/, their BEARER_TOKEN (which will be provided by SmartLinx to manage access/authentication into the system), and the desired location of the output feature class. 

### Setup Requirments
1. ArcGIS cloned Python env with aiohttp and asyncio installed
2. Bearer_token (provided by SmartLinx)

### Tool Parameters
1. SmartLinx API -> copy here: https://ats-api.smartlinx.tech/api/v2/
2. Bearer Token to SmartLinx API -> as text
3. Output Feature Class Location -> make an output name in an Esri File Geodatabase

### Environment Setup Tutorial
1. Within Esri ArcGIS Pro, Navigate using the Project Button-> Package Manager
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/ab39cfbe-df28-410b-bb8c-04288235c5ff)
2. Within the Package Manager Page, click the gear icon followed by the plus-folder icon (which says clone environment)
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/5492c77f-7a57-4c84-9f6f-371559584120)
A Dialog Box will pop-up stating, "Clone Environment" and provide options for "Source" and "Destination." Leave the "Source" as deault, as it is the original Python environment that is configured to work with ArcGIS Pro, but modify the "Destination" to a location of your choosing (can be the same as the Source Path but with a different ending name i.e if "Source" is C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3, it can be C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3-main). Once you have decided a Path for your clone, Click "Okay". After clicking "Okay" ArcGIS will begin cloning your environment, which will take a little time. Wait a little bit to receieve a confirmation that the clone has been successfully created.
3. After creating the cloned environment, Click the "Active Environment" window, and select the new environment, that was just created. Once we have a cloned environment, we have the ability to modify it i.e add packages. But before we can add packages, it must be set as the "Active Environment" in the ArcGIS Pro window.
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/ce968a41-3e08-4fad-a4a0-0cf894c57d4b)
4. Once you have created your cloned env, and activated it within Esri ArcGIS Package manager, open the windows start panel and navigate to the app "Python Command Prompt"

![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/055d754a-38c2-421f-b50a-1daa6b430973)

5. Enter the app, and a terminal window should open. It is necessary to open this specific terminal, because it is installed with ArcGIS Pro and has access to the ArcGIS anaconda python environments.
You should receive a terminal, resembling the windows below -> That shows it is "active" with the new Esri ArcGIS Pro Env, i.e. the cloned env that was just created. If it says arcgispro-py3 ONLY, and not the name of the one that was just created, please ensure that the cloned environment is showing up in Pro, and that it is set as the "Active Environment."
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/135ca046-be53-4144-92c8-cc8aaec15ce8)
6. Run the command below in the termainl to install aiohttp

```
pip install aiohttp
```

7. Run the command below in the terminal to install asyncio

```
pip install asyncio
```

8. Assuming packages install successfully, exit the terminal window and go back to Esri ArcGIS Pro

### Tool Download / Use in ArcGIS Pro
1. Using the "Download ZIP" button in the Github webpage, download the repo to a location on your harddrive
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/896f03eb-1a6e-465e-9db7-50569f050c9a)

If you know git, can also use git clone:

```
git clone https://github.com/SDGIS/ArcProTool_Smartlinx.git
```

Once you have downloaded the repo, you can proceed to using the tool in ArcGIS Pro.

2. Using ArcGIS Pro Catalog View -> Navigate to the Toolbox SmartLinx.atbx which will be in the location where you downloaded the repo
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/cd53a28a-1dad-4768-a2f2-733ffd2c65af)

3. Double click on SmartLinx toolbox to enter the toolbox, and see that the SmartLinxToFeatureClass tool is within the toolbox
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/843f2701-4fe4-4f0d-900b-cca5bc3b00a0)

4. Double click on the SmartLinxToFeatureClass Tool and the GP Pane will open the tool where you can fill in the parameters.
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/b95ff8c2-bcbe-4ec0-ab07-e3b83af1997d)

5. Fill in the API (https://ats-api.smartlinx.tech/api/v2/), add your Bearer Token from SmartLinx as text, and select an output feature class, and click the Run button in the bottom of the pane. The tool should beginning running, and display messages.
![image](https://github.com/SDGIS/ArcProTool_Smartlinx/assets/42779730/d078d813-e17a-495e-a8e1-524ae599772f)

6. Check your output feature class for your results!







