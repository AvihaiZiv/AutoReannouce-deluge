# AutoReannouce-deluge
This script is used to automatically re-announce a torrent to its tracker in case the tracker status is not "Announce OK".

## Usage
1. Install the Execute plugin: Go to Deluge preferences, then to Plugins, and search for "Execute". Click on the Install button next to the Execute plugin to install it.
2. Make sure the script is executable (chmod +x autoreannounce).
3. Add the script to Deluge: In the Deluge preferences, go to the Execute tab. Click on the Add button to add a new event handler. Choose the event that you want to trigger the script (e.g., "Torrent Complete").

## Configuration

Before using this script, make sure to update the following variables according to your configuration:

    Dport: the port number of the Deluge daemon
    logpath: the path to the log file

## Functionality

The script uses the Deluge console to update the tracker for the specified torrent, and checks the tracker status. If the tracker status is not "Announce OK", the script will continue to update the tracker and check the status until either the status is "Announce OK" or 100 attempts have been made.

The script will output the following information to the log file:

    Torrent Name: the name of the torrent
    Torrent ID: the ID of the torrent in Deluge
    Torrent Path: the path to the torrent on the system
    Tracker status: the final status of the tracker after re-announcing the torrent
    Re-announced: the number of times the tracker was updated and checked

If the tracker status is not "Announce OK" after 100 attempts, the script will exit with an error code of 1, otherwise it will exit with a success code of 0.
