# UE4PyServer
<h2>Unreal Engine Python Plugin</h2>
<h3>Installation: (Tested only on Linux but should work on other platforms as well)</h3><br/>
<h4>Prerequisites</h4>
- Unreal Engine for Linux installation:  <a href="https://wiki.unrealengine.com/Building_On_Linux">UE4</a><br/>
- Python 3.x installation<br/>
For the purpose of the demo, I installed Python 3.5 Anaconda <a href="https://www.continuum.io/downloads" >Anaconda</a>. <br/>
<h4>Prerequisites For Optical-Flow Demo</h4>
- OpenCV for Python 3<br/>
conda install -c menpo opencv3<br/>
- numpy<br/>
conda install numpy 

<h4>Plugin Setup</h4>
- Create a project in unreal engine:<br/>
- Add an empty c++ class so the project will be a code project<br/>
- Close the project<br/>
- In the project dir create Plugins dir<br/>
- Clone UE4PyServer into that dir<br/>
git clone  https://github.com/orig74/UE4PyServer.git<br/>
- cd to:  [ProjectPath]/Plugins/UE4PyServer/Source/PyServer<br/>
- run: <br/>
python config.py --entry_point \<your entry point\><br/>
for the test demo run:<br/>
python config.py --entry_point track_test
- run:<br/>
python build.py --ue4path=\<unreal engine dir PATH\><br/>
or (if you are using other python distribution)<br/>
python3 build.py --ue4path=\<unreal engine dir PATH\><br/>
- Open your project and enable the plugin:<br/>
goto Edit->Plugins and enable the PyServer Plugin (under other).<br/>

<h4>Running minimal example:</h4>
- Set entry point for the minimal file<br/>
python config.py --entry_point minimal<br/>
the minimal file is minimal.py<br/>
- Add "PyServerTickActor":<br/>
Press the Plugin button PyServer. PyServerTickActor will appear in the Outliner panel on the right.<br/>
- Play:<br/>
Press the play button in Play button in the Toolbar. <br/>

<h4> working in your own directory:</h4>
run:<br/>
python config.py --entry_point \< your entrypoint module \> --entry_path  \< module path \> <br/>
The entry_point tells the module where the main_loop function exists. If the entrypoint file does not exists, it is created with the functions main_loop and the function kill.<br/>

<h4>Running The Demo:</h4>
The demo is "Lucas-Kanade optical flow tracking" from OpenCV library. <br/>
- Add Camera CameraActor_2  and a WindDirectionalSource:<br/>
In the Modes Pannel in the Place Tab add a Camera Actor. Change The name of the actor to "CameraActor_2".<br/>
In the Modes Pannel in the Place Tab add a WindDirectionalSource. Change The name to "WindDirectionalSource1"<br/>
- Add "PyServerTickActor":<br/>
Press the Plugin button PyServer. PyServerTickActor will appear in the Outliner panel on the right.<br/>
- Play:<br/>
Press the play button in Play button in the Toolbar. The supporting modes for this demo are:  "Selected ViewPort"  and "New Editor Window" <br/>
Focus on the engine window to get 30 fps!!<br/>
Watch demo on: <a href="https://youtu.be/ydBFlI_fhso">demo</a><br/>
- More Demos:<br/>
This <a href="https://youtu.be/nXu6NCOoIRQ">demo</a> uses a SceneCapture2D and a Render Target to play inside an OpenCV window.<br/>
Another <a href="https://youtu.be/oNB7iSDiUX0">demo</a> uses two SceneCapture2D one for RGB image and the other for depth image.<br/>

<h4>Contact Me:</h4>
For any help regarding the installation, please contact me at:<br/>
oga13@uclive.ac.nz<br/>
