Draupnir Fikse - Cell Tower Fix
===
This is a Python v3.8 script called "Draupnir Fikse" that generates a KML file with a circle overlay for a cell tower. The KML file can be used to visualize the coverage area of the cell tower on various KML viewers.
Features

    Calculates the distance variable for the circle overlay using the Friis transmission equation.
    Generates a KML file with a circle overlay for a given cell tower location and parameters.
    Supports customization of cell tower parameters such as receiver gain (Gr), transmitter gain (Gt), transmitter power (Pt), receiver power (Pr), and cellphone frequency (Cf).
    Provides default values for the parameters if not specified.
    Allows specification of an output directory for the generated KML file.
    Displays a dialog box with information on the saved KML file location.
    Provides a Help button to show information about the input parameters and their default values.
    Provides an About button to display information about the script.

Prerequisites
===
    Ubuntu 18+ or Windows
    Python 3.8 or above
    Tkinter library

Usage
===
    Ensure you have Python 3.8 or above installed on your system.
    Install the required Tkinter library if it is not already installed.
    Run the script using the Python interpreter.
    Fill in the required parameters and optional parameters in the provided entry fields.
    Click the "Add Entry" button to generate the KML file with the circle overlay based on the entered parameters.
    The generated KML file will be saved in the specified output directory or the current working directory if no directory is specified.
    A dialog box will appear with the path to the saved KML file.
    Open the generated KML file in a KML viewer to visualize the cell tower coverage area.

Resources
===
    Possible cell tower information sources:
        OpenCellID
        CellMapper

    Possible KML viewers:
        Doogal KmlViewer
        NSSpot KML Viewer (limited daily uploads)

Disclaimer
===
Please note that this script assumes ideal conditions and does not consider real-world factors such as terrain, interference, atmospheric conditions, or the presence of obstacles. The generated coverage area is an approximation based on the provided parameters and should be used for demonstration purposes only.
