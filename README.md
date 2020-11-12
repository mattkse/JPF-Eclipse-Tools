# JPF-Eclipse-Tools (JET)

JPF Eclipse Tools (JET)

Watch this page for information regarding development status and plug-in releases of JET.

Plug-in installation instructions:

    Prerequisite: Java VM installation
        Sun's Java VM: http://www.oracle.com/technetwork/java/javase/downloads/index.html
        IBM's Java VM: https://www.ibm.com/developerworks/java/jdk/
        Open Source Java implementation: http://openjdk.java.net/
        Others: http://en.wikipedia.org/wiki/List_of_Java_virtual_machines 

    Prerequisite: Eclipse 3.6 (Helios) Distribution
        Eclipse with Java plug-ins: http://www.eclipse.org/downloads/packages/eclipse-ide-java-developers/heliosr 

Installation instructions

    Download https://bitbucket.org/mattkse/jet/downloads/JET_v1.2.0.zip
    Extract underneath eclipse directory structure at <path_to_eclipse_install>/dropins
    Restart Eclipse 

Uninstallation instructions

    Remove the extracted folder underneath your dropins directory and restart Eclipse 

How to use hotkey navigation to navigate from model class to peer class

    Open a model class
    Press the key sequence "Shift+F3" 

Afterwords, your editor should immediately switch to the corresponding peer class.

NOTES:

    the same action can be invoked via an editor context menu by selecting "[JPF] Open Peer Implementation".
    the hotkey sequence can be changed via "Window" -> "Preferences" -> "Keys" 

How to use hotkey navigation to navigate from model class to standard library implementation

    Open a model class
    Press the key sequence "Alt+F3" 

Afterwords, your editor should immediately switch to the corresponding standard library class.

NOTES:

    the same action can be invoked via an editor context menu by selecting "[JPF] Open Library Definition".
    the hotkey sequence can be changed via "Window" -> "Preferences" -> "Keys" 

How to use the Jet Peer View feature

* The following assumes you have an eclipse project containing model classes and corresponding peers according to standard JPF layout *

    Open a model class
    Open the Jet Peer View (Window -> Show View -> Other... -> Jet -> Jet Peer View)
    Select a native method under the Jet Peer View
    Open the context menu (e.g. right click)
    Select "[JPF] Open Peer Implementation" 

Afterwords, your editor should immediately switch to the corresponding peer class.
How to use the site.properties editor feature

    Open Preferences (Window -> Preferences)
    Select "JET Preferences"
    Ensure that "Path to site.properties" refers to a valid location for a site.properties file, otherwise you will be prompted to create a new site.properties file at the corresponding location
    Click "Configure..."
    Add extensions that you want to include in the JPF extensions property under included extensions, and all other extensions under excluded extensions 

Notes:

    Up/Down buttons change the relative ordering of extensions
    Reload button causes a refresh of the dialog from the site.properties file, if it exists
    Save button saves current dialog configuration to site.properties file without closing the dialog 

How to use the JPF Project wizard feature

    Open the new wizards menu (e.g. File -> New -> Other...)
    Select "JPF Project" underneath the "JPF" category and click Next
    Enter a Project Name
    Enter a project location if desired, otherwise a default is used
    Ensure that jpf-core is installed on your system and that "JPF core path" points to its root directory
    Click Finish
    Create a new Java Project in the workspace with the same name as the project you just created 

Afterwords, you should see your new JPF templated project in the package explorer.

OLD INSTRUCTIONS:

You have three options for your preferred method of installation:
(a) Install plug-in from internet update site (simple, quick)

    TODO 

(b) Install plug-in from downloaded zip file update site (more steps, but more portable)

    Download http://bitbucket.org/mattkse/jet/downloads/jet_update_site.zip
    Go to "Help" -> "Install New Software..." 

If you have previously installed JET...

    Select the update site previously used from the pull down menu
    (select checkbox next to "JPF Eclipse Tools") -> "Next" -> "Next" -> (accept license terms) -> "Finish" -> (wait for installation process and allow any warnings that pop up) -> "Restart Now" when prompted. 

If you have NOT previously installed JET...

    Go to "Add..." -> "Archive" -> (select jet_update_site.zip) -> "OK" or "Open" -> optionally, enter a descriptive name under "Name" -> "OK" -> (select checkbox next to "JPF Eclipse Tools") -> "Next" -> "Next" -> (accept license terms) -> "Finish" -> (wait for installation process and allow any warnings that pop up) -> "Restart Now" when prompted. 

