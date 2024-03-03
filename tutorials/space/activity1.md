# Thám hiểm không gian


## Introduction @unplugged

** Hãy khám phá những cung đường của không gian! **

Trong hướng dẫn này, bạn sẽ thiết kế một chiếc tàu vũ trụ cho hành trình của mình.

![Flying through space](/static/skillmap/space/space1.gif "Blasting through a starfield" )

## Thiết lập cảnh quan

---

🔲 Kéo khối code ``||scene:start screen [confetti] effect ⊕||`` từ phần   ``||scene:Scene||`` và đặt vào khối code lớn ``||loops:on start||`` đã có sẵn ở màn hình chính.

🔲 Tiếp theo, chọn ``||scene:star field||`` (thay vì ``||scene:confetti||``) từ nhiều lựa chọn và ngắm xem quang cảnh ngoài không gian.


---


```blocks
// @highlight
effects.starField.startScreenEffect()
```



## Vẽ chiếc tàu của bạn
**🧑🏿‍🚀 Đến lúc chọn tàu của chúng ta! 👩🏾‍🚀**

---

🔲 Từ phần  ``||sprites:Sprites||`` kéo khối code ``||variables:set [mySprite] to sprite [ ] of kind [Player]||`` 
và đặt nó ở cuối khối code chính ``||loops:on start||``.

🔲 Nhấp vào hộp màu xám ở giữa của khối
 ``||variables:set [mySprite] to sprite [ ] of kind [Player]||``
để thiết kế một chiếc tàu của riêng bạn! Chiếc tàu này có phải là một đống phế liệu gỉ sét hay một tên lửa mạnh mẽ tương lai hóa?

---

**Mẹo Nhỏ:** Nếu Bạn không muốn vẽ chiếc tàu? Khi bạn ở trong trình chỉnh sửa sprite, bạn có thể
chuyển sang thư viện và chọn từ các hình ảnh sẵn có.

```blocks
effects.starField.startScreenEffect()
// @highlight
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
```

## Điều khiển chiếc tàu của bạn

🌟 Hãy làm cho chiếc tàu của bạn di chuyển 🌟

---

🔲 Tìm khối code nhỏ ``||controller:move [mySprite] with buttons ⊕||`` 
và kéo nó vào đoạn cuối của khối code lớn ``||loops:on start||``. 

**Bây giờ hãy thử di chuyển tàu của bạn trong bộ mô phỏng!**
Tàu của bạn sẽ di chuyển với phím mũi tên hoặc phím W A S D.  



```blocks
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
// @highlight
controller.moveSprite(mySprite)
```

## Giữ tàu trong màn hình

**Ôi không, nếu bạn di chuyển ra khỏi màn hình, tàu của bạn sẽ biến mất!**

---

🔲 Để giữ cho tàu của bạn không khám phá ra màn hình, tìm
 khối code nhỏ
 ``||sprites:set [mySprite] stay in screen <on>||`` 
 chọn chế độ bật (**on**) kéo nó vào cuối chương trình.
 


```blocks
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
// @highlight
mySprite.setStayInScreen(true)

```


## Finale @unplugged

**Bạn làm tốt lắm!**

---

Bây giờ hãy chắc chắn rằng bạn chơi trò chơi của mình trên bộ mô phỏng
trước khi bạn nhấp vào kết thúc trên hướng dẫn này. 

![You in space](/static/skillmap/space/space1end.gif "Blasting through your own game" )

Mọi thứ có ổn không? Bạn luôn có thể quay lại các bước trước và chỉnh sửa nếu bạn phát hiện ra điều gì đó bất hợp lý.



## Tạm biệt

** 🚀 Chỉ có vậy thôi 🚀**

Bạn đã sẵn sàng để du hành vũ trụ!

Nhấp vào **"Finish"** để thoát ra
