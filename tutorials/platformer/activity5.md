# Enemy AI

```jres
{
    "transparency16": {
        "data": "hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile1": {
        "data": "hwQQABAAAADMzMzMzMzMzLy7u7u7u7vLvMvMzMzMvMu8vMzMzMzLy7zMy8zMvMzLvMy8zMzLzMu8zMzLvMzMy7zMzLzLzMzLvMzMvMvMzMu8zMzLvMzMy7zMvMzMy8zLvMzLzMy8zMu8vMzMzMzLy7zLzMzMzLzLvLu7u7u7u8vMzMzMzMzMzA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile2": {
        "data": "hwQQABAAAAAiIiIiIiIiIkJEREREREQkQiIiIiIiIiRCIiIiIiIiJEIiREQiIiIkQkJERCIkJCRCQiREJCQkJEJCREQiQiIkQkJERCRCIiRCQiREIiQkJEIiREQkJCQkQiIiIiIiIiRCIiIiIiIiJEIiIiIiIiIkQkRERERERCQiIiIiIiIiIg==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile3": {
        "data": "hwQQABAAAAB3d3d3d3d3d1dVVVVVVVV1V3d3d3d3d3VXd3d3d3d3dVdXVVVVVXd1V1dXV3d3d3VXV3VVd3d3dVdXV1d3d3d1V3d1dXV3d3VXd1VXdXd3dVd3dXV1d3d1V3dVVXV3d3VXd3d3d3d3dVd3d3d3d3d1V1VVVVVVVXV3d3d3d3d3dw==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile4": {
        "data": "hwQQABAAAABERERERERERFRVVVVVVVVFVEREREREREVURFRFRERERVRERVRERERFVFRVVUVEREVUVFVVVURFRVRUVVVVVUVFVFRVVVVVRUVUVFVVVURFRVRUVVVFRERFVERFVEREREVURFRFRERERVRERERERERFVFVVVVVVVUVERERERERERA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile5": {
        "data": "hwQQABAAAACqqqqqqqqqqrq7u7u7u7uruqqqqqqqqqu6qqqqqqqqq7qqqqqqqqqruqqqqqqqqqu6qrurqqqqq7q6u7u7uqururq7u7u6q6u6qrurqqqqq7qqqqqqqqqruqqqqqqqqqu6qqqqqqqqq7qqqqqqqqqruru7u7u7u6uqqqqqqqqqqg==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "level": {
        "id": "level",
        "mimeType": "application/mkcd-tilemap",
        "data": "MTAxZTAwMGEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDA0MDAwMDAwMDAwMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAzMDAwMDAwMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMDAwMDEwMDAwMDUwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDUwMDAwMDAwMDAwMDUwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAyMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjIwMjIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDIwMjIyMjIyMjIwMjAwMDAwMDAwMDAyMDIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMg==",
        "tileset": [
            "myTiles.transparency16",
            "myTiles.tile1",
            "myTiles.tile3",
            "myTiles.tile4",
            "myTiles.tile5",
            "myTiles.tile2"
        ]
    },
    
    "level2": {
        "id": "level2",
        "mimeType": "application/mkcd-tilemap",
        "data": "MTAxZTAwMGEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDQwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAzMDAwMDAwMDAwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwNDAwMDAwMDAwMDAwMDAwMDAwMTAxMDUwMDAwMDEwMTAwMDAwMDAwMDEwMDAwMDAwMDAwMDAwMTAwMDAwMDAwMDUwMTAxMDEwMDAwMDEwMDAxMDUwNTAxMDEwMTAwMDAwMDAxMDEwMDAwMDAwMDAwMDAwMTAxMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDUwNTAxMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTA1MDUwNTA1MDAwMTAwMDEwMDAxMDUwNTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMjAwMDAwMDAwMDAwMDAwMDAwMDAwMDIwMDAwMDAwMDAwMDAyMDAwMDAwMDAwMjIwMDIwMDIwMDIwMDAwMDAwMDIwMDAwMjIwMjIwMjAwMDIyMDIwMDIyMDAwMDAwMjIwMDAwMDAyMjIyMjIwMDAyMjIyMjIyMjIyMjIyMjIyMjAwMDAyMDIwMjAwMA==",
        "tileset": [
            "myTiles.transparency16",
            "myTiles.tile1",
            "myTiles.tile3",
            "myTiles.tile4",
            "myTiles.tile5",
            "myTiles.tile2"
        ]
    },

    "*": {
        "mimeType": "image/x-mkcd-f4",
        "dataEncoding": "base64",
        "namespace": "myTiles"
    }
}
```






