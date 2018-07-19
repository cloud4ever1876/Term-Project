# 华容道
![游戏截图](https://github.com/zerofang/Term-Project/blob/master/Java/term-project-java/images/start.jpg)
![游戏截图](https://github.com/zerofang/Term-Project/blob/master/Java/term-project-java/images/success.jpg)
#### 1)	游戏界面的构造
利用Java Swing 制作游戏界面，分为四部分：游戏角色方块，游戏区边框，重新开始按钮，成功提示。
游戏角色方块用按钮制作，根据人物角色的不同设置不同的尺寸，并根据计算好的位置摆放按钮，并对其添加事件监听。
游戏边框也是按钮，根据计算好的尺寸和位置摆放，按钮设置为不可用。
重新开始按钮是一个普通按钮，摆放在计算好的位置，点击后new一个新的华容道对象，实现游戏重置。
成功提示是当代表曹操的方块移动到下方边界中央时在游戏上方空白处出现“成功出逃！”字样，具体实现方法为在游戏开始时将成功提示的位置定在游戏界面之外，使其对用户不可见，当游戏成功后再设置到游戏界面以内的正常位置，使其对用户可见。
#### 2)	游戏逻辑及动作的实现
我们将代表不同角色的按钮按对角线逻辑划分为四块不同的区域，代表不同的方向，当用户点击具体某一区域时，从点击事件监听器获取点击位置的坐标，然后通过计算得到点击位置所属区域，进而得到方块下一步要移至的方向。然后检查要移至的区域是否已经存在其他方块或者存在边界，具体检查方法是将所有按钮占据的区域转换为矩形，然后遍历所有角色按钮和边框按钮，看是否与当前按钮将要移至的位置矩形发生重叠，若重叠则说明此移动方向不合法，不予任何反馈，否则为相应按钮方块设置新的位置，方块移动至相应的合法方向，当用户将代表曹操的方块移动至靠近下方边界中间位置时提示成功出逃：
![游戏设计](https://github.com/zerofang/Term-Project/blob/master/Java/term-project-java/images/design.jpg)