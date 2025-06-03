# Speed-extraction
Code for speed extraction of players in football videos. 

# Dependencies
Create and activate environment
```bash
python -m venv myenv
source venv/bin/activate
```

The code runs with python 3.10, but potentially with other versions too. The repo was used in ml-node (https://www.uio.no/tjenester/it/forskning/kompetansehuber/uio-ai-hub-node-project/it-resources/ml-nodes/), which uses GCCcore. Therefore, the following packages were downloaded from ml-node, compatible with GCCcore:
- **PyTorch**: 1.7.0
- **bzip2**: 1.0.8 (built with GCCcore 10.3.0)
- **GCCcore**: 10.3.0
- **FFmpeg**: 4.4.2

The other packages can be installed with:

```bash
pip install -r requirements.txt
```

# Run
Run run_pose.py to estimate keypoints (can train the model using train_pose.py, or use the weights at https://drive.google.com/file/d/1L19dFxpzKHyzABrjgbb7GpkMg6xxiYUN/view?usp=drive_link) and get the bounding box ids and coordinates from running Deep-EIoU (https://github.com/hsiangwei0903/Deep-EIoU), and run the speed prediction based on this data with speed_extraction.py. speed_extraction.py calculates the homography transformation and predicts the player speeds for the events.

Get bounding boxes, keypoint and line predictions from the pipeline using PnLCalib (https://github.com/eirikeg1/dribbling-detection-pipeline) 
