# parse_vNav_Motion.py

This is a small python script to parse the DICOM files from a vNavs series and convert them into an average RMS motion score. The script takes the 
following arguments:

1. `--tr` which is the TR of the parent sequence (i.e., the MPRAGE) expressed in seconds (e.g., `--tr 2.4`); and
2. `--input` which is the list of files DICOM files that makeup the vNavs series; or
3. `--input-dir` which is a directory containing DICOM files that makeup the vNavs series; or
4. `--input-json` which is a BIDS  JSON sidecar file containing an `ImageComments` array; and
5. either `--rms` or `--max` which decides whether the time-averaged RMS motion or time-averaged max motion is printed; and
6. `--output-dir` which is the desired output directory

This script will output a JSON file containing 

1. `Transforms`
2. `HomogeneousTransforms`
3. `vNavMotionScoresRMS`
4. `vNavMotionScoresMax`
5. `MeanMotionScoreRMSPerMin`
6. `MeanMotionScoreMaxPerMin`
7. `Failed` which is ether `null` or an array containing the `AquisitionNumber` and `InstanceNumber` where vNav failed.

The script assumes that you've got a version of pydicom installed. For directions on doing that, see https://github.com/pydicom/pydicom

If you find bugs, please report them in the issues section of https://github.com/MRIMotionCorrection/parse_vNav_Motion

If you want to add features, please make a pull request on GitHub as well. We'd love to see this expanded.
