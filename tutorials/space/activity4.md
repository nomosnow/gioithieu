# Tiếp Thêm Năng Lượng
## Giới Thiệu @unplugged

Đến lúc nạp năng lượng!

Trong hướng dẫn này, chúng ta sẽ thêm một thanh nhiên liệu vào tàu vũ trụ của bạn để giảm dần khi bạn đi khám phá ngoài không gian.

Hãy chắc chắn bắt các vật phẩm năng lượng để giữ cho tàu không bị hỏng!

![Fuel Up!](/static/skillmaps/space/eat-gas.gif "Is it raining...tacos?")


## Bước 1
😵 Đoạn code khởi đầu đang chiếm rất nhiều không gian!
Đừng lo lắng, không gian làm việc Arcade sẽ mở rộng cho bạn. Chỉ cần cuộn lên và qua (hoặc xuống và qua) để tiếp tục viết code game nha.
<hr/>

🔲 Hãy nhìn vào mục mới  ``||statusbars:Status Bars||``.
Bạn sẽ tìm thấy ``||variables:set [statusbar] to create status bar sprite width [20] height [4] kind [Health]||``.
Kéo một cái vào cuối khối chính ``||loops:on start||``.

🔲 Để theo dõi lượng còn bao nhiêu nhiên liệu còn lại, đặt thông số cho
**statusbar** thành **Energy**.
<hr/>

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
```

## Bước 2
Nếu chúng ta muốn thanh trạng thái hiển thị chi tiết của **mySprite**, chúng ta sẽ cần liên kết hai cái với nhau.

<hr/>

🔲 Kéo ``||statusbars:attach [statusbar] to [mySprite] ⊕||`` 
vào cuối khối lớn ``||loops:on start||``.

🔲 Nhấp vào **⊕** trên khối mới để hiện các tùy chọn
để thay đổi vị trí của thanh trạng thái máu liên quan đến **mySprite**.
Bạn có thể tìm ra cách để thanh máu xuất hiện dưới tàu của bạn không?

<br/>

```block
let statusbar = statusbars.create(20, 4, StatusBarKind.Energy)
// @highlight
statusbar.attachToSprite(mySprite, -25, 0)
```

## Bước 3
⏰ Càng lâu bạn ở trong không trung, bạn sẽ sử dụng nhiều nhiên liệu hơn ⏰

Dưới đây là cách làm cho nhiên liệu giảm dần khi thời gian trôi qua. 
<hr/>

🔲 Kéo một khối ``||game:on game update every [500] ms||`` vào
 màn hình chính. Điều chỉnh đối số thời gian thành **300 ms**.

🔲 Kéo một khối  ``||statusbars:change [statusbar] [value] by [0]||``
vào khối **game update**.

🔲 Thay đổi số lượng thanh trạng thái máu thay đổi từ **0** thành **-1**.
<hr/>

>> *Mẹo: Nhớ bước này sau này. Nếu nhiên liệu hết quá nhanh trong
trò chơi, bạn có thể quay lại và điều chỉnh các khối này.*


```blocks
let statusbar: StatusBarSprite = null
game.onUpdateInterval(300, function () {
    statusbar.value += -1
})
```

## Bước 4
⛽ Đến lúc nạp nhiên liệu ⛽

Bạn có thể thả hộp nhiên liệu, tinh thể năng lượng, hoặc bánh hamburger ngon...bất cứ thứ gì
phù hợp với tàu bạn có.

Code để thả nhiên liệu khá giống với để để thả kẻ thù.
Để làm mới về cách thức hoạt động, tìm các khối **myEnemy** màn hình chính và sử dụng chúng như một hướng dẫn.
<hr/>
🔲 Kéo một khối ``||game:on game update every [500] ms||`` mới vào màn hình chính và thay đổi khoảng thời gian thành **5 seconds (5000 ms)**. (5 giây)

🔲 Thả một khối
``||variables:set [projectile2] to||`` ``||sprites:projectile [ ] from side with vx [50] vy [50]||``
  vào bên trong **on game update**.

🔲 Nhấp vào ``||variables:[projectile2]||`` và đổi tên sprite thành ``||variables:[myFuel]||``.

🔲 Nhấp vào hình vuông màu xám để hiển thị trình soạn thảo sprite để bạn có thể
vẽ một sprite nhiên liệu (hoặc chọn một trong bộ sưu tập **Gallery**.) 

🔲 Đổi các đơn vị **vx** và **vy** của nhiên liệu cho đến khi nó rơi
thẳng xuống với tốc độ khá.

<br/>


```blocks
game.onUpdateInterval(5000, function () {
    let myFuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
})
```
## Bước 5
Giống như với kẻ thù, chúng ta muốn nhiên liệu rơi từ một vị trí ngẫu nhiên
trên đỉnh màn hình.

<hr/>
🔲 Kết nối một khối ``||sprites:set [mySprite] [x] to [0]||`` ở phía dưới của ``||game:on game update every [5000] ms||``.  

🔲 Để đảm bảo chúng ta đang sử dụng đúng các sprite, thay đổi tên``||variables:mySprite||`` to ``||variables:myFuel||``.

🔲 Để đặt một [__*x*__](#setX "vị trí chiều ngang")  ngẫu nhiên cho nhiên liệu, kéo một
khối
``||Math:pick random [0] to [10]||`` và kết nối nó để thay thế đối số **0** trong khối code
``||sprites:set [mySprite] [x] to [0]||``.

🔲 Cập nhật giá trị tối thiểu của khối code``||Math:pick random [0] to [10]||`` thành **5** và giá trị tối đa thành **155**. 
<hr/>

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

game.onUpdateInterval(5000, function () {
    let myFuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
        // @highlight
    myFuel.x = randint(5, 155)   
})
```

