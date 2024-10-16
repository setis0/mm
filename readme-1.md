## получение всех каналов
### описание полей
* **displayname** отображение название канала
* **totalmsgcount** собщение + коментарии
* **totalmsgcountroot** сообщение
### запрос
``` 
select 
    channels.displayname, 
    channels.totalmsgcount, 
    channels.totalmsgcountroot 
from channels
where
channels.displayname != ''
```
### пример 
| displayname | totalmsgcount | totalmsgcountroot |
| :--- | :--- | :--- |
| Чайхана | 3 | 3 |
| Town Square | 0 | 0 |
| Чайхана \(реализация\) | 0 | 0 |
| Чайхана \(флуд\) | 0 | 0 |
| Продажи \(Чайхана\) | 18 | 18 |
| Town Square | 32 | 32 |
| Off-Topic | 1 | 1 |
| Реализация \(Чайхана\) | 48 | 48 |
| Флуд \(Чайхана\) | 29 | 29 |
| Off-Topic | 23 | 23 |



## получение всех пользовательй
### описание полей
* **username** имя пользователя
* **createat** создание пользователя !отображение даты смотреть вниз 
* **updateat** обновление данных пользователя !отображение даты смотреть вниз
* **deleteat** удаление пользователя !отображение даты смотреть вниз
* **lastlogin** последный раз авторизироваля !отображение даты смотреть вниз
* **locale** язык интерфейса
* **lastpasswordupdate** последние обновление пароля !отображение даты смотреть вниз
* **lastpictureupdate** последние обновление аватару !отображение даты смотреть вниз
### запрос
```
select 
* 
from users 
where users.password != '' 
```
### пример только пользователей

| id | createat | updateat | deleteat | username | password | authdata | authservice | email | emailverified | nickname | firstname | lastname | roles | allowmarketing | props | notifyprops | lastpasswordupdate | lastpictureupdate | failedattempts | locale | mfaactive | mfasecret | position | timezone | remoteid | lastlogin |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 5hfjyuiemf8b58gsyndhjnp4ao | 1726578384737 | 1726579271382 | 0 | anastasia | $2a$10$NoLHz2HyBxJdWUh/BwzMNeBge7Ts9UYimECUsJfrIq4kJs6RXKoq6 | null |  | a.puhlovskaya@tazmar.ru | false |  |  |  | system\_user system\_admin | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1726578384737 | 0 | 0 | ru | false |  |  | {"manualTimezone": "", "automaticTimezone": "Europe/Moscow", "useAutomaticTimezone": "true"} |  | 1726578385075 |
| pujzmcjen7fnpmow74k1corrhw | 1726578372938 | 1726579299212 | 0 | nikita | $2a$10$x/DjhkRPMFnzfwD6mMI96OlkZbu4ACmWiQ8U.oy73bIBuYYzNeXJy | null |  | n.efremenkov@tazmar.ru | false |  |  |  | system\_user system\_admin | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1726578372938 | 0 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "Europe/Moscow", "useAutomaticTimezone": "true"} |  | 1726578373615 |
| zn1q3hg4xtfs3fbmde87dejkpw | 1726748640557 | 1726748641602 | 0 | testusername | $2a$10$Cx1jHjnBj6hYKalu4BzbqehG9sCr3RngTG2rIwfXjdihL3byjRrOW | null |  | pryanysh@inbox.ru | false |  |  |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1726748640557 | 0 | 0 | ru | false |  |  | {"manualTimezone": "", "automaticTimezone": "Europe/Moscow", "useAutomaticTimezone": "true"} |  | 1726748640973 |
| 5b868apbnb8tmxyetxi6t9bpgc | 1716925228832 | 1728569611452 | 0 | admin | $2a$10$zwXv5PhF.bo9YQLeeHo93eZEEKhmxPXiuGsfWnrwduol5Lh8p2HfG | null |  | admin@tazmar.ru | false |  |  |  | system\_admin system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1716973022041 | 0 | 1 | ru | false |  |  | {"manualTimezone": "", "automaticTimezone": "Europe/Moscow", "useAutomaticTimezone": "true"} | null | 1728569611449 |

> users.password != '' с паролями только пользователей

> users.password = '' только ботов
### пример только ботов
| id | createat | updateat | deleteat | username | password | authdata | authservice | email | emailverified | nickname | firstname | lastname | roles | allowmarketing | props | notifyprops | lastpasswordupdate | lastpictureupdate | failedattempts | locale | mfaactive | mfasecret | position | timezone | remoteid | lastlogin |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 3okzpxypmjfkirujfbfiupeuyy | 1716925026661 | 1716925027191 | 0 | feedbackbot |  | null |  | feedbackbot@localhost | false |  | Feedbackbot |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1716925026661 | 1716925027191 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "", "useAutomaticTimezone": "true"} | null | 0 |
| yycxkax9gjgsiyppnr1zhitdky | 1716925500004 | 1716925500004 | 0 | system-bot |  | null |  | system-bot@localhost | false |  | System |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1716925500004 | 0 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "", "useAutomaticTimezone": "true"} | null | 0 |
| ssbsmmk7w7y49fhxbses8b4eic | 1726767422701 | 1726767422758 | 0 | mscalendar |  | null |  | mscalendar@localhost | false |  | Microsoft Calendar |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1726767422701 | 1726767422758 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "", "useAutomaticTimezone": "true"} | null | 0 |
| 9dnfo7ydtbrk8eiswy34jeyjtw | 1716925029385 | 1728913677015 | 0 | playbooks |  | null |  | playbooks@localhost | false |  | Playbooks |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1716925029385 | 1728913677015 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "", "useAutomaticTimezone": "true"} | null | 0 |
| r99sjhhcgbgkfcr1xsuu7u59gw | 1716925029016 | 1728913677680 | 0 | calls |  | null |  | calls@localhost | false |  | Calls |  | system\_user | false | {} | {"push": "mention", "email": "true", "channel": "true", "desktop": "mention", "comments": "never", "first\_name": "false", "push\_status": "away", "mention\_keys": "", "push\_threads": "all", "desktop\_sound": "true", "email\_threads": "all", "desktop\_threads": "all"} | 1716925029016 | 1728913677680 | 0 | en | false |  |  | {"manualTimezone": "", "automaticTimezone": "", "useAutomaticTimezone": "true"} | null | 0 |

