![miniature](https://user-images.githubusercontent.com/67419505/147802874-73ac3d84-fa5f-4e83-ade0-04754049aa95.png)

**Description**
> WavePlayTimeRewards is an amazing ESX & QBUS ready resource, allowing your players to be rewarded for their playtime on your server.
> Every features is configurable and can be adapted to all your tastes! 

**Showcase**
> Watch the [Showcase](https://www.youtube.com/watch?v=FnnDBRIFGwI) !

**Discord**
> https://discord.gg/5x2kXXkZTR

**Tebex**
> [WaveResources | Home (tebex.io)](https://waveresources.tebex.io/) - 15€ + taxes

**Features**
* resmon : 0.0ms Closed, 0.2ms opened
* Looped Rewards
 * You can give items,weapons,vehicles,bank money,cash money, black money.
 * You can configure the count/ammos/amount you want to give.
 * You can configure the percentage of chance of each reward.
 * You can configure the percentage of chance to win nothing.
 * New Players
  * You can change the required number of minutes of playing time for new players
  * You can change the maximum playing time being considered as a new player
 * Gives a random reward among those configured every x minutes of playing time.
* Play Time Rewards
 * gives the reward of your choice as soon as the player reaches the set amount of play time
* Configurable number of reward draws to be more random
* Give a reward to all players on the server from console or whitelisted player
* Based on client side database aka kvp
* Openable with command or pressed key
* Anti-Glitchs
* Nice sounds
* Nices Notifications
* built-in RageUI edited
* Multiples Languages supported
* ESX & QBUS Ready
* And more...

**Config Example**
```
wavePlayTimeRewards = {
    frameWork = "ESX", --ESX OR QBCORE
    Language = "EN",
    getSharedObject = "esx:getShayyyzenaredObjayyyzenect",
    Currency = "$",
    settings = {
        menu = {
            menuCommandName = "rewards",
            enableKey = true,
            menuKey = "F10",
        },
        giveRewardToAllPlayersCommand = {
            enable = true, --if enabled, will give a reward to all your players if you run the command from the console or from a whitelisted player
            commandName = "giveAllReward",
            whiteListedLicenses = {
                ["license:171a23d246444c95bd897754beb26aa197ab3570"] = true,
            },
        },
        nbOfDraws = 30, -- number of random draws higher is better
        giveVehicleEvent = "esx_vehicleshop:setVehicleOwned",
        vehiclePlate = "REWARD",
    },

    playTimeRewards = {
        enable = true, --It will give the reward that you set in the list according to player's playtime on the server
        rewards = { --playTime is the needed playtime to get the reward ( in minutes )
            --this is all possible rewards ( obviously you can edit whatever you want, only type must be -> item/weapon/vehicle/account)
            -- you can add, edit, or remove rewards as much as you want
            {playTime = 10,type = "item",name="bread",count=5},
            {playTime = 20,type = "weapon",name="weapon_pistol",ammos=250},
            {playTime = 30,type = "vehicle",name="blista"},
            {playTime = 40,type = "account",name="money",amount=1000},
            {playTime = 50,type = "account",name="black_money",amount=1000},
            {playTime = 60,type = "account",name="bank",amount=1000},
        },
    },
    loopedRewards = {
        enable = true, -- if enabled, will give 1 random reward among the list every minutes you setted below
        loopMinutes = 60, -- how often it will give reward (in minutes)
        newPlayerRewards = {
            enable = true,
            maxTimePlayedConsideratedToBeNonNewPlayer = 120, --means that after this number ( in minutes) of timeplay, he will not be considerated as a new player
            loopMinutesNewPlayer = 15, --how often it will give reward (in minutes)
        },
        rewards = { --chance is the percentage of chance between 0 and 1 to get the reward ( all chances arent needed to make sum of 1.0, we use our own random draw system)
            --this is all possible rewards ( obviously you can edit whatever you want, only type must be -> item/weapon/vehicle/account)
            -- you can add, edit, or remove rewards as much as you want
            {type = "item",name="bread",count=5,label = "Sandwich",chance=0.3},
            {type = "weapon",name="weapon_pistol",ammos=250,label = "Pistol",chance=0.2},
            {type = "vehicle",name="blista",chance=0.3},
            {type = "account",name="money",amount=1000,label = "Cash",chance=0.3},
            {type = "account",name="black_money",amount=1000,label = "Dirt Money",chance=0.3},
            {type = "account",name="bank",amount=1000,label = "Bank Money",chance=0.3},
            
        },
        winNotingChance = 0.01,
    },
}
```
