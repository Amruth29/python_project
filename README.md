# 🐍 Snake Game - Python Implementation

A classic Snake game built with Python and Tkinter, featuring a modern GUI, score tracking, leaderboard system, and smooth gameplay mechanics.

![Snake Game](https://img.shields.io/badge/Python-3.x-blue) ![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange) ![Game](https://img.shields.io/badge/Game-Classic-green)

## 📋 Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Installation](#installation)
- [How to Play](#how-to-play)
- [Game Architecture](#game-architecture)
- [Key Components](#key-components)
- [Game Mechanics](#game-mechanics)
- [File Structure](#file-structure)
- [Screenshots](#screenshots)
- [Contributors](#contributors)

## 🎮 Overview

This Snake game is a complete implementation of the classic arcade game with modern features including:
- **User Authentication**: Players can enter their username
- **Score Tracking**: Real-time score display with high score persistence
- **Leaderboard System**: Tracks and displays top players
- **Pause/Resume**: Full game control with keyboard shortcuts
- **Visual Effects**: Score animations and bonus point indicators
- **Responsive Design**: Full-screen gameplay with custom backgrounds

## 🛠️ Tech Stack

### Core Technologies
- **Python 3.x**: Primary programming language
- **Tkinter**: GUI framework for creating the game interface
- **Canvas Widget**: For rendering game graphics and animations

### Libraries Used
- `tkinter`: GUI development and window management
- `time`: For game loop timing and delays
- `random`: For food placement and game randomization

### File I/O Operations
- Text file handling for persistent data storage
- Score and name management through file operations

## ✨ Features

### 🎯 Core Gameplay
- **Snake Movement**: Arrow key controls with smooth movement
- **Food Collection**: Tomato-themed food items that increase snake length
- **Collision Detection**: Wall and self-collision detection
- **Score System**: Points for each food item + bonus points every 20 points

### 🏆 Advanced Features
- **High Score Tracking**: Persistent high score storage
- **Leaderboard**: Global player ranking system
- **User Profiles**: Individual player score tracking
- **Game Controls**: Pause/Resume functionality
- **Visual Feedback**: Score animations and bonus indicators

### 🎨 User Interface
- **Welcome Screen**: Attractive landing page with game options
- **Custom Backgrounds**: Professional visual design
- **Responsive Layout**: Full-screen game experience
- **Intuitive Controls**: Clear button placement and keyboard shortcuts

## 🚀 Installation

### Prerequisites
- Python 3.x installed on your system
- Tkinter (usually comes with Python installation)

### Setup Instructions
1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd python_project
   ```

2. **Run the game**
   ```bash
   python main.py
   ```

3. **Required Files**
   Ensure all project files are in the same directory:
   - `main.py` (main game file)
   - `background1.png` (background image)
   - `Tomato_image.png` (food image)
   - `Instructions.txt` (game instructions)
   - `High_Score.txt` (high score storage)
   - `Name.txt` (player names)
   - `Score_list.txt` (player scores)

## 🎮 How to Play

### Controls
- **Arrow Keys**: Control snake direction
- **Space Bar**: Pause game
- **Enter Key**: Resume game
- **Mouse**: Click buttons for menu navigation

### Game Rules
1. **Objective**: Eat food to grow the snake and score points
2. **Movement**: Use arrow keys to navigate
3. **Food**: Collect tomato items to increase length and score
4. **Collision**: Avoid hitting walls or the snake's own body
5. **Scoring**: +1 point per food, +5 bonus every 20 points
6. **Game Over**: Occurs when snake hits wall or itself

## 🏗️ Game Architecture

### Program Structure
The game follows a modular architecture with clear separation of concerns:

```
main.py
├── Welcome Screen (window1)
├── Username Input (window2)
├── Game Screen (window3)
├── Game Over Screen (window4)
├── Instructions Screen (window7)
└── Leaderboard Screen (window8)
```

### Key Functions
- `start()`: Initializes game and username input
- `setup()`: Creates main game window and initializes game state
- `movement()`: Handles snake movement mechanics
- `collision_food()`: Manages food collection and scoring
- `collision_tail()`: Detects self-collision
- `game_over()`: Handles game termination and score saving

## 🔧 Key Components

### 1. Game State Management
```python
# Global variables for game state
game = True          # Current game status
game_is_on = True    # Overall game running status
score = 0           # Current player score
x, y = 20, 0        # Snake movement direction
```

### 2. Snake Body Management
- **Dynamic Array**: Snake body stored as list of canvas objects
- **Movement Algorithm**: Each segment follows the previous one
- **Growth Mechanism**: New segments added when food is collected

### 3. Food System
- **Random Placement**: Food appears at random coordinates
- **Collision Detection**: Precise hit detection for food collection
- **Visual Feedback**: Score animations and bonus indicators

### 4. Score Management
- **Real-time Updates**: Score displayed during gameplay
- **High Score Persistence**: Stored in text file
- **Player Tracking**: Individual player statistics maintained

## 🎯 Game Mechanics

### Movement System
```python
def movement():
    # Move each body segment to follow the previous one
    for j in range(len(snake_body) - 1, 0, -1):
        c = canvas3.coords(snake_body[j - 1])
        canvas3.moveto(snake_body[j], c[0] - 1, c[1] - 1)
    # Move head in current direction
    canvas3.move(snake_body[0], x, y)
```

### Collision Detection
- **Wall Collision**: Checks if snake head touches screen boundaries
- **Self Collision**: Detects if head collides with any body segment
- **Food Collision**: Determines when snake head overlaps with food

### Scoring Algorithm
- **Base Points**: +1 for each food item collected
- **Bonus System**: +5 bonus points every 20 points
- **High Score**: Automatically updates when beaten

## 📁 File Structure

```
python_project/
├── main.py              # Main game logic and GUI
├── background1.png      # Welcome screen background
├── Tomato_image.png     # Food item sprite
├── Instructions.txt     # Game instructions
├── High_Score.txt      # Persistent high score
├── Name.txt            # Player names database
├── Score_list.txt      # Player scores database
└── README.md           # Project documentation
```

## 🖼️ Screenshots

### Welcome Screen
- Professional landing page with game title
- Three main options: Start, Leaderboard, Instructions

### Game Screen
- 600x600 game canvas with green background
- Real-time score and high score display
- Play/Pause controls
- Smooth snake movement with visual feedback

### Game Over Screen
- Score display with congratulations message
- Restart and Quit options
- High score celebration for new records

## 👥 Contributors

This project was developed by:
- **Keerthan Shenoy**
- **Amruth R**
- **C Ashik Poojary**

## 🎯 Interview Explanation

### Technical Implementation Highlights

#### 1. **Object-Oriented Design Principles**
- Modular function design with clear responsibilities
- Global state management for game variables
- Separation of UI and game logic

#### 2. **Data Structures Used**
- **Lists**: Snake body segments, food items, player names, scores
- **Canvas Objects**: Visual representation of game elements
- **File I/O**: Persistent data storage for scores and names

#### 3. **Algorithm Complexity**
- **Movement**: O(n) where n is snake length
- **Collision Detection**: O(n) for self-collision, O(1) for wall/food
- **Score Management**: O(1) for updates, O(n log n) for leaderboard sorting

#### 4. **Key Technical Challenges Solved**
- **Smooth Movement**: Implemented segment-following algorithm
- **Collision Detection**: Precise coordinate-based hit detection
- **State Management**: Proper game state transitions
- **Data Persistence**: File-based score and name storage

#### 5. **Scalability Considerations**
- Modular design allows easy feature additions
- File-based storage can be upgraded to database
- Canvas-based rendering supports visual enhancements

### Learning Outcomes
- **GUI Development**: Mastered Tkinter for desktop applications
- **Game Development**: Understanding of game loops and mechanics
- **Data Management**: File I/O operations and data persistence
- **User Experience**: Intuitive interface design and user feedback
- **Problem Solving**: Complex collision detection and movement algorithms

This project demonstrates proficiency in Python programming, GUI development, game mechanics, and software engineering principles suitable for both academic and professional contexts.