## общие количество сообщений от пользователя
### описание
* **username** имя пользователя
* **msgcount,** собщение + коментарии
* **msgcountroot** сообщение
### запрос
```
select 
    users.username, 
    sum(channelmembers.msgcount) as msgcount,
    sum(channelmembers.msgcountroot) as msgcountroot 
from users
    join  channelmembers on channelmembers.userid = users.id
    join channels on channels.id = channelmembers.channelid
group by users.username 
```
### пример 
| username | msgcount | msgcountroot |
| :--- | :--- | :--- |
| testusername | 32 | 32 |
| feedbackbot | 0 | 0 |
| anastasia | 137 | 137 |
| admin | 59 | 59 |
| nikita | 154 | 154 |


## количество сообщений в каналах от пользователя
### описание
* **username** имя пользователя
* **name,** имя канала
* **displayname,** отображение название канала
* **msgcount,** собщение + коментарии
* **msgcountroot** сообщение
### запрос
```
select 
    users.username, 
    channels.name,
    channels.displayname, 
    channelmembers.msgcount,
    channelmembers.msgcountroot 
from users
join channelmembers 
    on channelmembers.userid = users.id
join channels 
    on channels.id = channelmembers.channelid 
```
### пример
| username | name | displayname | msgcount | msgcountroot |
| :--- | :--- | :--- | :--- | :--- |
| nikita | off-topic | Off-Topic | 23 | 23 |
| anastasia | a353adad5bd61e29a2c998706c321ed1 | Реализация \(Чайхана\) | 48 | 48 |
| admin | town-square | Town Square | 32 | 32 |
| anastasia | 30f4b6f2c99e7dcb4558988107e31a39 | Флуд \(Чайхана\) | 29 | 29 |
| admin | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc |  | 3 | 3 |
| anastasia | off-topic | Off-Topic | 23 | 23 |
| nikita | town-square | Town Square | 32 | 32 |
| anastasia | town-square | Town Square | 32 | 32 |
| anastasia | town-square | Town Square | 0 | 0 |
| nikita | town-square | Town Square | 0 | 0 |
| nikita | 277e6faee45a9ea1395d936fb6c83150 | Чайхана | 3 | 3 |
| anastasia | off-topic | Off-Topic | 1 | 1 |
| anastasia | 277e6faee45a9ea1395d936fb6c83150 | Чайхана | 3 | 3 |
| anastasia | ceab4ec67891a2df840a705650abf1af | Продажи \(Чайхана\) | 0 | 0 |
| admin | off-topic | Off-Topic | 23 | 23 |
| nikita | off-topic | Off-Topic | 1 | 1 |
| nikita | a353adad5bd61e29a2c998706c321ed1 | Реализация \(Чайхана\) | 48 | 48 |
| feedbackbot | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc |  | 0 | 0 |
| admin | 5b868apbnb8tmxyetxi6t9bpgc\_\_5b868apbnb8tmxyetxi6t9bpgc |  | 0 | 0 |
| admin | town-square | Town Square | 0 | 0 |
| nikita | 30f4b6f2c99e7dcb4558988107e31a39 | Флуд \(Чайхана\) | 29 | 29 |
| admin | off-topic | Off-Topic | 1 | 1 |
| nikita | ceab4ec67891a2df840a705650abf1af | Продажи \(Чайхана\) | 18 | 18 |
| testusername | off-topic | Off-Topic | 0 | 0 |
| testusername | town-square | Town Square | 32 | 32 |
| feedbackbot | 3okzpxypmjfkirujfbfiupeuyy\_\_5hfjyuiemf8b58gsyndhjnp4ao |  | 0 | 0 |
| anastasia | 3okzpxypmjfkirujfbfiupeuyy\_\_5hfjyuiemf8b58gsyndhjnp4ao |  | 1 | 1 |


## статистика количество сообщений от пользователя для диагрмаы
### описание
* **username** имя пользователя
* **name,** имя канала
* **displayname,** отображение название канала
* **msgcount,** собщение + коментарии
* **msgcountroot** сообщение
* **fileids** список файлов
### запрос

