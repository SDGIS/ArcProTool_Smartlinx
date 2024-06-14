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
1. Using git clone or the download button in the Github webpage, download the repo to a location on your harddrive
2. Using Catalog View -> Add Folder Connection (make the new folder visible to ArcGIS Pro)
3. Open the toolbox within double click on the Scipt Tool, named "SmartLinxToFeatureClass" which will open the tool dialog interface
4. Fill in the tool parameters, and Run the tool.



