# Get to Know MakeCode Arcade 


```ghost
let mySprite: Sprite = null;
mySprite.startEffect(effects.spray)
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    game.showLongText("The little unicorn walked into the meadow.", DialogLayout.Top)
    scene.cameraShake(4, 500)
})
scene.setBackgroundColor(9)
scene.setBackgroundImage()
mySprite.x += 0
effects.confetti.startScreenEffect()
effects.confetti.endScreenEffect()
mySprite.setPosition(70, 80)
for (let index = 0; index < 4; index++) {
    controller.moveSprite(mySprite)
    music.setVolume(20)
    music.playMelody("- - - - - - - - ", 120)
}
game.onUpdateInterval(5000, function () {
    if (game.askForString("Continue?") == "Y" || game.askForString("Continue?") == "y") {
        mySprite.say(":)")
    }
    game.splash("")
})

```

### @explicitHints true

## Introduction @unplugged

![Psyched Monkey](/static/skillmap/interface/monkey.png "Psyched Monkey is Ready!" )

**Bạn Đã Sẵn Sàng Tạo Game Một Game Riêng Cho Mình Chưa?**

Hoàn Thành hướng dẫn để học cách:
- làm theo hướng dẫn 
- Tìm Đoạn code hợp lý từ thanh công cụ
- xây dựng code trên màn hình chính
- chạy game trên máy giả lập game


Chúc Bạn Vui Vẻ

## Bước 1

**⭐ Chào Mừng Bạn ⭐**

Một trong những phần quan trọng nhất trong việc làm theo hướng dẫn đó là đọc hướng dẫn!

---

Sau khi hoàn thành hướng dẫn Ấn **[ ->  Next]** để tiếp tục bước tiếp theo  


## Bước 2

Đây là hướng dẫn đầu tiên .
Nếu Bạn không hiểu đươc hưỡng dẫn , hãy nhấn hình bóng đèn phía dưới bên trái để có thêm giải thích hoặc lời giải.


#### ~ tutorialhint 
```
**Bạn đã tìm thấy lời giải tại đây!**
```

## Bước 3: Sử Dụng Màn Hình Chính Để Viết code

Màn hình chính bên phải là nơi liên kết các đoạn khối code lại với nhau để tạo thành trò chơi.
Trên màn hình chính có khối code **on start** để bạn bắt đầu.

---

🔲  Ấn chuột vào dòng chữ``||game:splash "___"||`` và thay đổi thành một câu hoàn chỉnh.

---


#### ~ tutorialhint 
```blocks
game.splash("Tôi thích chơi game")
```

```template
game.splash("Đây là câu có sẵn")

```

## Bước 4: Giới thiệu về khối code  @unplugged

