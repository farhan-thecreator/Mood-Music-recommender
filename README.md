# Mood-Music-recommender
AI-powered music recommender that detects your mood from either text or image input and suggests Spotify songs based on emotion. Built using HuggingFace, DeepFace, and a Kaggle Spotify dataset. Supports Happy, Sad, Energetic, and Chill moods.
# Spotify Mood-Based Music Recommender

This project detects your mood from either a **text journal** or a **face image**, and recommends songs using a Spotify dataset. Perfect for journaling, chilling, or vibing.

---

## Features

-  Text-based mood detection (via HuggingFace Transformer)
-  Image-based emotion detection (via DeepFace)
-  Mood-clustered song recommendations
-  Spotify search links auto-generated
-  KMeans clustering based on `valence` and `energy`

---

## How it Works

| Input Type | Model Used                         | Output           |
|------------|-------------------------------------|------------------|
| Text       | `distilroberta` via HuggingFace     | Emotion → Mood   |
| Image      | `DeepFace`                          | Facial Emotion   |
| Mood       | Used to recommend songs from dataset|

---

##  Dataset

- Source: [Kaggle – Spotify Dataset by Vatsal Mavani](https://www.kaggle.com/datasets/vatsalmavani/spotify-dataset)
- Preprocessed & clustered using KMeans
- 4 Mood categories: `Happy`, `Sad`, `Chill`, `Energetic`

---

## Sample Usage

```python
# Text input
user_text = "I'm feeling a bit low and tired today."
mood = detect_mood_from_text(user_text)
recommend_songs(mood)

# Image input
mood = detect_mood_from_image("my_face.jpg")
recommend_songs(mood)
