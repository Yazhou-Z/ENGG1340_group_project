# ENGG1340_Group_172

## Team_Member

Zhao Yazhou 3035772638 

Li Zicheng 3035772157

## Game_description

"Long long ago, there was a man, flawed and having his back to the wall. The only thing in his bag was a claw and a string. Fortunately, he found a mystery place. Instead of several stones, gold, diamond and something unknown was under the ground."



GOLD MINE is a game for one player. Players will control miniature miners who traverse the mine collecting gold. Players will face several rounds one by one. Each round, players will get 60 seconds to mine and make money. Only when they achieve a specific goal will they get access to enter the next round.

## Game_rules

1.Press `[space]` to shoot your claw

2.If you successfully grab something, the claw will drag back the object, if not, it will return when brush up against the wall

3.The larger the object is, the longer it will take to drag it back, also the more money it will make

4.Different ore has different getting speed and reward.

## Map

Map is printed every second.

#### Golds

Golds are generated randomly.

We desgin a struct `Golds_ret`, an array `gold[MAX]` to store the information of the ores.

```c++
struct Golds_ret
    {
        int x, y, id;
        bool exist; //whether had been mined
        int size;   //small:2  middle:3  large:5
        char type;
    };

    Golds_ret gold[MAX];

```



#### Parameter explanation

Map is an int array, shape is 60 * 70

| Name    | Num  |
| :------ | ---- |
| space   | 0    |
| barrier | 1    |
| stone   | 7    |
| gold    | 8    |
| diamond | 9    |
| Nothing | 10   |
| Wall    | 11   |

### calculate_reward

`reward = size_reward * type_reward`

| Type    | type_reward` | Size   | size_reward |
| ------- | ------------ | ------ | ----------- |
| Stone   | 2            | Small  | 10          |
| Gold    | 10           | Medium | 30          |
| Diamond | 50           | Large  | 50          |



