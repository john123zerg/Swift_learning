# Swift_learning



# for
for i in 1 ... num{
  code()


}

# if 
if condition {
  code()
}

# Logic
&&, ||, !

# var
after saving an information type, you can never change it
(e.g., var a = 3
a = 'a' -> can not do)

var gemCounter = 
while !isOnGem{
    moveForward()
    if isOnGem{
        collectGem()
        gemCounter+=1
    }
    if gemCounter==1{
        break
    }
}


===
var gemCounter=0
var blockCounter = 0
while !isOnGem{
    blockCounter=0
    moveForward()
    if isOnGem{
        collectGem()
        gemCounter+=1
    }
    while isBlocked{
        turnRight()
        blockCounter+=1
    }
    if blockCounter==2{
        break
    }
}

=====
greenPortal.isActive = false
var greenPortal_num=0
while !isBlocked {
    moveForward()
    if !isBlockedLeft{
        turnLeft()
    }
    if isOnClosedSwitch{
        toggleSwitch()
        greenPortal_num+=1
    }
    if isBlocked{
        turnRight()
        turnRight()
    }
    if greenPortal_num==3{
        break
    }
}
===
var gem_num=0
bluePortal.isActive=false
pinkPortal.isActive=false
while gem_num<4{
    moveForward()
    if isOnGem{
        collectGem()
        turnLeft()
        turnLeft()
        gem_num+=1
    }
    if gem_num==1{
        pinkPortal.isActive=true
        bluePortal.isActive=true
    }
    if gem_num==3{
        bluePortal.isActive=false
    }
    if isBlocked{
        turnLeft()
        turnLeft()
    }

}

====
let expert = Expert()
var gem_num=0
while gem_num<3{
    for i in 1 ... 3{
        expert.moveForward()
    }
    if expert.isOnGem{
        expert.collectGem()
        gem_num+=1
        expert.turnRight()
        expert.turnRight()
    }
    else if expert.isBlocked{
        expert.turnLockUp()
        expert.turnRight()
        expert.turnRight()
    }
    else if !expert.isBlocked{
        expert.turnRight()
        
    }
}

=====
func moveAndCollect() {
    moveForward()
    collectGem()
}

func moveAndToggle() {
    moveForward()
    toggleSwitch()
}

func move() {
    var gem_num = 0
    while gem_num < 4 {
        moveAndCollect()
        gem_num += 1

        moveAndToggle()
        moveForward()
        turnLeft()

        moveAndCollect()
        gem_num += 1

        moveAndToggle()
        moveForward()
        moveForward()
        turnLeft()
    }
}

move()

====
let expert = Expert()
world.place(expert, atColumn: 2, row: 6)
var gem_num=0
while gem_num<3{
    if gem_num==3{
        break
    }
    if expert.isBlockedLeft{
        expert.turnLeft()
        expert.turnLockUp()
        expert.turnRight()
        expert.turnRight()
        expert.moveForward()
        if expert.isOnGem{
        expert.collectGem()
        gem_num+=1
        }
        expert.turnLeft()
        expert.turnLeft()
        expert.moveForward()
        expert.turnRight()
        expert.moveForward()
        expert.moveForward()
        expert.moveForward()
        expert.moveForward()
        expert.moveForward()
    }
    if expert.isOnGem{
        expert.collectGem()
        gem_num+=1
    }

}