```
select
    users.username,
    posts.createat,
    posts.updateat,
    posts.deleteat,
    channels.name,
    posts.fileids
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id

```
### пример 
| username | createat | updateat | deleteat | name | fileids |
| :--- | :--- | :--- | :--- | :--- | :--- |
| admin | 1716925235061 | 1716925235061 | 0 | town-square | \[\] |
| admin | 1716925235107 | 1716925235107 | 0 | off-topic | \[\] |
| admin | 1716973056166 | 1716973061515 | 0 | off-topic | \[\] |
| admin | 1716973056166 | 1716973061515 | 1716973061515 | off-topic | \[\] |
| admin | 1716973072032 | 1716973080931 | 0 | off-topic | \[\] |
| admin | 1716973072032 | 1716973080931 | 1716973080931 | off-topic | \[\] |
| admin | 1716973086471 | 1716973091724 | 0 | off-topic | \[\] |
| admin | 1716973086471 | 1716973091724 | 1716973091724 | off-topic | \[\] |
| admin | 1716993806516 | 1716993811866 | 0 | off-topic | \[\] |
| nikita | 1726579448752 | 1726579448752 | 0 | 4257a2c6b1d1128dbbda5bd1c28b326f | \[\] |
| nikita | 1726580220957 | 1726580220957 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726580278237 | 1726588838248 | 1726588838248 | ceab4ec67891a2df840a705650abf1af | \[\] |
| admin | 1716993806516 | 1716993811866 | 1716993811866 | off-topic | \[\] |
| admin | 1716993824601 | 1716993829868 | 0 | off-topic | \[\] |
| feedbackbot | 1726575264649 | 1726575264649 | 0 | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc | \[\] |
| admin | 1716993824601 | 1716993829868 | 1716993829868 | off-topic | \[\] |
| admin | 1716994494527 | 1716994574894 | 0 | off-topic | \[\] |
| admin | 1716994494527 | 1716994574894 | 1716994574894 | off-topic | \[\] |
| admin | 1716994991518 | 1716994996797 | 0 | off-topic | \[\] |
| admin | 1716994991518 | 1716994996797 | 1716994996797 | off-topic | \[\] |
| admin | 1716995927548 | 1716995932943 | 0 | off-topic | \[\] |
| nikita | 1726584794566 | 1726584794566 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584794801 | 1726584794801 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584794950 | 1726584794950 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584795304 | 1726584795304 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584795478 | 1726584795478 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584796797 | 1726584796797 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584797070 | 1726584797070 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584797252 | 1726584797252 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584797473 | 1726584797473 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584797651 | 1726584797651 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584797855 | 1726584797855 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584798113 | 1726584798113 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| admin | 1716995927548 | 1716995932943 | 1716995932943 | off-topic | \[\] |
| admin | 1716996593272 | 1716996611402 | 0 | off-topic | \[\] |
| admin | 1726575322177 | 1726575322177 | 0 | off-topic | \[\] |
| admin | 1716996593272 | 1716996611402 | 1716996611402 | off-topic | \[\] |
| admin | 1716996849737 | 1716996855044 | 0 | off-topic | \[\] |
| admin | 1716996849737 | 1716996855044 | 1716996855044 | off-topic | \[\] |
| admin | 1716997064174 | 1716997069484 | 0 | off-topic | \[\] |
| admin | 1716997064174 | 1716997069484 | 1716997069484 | off-topic | \[\] |
| admin | 1716997220874 | 1716997226182 | 0 | off-topic | \[\] |
| nikita | 1726588824940 | 1726588824940 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1716997220874 | 1716997226182 | 1716997226182 | off-topic | \[\] |
| admin | 1716997686953 | 1716997692272 | 0 | off-topic | \[\] |
| admin | 1716997686953 | 1716997692272 | 1716997692272 | off-topic | \[\] |
| admin | 1716998546305 | 1716998551743 | 0 | off-topic | \[\] |
| admin | 1716998546305 | 1716998551743 | 1716998551743 | off-topic | \[\] |
| nikita | 1726578373161 | 1726578373161 | 0 | town-square | \[\] |
| nikita | 1726578373182 | 1726578373182 | 0 | off-topic | \[\] |
| admin | 1716998563520 | 1716998568917 | 0 | off-topic | \[\] |
| admin | 1716998563520 | 1716998568917 | 1716998568917 | off-topic | \[\] |
| admin | 1716998899114 | 1716998918935 | 0 | town-square | \[\] |
| nikita | 1726588825408 | 1726588825408 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588825599 | 1726588825599 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588825811 | 1726588825811 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1716998899114 | 1716998918935 | 1716998918935 | town-square | \[\] |
| admin | 1716998969533 | 1716998974659 | 0 | town-square | \[\] |
| admin | 1716998969533 | 1716998974659 | 1716998974659 | town-square | \[\] |
| admin | 1717012694675 | 1717012700175 | 0 | town-square | \[\] |
| admin | 1717012694675 | 1717012700175 | 1717012700175 | town-square | \[\] |
| admin | 1717023663748 | 1717023673872 | 0 | town-square | \[\] |
| admin | 1717023663748 | 1717023673872 | 1717023673872 | town-square | \[\] |
| admin | 1717041641548 | 1717041659571 | 0 | town-square | \[\] |
| admin | 1717041641548 | 1717041659571 | 1717041659571 | town-square | \[\] |
| admin | 1717041666444 | 1717041684559 | 0 | town-square | \[\] |
| admin | 1717041666444 | 1717041684559 | 1717041684559 | town-square | \[\] |
| admin | 1717048890068 | 1717048961105 | 0 | off-topic | \[\] |
| admin | 1717048890068 | 1717048961105 | 1717048961105 | off-topic | \[\] |
| admin | 1717048997198 | 1717049017630 | 0 | town-square | \[\] |
| admin | 1717048997198 | 1717049017630 | 1717049017630 | town-square | \[\] |
| admin | 1717049616743 | 1717049673389 | 0 | town-square | \[\] |
| admin | 1717049678552 | 1717049707671 | 1717049707671 | town-square | \[\] |
| admin | 1717049616743 | 1717049673389 | 1717049673389 | town-square | \[\] |
| admin | 1717049678552 | 1717049707671 | 0 | town-square | \[\] |
| admin | 1717052353204 | 1717052415415 | 0 | town-square | \[\] |
| admin | 1717052353204 | 1717052415415 | 1717052415415 | town-square | \[\] |
| admin | 1717053960305 | 1717054022787 | 0 | town-square | \[\] |
| admin | 1717053960305 | 1717054022787 | 1717054022787 | town-square | \[\] |
| admin | 1717054329776 | 1717054334949 | 0 | town-square | \[\] |
| admin | 1717054329776 | 1717054334949 | 1717054334949 | town-square | \[\] |
| admin | 1717055319972 | 1717055325771 | 0 | town-square | \[\] |
| admin | 1717055319972 | 1717055325771 | 1717055325771 | town-square | \[\] |
| admin | 1717055579370 | 1717055582159 | 0 | town-square | \[\] |
| admin | 1717055590788 | 1717055622959 | 1717055622959 | town-square | \[\] |
| admin | 1717055579370 | 1717055582159 | 1717055582159 | town-square | \[\] |
| admin | 1717055590788 | 1717055622959 | 0 | town-square | \[\] |
| admin | 1717055638195 | 1717055643501 | 0 | town-square | \[\] |
| admin | 1717055638195 | 1717055643501 | 1717055643501 | town-square | \[\] |
| admin | 1717056008205 | 1717056426030 | 0 | town-square | \[\] |
| admin | 1717056008205 | 1717056426030 | 1717056426030 | town-square | \[\] |
| admin | 1717063963356 | 1717064672292 | 0 | town-square | \[\] |
| admin | 1717063963356 | 1717064672292 | 1717064672292 | town-square | \[\] |
| admin | 1717095131743 | 1717095152131 | 0 | town-square | \[\] |
| admin | 1717095131743 | 1717095152131 | 1717095152131 | town-square | \[\] |
| admin | 1717140643650 | 1717140649043 | 0 | town-square | \[\] |
| admin | 1717140643650 | 1717140649043 | 1717140649043 | town-square | \[\] |
| admin | 1717141103119 | 1717141108457 | 0 | town-square | \[\] |
| admin | 1717141103119 | 1717141108457 | 1717141108457 | town-square | \[\] |
| admin | 1717141366108 | 1717141420379 | 0 | town-square | \[\] |
| admin | 1717141366108 | 1717141420379 | 1717141420379 | town-square | \[\] |
| admin | 1717141862212 | 1717141870576 | 0 | town-square | \[\] |
| admin | 1717141862212 | 1717141870576 | 1717141870576 | town-square | \[\] |
| admin | 1717141891535 | 1717141903831 | 0 | town-square | \[\] |
| admin | 1717141926253 | 1717141931355 | 0 | off-topic | \[\] |
| admin | 1717141926253 | 1717141931355 | 1717141931355 | off-topic | \[\] |
| admin | 1717142012455 | 1717142022214 | 1717142022214 | off-topic | \[\] |
| admin | 1717141891535 | 1717141903831 | 1717141903831 | town-square | \[\] |
| admin | 1717142012455 | 1717142022214 | 0 | off-topic | \[\] |
| admin | 1717142587113 | 1717142619946 | 0 | town-square | \[\] |
| admin | 1717142587113 | 1717142619946 | 1717142619946 | town-square | \[\] |
| admin | 1717142725028 | 1717142769728 | 0 | town-square | \[\] |
| admin | 1717142725028 | 1717142769728 | 1717142769728 | town-square | \[\] |
| admin | 1717142788428 | 1717142820887 | 0 | town-square | \[\] |
| admin | 1717142788428 | 1717142820887 | 1717142820887 | town-square | \[\] |
| admin | 1717143269100 | 1717143323126 | 0 | town-square | \[\] |
| admin | 1717143269100 | 1717143323126 | 1717143323126 | town-square | \[\] |
| admin | 1717144185998 | 1717144208355 | 0 | town-square | \[\] |
| admin | 1717144185998 | 1717144208355 | 1717144208355 | town-square | \[\] |
| feedbackbot | 1717571815209 | 1717571815209 | 0 | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc | \[\] |
| feedbackbot | 1720964388470 | 1720964388470 | 0 | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc | \[\] |
| admin | 1721117817235 | 1721117817235 | 0 | town-square | \[\] |
| admin | 1721118802558 | 1721118802558 | 0 | town-square | \[\] |
| admin | 1724423132478 | 1724423132478 | 0 | town-square | \[\] |
| anastasia | 1726578384858 | 1726578384858 | 0 | town-square | \[\] |
| anastasia | 1726578384894 | 1726578384894 | 0 | off-topic | \[\] |
| nikita | 1726578584829 | 1726578584829 | 0 | 277e6faee45a9ea1395d936fb6c83150 | \[\] |
| nikita | 1726578739512 | 1726578739512 | 0 | 277e6faee45a9ea1395d936fb6c83150 | \[\] |
| nikita | 1726578902383 | 1726579012541 | 0 | 277e6faee45a9ea1395d936fb6c83150 | \[\] |
| anastasia | 1726579271403 | 1726579271403 | 0 | town-square | \[\] |
| anastasia | 1726579271430 | 1726579271430 | 0 | off-topic | \[\] |
| nikita | 1726579299255 | 1726579299255 | 0 | town-square | \[\] |
| nikita | 1726579299273 | 1726579299273 | 0 | off-topic | \[\] |
| nikita | 1726579357594 | 1726579357594 | 0 | 4257a2c6b1d1128dbbda5bd1c28b326f | \[\] |
| nikita | 1726579426652 | 1726579426652 | 0 | 61f57c9d448d4fd65302bd843a89e601 | \[\] |
| nikita | 1726579444864 | 1726579444864 | 0 | 61f57c9d448d4fd65302bd843a89e601 | \[\] |
| nikita | 1726579945745 | 1726579945745 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726579954727 | 1726579954727 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726580215161 | 1726580215161 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726582169506 | 1726582169506 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582169740 | 1726582169740 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582169991 | 1726582169991 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582170229 | 1726582170229 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582170486 | 1726582170486 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582170753 | 1726582170753 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582170977 | 1726582170977 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582171260 | 1726582171260 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582171537 | 1726582171537 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582171792 | 1726582171792 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582172070 | 1726582172070 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582172313 | 1726582172313 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582172558 | 1726582172558 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582172779 | 1726582172779 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582172996 | 1726582172996 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582173271 | 1726582173271 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582173544 | 1726582173544 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726582173807 | 1726582173807 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726587388103 | 1726587388103 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1726587392174 | 1726587392174 | 0 | off-topic | \[\] |
| admin | 1726588825621 | 1726588825621 | 0 | town-square | \[\] |
| nikita | 1726584711297 | 1726584760897 | 1726584760897 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584793622 | 1726584793622 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584793887 | 1726584793887 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584794028 | 1726584794028 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584794213 | 1726584794213 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584794389 | 1726584794389 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584733584 | 1726584756417 | 1726584756417 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584781452 | 1726584787336 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584781452 | 1726584787336 | 1726584787336 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584795303 | 1726584795303 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584795640 | 1726584795640 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584795814 | 1726584795814 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584796762 | 1726584796762 | 0 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584796426 | 1726586227586 | 1726586227586 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726584796426 | 1726586578552 | 1726586578552 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| admin | 1726586701243 | 1726586701243 | 0 | off-topic | \[\] |
| admin | 1726587038679 | 1726587038679 | 0 | town-square | \[\] |
| admin | 1726587038716 | 1726587038716 | 0 | off-topic | \[\] |
| nikita | 1726587251249 | 1726587264963 | 1726587264963 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1726587353995 | 1726587353995 | 0 | off-topic | \[\] |
| nikita | 1726587421179 | 1726587421179 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1726587471125 | 1726587471125 | 0 | off-topic | \[\] |
| nikita | 1726586814140 | 1726588663338 | 1726588663338 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| admin | 1726587045459 | 1726588668437 | 1726588668437 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| admin | 1726587132179 | 1726587132179 | 0 | off-topic | \[\] |
| nikita | 1726587310848 | 1726587310848 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588387864 | 1726588649245 | 1726588649245 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| admin | 1726587075849 | 1726588653865 | 1726588653865 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726588827212 | 1726588827212 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588827820 | 1726588827820 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| feedbackbot | 1727248868381 | 1727248868381 | 0 | 3okzpxypmjfkirujfbfiupeuyy\_\_5hfjyuiemf8b58gsyndhjnp4ao | \[\] |
| nikita | 1726587354609 | 1726587354609 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726587360665 | 1726587360665 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588825124 | 1726588825124 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726587973792 | 1726587973792 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726587997474 | 1726587997474 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588012724 | 1726588012724 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588279903 | 1726588279903 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726586844743 | 1726588659015 | 1726588659015 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726588824698 | 1726588824698 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588693593 | 1726588812739 | 1726588812739 | a353adad5bd61e29a2c998706c321ed1 | \[\] |
| nikita | 1726588790905 | 1726588817449 | 1726588817449 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1726588822867 | 1726588822867 | 0 | town-square | \[\] |
| nikita | 1726588823538 | 1726588823538 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588823831 | 1726588823831 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588824085 | 1726588824085 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588824276 | 1726588824276 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588824507 | 1726588824507 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| admin | 1726588825632 | 1726588825632 | 0 | off-topic | \[\] |
| nikita | 1726588826049 | 1726588826049 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588826302 | 1726588826302 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588826475 | 1726588826475 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588826738 | 1726588826738 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588826928 | 1726588826928 | 0 | 30f4b6f2c99e7dcb4558988107e31a39 | \[\] |
| nikita | 1726588803340 | 1726588833783 | 1726588833783 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726580271524 | 1726588838244 | 1726588838244 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589664779 | 1726589664779 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589664993 | 1726589664993 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589665188 | 1726589665188 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589665399 | 1726589665399 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589665641 | 1726589665641 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589665856 | 1726589665856 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589666068 | 1726589666068 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589666265 | 1726589666265 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589666463 | 1726589666463 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589666695 | 1726589666695 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589666881 | 1726589666881 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589667104 | 1726589667104 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589667314 | 1726589667314 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589667534 | 1726589667534 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589667743 | 1726589667743 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589667986 | 1726589667986 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726589668164 | 1726589668164 | 0 | ceab4ec67891a2df840a705650abf1af | \[\] |
| nikita | 1726579803525 | 1726590294241 | 1726590294241 | 277e6faee45a9ea1395d936fb6c83150 | \[\] |
| nikita | 1726579825434 | 1726590298689 | 1726590298689 | 277e6faee45a9ea1395d936fb6c83150 | \[\] |
| testusername | 1726748640690 | 1726748640690 | 0 | town-square | \[\] |
| testusername | 1726748640727 | 1726748640727 | 0 | off-topic | \[\] |