```template
scene.onOverlapTile(SpriteKind.Player, myTiles.tile2, function (sprite, location) {
    game.over(false)
})
scene.onOverlapTile(SpriteKind.Player, myTiles.tile4, function (sprite, location) {
    startNextLevel()
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.vy = -200
})
function startNextLevel () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        value.destroy()
    }
    currentLevel += 1
    if (currentLevel == 1) {
        scene.setBackgroundColor(11)
        tiles.setTilemap(tilemap`level`)
    } else if (currentLevel == 2) {
        scene.setBackgroundColor(9)
        tiles.setTilemap(tilemap`level2`)
    } else {
        game.over(true)
    }
    tiles.placeOnRandomTile(mySprite, myTiles.tile3)
    for (let value of tiles.getTilesByType(myTiles.tile5)) {
        myEnemy = sprites.create(img`
            a a a a a a a a a a a a a a a a 
            a b b b b b b b b b b b b b b a 
            a b a a a a a a a a a a a a b a 
            a b a a b b a a a a b b a a b a 
            a b a a a a b a a b a a a a b a 
            a b a a a a a a a a a a a a b a 
            a b a a a b a a a a b a a a b a 
            a b a a a b a a a a b a a a b a 
            a b a a a a a a a a a a a a b a 
            a b a a a a a a a a a a a a b a 
            a b a a a b b b b b b a a a b a 
            a b a a b a a a a a a b a a b a 
            a b a a a a a a a a a a a a b a 
            a b a a a a a a a a a a a a b a 
            a b b b b b b b b b b b b b b a 
            a a a a a a a a a a a a a a a a 
            `, SpriteKind.Enemy)
        tiles.placeOnTile(myEnemy, value)
        myEnemy.follow(mySprite, 30)
    }
}
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    if (sprite.bottom < otherSprite.y) {
        sprite.vy = -100
    } else {
        info.changeLifeBy(-1)
    }
})
let myEnemy: Sprite = null
let currentLevel = 0
let mySprite: Sprite = null
mySprite = sprites.create(img`
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3 
    3 1 3 3 1 3 3 1 3 1 1 3 3 3 1 3 
    3 1 3 3 1 3 3 1 3 3 1 3 3 3 1 3 
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3 
    3 1 3 3 1 3 3 3 3 3 1 3 3 3 1 3 
    3 1 3 3 1 3 3 3 3 1 1 1 3 3 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3 
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3 
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 
    `, SpriteKind.Player)
mySprite.ay = 500
controller.moveSprite(mySprite, 100, 0)
scene.cameraFollowSprite(mySprite)
info.setLife(3)
startNextLevel()

```

## Khởi động @unplugged

Bạn có thể thấy rằng kẻ địch của chúng ta vẫn chỉ biết lao về phía nhân vật và không biết tránh các chướng ngại vật? Chúng có vẻ không thông minh lắm nhỉ?

