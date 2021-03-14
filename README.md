# RayZ - Вступление

#### Зарегистрированные события
Каждому сообщению в журнале предшествует отметка времени в формате ЧЧ:ММ:СС. Пример:11:06:00
| Мероприятие | Описание | Пример |
|------|-------------|------|
| Подключить/отключить | Сообщение о подключении и отключении для каждого игрока, присоединяющегося/покидающего сервер | Игрок "Survivor" подключен (id = DAYZGUID) |
||| Игрок "Survivor" (id = DAYZGUID) отключен |
| Чат | Журнал чата | Чат ("Survivor" (id = DAYZGUID)): привет, журнал |
| Отчет игрока | Сообщение для отчета активируется путем ввода "#toadmin yourmessage" в игровом чате. | ОТЧЕТ ИГРОКА: <2019-1-23_11-23-26> <DAYZGUID>: ваше сообщение |
| Бессознательное состояние | Игрок падает и приходит в сознание | Игрок «Survivor» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) без сознания |
||| Игрок «Выживший» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) пришел в сознание. |
| Источник урона игрока | Игроки получают удары от других сущностей и падают - включая текущее общее состояние здоровья, источник урона, зону поражения (+ компонент), использованные боеприпасы и дальность, если источником было оружие дальнего боя. | Игрок «Выживший A» (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) [HP: 74] получил удар «Survivor B» (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) в голову (0) для 26 повреждений (Bullet_45ACP) с FX-45 с 1,12831 метра |
||| Игрок "Survivor" (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) [HP: 76.7] поражен Волком в LeftArm (18), нанося 20 урона (MeleeWolf) |
||| Игрок «Выживший» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) [HP: 96,7] поражен FallDamage |
||| Игрок "Survivor" (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) [HP: 96,7] поражен Камином с FireDamage |
| Журнал смерти игрока | Причина смерти  игрока. Распечатает общее сообщение о смерти с дополнительной информацией о состоянии, чтобы помочь определить причину, если она неясна. | Игрок «Survivor A» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) убит «Survivor B» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) из M4-A1 с 42 метров |
||| Игрок "Survivor" (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) убит Infected |
||| Игрок «Survivor» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) умер. Статистика> Вода: 489,53 Энергия: 594,765 Источники кровотечения: 2 |
| Самоубийство | Смерть игрока в результате самоубийственного жеста | Игрок «Выживший» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) покончил жизнь самоубийством. |
| тест | тоже | 554 |
| тест | тоже | 554 |
| тест | тоже | 554 |
| тест | тоже | 554 |
||| 554 |

###
[Истекать кровью]

Игрок умирает от недостатка крови

Игрок "Survivor" (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) истек кровью

###
[Размещение]

Регистрируйте, когда игрок помещает предмет в мир, используя действие размещения. Требуется adminLogPlacement = 1;

Игрок «Выживший» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) поставил медвежью ловушку.

Игрок «Выживший» (id = DAYZGUID, pos = <13212.8, 10124.8, 6.0>) поставил камин

###
[Действия по строительству базы]

Записывать, когда игрок выполняет действие по строительству базы. Требуется adminLogBuildActions = 1;

Игрок «Выживший» (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) построил забор с лопатой.

Игрок «Выживший» (id = DAYZGUID pos = <3605.9, 2296.0, 6.0>) разобрал забор с помощью молотка.

###
[Печать списка игроков]

Распечатывает список игроков на сервере и их текущие позиции каждые 5 минут. Требуется adminLogPlayerList = 1;

Журнал PlayerList: 2 игрока

Игрок «Выживший А» (id = DAYZGUID pos = <3533.2, 2256.4, 6.8>)

Игрок «Выживший Б» (id = DAYZGUID pos = <3533.2, 2256.4, 6.8>)

{{GameCategory|dayz|Server}}
== Introduction ==
This article details '''Administration Log''', a file which records key gameplay events such as chat, player hits and deaths. It's main purpose is to help server administrators identify exploiters, cheaters or spot breaches of any custom rules the server might have set up.   

To enable the logging, server must run with the launch parameter '''-adminlog'''

The log file is named '''server_exe_name.ADM''' and it is created in the profiles folder, specified by the -profiles launch parameter.

The page is updated for patch '''1.02'''

== Logged events ==
Each message in the log is prefixed by a time stamp in a HH:MM:SS format

