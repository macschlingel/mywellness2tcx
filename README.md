# Convert treadmill activity from MyWellness JSON format to TCX

`mywellness2tcx.py` script converts treadmill acivity data including HR and Elevation/Altitude in MyWellness JSON format to TCX suitable to import to Strava, Trainingpeaks, etc., and its sole reason for existing is because technogym is incapable of creating anything useful but hardware.
If you need to convert files from a technogym bike, please go to the original [project](https://github.com/ods/mywellness2tcx)

## Usage

1. Go to [https://www.mywellness.com/cloud/Training](https://www.mywellness.com/cloud/Training).
2. Open Developer Tools window in your browser, switch to Network tab, select XHR filter.
3. Click on a circle with number to expand activities for needed date, go to activity page.
4. Right click on last request in Developer Tools window (`GET https://services.mywellness.com/Training/CardioLog/…/Details?…`), choose Copy response.
5. Save copied data into file.
6. Run `mywellness2tcx.py JSON_FILE ACTIVITY_START_TIME`, where JSON_FILE is the path to the file you just saved and ACTIVITY_START_TIME is UTC start time for the activity in `%Y-%m-%dT%H:%M` format.
7. There schould `.tcx` file appear in the same folder as JSON_FILE. Upload it to whatever service you please.
