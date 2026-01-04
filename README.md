# 🃏 Solitaire - SFML Edition

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++"/>
  <img src="https://img.shields.io/badge/SFML-8CC445?style=for-the-badge&logo=sfml&logoColor=white" alt="SFML"/>
  <img src="https://img.shields.io/badge/Visual%20Studio-5C2D91? style=for-the-badge&logo=visual%20studio&logoColor=white" alt="Visual Studio"/>
</p>

A beautifully implemented classic Solitaire (Klondike) card game built with **C++** and **SFML** (Simple and Fast Multimedia Library). Experience the timeless card game with smooth graphics, intuitive controls, and a polished visual design. 

---

## ✨ Features

- 🎴 **Full 52-Card Deck** - Complete deck with all suits (Hearts, Diamonds, Clubs, Spades)
- 🖼️ **Beautiful Graphics** - Custom card designs and stunning background artwork
- 🎮 **Multiple Screens** - Main menu, Rules screen, Game mode selection, and Game board
- 📐 **7-Column Tableau** - Classic Solitaire layout with proper card stacking
- 🏆 **4 Foundation Piles** - Build your suits from Ace to King
- 🖱️ **Interactive Controls** - Drag and drop card mechanics
- 📖 **Built-in Rules** - Easy access to game rules for new players

---

## 📸 Screenshots

| Main Menu | Game Board |
|:---------:|: ----------:|
| ![Background](Background.png) | ![Board](Board.png) |

---

## 🚀 Getting Started

### Prerequisites

- **Visual Studio 2019/2022** (recommended) or any C++ IDE
- **SFML 2.5+** library
- **Windows OS** (for . vcxproj configuration)

---

## 🔧 SFML Integration Guide (Visual Studio)

### Step 1: Download SFML

1. Visit the [official SFML website](https://www.sfml-dev.org/download.php)
2. Download the **Visual C++ 15 (2017) - 32-bit** or **64-bit** version (match your project configuration)
3. Extract the downloaded archive to a location (e.g., `C:\SFML-2.5.1`)

### Step 2: Configure Visual Studio Project

#### Include Directories
1. Right-click your project → **Properties**
2. Navigate to **C/C++** → **General**
3. Add to **Additional Include Directories**:
   ```
   C:\SFML-2.5.1\include
   ```

#### Library Directories
1. Navigate to **Linker** → **General**
2. Add to **Additional Library Directories**:
   ```
   C:\SFML-2.5.1\lib
   ```

#### Link SFML Libraries
1. Navigate to **Linker** → **Input**
2. Add to **Additional Dependencies**: 

   **For Debug Configuration:**
   ```
   sfml-graphics-d.lib
   sfml-window-d.lib
   sfml-system-d.lib
   sfml-audio-d.lib
   ```

   **For Release Configuration:**
   ```
   sfml-graphics.lib
   sfml-window.lib
   sfml-system. lib
   sfml-audio.lib
   ```

### Step 3: Copy DLL Files

Copy the following DLL files from `C:\SFML-2.5.1\bin` to your project's output directory (where the `.exe` is generated):

**Debug:**
- `sfml-graphics-d-2.dll`
- `sfml-window-d-2.dll`
- `sfml-system-d-2.dll`

**Release:**
- `sfml-graphics-2.dll`
- `sfml-window-2.dll`
- `sfml-system-2.dll`

### Step 4: Verify Installation

Create a simple test file to verify SFML is working: 

```cpp
#include <SFML/Graphics.hpp>

int main() {
    sf::RenderWindow window(sf::VideoMode(800, 600), "SFML Test");
    while (window.isOpen()) {
        sf::Event event;
        while (window. pollEvent(event)) {
            if (event.type == sf::Event::Closed)
                window.close();
        }
        window.clear(sf::Color::Green);
        window.display();
    }
    return 0;
}
```

If a green window appears, SFML is correctly configured!  ✅

---

## 📂 Project Structure

```
Solitaire_Project_SFML/
├── 📄 Solitaire_Project_SFML.cpp   # Main game loop and entry point
├── 📄 Cards. h                       # Card class with sprite handling
├── 📄 Deck.h                        # Deck management and shuffling
├── 📄 Tableau.h                     # Tableau pile implementation
├── 📄 Suitdeck.h                    # Foundation pile logic
├── 📄 Helper.h                      # Enums for suits and colors
├── 🖼️ Background. png               # Main menu background
├── 🖼️ Board.png                    # Game board background
├── 🖼️ Rules.png                    # Rules screen
├── 🖼️ mode. png                     # Mode selection screen
├── 🖼️ back.png                     # Card back design
├── 🖼️ empty.png                    # Empty pile placeholder
├── 📁 Final_deck/                   # Card face images
│   ├── 📁 hearts/
│   ├── 📁 diamonds/
│   ├── 📁 clubs/
│   └── 📁 spades/
├── 📁 include/                      # SFML headers
└── 📁 lib/                          # SFML libraries
```

---

## 🎮 How to Play

1. **Launch the Game** - Run the executable to see the main menu
2. **Start New Game** - Click on "NEW GAME" to proceed
3. **Select Mode** - Choose your preferred difficulty
4. **Play Solitaire** - 
   - Build tableau piles in descending order with alternating colors
   - Move Aces to foundation piles and build up by suit
   - Win by moving all cards to the four foundation piles

### Controls

| Action | Control |
|--------|---------|
| Select Card | Left Click |
| Drag Card | Hold Left Click + Move Mouse |
| View Rules | Click "RULES" button |
| Return to Menu | Click "BACK" button |

---

## 🎯 Game Rules

1. **Tableau Building** - Cards must be placed in descending order with alternating colors (Red on Black, Black on Red)
2. **Foundation Building** - Start with Ace, build up to King in the same suit
3. **Moving Cards** - Only face-up cards can be moved; revealing a face-down card flips it automatically
4. **Winning** - Successfully move all 52 cards to the four foundation piles

---

## 🐛 Known Issues & Future Prospects

> ⚠️ **Note:** There are minor bugs currently present in the game that will be addressed in future updates. 

### Planned Improvements
- [ ] Complete drag-and-drop functionality for all cards
- [ ] Implement full game logic validation
- [ ] Add undo/redo feature
- [ ] Implement scoring system
- [ ] Add save/load game functionality
- [ ] Sound effects and background music
- [ ] Timer and move counter
- [ ] Win animation celebration

---

## 🛠️ Built With

- **[C++](https://isocpp.org/)** - Programming Language
- **[SFML 2.5](https://www.sfml-dev.org/)** - Simple and Fast Multimedia Library
- **[Visual Studio](https://visualstudio.microsoft. com/)** - IDE

---

## 📝 License

This project is open source and available for educational purposes.

---

## 👨‍💻 Author

**Obsi19** - [GitHub Profile](https://github.com/Obsi19)

---

## 🙏 Acknowledgments

- SFML development team for the amazing graphics library
- Classic Solitaire for the timeless gameplay inspiration
- Billy Argel for the beautiful font

---

<p align="center">
  Made with ❤️ and C++
</p>

<p align="center">
  ⭐ Star this repository if you found it helpful!
</p>
