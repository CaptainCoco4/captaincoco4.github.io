## MNMLST
![Logo](captaincoco4.github.io/logo.PNG)

### Game Description
**MNMLST**, also known as _MINIMALIST_, is a game where one is expected to stay focused.

### Game Preview
Anyone with enough intuition can easily play the game from the get-go. But first, you must press Enter in order to proceed to the next screen.

**1.** Choose wave count (number of circles being dropped per wave)

![ Wave ](captaincoco4.github.io/wave.PNG)

**2.** A 3-2-1 countdown will commence to prepare you for the incoming wave of _Directions_

![ Countdown ](captaincoco4.github.io/countdown.PNG)

**3.** Circles with arrows, referred to as _Directions_, will start going down. The amount of _Directions_ per game will depend on the number you've chosen from the previous screen.

![ Game ](captaincoco4.github.io/game.PNG)

These _Directions_ are instances of a user-defined object, `Arrow`.
```markdown
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

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/CaptainCoco4/captaincoco4.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