определеный какнал и пользователь
```
select
    users.username,
    posts.createat,
    posts.updateat,
    posts.deleteat,
    channels.name,
    posts.fileids
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
and
users.username = 'admin';
```
> channels.name = 'off-topic'
and
users.username = 'admin';

| username | createat | updateat | deleteat | name | fileids |
| :--- | :--- | :--- | :--- | :--- | :--- |
| admin | 1716925235107 | 1716925235107 | 0 | off-topic | \[\] |
| admin | 1716973056166 | 1716973061515 | 0 | off-topic | \[\] |
| admin | 1716973056166 | 1716973061515 | 1716973061515 | off-topic | \[\] |
| admin | 1716973072032 | 1716973080931 | 0 | off-topic | \[\] |
| admin | 1716973072032 | 1716973080931 | 1716973080931 | off-topic | \[\] |
| admin | 1716973086471 | 1716973091724 | 0 | off-topic | \[\] |
| admin | 1716973086471 | 1716973091724 | 1716973091724 | off-topic | \[\] |
| admin | 1716993806516 | 1716993811866 | 0 | off-topic | \[\] |
| admin | 1716993806516 | 1716993811866 | 1716993811866 | off-topic | \[\] |
| admin | 1716993824601 | 1716993829868 | 0 | off-topic | \[\] |
| admin | 1716993824601 | 1716993829868 | 1716993829868 | off-topic | \[\] |
| admin | 1716994494527 | 1716994574894 | 0 | off-topic | \[\] |
| admin | 1716994494527 | 1716994574894 | 1716994574894 | off-topic | \[\] |
| admin | 1716994991518 | 1716994996797 | 0 | off-topic | \[\] |
| admin | 1716994991518 | 1716994996797 | 1716994996797 | off-topic | \[\] |
| admin | 1716995927548 | 1716995932943 | 0 | off-topic | \[\] |
| admin | 1716995927548 | 1716995932943 | 1716995932943 | off-topic | \[\] |
| admin | 1716996593272 | 1716996611402 | 0 | off-topic | \[\] |
| admin | 1726575322177 | 1726575322177 | 0 | off-topic | \[\] |
| admin | 1716996593272 | 1716996611402 | 1716996611402 | off-topic | \[\] |
| admin | 1716996849737 | 1716996855044 | 0 | off-topic | \[\] |
| admin | 1716996849737 | 1716996855044 | 1716996855044 | off-topic | \[\] |
| admin | 1716997064174 | 1716997069484 | 0 | off-topic | \[\] |
| admin | 1716997064174 | 1716997069484 | 1716997069484 | off-topic | \[\] |
| admin | 1716997220874 | 1716997226182 | 0 | off-topic | \[\] |
| admin | 1716997220874 | 1716997226182 | 1716997226182 | off-topic | \[\] |
| admin | 1716997686953 | 1716997692272 | 0 | off-topic | \[\] |
| admin | 1716997686953 | 1716997692272 | 1716997692272 | off-topic | \[\] |
| admin | 1716998546305 | 1716998551743 | 0 | off-topic | \[\] |
| admin | 1716998546305 | 1716998551743 | 1716998551743 | off-topic | \[\] |
| admin | 1716998563520 | 1716998568917 | 0 | off-topic | \[\] |
| admin | 1716998563520 | 1716998568917 | 1716998568917 | off-topic | \[\] |
| admin | 1717048890068 | 1717048961105 | 0 | off-topic | \[\] |
| admin | 1717048890068 | 1717048961105 | 1717048961105 | off-topic | \[\] |
| admin | 1717141926253 | 1717141931355 | 0 | off-topic | \[\] |
| admin | 1717141926253 | 1717141931355 | 1717141931355 | off-topic | \[\] |
| admin | 1717142012455 | 1717142022214 | 1717142022214 | off-topic | \[\] |
| admin | 1717142012455 | 1717142022214 | 0 | off-topic | \[\] |
| admin | 1726587392174 | 1726587392174 | 0 | off-topic | \[\] |
| admin | 1726586701243 | 1726586701243 | 0 | off-topic | \[\] |
| admin | 1726587038716 | 1726587038716 | 0 | off-topic | \[\] |
| admin | 1726587353995 | 1726587353995 | 0 | off-topic | \[\] |
| admin | 1726587471125 | 1726587471125 | 0 | off-topic | \[\] |
| admin | 1726587132179 | 1726587132179 | 0 | off-topic | \[\] |
| admin | 1726588825632 | 1726588825632 | 0 | off-topic | \[\] |