Vậy thì để cho chúng trở nên khó lường hơn, độ khó của game sẽ tăng lên và thú vị hơn, ta dùng cơ chế [_**AI**_](#fakeSmart "artificial intelligence") nhé.



## Cơ chế AI? @unplugged

Cơ chế tạo kẻ địch ở game này xoay quanh việc đặt vị trí các ô **[ ! ]** (màu tím).
Một khi kẻ địch xuất hiện, chúng chỉ biết lao về phía bên trái nơi có nhân vật. Một khi nhân vật đã vượt qua chúng (nhảy qua đầu) hoặc gặp phải chướng ngại vật thì những kẻ địch chỉ còn biết đứng nhìn. Chúng ta biết chuyện này hơi vô lí nên sẽ phải chỉnh sửa chút nhé.
<hr/>
**Có 2 điều ta cần làm để cho kẻ địch mạnh hơn:**

1. **Khi sắp va vào tường chắn, kẻ địch phải biết nhảy vượt qua**  
2. **Khi kẻ địch chạm vào chướng ngaị vật, chúng sẽ biết quay đầu**

<hr/>

Mỗi một điều ở trên bao gồm *điều kiện* dẫn tới *hành động*.  

Khi đạt được *điều kiện* (va vào tường chắn hoặc chạm chướng ngại vật) thì *hành động* tương ứng sẽ diễn ra (nhảy qua hoặc quay đầu).
Ta sẽ gán các *điều kiện* cụ thể với *hành động* tương ứng.

## Xử lý các hành vi có tính lặp lại (phần 1)

Ta cần 1 dãy lệnh **phản ứng** mỗi khi có sự thay đổi của trạng thái mỗi kẻ địch trong game. Từ đó, ta sẽ dễ dàng thiết lập hành vi của những tên địch này ở từng trường hợp.   
<hr/>

🔲 Kéo khối lệnh ``||game:on game update||`` ra màn hình làm việc.

🔲 Kéo tiếp khối ``||loops: for element [value] of [list]||`` vào bên trong khe trống của lệnh **on game update** vừa tạo.

```blocks
let list: number[] = [];
game.onUpdate(function () {
    for (let value of list) {
    }
})
```

## Xử lý các hành vi có tính lặp lại (phần 2)

Mỗi hành vi và trạng thái của từng kẻ địch diễn ra, ta sẽ đều để một hành động phản ứng lại nhanh chóng.
<hr/>

🔲 Từ công cụ ``||sprites:Sprites||`` ta kéo khối ``||sprites:array of sprites of kind||`` ra ngoài.

🔲 Kéo khối đó vào chèn thay chỗ ô ``||variables: list||`` màu đỏ trong lệnh loop **for element**.

🔲 Đổi giá trị sau "kind" từ **Player** thành **Enemy**.  
<br/>

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
    }
})
```

## Kẻ địch biết nhảy! (phần 1)

Bắt đầu với cặp **điều kiện** - **hành đông** đầu tiên:

> 1. **Khi sắp va vào tường chắn, kẻ địch phải biết nhảy vượt qua**  
<hr/>

🔲 Lại dùng hàm **if- then**, ta kéo khối lệnh ``||logic: if <true> then||`` vào khe trống trong lệnh **on game update** (màu xanh lá cây).

🔲 Kéo và thả chèn thay ô ``||logic: <true>||`` màu xanh bên trong hàm **if/then** bằng khối ``||scene: is [mySprite] hitting wall [left]||``.  

🔲 Đổi giá trị ``||variables: mySprite||`` bằng cách kéo ô ``||variables: value||`` màu đỏ từ trên hàm **for element** xuống chèn vào.

🔲 Đổi giá trị từ **left** thành **bottom**.


```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
           
        }
    }
})
```

## Kẻ địch biết nhảy! (phần 2)

Giờ kẻ địch đang ở trạng thái dưới mặt đất, và chúng có 2 trường hợp có thể xảy ra với chúng:  
 - Kẻ địch đi sang trái và trước mặt chúng có tường chắn
 - Kẻ địch đi sang phải và trước mặt chúng cũng sẽ có tường chắn

Ta lại dùng hàm **nếu-thì** (**if/then**) để thể hiện 2 trươngf hợp này nhé.
<hr/>

🔲 Kéo tiếp mộtj khối lệnh ``||logic:if <true> then||`` và đặt vào trong khe trống của lệnh **if-then** trước đó.

🔲 Để cùng lúc có thể xử lý 2 trường hợp trên của kẻ địch, ta kéo cụm ``||logic: < > and < >||`` và thay cho ô ``||logic:<true>||`` màu xanh bên trong hàm **if/else** mới nhất.

🔲 Với ô trống bên phải dấu **=**, ta kéo cụm ``||scene: tile to the [left] of [mySprite] is [ ]||`` và thả vào.

🔲 Nhân bản ô ``||variables: value||`` màu đỏ phía trên rồi kéo xuống thay thế cho ô ``||variables: mySprite||`` , đồng thời kích vào ô vuông xám để đổi thành dấu **[X]**. 

🔲 Với ô trống còn lại bên trái dấu **=**, kéo cụm ``||logic: [0] [<] [0]||`` và thả vào.   

Sẵn sàng chuyển sang công đoạn tiếp theo.  

<br/>

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (0 < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
               
            } 
})
```

## Kẻ địch biết nhảy! (phần 3)

Giờ ta sẽ giúp kẻ địch phân biệt hai bên **trái - phải**.
<hr/>

🔲 Nhìn vào ô ``||logic: [0] [<] [0]||`` màu xanh dương, ta kéo cụm ``||sprites: [mySprite] [x]||`` ra và thả vào thay thế số **0** bên trái.

🔲 Tiếp tục nhân bản ô ``||variables: value||`` màu đỏ và kéo vào thay thế cho từ ``||variables: mySprite||`` bên dưới, đồng thời đổi giá trị **x** bên cạnh thành **vx (velocity x)**.   
<br/>


