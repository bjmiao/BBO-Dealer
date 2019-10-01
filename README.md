# BBO-Dealer
发牌机选项

Documentary example
generate   10000
produce    25
vulnerable EW
dealer     west
predeal    south SAQ542, HKJ87, D32, CAK
west1c   = hcp(west)>11 && clubs(west)>= 3
# Condition describing west's 1C opener.
north2d  = diamonds(north)>=6 && (hcp(north)>5 && hcp(north)<12)
# Condition describing north's 2D overcall.
condition  west1c && north2d
# Require that west bids 1C and north 2D
action     printall

north_high = hcp(north)>18 && hcp(north)<22
north_low = hcp(north)>12 && hcp(north)<16
north_middle = hcp(north)>15 && hcp(north)<19
north_strong = hcp(north)>21

north_balance = shape(north, any 4333 + any 4432 + any 5332)
north_semi_balance = shape(north, any 4333 + any 4432 + any 5332 + any 5431 + any 5422)
north_deal = shape(north, any 5422 + any 5431 + any 5440 + any 5521 + any 5530 + any 6421 + any 6430 + any 6511 + any 6520 + any 7411 + any 7420)
south_res = hcp(south)>5

north_open = hcp(north)>11 && hpc(north) < 22
north_1M = hearts(north)>=5 || spades(north)>=5

south_res_2C = hcp(south)>11 && (shape(south , any 4333 + any 4432)) || clubs(south) >= 5)
south_res_2D = hcp(south)>11 && (diamonds(south) >= 5)

condition north_open && north_1M && (south_res_2C || south_res_2D )

condition north_high && south_res && north_deal