переиод определеный

```
select
    users.username,
    posts.createat,
    posts.updateat,
    posts.deleteat,
    channels.name,
    posts.fileids   
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
and
users.username = 'admin'
and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day';
```
> TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day' смотреть внизу

| username | createat | updateat | deleteat | name | fileids |
| :--- | :--- | :--- | :--- | :--- | :--- |
| admin | 1726587038716 | 1726587038716 | 0 | off-topic | \[\] |
| admin | 1726587132179 | 1726587132179 | 0 | off-topic | \[\] |
| admin | 1726588825632 | 1726588825632 | 0 | off-topic | \[\] |
| admin | 1726575322177 | 1726575322177 | 0 | off-topic | \[\] |
| admin | 1726587392174 | 1726587392174 | 0 | off-topic | \[\] |
| admin | 1726586701243 | 1726586701243 | 0 | off-topic | \[\] |
| admin | 1726587353995 | 1726587353995 | 0 | off-topic | \[\] |
| admin | 1726587471125 | 1726587471125 | 0 | off-topic | \[\] |

без файлов
```
select
    users.username,
    posts.createat,
    posts.updateat,
    posts.deleteat,
    channels.name,
    posts.fileids
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
and
users.username = 'admin'
and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
and posts.fileids ='[]';
    
```
> posts.fileids ='[]'

