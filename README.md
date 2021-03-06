# Record iOS Simulator
A script to start and stop video recordings from the iOS Simulator as easily as taking a screenshot.

Run the script to start a video recording, then run it again to stop that recording and have it saved to the Desktop with a name like `Simulator 2019-01-04 at 10.16.21.mp4`.

Also includes Alfred and Keyboard Maestro implementations that allow you to start and stop a recording easily with ⌘R in the Simulator (or any other trigger those apps support).

# Usage Instructions

## Alfred
Download the [Record Simulator.alfredworkflow](https://github.com/mono0926/record-ios-simulator/releases/download/1.0.0/Record.Simulator.alfredworkflow) file and open it to add the workflow to Alfred.

![](images/alfred.png)

## Keyboard Maestro
Download the `Record Simulator.kmmacros` file and open it to add the macro to Keyboard Maestro. By default it is triggered using the ⌘R hotkey while the Simulator is focused, but you can tweak this behaviour after adding the macro if desired.

Once the macro has been added, just use the hotkey in the Simulator to start a video recording, and then again to end the recording.

## Script Usage
If using other utilities, or wanting to simply have a script that you can run in the terminal, then download and run the bash script. On first run it will start a recording, on second run it will end the recording and save it to the Desktop.

# Behaviour
There are several variables at the top of the script that can be edited to modify the behaviour:

| Variable | Default | Description |
| --- | --- | --- |
| `outputDirectory` | `~/Desktop/` | Determines where recordings are saved. |
| `openRecordings` | `true` | If `true` video recordings will be opened when ended, otherwise a notification is displayed. |
| `playSounds` | `true` | If `true` system sounds will be played when starting and stopping a recording. |
| `filename` | `"Simulator "$(date '+%Y-%m-%d at %H.%M.%S')` | By default files are saved with date-based names like `Simulator 2019-01-04 at 10.16.21.mp4`, tweak this to change filenames to your liking. (No need to include an extension, `.mp4` is added further into the script) |

# Contributing

PRs with improvements, fixes, features welcomed.

After modifying the script, please run the `utils/generateFiles.sh` script to update the Keyboard Maestro and Alfred implementations with the script changes, and include those changes with your script update commit. You do __not__ need Alfred or KM to do this.
