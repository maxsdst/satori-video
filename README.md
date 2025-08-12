# Satori Video – Short Video-Sharing Platform

A short video-sharing platform similar to TikTok, where users can upload, view, and interact with videos, featuring personalized recommendations powered by machine learning.

<br/>

## Table of Contents

1. [Features](#features)
2. [Demo](#demo)
3. [Project Architecture](#project-architecture)
4. [Installation](#installation)

<br/>

## Features

-   **Authentication**: Sign up, log in, and log out.
-   **User profiles**: Create profiles, follow other users, and view followers.
-   **Video upload and playback**: Upload videos and stream them smoothly using adaptive streaming.
-   **Video interactions**: Like, comment, share, save, and report videos.
-   **Personalized recommendations**: Machine learning-powered suggestions based on user preferences.
-   **Latest and popular videos**: Explore newly uploaded content and what's currently trending among users.
-   **Search functionality**: Search for videos and profiles.
-   **Watch history**: Track previously viewed videos.
-   **Notifications**: Receive updates on likes, comments, follows, and other user activities.
-   **Responsive design**: Optimized for mobile, tablet, and desktop viewing.

<br/>

## Demo

[satori.video](https://satori.video/)

[<img src="https://github.com/user-attachments/assets/09f8fdc1-16cf-4b11-9782-c4d8a26d9db1">](https://satori.video/)

<br/>

## Project Architecture

![diagram](https://github.com/user-attachments/assets/7cb9e383-3906-41fe-9fb5-7640f4dcea23)

The frontend is a single-page application built with **React**, which communicates with the backend through a **REST API**. The backend is implemented using **Django**, and **PostgreSQL** is used for data storage. **AWS S3** serves as the file storage.

Background tasks, such as video processing, are managed with **Celery** and a **Redis** message broker. **FFmpeg** handles video processing, and videos are served from **AWS S3** using the **HLS streaming protocol** for smooth playback.

Personalized video recommendations are powered by **[Gorse](https://github.com/gorse-io/gorse)**, which employs collaborative filtering to suggest videos based on user preferences. User actions such as likes, saves, and shares are treated as positive feedback, influencing their personalized recommendations. Additionally, Gorse provides popular and latest video suggestions.

Video search functionality is implemented with **PostgreSQL Full Text Search**, allowing users to find videos by title and description, sorted by relevance.

<br/>

## Installation

[Frontend installation instructions](https://github.com/maxsdst/satori-video-frontend)  
[Backend installation instructions](https://github.com/maxsdst/satori-video-backend)
