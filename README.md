# Vision-Based Estimation of da Vinci Master Tool Manipulator Kinematics for Surgical Performance Assessment

This repository contains the **code and dataset** associated with the paper:


> **Evaluating Surgeons' Performance on the da Vinci System Using Vision-Based Kinematic Tracking**  
> Andrea Roberti 1* , Pio Giacomo Cimino 1* , Maria Bencivenga 2 ,
Simone Giacopuzzi 2 , Riccardo Muradore 1
1* Department of Engineering for Innovation Medicine, University of
Verona, Strada le Grazie 15, Verona, 37134, Italy.
2 Department of Surgery, Dentistry, Pediatrics and Gynaecology,
University of Verona, Piazzale Ludovico Antonio Scuro 10, Verona,
37134,Italy. 

The project proposes a **non-invasive hybrid vision-based framework** for tracking surgeon hand motion and dVRK Master Tool Manipulator (MTM) motion using complementary **markerless (MediaPipe)** and **marker-based (ArUco)** vision approaches, enabling the extraction of task-level kinematic metrics for surgical skill assessment.


## Dataset Description

The dataset includes recordings from a **standard peg-and-ring skill-assessment task** performed on the **da Vinci Research Kit (dVRK)**.

- **Participants:** 3 users  
- **Trials per user:** 5  
- **Task:** Color-matched peg-and-ring placement  
- **Ground truth:** dVRK MTM kinematics  
- **Vision data:** RGB camera recordings synchronized with robot data  

The dataset enables quantitative evaluation of:
- 3D trajectory reconstruction accuracy
- Inter-user and intra-user variability
- Kinematic performance indicators

See `dataset/README.md` for detailed information on file formats and data organization.

---

## Installation

### Requirements

- Python ≥ 3.8
- OpenCV
- MediaPipe
- NumPy
- SciPy
- Matplotlib

Install dependencies with:

```bash
pip install -r requirements.txt
```
## Usage
1. Run MediaPipe-based hand tracking

``` python3 code/mediapipe_tracker/run_tracker.py --input path/to/video ```

2. Run ArUco-based marker tracking

``` python3 code/aruco_tracker/run_tracker.py --input path/to/video ```

3. Multimodal trajectory fusion

``` python3 code/fusion/fuse_trajectories.py --config config.yaml ```

4. Extract kinematic metrics

``` python3 code/metrics/compute_metrics.py --input path/to/trajectory ```

6. Visualization

``` python3 code/visualization/plot_trajectories.py ```

## Limitations
The framework is designed for task-level kinematic metrics, not sub-millimetric motion analysis.

- Hand/MTM motion is used as a proxy for surgeon behavior, not as a direct measure of tool–tissue interaction.

- Performance metrics are meaningful at the trajectory and temporal level, as validated in consultation with surgeons.

These aspects are discussed in detail in the accompanying paper.

## Contact
For questions or collaborations, please contact:

- Andrea Roberti - University of Verona

- Email: andrea.roberti@univr.it