(c) Install plug-in by manually copying file into Eclipse directory structure (most direct, but most error-prone)

    Download http://bitbucket.org/mattkse/jet/downloads/jet_dropin.zip
    Extract underneath eclipse directory structure at <path_to_eclipse_install>/dropins 

Development Status Log:

Post Date: 08/08
STATUS: Site.properties editor is complete and CreateProject tool is integrated into JET. Update site has been posted.


Post Date: 08/03
STATUS: Still finishing up some logic and verifying correctness. Update site to be posted as soon as possible.


Post Date: 08/01
Task(s): site.properties preferences
STATUS: Added support for new site.properties format. Up/Down logic is implemented, but could use a little more polishing. Cleaned up more code and added more GUI logic overall. Update site for plug-in to be posted by Monday night.


Post Date: 07/25
Task(s): site properties preferences
STATUS: Modified implementation to support the upcoming changes to site.properties as proposed by Peter. Also revamped the Table UI logic to make it cleaner and follow the MVC pattern more strictly. Other modifications include UI enhancements and infrastructure for ordering of extensions. Still need to solidify logic for "Up" and "Down" buttons, and the new logic for the updated site.properties format.
Future Task(s):

    Up/Down button logic in extensions editor
    Modify logic for updated site.properties format
    Ensure jpf-core path points to valid jpf-core
    Link new project wizard with preferences page
    Create project resource in Eclipse workspace upon finishing wizard
    Create jpf.properties UI
    Implement jpf.properties resource management
    Associate jpf.properties with newly created project resource
    Create MJI editor UI
    Implement MJI editor logic 

