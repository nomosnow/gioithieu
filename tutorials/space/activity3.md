
## Giới Thiệu @unplugged

**Du hành vượt vũ trụ thật sự rất nguy hiểm!**

Hãy thêm vào một số kẻ thù để tàu của bạn tránh né.
Chúng có thể là đá hải vật, mảnh vụn phóng xạ hoặc cá mập không gian tức giận!

![Releasing projectiles](/static/skillmap/space/projectiles.gif "Here, enemy ship. Would you like to borrow an asteroid?")


## Bước 1

**👾Tạo kẻ thù rơi từ trên trời xuống không? 👾**

Hãy thêm một số khối code để thả một kẻ thù về phía tàu mỗi giây hoặc như vậy.

---
 
🔲 Thêm một khối code``||game:on game update every [500] ms||`` 

🔲 Thay đổi đối số cuối cùng thành **1000** [__*ms*__](#millis "milliseconds...aka 1/1000 of a second") 
(ohoặc chọn **1s** giây từ menu thả xuống)    
<br/>

```blocks
game.onUpdateInterval(1000, function () {
})
```

## Bước 2

🔲 Trong phần ``||sprites:Sprites||`` tìm khối 
``||variables:set [projectile2] to projectile [ ] from side with vx [50] vy [50]||``
và kéo vào khối code lớn **on game update**.

🔲 Nhấp vào giá trị ``||variables:[projectile2]||`` bên trong khối mới và
chọn "Rename variable..." để đổi tên.

🔲 Thay đổi tên biến thành ``||variables:myEnemy||`` để chúng ta biết rằng đó là kẻ thù.  
<br/>
```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
    // @highlight
    myEnemy = sprites.createProjectileFromSide(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, 50, 50)
})
```

## Bước 3
**🎆 Hãy cho kẻ thù di chuyển theo hướng đúng 🎆**

---

🔲 Nhấp vào hình vuông màu xám bên trong khối mới để thiết kế kẻ thù của bạn
(hoặc chọn một trong số đó từ thư viện **galery**.

🔲 Điều chỉnh các giá trị **vx** và **vy** của **myEnemy** cho đến khi
các hình mới của bạn đang rơi thẳng xuống bên cạnh màn hình. 


```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
    // @highlight
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
})
```

## Bước 4


Kẻ thù không thể gây ra vụ nổ tàu nếu chúng đều ở ngoài lề,
vì vậy hãy thêm một chút bất ngờ bằng cách sử dụng [__*random numbers*__](#randos "numbers appearing seemingly without a predictable pattern") .

---


🔲 Kéo một khối code``||sprites:set [mySprite] [x] to [0]||`` vào cuối của
khối **on game update**.  

🔲 Để chắc chắn rằng chúng ta đang tác động vào đúng nhân vật,
sử dụng menu thả xuống trong khối mới để thay đổi ``||variables:mySprite||`` to ``||variables:myEnemy||``.

🔲 Chọn một [__*x*__](#setX " vị trí ngang)  ngẫu nhiên cho kẻ thù, sử dụng một khối code 
``||Math:pick random [0] to [10]||`` từ ``||Math:Math||``.
Kết nối nó để thay thế **0** trong khối code **set mySprite x**.

🔲 Cuối cùng, cập nhật đối số tối thiểu của khối code 
``||Math:pick random [0] to [10]||`` thành **5** và đối số tối đa thành **155**. 

---

**Gợi ý**: Màn hình máy giả lập có chiều rộng là 160px,
vì vậy bạn có thể làm cho kẻ thù của bạn rơi ở bất kỳ nơi nào giữa 0 và 160
và vẫn có thể nhìn thấy chúng.


```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
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

    // @highlight
    myEnemy.x = randint(5, 155)
})
```


## Bước 5

Có thể bạn muốn thêm nhiều loại kẻ thù khác nhau rơi từ trên trời xuống.
Chúng ta có thể đảm bảo rằng tất cả chúng đều có cùng một hiệu ứng bằng cách sử dụng cùng một chủng loại
"**Enemy**".

---

🔲 Kéo một khối ``||sprites:set [mySprite] kind to [Player]||`` vào dưới cùng của
khối chính **on game update**. 

🔲 Thay đổi ``||variables:mySprite||`` thành ``||variables:myEnemy||``, sau đó chọn 
 ``||sprites:Enemy||`` thành loại.  
 <br/>


```blocks
let myEnemy: Sprite = null
game.onUpdateInterval(1000, function () {
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
    //@highlight
    myEnemy.setKind(SpriteKind.Enemy)
})
```




## Step 6


**💥 Đến lúc tạo hành vi cho kẻ thù 💥**

Để tạo thêm sự hứng thú cho trò chơi, hãy tạo một sự kiện khi một kẻ thù va chạm với tàu của chúng ta.

---


🔲 Kéo một khối code ``||sprites:on [sprite] of kind [Player] overlaps [othersprite] of kind [Player]||`` 
vào màn hình chính

🔲 Thay đổi ``||variables:Player||`` thành ``||variables:Enemy||``.

---

**Mẹo**: Đừng cố gắng thay đổi "sprite" → "mySprite" hoặc "otherSprite" → "myEnemy".
Các đối số "sprite" và "otherSprite" ở đây mô tả hai loại sprite chung trên màn hình
(không phải là các tạo vật cụ thể mà chúng ta đã đặt tên trước đó.)


```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {

})
```

## Bước 7

Khi kẻ thù va chạm với tàu,
chúng ta muốn nó giảm một mạng sống... rồi biến mất. 

---


🔲 Kéo một khối code ``||info:change life by [-1]||`` từ phần ``||info:Info||`` vào khối lớn
**on player overlaps enemy**. 
Điều này loại bỏ một mạng sống từ người chơi mỗi khi bị kẻ thù đánh.

🔲 Tìm khối code ``||sprites:destroy [mySprite] ⊕||`` và kéo nó xuống dưới khối trước.

🔲Để cho khối code **destroy** ảnh hưởng đến kẻ thù chạm vào thuyền của mình, 
ấn vào ``||variables:otherSprite||``từ **overlaps** và kéo nó xuống thay thế phần 
``||variables:mySprite||`` từ ``||sprites:destroy [mySprite] ⊕||``.
![Grabbing variable from block](/static/skillmap/space/give-var.gif "So that's how you do that!")

---

**Mẹo**: Nhấn ⊕ trên khối ``||sprites:destroy [otherSprite] ⊕||`` để có
một menu hiệu ứng hiển thị khi kẻ thù của bạn bị tiêu diệt!

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    otherSprite.destroy(effects.spray, 500)
})
```

## Bước 8

**🌍 Đến lúc cứu thế giới 🌏**

Thêm một **overlap** khác sẽ giúp các đạn đạo của chúng ta
tiêu diệt kẻ thù của chúng ta khi va chạm với chúng.

---


🔲 Kéo một khối code``||sprites:on [sprite] of kind [Player] overlaps [othersprite] of kind [Player]||`` khác vào màn hình chính. 

🔲 Thay đổi chủng loại đầu tiên thành ``||sprites:Enemy||`` và chủng loại thứ hai thành
``||sprites:Projectile||``. 

🔲 Bên trong, thêm hai khối code ``||sprites:destroy [mySprite] ⊕||`` và sau đó thay đổi các đối số
để phá hủy kẻ thù(``||variables:sprite||``) và cùng một lúc khác phá huỷ đạn(``||variables:otherSprite||``).

---

**Mẹo**: Đừng quên nhấn **⊕** trên khối **destroy** để có
một số hiệu ứng ngoạn mục khi viên đạn của bạn va chạm!

```blocks
sprites.onOverlap(SpriteKind.Enemy, SpriteKind.Projectile, function (sprite, otherSprite) {
    sprite.destroy(effects.bubbles, 500)
    otherSprite.destroy(effects.smiles, 500)
})
```

## Hoàn thành 

**Chúc mừng Bạn**

Bây giờ bạn đã có một loạt kẻ thù đầy đủ để chiến đấu!
Đừng quên thử trò chơi của bạn trên game mô phỏng trước khi nhấp vào "Done".

Khi bạn đã có trò chơi như mong muốn, nhấp vào nút "Done" để trở lại bản đồ và chọn phần kế tiếp.