khối code có thể giữ và kéo ra khỏi thanh công cụ [__*toolbox*__](#tools "Phía bên trái màn hình chính. Tại Đây có danh sách các khối chính"), 

liên kết, nhân bản hoặc là xoá bỏ.

Tiếp tục học thêm về khối code.

![Block Animation](/static/skillmap/interface/use_blocks.gif "Blocks appear, duplicate, and delete." )



## Bước 5: Thanh công cụ Toolbox

**Khối code không phải lúc nào cũng có mặt sẵn trên màn hình.**

khối code luôn luôn cùng màu với danh mục của nó

**Ví Dụ:** chúng ta có thể dùng khối code ``||game:splash "___"||`` thực ra là chúng tôi muốn bạn tìm thấy cái này: 

```block
game.splash(" ")
```

Đoạn khối code này tạo  [__*đoạn chữ giới thiệu*__](#splasht "A full-screen message that shows while a program or level is loading") cho game của bạn.

## Bước 6: Thanh Công cụ toolbox thứ 2



**thử xem nào**

🔲 Tìm khối code
``||scene:set background color to [ ]||`` đặt lên phía trong đầu tiên
của **on start** đã có sẵn ở màn hình chính. 

#### ~ tutorialhint 
```blocks
scene.setBackgroundColor(0)
game.splash("game của tôi là hay nhất")
```



## The Exception

Every rule has an exception, so let's look at one of the blocks
that doesn't share the same color as the category where it lives.

The ``||variables:set [mySprite] to sprite [ ] of kind [Player]||`` block
is red, but it lives inside the ``||sprites:Sprites||`` category.

---

<!-- **Tip:** If you can't find the block you're looking for, try -->


🔲 Snap ``||variables:set [my sprite] to sprite [ ] of kind [Player]||`` into the
end of the **on start** container and 
play around with it until a [__*sprite*__](#sprote "A 2-D image that moves on the screen") shows on the screen.

*(Roll your mouse over the word __sprite__ above to see a definition.)*

---

**Tip:** Drag ``||game:splash "___"||`` out of the ``||loops:on start||`` container
and drop it back into the toolbox to delete it so your sprite will be revealed!

#### ~ tutorialhint

![Open image editor](/static/skillmap/misc/open-image-editor-small.gif "How to open the image editor." )

---



```blocks
scene.setBackgroundColor(5)
let mySprite = sprites.create(img`
    e e e . . . . e e e . . . . 
    c d d c . . c d d c . . . . 
    c b d d f f d d b c . . . . 
    c 3 b d d b d b 3 c . . . . 
    f b 3 d d d d 3 b f . . . . 
    e d d d d d d d d e . . . . 
    e d f d d d d f d e . b f b 
    f d d f d d f d d f . f d f 
    f b d d b b d d 2 f . f d f 
    . f 2 2 2 2 2 2 b b f f d f 
    . f b d d d d d d b b d b f 
    . f d d d d d b d d f f f . 
    . f d f f f d f f d f . . . 
    . f f . . f f . . f f . . . 
    `, SpriteKind.Player)
```


## Container Blocks

**Now let's look at different types of blocks and how to use them.** 

First, there are [__*container blocks*__](#blockIt "Blocks that hold other blocks"). 
Container blocks have an edge at both the the top and bottom with an open space
in the middle that allows other blocks to snap inside. Container blocks control 
*when* the code inside runs. Here is an example:

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
```
---

🔲  Find an ``||controller:on [A] button pressed ||`` container 
block and drag it into the workspace. You will add to it in the next step.  

#### ~ tutorialhint

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let mySprite: Sprite = null
})
```

## Standard Blocks

Next, there are [__*standard blocks*__](#sBlockIt "Single line blocks that make up the majority of most programs"). 
Standard blocks are single-line blocks with notches at the top and bottom that
allow them to click-in between other pieces. These blocks run in order from top 
to bottom within the container that they're placed.

Here is an example of a standard block:

```block
let mySprite: Sprite = null;
mySprite.startEffect(effects.spray)
```

---

🔲  Find a ``||sprites:[mySprite] start [spray] effect ||``  
block and snap it into the  **on A button pressed** container...then 
choose your own effect!

#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.startEffect(effects.confetti)
})
```



## Value Blocks

Finally, we have [__*value blocks*__](#aBlockIt "special pieces that provide values for other blocks"). 
Value blocks are special pieces that add information to other
blocks. Sometimes they're pointy, sometimes they're rounded,
but they always need another block to snap into. Value blocks look something like this:

![Value Blocks](/static/skillmap/interface/parameter-blocks.png "This is what the shape of an value block looks like" )

---

🔲  Snap a ``||sprites:[mySprite] say [":)"] ||`` block into the end of the
**on A button pressed** container.

🔲  Find the ``||game: ask for number [" "] ||`` value block and pop it inside to replace **":)"**.

---

**Tip:** Value blocks have different shapes 
depending on what kind of information they add. Each value will only
fit in certain types of spaces. 

#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.say(game.askForNumber(""))
})
```

## Putting it Together

🎨 Now get creative 🎨

Feel free to take a look at the extra blocks we've added into the toolbox. 

It's okay if you don't know what they all do.
Play around with them and see how they affect your game!

---

**Tip:** You can test your game whenever you want using the simulator
to the left!  Use the refresh button (🔄) to reload it, and play your
game using the buttons you've programmed!  



## Conclusion 

🎈 Congratulations 🎈 

You've learned everything you need to know to graduate to a new tutorial.

Now you can continue on and learn even more tricks for
creating games with MakeCode Arcade!  
