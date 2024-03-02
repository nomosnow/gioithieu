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



## Bước 7

Đôi khi không phải lúc nào khối code có cùng màu với danh mục của nó.

Khối code ``||variables:set [mySprite] to sprite [ ] of kind [Player]||`` màu đỏ, nhưng lại nằm bên trong danh mục``||sprites:Sprites||``.

---

<!-- **Tip:** If you can't find the block you're looking for, try -->


🔲 Đặt``||variables:set [my sprite] to sprite [ ] of kind [Player]||`` vào phía cuối của **on start** a [__*sprite*__](#sprote "một vật thể 2-D di chuyển trên màn hình ")trên màn hình chính .

*(Di chuyển chuột đến từ *sprite* để xem định nghĩa)*

---

**Tip:** khi bạn tạo một sprite thì mặc định nó sẽ được đặt ở trung tâm màn hình. khối code *splash* đã che mất.
kéo khối code``||game:splash "___"||`` out of the ``||loops:on start||`` thả lại vào trong toolbox đễ xoá đi thì sprite sẽ xuất hiện.
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


## Bước 8: Khối code chính

**Bây giờ, chọn một khối code chính mới và học cách sử dụng nó** 

Trước tiên, chọn một khối code chính. đây là một khối code chữ nhật với chỗ trống ở giữa có thể chứa các khối code nhỏ khác. Khối code này có thể chạy được các khối code bên trong nó. 
thí dụ:

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
```
---

🔲  Tìm Khối code ``||controller:on [A] button pressed ||`` và đặt nó trên màn hình chính. chúng ta sẽ sử dụng nó vào bước kế tiếp.  

#### ~ tutorialhint

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let mySprite: Sprite = null
})
```

## Bước 9: khối code nhỏ

 Tiếp đến, khối code nhỏ hơn trông giống như mảnh ghép, giúp chúng có thể được đặt trong khối code chính. Chúng có thể đặt trồng lên nhau và chạy theo thứ tự từ trên xuống dưới.

đây là ví dụ của khối code nhỏ:

```block
let mySprite: Sprite = null;
mySprite.startEffect(effects.spray)
```

---

🔲 tìm khối code ``||sprites:[mySprite] start [spray] effect ||``  
 và đặt vào trong của khối code chính **on A button pressed** và lựa chọn hiệu ứng tại mũi tên đi xuống.

#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.startEffect(effects.confetti)
})
```



## Bước 10: chọn giá trị của khối code
Cuối cùng, ta có thể chọn giá trị cho từng khối code. Đôi khi đó là hình nhon, cong hoăc tròn.
 Giống như thế này:

![Value Blocks](/static/skillmap/interface/parameter-blocks.png "This is what the shape of an value block looks like" )

---

🔲  Đặt khối code `||sprites:[mySprite] say [":)"] ||`` xuống phía cuối của 
**on A button pressed**.

🔲  viết giá trị bất kì tại``||game: ask for number [" "] ||``" ".


#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.say(game.askForNumber(""))
})
```

##Bước 11: chạy thử

🎨Giờ là lúc chơi thử🎨

chọn bất kì khối code nào và xem phản ứng từ game



##  Bước 12: kết thúc 

🎈  Chúc mừng 🎈 