## Bước 6
Bây giờ chúng ta cần đặt chủng loại sprite **myFuel**  **GAS**.
<hr/>
🔲 Kéo một  ``||variables:set [mySprite] kind to [Player]||`` 
vào dưới cùng của khối chính **on game update**.

🔲 Thay đổi  ``||variables:mySprite||`` thành ``||variables:myFuel||``. 

🔲 ấn ``||sprites:Player||`` rồi chọn
``||sprites:Add a new kind...||`` viết vào **GAS**.  
<br/>

```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

game.onUpdateInterval(5000, function () {
    let myFuel = sprites.createProjectileFromSide(img`
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        5 . . . . . . . . . . . . . . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 . . 5 5 5 5 . 5
        5 . 5 5 5 5 . 5 5 . 5 5 5 5 . 5
        5 . 5 5 5 5 . . . . 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . 5 5 5 5 5 5 5 5 5 5 5 5 . 5
        5 . . . . . . . . . . . . . . 5
        5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
        `, 0, 50)
    myFuel.x = randint(5, 155) 
    // @highlight  
    myFuel.setKind(SpriteKind.Gas)
})
```


## Bước 7
Khi tàu của bạn chạm với nhiên liệu, bạn muốn nhiên liệu biến mất khi bình nhiên liệu được làm đầy lại.
<hr/>  

🔲 Kéo một ``||sprites:on [sprite] of kind [Player] overlaps [othersprite] of kind [Player]||`` 
vào màn hình. 

🔲 Thay đổi lựa chọn  ``||sprites:Player||`` thành ``||sprites:Gas||``.  

🔲 Để làm đầy lại thanh trạng thái sau khi lấy nhiên liệu, kéo một khối code ``||statusbars:set [statusbar] [value] to [0]||`` và kết nối nó vào khối **overlaps** mới nhất của bạn. Thay đổi giá trị từ **0** thành **100**.

🔲 Cuối cùng, đảm bảo nhiên liệu đã sử dụng biến mất bằng cách kéo một khối``||sprites:destroy [mySprite] ⊕||`` vào phía cuối của **overlaps** và đổi giá trị ``||variables:mySprite||`` thành ``||variables:otherSprite||``

![Grabbing variable from block](/static/skillmaps/space/give-var.gif "So that's how you do that!")

<br/>