| username | createat | updateat | deleteat | name | fileids |
| :--- | :--- | :--- | :--- | :--- | :--- |
| admin | 1726587038716 | 1726587038716 | 0 | off-topic | \[\] |
| admin | 1726587132179 | 1726587132179 | 0 | off-topic | \[\] |
| admin | 1726588825632 | 1726588825632 | 0 | off-topic | \[\] |
| admin | 1726575322177 | 1726575322177 | 0 | off-topic | \[\] |
| admin | 1726587392174 | 1726587392174 | 0 | off-topic | \[\] |
| admin | 1726586701243 | 1726586701243 | 0 | off-topic | \[\] |
| admin | 1726587353995 | 1726587353995 | 0 | off-topic | \[\] |
| admin | 1726587471125 | 1726587471125 | 0 | off-topic | \[\] |

с файлами
```
select
    users.username,
    posts.createat,
    posts.updateat,
    posts.deleteat,
    channels.name,
    posts.fileids
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
and
users.username = 'admin'
and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
and posts.fileids !='[]';

```
>  posts.fileids !='[]'

| username | createat | updateat | deleteat | name | fileids |
| :--- | :--- | :--- | :--- | :--- | :--- |



## статистика количество сообщений от пользователя по каналу,
### описание
* **username** имя пользователя
* **name,** имя канала
* **msgcount,** собщение + коментарии
* **count** сообщение
### запрос

