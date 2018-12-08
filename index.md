## MNMLST
![Logo](captaincoco4.github.io/logo.PNG)

## Game Description
**MNMLST**, also known as _MINIMALIST_, is a game where one is expected to stay focused.

## Game Preview
Anyone with enough intuition can easily play the game from the get-go. But first, you must press Enter in order to proceed to the next screen.

**1.** Choose wave count (number of circles being dropped per wave)

![ Wave ](captaincoco4.github.io/wave.PNG)

**2.** A 3-2-1 countdown will commence to prepare you for the incoming wave of _Directions_

![ Countdown ](captaincoco4.github.io/countdown.PNG)

**3.** Circles with arrows, referred to as _Directions_, will start going down. The amount of _Directions_ per game will depend on the number you've chosen from the previous screen.

![ Game ](captaincoco4.github.io/game.PNG)

These _Directions_ are instances of a user-defined object, `Arrow`.
```python
# defined in engine.py
class Box:
    def __init__(self, x, y, width, height):
        self.x = x
        self.y = y
        self.w = width
        self.h = height
        
# defined in assets.py
class Arrow:
    def __init__(self, x, y, width, height, image, direction):
        self.box = engine.Box(x, y, width, height)
        self.pic = picture(self.box.x + self.box.w// 4, self.box.y + self.box.y // 4, self.box.w//2, image, height=self.box.h//2)
        self.direction = direction

    def moveDown(self, velocity):
        self.box.y -= int(velocity)
        self.pic.y -= int(velocity)

    def place(self, x=None, y=None):
        if x != None:
            self.box.x = x
            self.pic.x = self.box.x + self.box.w//4
        if y != None:
            self.box.y = y
            self.pic.y = self.box.y + self.box.h//4
    
    def draw(self):
        self.pic.draw()
```

**4.** The game will end when the timer ends, missed a _Direction_, or pressed one of the arrow keys too early. The game will show your final score at the end.

![ Final ](captaincoco4.github.io/final.PNG)

## Game Controls
- Quit Game --> **Esc**
- Play Game --> **Arrow Keys**

## Game Graphics
- Backgorund Image --> [ Here ](https://wallpaperscraft.com/download/triangles_patterns_texture_127001/3840x2160?fbclid=IwAR2-L6SA7j3C1TfD8mKRmt77QAE49_pKG5UdW-1SPc1-MigsAmg-in7nWmc)

![ Background Image ](captaincoco4.github.io/background2.jpg)

- Sample Hit Arrow

![ Right Arrow ](captaincoco4.github.io/right.png)

- Sample Moving Arrow

![ Moving Right Arrow ](captaincoco4.github.io/mright.png)

- Column Highlighter
![ Column Highlighter ](captaincoco4.github.io/highlighter.png)