![alt text](https://github.com/mattkse/JPF-Eclipse-Tools/blob/main/updated_preferences.JPG?raw=true)


Post Date: 07/18
Task(s): site properties preferences
STATUS: Added support for parsing site.properties file when site config dialog is opened. Added support for saving extensions to site.properties when user presses OK. Also added a sample property page and more UI logic. Need a few more additions to the logic to ensure proper user interface guidelines such as ensuring jpf-core exists and informing the user before saving.
Future Task(s):

    Ensure jpf-core path points to valid jpf-core
    Link new project wizard with preferences page
    Create project resource in Eclipse workspace upon finishing wizard
    Associate JPF project properties with newly created project resource 

extensions.JPG


Post Date: 07/11
Task(s): site properties preferences
STATUS: Borrowed partial designs from standard Eclipse "Linked Resources" property page, along with the preference framework from VJP. The preference UI is now almost up to speed, and the framework for saving and reloading data is in place. Spent a lot of time integrating GUI logic between VJP and Eclipse controls, and it is now mostly stable. A little more work needs to be done to polish UI and start committing user-entered data to file system.
Future Task(s):

    Finish file system logic
    Link new project wizard with preferences page
    Create project resource in Eclipse workspace upon finishing wizard
    Associate JPF project properties with newly created project resource 

preferences.JPG


Post Date: 07/05
Task(s): JPF project wizard and site properties preferences
STATUS: Spent the holiday weekend finishing the JPF project wizard. The standard Eclipse wizards were not designed for reuse, and therefore I spent some time piecing together different GUI controls and ensuring the logic is correct. After that, I moved on to create a new editor for site.properties files, which is accessible from the preferences window. I reused some code from eclipse-jpf and VJP, I just need to implement the logic for modifying the actual files.
Future Task(s):

    Finish file system logic
    Link new project wizard with preferences page
    Create project resource in Eclipse workspace upon finishing wizard
    Associate JPF project properties with newly created project resource 


Post Date: 06/26
Task(s): classpath selector
UPDATE: Classpath navigation workaround in Eclipse:
1. In Package Explorer/Navigator, right click your project (e.g. jpf-core) and select "Properties"
2. Select Java Build Path and then the "Order and Export" tab
3. Select "JRE System Library" and click the "Top" button. This will tell Eclipse to search the JRE system library before searching the project files.
STATUS: The command framework has to be one of the most important, yet one of the least documented components of Eclipse. In order to reuse the existing implementation for "Open Declaration", it appears necessary to override the standard handler that Eclipse provides. However, this is non-trivial. There are unintuitive XML definitions for command handlers and a nightmare of command ID references. Apparently it has been done, but documentation is sparse. I am switching to the simpler task of creating projects and preference pages so as to get some code rolling out.
References: Commands:

    http://www.eclipse.org/forums/index.php?t=tree&th=157754&
    http://wiki.eclipse.org/Command_Core_Expressions
    http://wiki.eclipse.org/Menu_Contributions
    http://help.eclipse.org/help33/topic/org.eclipse.platform.doc.isv/guide/workbench_cmd.htm 


Post Date: 06/20
Task(s): #2 & others
STATUS:

    I've been sidetracked a bit by some administrative issues in dealing with Eclipse and configuration in general. Among other things, I've done the following: dealt with a few minor hardware issues and system reorganization, reinstalled Eclipse fresh after reading some tutorials on p2 provisioning (see references), optimized Eclipse and JVM run-time settings, and completely configured all Eclipse preferences, project, and workspace settings after reading more tutorials and blog posts (see references). 

    I've also been reading more tutorials on the command framework and Eclipse in general (see references). Eclipse is such a complex system that its architecture cannot be easily or concisely understood. Instead, one wiki page leads to another and after a few hours you finally start to piece together the seemingly chaotic, but nonetheless completely logical and intelligently organized components of the Eclipse architecture. Further updates to be posted soon. I hope to release some code soon, but it's really about 80% learning and 20% development. I may move on to another feature if I don't make progress soon, since it's beginning to look like feature #2 is going to be the hardest to implement. 

References:
Setup Related:

    http://wiki.eclipse.org/FAQ_Where_do_I_get_and_install_Eclipse%3F
    http://wiki.eclipse.org/FAQ_How_do_I_run_Eclipse%3F
    http://wiki.eclipse.org/FAQ_How_do_I_increase_the_heap_size_available_to_Eclipse%3F
    http://wiki.eclipse.org/FAQ_How_do_I_increase_the_permgen_size_available_to_Eclipse%3F
    http://www.eclipsezone.com/eclipse/forums/t20732.html
    http://wiki.eclipse.org/Equinox_p2
    http://wiki.eclipse.org/Equinox_p2_Getting_Started
    http://www.ibm.com/developerworks/opensource/library/os-eclipse-equinox-p2/ 

Development Related:

    http://wiki.eclipse.org/User_Interface_Guidelines (wow)
    http://wiki.eclipse.org/FAQ_Why_should_I_add_my_own_project_nature%3F
    http://www.eclipse.org/articles/Article-Builders/builders.html
    https://www.ibm.com/developerworks/opensource/library/os-eclipse-api-tools/
    http://www.eclipse.org/articles/article.php?file=Article-action-contribution/index.html 


Post Date: 06/15
Task: #2
STATUS: After debugging Eclipse vigorously, I have found out that opening a source file via the "Open Declaration" menu or the F3 hotkey is handled by generic event tables within Eclipse (this is due to the "Command" architecture). Because of this, it is only possible to reuse the existing "open editor" command, not extend it. Ideally, I would be able to reuse the code for the "Select Element" disambiguation feature (see last post). However, it appears that this is not possible. As a result, I will probably have to hack in some code to manually open an editor based upon a user selection. I have started to look into this and will continue to post updates as I find out more.
Notes: The relevant action ID for an "open editor" action is org.eclipse.jdt.ui.edit.text.java.open.editor.

Related Links:

    http://wiki.eclipse.org/Platform_Command_Framework
    http://www.vogella.de/articles/EclipseCommands/article.html
    http://wiki.eclipse.org/FAQ_How_do_I_open_an_editor_on_a_file_outside_the_workspace%3F
    http://www.slideshare.net/madhusamuel/eclipse-commands 


Post Date: 06/13
Task: #2
STATUS: Figured out how Eclipse resolves classpath discrepancies. Code almost implemented for JPF specific lookups (i.e. injecting source entries to be looked up). Lookup will be done similar to how Eclipse resolves normal standard library ambiguities (e.g. see ambiguous type "Action" in pic below) via a new context-menu item for a proof-of-concept. Expecting to push plug-in release for external testing in next 1-2 days.
Notes: See the pics below for reference

ambiguous_selection_dialog.JPG


Post Date: 06/09
Task: Looked into "Attach source..." implementation in order determine how Eclipse remembers source matchings.
Result: Eclipse appears to store source matchings exclusively for each project in the .classpath file.
Next task: #2
Notes: See the pics below for reference

attach_source3.JPG

attach_source5.JPG

open_declaration3.JPG


Post Date: 06/06
Task: Investigated source code of eclipse-jpf, VJP, and Fugu (UIUC CS 427 project) over the weekend
Result: Better understanding of what each project accomplished and how they implemented functionality.
Next Task: #1
Notes: none