```blocks
namespace SpriteKind {
    export const Gas = SpriteKind.create()
}

let statusbar: StatusBarSprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Gas, function (sprite, otherSprite) {
    statusbar.value = 100
    otherSprite.destroy()
})
```

## Bước 9
🌌 Nếu bạn hết nhiên liệu, bạn sẽ bị bỏ lại trong không gian! 🌌

Đây là mối đe dọa là thực sự.

<hr/>
🔲 Để thêm hậu quả cho việc hết nhiên liệu, kéo một
``||statusbars:on status bar kind [Health] zero [status]||`` 
vào màn hình chính.

🔲 Thay đổi loại thanh trạng thái năng lượng thành **Energy**.(Trong tiếng anh Energy nghĩa là năng lượng) 

🔲 Kéo một khối code ``||game:game over <LOSE>||`` vào trong như số phận cuối cùng.

<hr/>
Và đó là tất cả!  Bạn nên có một trò chơi hoàn chỉnh.
<br/>

```blocks
statusbars.onZero(StatusBarKind.Energy, function (status) {
    game.over(false)
})
```

```template

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let projectile = sprites.createProjectileFromSprite(img`
3 3 3 3 3 3 3 3
3 . . . . . . 3
3 . 3 3 3 3 . 3
3 . 3 . . 3 . 3
3 . 3 . . 3 . 3
3 . 3 3 3 3 . 3
3 . . . . . . 3
3 3 3 3 3 3 3 3
    `, mySprite, 0, -70)
    projectile.startEffect(effects.ashes)
})
sprites.onOverlap(SpriteKind.Projectile, SpriteKind.Enemy, function (sprite, otherSprite) {
    sprite.destroy(effects.bubbles, 500)
    otherSprite.destroy(effects.smiles, 500)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    otherSprite.destroy(effects.disintegrate, 500)
})
let myEnemy: Sprite = null
effects.starField.startScreenEffect()
let mySprite = sprites.create(img`
    . . . . . . . 9 9 . . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . 9 . 9 9 9 9 9 9 . 9 . . .
    . . . 9 . 9 . . . . 9 . 9 . . .
    . . 9 . 9 9 . 9 9 . 9 9 . 9 . .
    . . 9 . 9 9 . . . . 9 9 . 9 . .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    9 . 9 9 9 9 9 9 9 9 9 9 9 9 . 9
    9 . . . . . . . . . . . . . . 9
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9
`, SpriteKind.Player)
controller.moveSprite(mySprite)
mySprite.setFlag(SpriteFlag.StayInScreen, true)
game.onUpdateInterval(500, function () {
    myEnemy = sprites.createProjectileFromSide(img`
        2 2 2 2 2 2 2 2 2 2 2 2 2 2 2 2
        2 . . . . . . . . . . . . . . 2
        2 . 2 2 2 2 2 2 2 2 2 2 2 2 . 2
        . 2 . 2 2 2 . . . . 2 2 2 . 2 .
        . 2 . 2 2 2 . 2 2 2 2 2 2 . 2 .
        . . 2 . 2 2 . . . 2 2 2 . 2 . .
        . . 2 . 2 2 . 2 2 2 2 2 . 2 . .
        . . . 2 . 2 . . . . 2 . 2 . . .
        . . . 2 . 2 2 2 2 2 2 . 2 . . .
        . . . . 2 . 2 2 2 2 . 2 . . . .
        . . . . 2 . 2 2 2 2 . 2 . . . .
        . . . . . 2 . 2 2 . 2 . . . . .
        . . . . . 2 . 2 2 . 2 . . . . .
        . . . . . . 2 . . 2 . . . . . .
        . . . . . . 2 . . 2 . . . . . .
        . . . . . . . 2 2 . . . . . . . 
        `, 0, 50)
    myEnemy.x = randint(5, 155)
    myEnemy.setKind(SpriteKind.Enemy)
})

```

```ghost
statusbar.positionDirection(CollisionDirection.Bottom)
```

```package
pxt-status-bar=github:jwunderl/pxt-status-bar
```