```
select
    users.username,
    count(posts.createat),
    channels.name
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id

group by channels.name, users.username


```
### пример
| username | count | name |
| :--- | :--- | :--- |
| feedbackbot | 1 | 3okzpxypmjfkirujfbfiupeuyy\_\_5hfjyuiemf8b58gsyndhjnp4ao |
| testusername | 1 | off-topic |
| nikita | 2 | town-square |
| nikita | 2 | 4257a2c6b1d1128dbbda5bd1c28b326f |
| nikita | 51 | a353adad5bd61e29a2c998706c321ed1 |
| nikita | 5 | 277e6faee45a9ea1395d936fb6c83150 |
| admin | 45 | off-topic |
| nikita | 20 | ceab4ec67891a2df840a705650abf1af |
| admin | 2 | a353adad5bd61e29a2c998706c321ed1 |
| admin | 65 | town-square |
| anastasia | 2 | town-square |
| nikita | 31 | 30f4b6f2c99e7dcb4558988107e31a39 |
| nikita | 2 | off-topic |
| anastasia | 2 | off-topic |
| testusername | 1 | town-square |
| feedbackbot | 3 | 3okzpxypmjfkirujfbfiupeuyy\_\_5b868apbnb8tmxyetxi6t9bpgc |
| nikita | 2 | 61f57c9d448d4fd65302bd843a89e601 |


определеный канал и пользователь
```
select
    users.username,
    count(posts.createat),
    channels.name
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
and
users.username = 'admin'
group by channels.name, users.username
```
> channels.name = 'off-topic'
and
users.username = 'admin'

| username | count | name |
| :--- | :--- | :--- |
| admin | 45 | off-topic |


переиод определеный

```
select
    users.username,
    count(posts.createat),
    channels.name
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
  and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
and
users.username = 'admin'
group by channels.name, users.username

```
> TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day' смотреть внизу

| username | count | name |
| :--- | :--- | :--- |
| admin | 8 | off-topic |


без файлов
```
select
    users.username,
    count(posts.createat),
    channels.name
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
  and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
and
users.username = 'admin'
and posts.fileids ='[]'
group by channels.name, users.username

```
> posts.fileids ='[]'

| username | count | name |
| :--- | :--- | :--- |
| admin | 8 | off-topic |

с файлами
```
select
    users.username,
    count(posts.createat),
    channels.name
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
channels.name = 'off-topic'
  and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
and
users.username = 'admin'
and posts.fileids !='[]'
group by channels.name, users.username
```
>  posts.fileids ='[]'

