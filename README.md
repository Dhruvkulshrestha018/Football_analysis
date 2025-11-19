# 🏆 Football Match Analysis Using YOLO & Tracking

This is an end-to-end **football analysis system** that detects players, tracks their movement, assigns them to teams based on jersey color, and identifies ball possession. The pipeline uses **YOLOv5** for detection, a custom tracker for maintaining identities, and color-based classification for teams, producing annotated video analysis from raw match footage.

---

## 📌 Features

- **Player & Ball Detection**  
  A YOLOv5 model detects football players, the ball, and referees in each frame.

- **Tracking**  
  Unique IDs are assigned to players across all frames using a custom tracking module.

- **Team Assignment**  
  Players are grouped into teams based on jersey color using clustering logic in `team_assigner`.

- **Ball Possession**  
  The ball is linked to the nearest player using distance-based logic in `player_ball_assigner` to estimate possession.

- **Video Processing**  
  Reads raw input from `input_videos/`, overlays bounding boxes and annotations, and writes annotated output to `output_videos/`.

---

## 📁 Project Structure

football-analysis/
├── main.py # Main execution pipeline
├── models/ # YOLO trained weights
├── input_videos/ # Raw match footage
├── output_videos/ # Annotated result videos
├── trackers/ # Tracking logic (unique IDs)
├── team_assigner/ # Jersey color-based team assignment
├── player_ball_assigner/ # Ball possession logic
├── utils/ # Helper modules
├── training_notebook/ # YOLOv5 training notebook
└── development_and_analysis/ # Color clustering & analysis


---

## 🚀 Workflow

1. Load input video  
2. Run YOLO detections on each frame  
3. Track detected objects across frames  
4. Assign each player to a team based on jersey color  
5. Identify which player is closest to the ball (possession)  
6. Generate annotated output video  

---

## 🎯 Goal

To build a lightweight, automated football analytics system that helps coaches, analysts, and developers understand player performance, ball control, and team dynamics using computer vision.

---

## 🛠️ How to Use

1. Put your match videos in `input_videos/`
2. Add YOLOv5 weights to the `models/` folder  
3. Run the pipeline:

```bash
python main.py