{| class="wikitable" style="width:100%;"
|-
! Event !! Description !! Example
|-
| rowspan="2" | Connect/Disconnect || rowspan="2" | Connect and disconnect message for each player joining/leaving the server  || <tt>Player "Survivor" is connected (id=DAYZGUID) </tt>
|-
| <tt>Player "Survivor"(id=DAYZGUID) has been disconnected</tt>
|-
| Chat || Chat log || <tt>Chat("Survivor"(id=DAYZGUID)): hello log</tt>
|-
| Player report || Report message activated by typing "#toadmin yourmessage" into the in game chat || <tt>PLAYER REPORT: <2019-1-23_11-23-26> <DAYZGUID>: yourmessage</tt>
|-
|  rowspan="2" | Unconscious state || rowspan="2" | Player falling into and regaining consciousness || <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) is unconscious</tt>
|-
|  <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) regained consciousness</tt>
|-
| rowspan="4" | Player damage source || rowspan="4" | Players receiving hits from other entities and falls - includes current global health, source of damage, hitzone(+component), ammunition used and range if the source was a ranged weapon  || <tt>Player "Survivor A"(id=DAYZGUID pos=<3605.9, 2296.0, 6.0>)[HP: 74] hit by "Survivor B"(id=DAYZGUID pos=<3605.9, 2296.0, 6.0>) into Head(0) for 26 damage (Bullet_45ACP) with FX-45 from 1.12831 meters</tt>
|-
|  <tt>Player "Survivor" (id=DAYZGUID pos=<3605.9, 2296.0, 6.0>)[HP: 76.7] hit by Wolf into LeftArm(18) for 20 damage (MeleeWolf)</tt>
|-
|  <tt>Player "Survivor" (id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>)[HP: 96.7] hit by FallDamage</tt>
|-
|  <tt>Player "Survivor" (id=DAYZGUID pos=<3605.9, 2296.0, 6.0>)[HP: 96.7] hit by Fireplace with FireDamage</tt>
|-
| rowspan="3" | Player death log || rowspan="3" | Player cause of death. Will print generic death message with additional status information to help determine the cause if it's unclear. || <tt>Player "Survivor A"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) killed by "Survivor B"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) with M4-A1 from 42 meters</tt>
|-
| <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) killed by Infected</tt>
|-
| <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) died. Stats> Water: 489.53 Energy: 594.765 Bleeding Sources: 2</tt>
|-
| Suicide || Player death caused by the suicide gesture || <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) committed suicide</tt>
|-
| Bleeding out || Player dying to lack of blood || <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) bled out</tt>
|-
| rowspan="2" | Placement || rowspan="2" | Log when player places an item in the world using the placement action. Requires '''adminLogPlacement=1;''' || <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) placed Bear Trap</tt>
|-
| <tt>Player "Survivor"(id=DAYZGUID, pos=<13212.8, 10124.8, 6.0>) placed Fireplace</tt>
|-
| rowspan="2" | Base building actions || rowspan="2" | Log when player executes a base building action. Requires '''adminLogBuildActions=1;''' || <tt>Player "Survivor" (id=DAYZGUID pos=<3605.9, 2296.0, 6.0>) built Fence with Shovel</tt>
|-
| <tt>Player "Survivor" (id=DAYZGUID pos=<3605.9, 2296.0, 6.0>) dismantled Fence with Hammer</tt>
|-
| Player list print || Prints a list of players on the server and their current positions every 5 minutes. Requires '''adminLogPlayerList=1;''' || <tt>PlayerList log: 2 players</tt>

<tt>Player "Survivor A" (id=DAYZGUID pos=<3533.2, 2256.4, 6.8>)</tt>

<tt>Player "Survivor B" (id=DAYZGUID pos=<3533.2, 2256.4, 6.8>)</tt>
|}

== Configuration ==

Some of the logging can be filtered in '''serverDZ.cfg''' depending on the server owner's needs


'''adminLogPlayerHitsOnly = 1;''' // log player hits only (no infected/animal hits) 

'''adminLogPlacement = 1;'''		// log placement ( traps, tents, ... )

'''adminLogBuildActions = 1;'''	// log basebuilding actions ( build, dismantle, destroy, ... )

'''adminLogPlayerList = 1;'''		// log periodic player list with position every 5 minutes

== Modding ==

You can easily add your own messages to the admin log file from your mod using the script function '''CGame::AdminLog( string text )'''

If you would like to modify the existing logging, all of the logic can be found in \Scripts\4_World\Plugins\PluginBase\'''PluginAdminLog.c''' where you can override specific events or change the message output.


Following log prints are currently handled in the executable and so they are not moddable:

Connect/Disconnect

Chat

Player report