| username | count | name |
| :--- | :--- | :--- |

## личные сообщение
###
```
select
    users.username,
    count(posts.createat)
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
    left join channelmembers on posts.channelid = channels.id
where
channels.displayname= ''
  and TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
group by  users.username
```


## статистика количество сообщений,
### описание
* **username** имя пользователя
* **count** сообщение
### запрос

```
select
    users.username,
    count(posts.createat)
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
group by users.username


```
### пример

| username | count |
| :--- | :--- |
| testusername | 2 |
| feedbackbot | 4 |
| admin | 112 |
| anastasia | 4 |
| nikita | 115 |


переиод определеный

```
| username | count |
| :--- | :--- |
| testusername | 2 |
| feedbackbot | 2 |
| admin | 13 |
| anastasia | 4 |
| nikita | 115 |


```
> TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day' смотреть внизу

| username | count |
| :--- | :--- |
| testusername | 2 |
| feedbackbot | 2 |
| admin | 13 |
| anastasia | 4 |
| nikita | 115 |


без файлов
```
select
    users.username,
    count(posts.createat)
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
    TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
    and posts.fileids ='[]'
group by users.username
```
> posts.fileids ='[]'

| username | count |
| :--- | :--- |
| testusername | 2 |
| feedbackbot | 2 |
| admin | 13 |
| anastasia | 4 |
| nikita | 115 |


с файлами
```
select
    users.username,
    count(posts.createat)
from posts
    LEFT join users on posts.userid =  users.id
    LEFT join channels on  posts.channelid = channels.id
where
    TO_TIMESTAMP(posts.createat / 1000)  > now() - interval '30 day'
    and posts.fileids !='[]'
group by users.username

```
>  posts.fileids !='[]'

| username | count |
| :--- | :--- |


## количество сообщений от команды  
### описание
* **name** название команды
* **displayname** отображение название комманды
* **username** имя пользователь 
* **count** количество сообщений
  
### запрос показать количество сообщений отделных пользователей в команндах
```
select
    teams.name,
    teams.displayname,
    users.username,
    count(posts.createat)
from teams
left join teammembers on teams.id = teammembers.teamid
left join users on teammembers.userid = users.id
left join channels on channels.teamid = teams.id
LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
group by teams.name, teams.displayname, users.username
```
### пример

| name | displayname | username | count |
| :--- | :--- | :--- | :--- |
| ff | Чайхана | admin | 8 |
| ff | Чайхана | anastasia | 2 |
| ff | Чайхана | nikita | 108 |
| tazmar | Tazmar | admin | 104 |
| tazmar | Tazmar | anastasia | 2 |
| tazmar | Tazmar | nikita | 7 |
| tazmar | Tazmar | testusername | 2 |


### запрос показать общие количество сообщений в командах

```
select
    teams.name,
    teams.displayname,
    count(posts.createat)
from teams
left join teammembers on teams.id = teammembers.teamid
left join users on teammembers.userid = users.id
left join channels on channels.teamid = teams.id
LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
group by teams.name, teams.displayname, users.username
```

### пример

| name | displayname | count |
| :--- | :--- | :--- |
| ff | Чайхана | 8 |
| ff | Чайхана | 2 |
| ff | Чайхана | 108 |
| tazmar | Tazmar | 104 |
| tazmar | Tazmar | 2 |
| tazmar | Tazmar | 7 |
| tazmar | Tazmar | 2 |


### запрос показать общие количество сообщений в командах по определену переоду
```
select
    teams.name,
    teams.displayname,
    count(posts.createat)
from teams
left join teammembers on teams.id = teammembers.teamid
left join users on teammembers.userid = users.id
left join channels on channels.teamid = teams.id
LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
where TO_TIMESTAMP(posts.createat / 1000)   > now() - interval '30 day'
group by teams.name, teams.displayname, users.username;
```
### пример

| name | displayname | count |
| :--- | :--- | :--- |
| ff | Чайхана | 8 |
| ff | Чайхана | 2 |
| ff | Чайхана | 108 |
| tazmar | Tazmar | 5 |
| tazmar | Tazmar | 2 |
| tazmar | Tazmar | 7 |
| tazmar | Tazmar | 2 |


### отображение даты
```
TO_CHAR(TO_TIMESTAMP(posts.createat / 1000), 'DD/MM/YYYY HH24:MI:SS')
```
[Data Type Formatting Functions ](https://www.postgresql.org/docs/current/functions-formatting.html)

### переиод определеный

```
TO_TIMESTAMP(posts.createat / 1000)   > now() - interval '30 day';
```
[INTERVAL - прибавить / отнять промежуток времени](https://hmarketing.ru/blog/mysql/interval/)
## задачи
- [x] статистика количество сообщений от пользователя,
- [x] количество сообщений в каналах.
- [x] количество сообщений в  командах.
- [x] Статистика по периодам и выбор периодов. 
- [ ] Коэффициенты активности. Последние не обозначены, но можно придумать базовые вроде количества сообщений по отношению ко всему сроку использования мм или за выбранный период, в том числе количество сообщений в день.

Другие метрики: 
- [ ] время в онлайне (день, неделя, месяц и т.д.). 
- [ ] Количество входов (если есть в бд).
- [ ] Количество отправленных файлов, ссылок, картинок.