```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
            }    
        }
    }
})
```


## Kẻ địch biết nhảy! (phần 4)

Giờ thì đã đủ điều kiện cho kẻ địch "**nhảy**"!
<hr/>

🔲 Ở hàm **if/else** trong cùng, ta kéo khối ``||sprites:set [mySprite] [x] to [0]||`` và thả vào trong khe trống.

🔲 Nhân bản ô đỏ ``||variables: value||`` và kéo xuống chèn thay ô ``||variables: mySprite||``, đồng thời đổi giá trị ``||sprites: x||`` thành ``||sprites: vy (velocity y)||``. 

🔲 Xoá số **0** và đánh **-150** vào.  
<br/>

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            } 
    }
})
```


## Jumping pt. 7

Next, we'll add the code to do the same thing to the right.
<hr/>

🔲 Click twice on the **⊕** button at the bottom of the innermost **if/else**
statement that we've just completed, to add an **else** then an **else if** clause.

🔲 Duplicate the entire **and** statement, then drop the duplicate into the
header of the **else if** clause.  

🔲 In the new clause, change **<** to **>** and **left** to **right**.

🔲 Duplicate the ``||sprites:set [value] [vy (velocity y)] to [-150]||`` block 
and snap the copy inside the empty **else if** statement.

🔲 We're done with this **if/else if** statement now, so you can click the 
**⊖** beside the **else** clause to remove it from the block.

<br/>

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            } else if (value.vx > 0 && value.tileKindAt(TileDirection.Right, myTiles.tile1)) {
                value.vy = -150
            }
        } 
    }
})
```


## Wall bouncing pt. 1

We've completed the code for rule #1, now let's take a look at rule #2.

> 2. **If the enemy does hit a wall, it will turn around**

<hr/>
The case for an enemy not running into a wall while traveling on the ground has been handled.
Next, we need to add cases for when an enemy runs into a wall on the left or right
while it's already trying to jump.

🔲 Click three times on the **⊕** button at the bottom of the outermost **if/else**
statement (**if <is value hitting wall bottom> then**) to add an **else** and two **else if** clauses.

🔲 Duplicate the ``||scene: is [value] hitting wall [bottom]||`` argument twice and 
place a copy in each of the new **else if** headers.

🔲 Change **bottom** to **left** in the first **else if**.

🔲 Change **bottom** to **right** in the second **else if**.  
<br/>

```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            } else if (value.vx > 0 && value.tileKindAt(TileDirection.Right, myTiles.tile1)) {
                value.vy = -150
            }
        } else if (value.isHittingTile(CollisionDirection.Left)) {

        } else if (value.isHittingTile(CollisionDirection.Right)) {
 
        }
    }
})
```

## Wall bouncing pt. 2

Finally, we need to add the code to make the enemies turn right if they were
going left and left if they were going right.
<hr/>

🔲 Make two duplicates of one of the ``||sprites:set [value] [vy (velocity y)] to [-150]||`` blocks from the original **if/then**
clause and snap one into each of the empty **else if** clauses.

🔲 For the **set value** block inside the first **else if** clause 
(**else if <is value hitting wall left> then**), change 
**vy (velocity y)** to **vx (velocity x)** and change **-150** to **30**.

🔲 For the **set value** block inside the second **else if** clause 
(**else if <is value hitting wall right> then**), change 
**vy (velocity y)** to **vx (velocity x)** and change **-150** to **-30**.


```blocks
game.onUpdate(function () {
    for (let value of sprites.allOfKind(SpriteKind.Enemy)) {
        if (value.isHittingTile(CollisionDirection.Bottom)) {
            if (value.vx < 0 && value.tileKindAt(TileDirection.Left, myTiles.tile1)) {
                value.vy = -150
            } else if (value.vx > 0 && value.tileKindAt(TileDirection.Right, myTiles.tile1)) {
                value.vy = -150
            }
        } else if (value.isHittingTile(CollisionDirection.Left)) {
            value.vx = 30
        } else if (value.isHittingTile(CollisionDirection.Right)) {
            value.vx = -30
        }
    }
})
```


## Finish

🎊 Congratulations 🎊

You've created an arcade game with levels, interactive tilemaps, and 
intelligent enemies! Now make sure to play through it, then share with friends.

Arcade has many options that haven't been explored here.  If you have time,
you should click out to the main Arcade page and play with our full editor
to make a game all of your own!

