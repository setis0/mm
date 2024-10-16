# оглавление

- [x] список каналов и команды с количеством пользователями
- [x] количество сообщений в каналах
- [x] количество сообщений в каналах по переиоду
- [x] количество сообщений  пользователй в каналах
- [x] количество сообщений  пользователй в каналах по определеному переиоду
- [x] количество сообщей в команндах
- [x] количество сообщей пользователей в команндах
- [x] количество сообщей пользователей в команндах по определеному переиоду

## список каналов и команды с количеством пользователями

### описание
* **team** команда
* **channel** канал
* **users** количество пользователей
### запрос
```
select teams.displayname    as team,
       channels.displayname as channel,
       count(users.id) as users
from teams
         left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
where
    channels.type != 'D'
group by teams.displayname, channels.displayname
```
### пример
| team | channel | users |
| :--- | :--- | :--- |
| Tazmar | Off-Topic | 4 |
| Tazmar | Town Square | 4 |
| Tazmar | Чайхана | 4 |
| Чайхана | Off-Topic | 3 |
| Чайхана | Town Square | 3 |
| Чайхана | Продажи \(Чайхана\) | 3 |
| Чайхана | Реализация \(Чайхана\) | 3 |
| Чайхана | Флуд \(Чайхана\) | 3 |
| Чайхана | Чайхана \(реализация\) | 3 |
| Чайхана | Чайхана \(флуд\) | 3 |

## количество сообщений в каналах
### описание
* **team** команда
* **channel** канал
* **count** сообщений
### запрос
```
select teams.displayname    as team,
       channels.displayname as channel,
        count(posts.createat) as count
from teams
         left join teammembers on teams.id = teammembers.teamid
         left join channels on channels.teamid = teams.id
LEFT join posts on posts.channelid = channels.id
where
    channels.type != 'D'
group by teams.displayname, channels.displayname
```
### пример
| team | channel | count |
| :--- | :--- | :--- |
| Tazmar | Off-Topic | 45 |
| Tazmar | Town Square | 65 |
| Tazmar | Чайхана | 5 |
| Чайхана | Off-Topic | 5 |
| Чайхана | Town Square | 5 |
| Чайхана | Продажи \(Чайхана\) | 20 |
| Чайхана | Реализация \(Чайхана\) | 53 |
| Чайхана | Флуд \(Чайхана\) | 31 |
| Чайхана | Чайхана \(реализация\) | 2 |
| Чайхана | Чайхана \(флуд\) | 2 |

## количество сообщений в каналах по переиоду
### описание
* **team** команда
* **channel** канал
* **count** сообщений
### запрос
```
select teams.displayname    as team,
       channels.displayname as channel,
        count(posts.createat) as count
from teams
         left join teammembers on teams.id = teammembers.teamid
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.channelid = channels.id
where
    channels.type != 'D'
and
    TO_TIMESTAMP(posts.createat / 1000)   > TIMESTAMP '2024-10-14' - interval '30 day'
group by teams.displayname, channels.displayname
```
> TO_TIMESTAMP(posts.createat / 1000)   > TIMESTAMP '2024-10-14' - interval '30 day'

> TO_TIMESTAMP(posts.createat / 1000)   > now() - interval '30 day';

[INTERVAL - прибавить / отнять промежуток времени](https://hmarketing.ru/blog/mysql/interval/)

[datatype-datetime](https://postgrespro.ru/docs/postgresql/17/datatype-datetime)
### пример
| team | channel | count |
| :--- | :--- | :--- |
| Чайхана | Чайхана \(флуд\) | 6 |
| Чайхана | Off-Topic | 15 |
| Чайхана | Флуд \(Чайхана\) | 93 |
| Tazmar | Off-Topic | 32 |
| Чайхана | Реализация \(Чайхана\) | 159 |
| Чайхана | Продажи \(Чайхана\) | 60 |
| Чайхана | Town Square | 15 |
| Tazmar | Town Square | 12 |
| Чайхана | Чайхана \(реализация\) | 6 |
| Tazmar | Чайхана | 20 |

## количество сообщений  пользователй в каналах
### описание
### запрос
```
select teams.displayname    as team,
       channels.displayname as channel,
       users.username as username,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
where
    channels.type != 'D'
group by teams.displayname, channels.displayname, users.username
```
### пример

| team | channel | username | count |
| :--- | :--- | :--- | :--- |
| Tazmar | Off-Topic | admin | 42 |
| Tazmar | Off-Topic | anastasia | 1 |
| Tazmar | Off-Topic | nikita | 1 |
| Tazmar | Off-Topic | testusername | 1 |
| Tazmar | Town Square | admin | 62 |
| Tazmar | Town Square | anastasia | 1 |
| Tazmar | Town Square | nikita | 1 |
| Tazmar | Town Square | testusername | 1 |
| Tazmar | Чайхана | admin | 0 |
| Tazmar | Чайхана | anastasia | 0 |
| Tazmar | Чайхана | nikita | 5 |
| Tazmar | Чайхана | testusername | 0 |
| Чайхана | Off-Topic | admin | 3 |
| Чайхана | Off-Topic | anastasia | 1 |
| Чайхана | Off-Topic | nikita | 1 |
| Чайхана | Town Square | admin | 3 |
| Чайхана | Town Square | anastasia | 1 |
| Чайхана | Town Square | nikita | 1 |
| Чайхана | Продажи \(Чайхана\) | admin | 0 |
| Чайхана | Продажи \(Чайхана\) | anastasia | 0 |
| Чайхана | Продажи \(Чайхана\) | nikita | 20 |
| Чайхана | Реализация \(Чайхана\) | admin | 2 |
| Чайхана | Реализация \(Чайхана\) | anastasia | 0 |
| Чайхана | Реализация \(Чайхана\) | nikita | 51 |
| Чайхана | Флуд \(Чайхана\) | admin | 0 |
| Чайхана | Флуд \(Чайхана\) | anastasia | 0 |
| Чайхана | Флуд \(Чайхана\) | nikita | 31 |
| Чайхана | Чайхана \(реализация\) | admin | 0 |
| Чайхана | Чайхана \(реализация\) | anastasia | 0 |
| Чайхана | Чайхана \(реализация\) | nikita | 2 |
| Чайхана | Чайхана \(флуд\) | admin | 0 |
| Чайхана | Чайхана \(флуд\) | anastasia | 0 |
| Чайхана | Чайхана \(флуд\) | nikita | 2 |

## количество сообщений  пользователй в каналах по определеному переиоду
### описание
### запрос
```
select teams.displayname    as team,
       channels.displayname as channel,
       users.username as username,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
where
    channels.type != 'D'
and
    TO_TIMESTAMP(posts.createat / 1000)   > TIMESTAMP '2024-10-14' - interval '30 day'
group by teams.displayname, channels.displayname, users.username
```
### пример

| team | channel | username | count |
| :--- | :--- | :--- | :--- |
| Tazmar | Off-Topic | admin | 5 |
| Tazmar | Off-Topic | anastasia | 1 |
| Tazmar | Off-Topic | nikita | 1 |
| Tazmar | Off-Topic | testusername | 1 |
| Tazmar | Town Square | anastasia | 1 |
| Tazmar | Town Square | nikita | 1 |
| Tazmar | Town Square | testusername | 1 |
| Tazmar | Чайхана | nikita | 5 |
| Чайхана | Off-Topic | admin | 3 |
| Чайхана | Off-Topic | anastasia | 1 |
| Чайхана | Off-Topic | nikita | 1 |
| Чайхана | Town Square | admin | 3 |
| Чайхана | Town Square | anastasia | 1 |
| Чайхана | Town Square | nikita | 1 |
| Чайхана | Продажи \(Чайхана\) | nikita | 20 |
| Чайхана | Реализация \(Чайхана\) | admin | 2 |
| Чайхана | Реализация \(Чайхана\) | nikita | 51 |
| Чайхана | Флуд \(Чайхана\) | nikita | 31 |
| Чайхана | Чайхана \(реализация\) | nikita | 2 |
| Чайхана | Чайхана \(флуд\) | nikita | 2 |

## количество сообщей в команндах
### описание
### запрос
```
select teams.displayname    as team,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
group by teams.displayname
```
### пример
| team | count |
| :--- | :--- |
| Tazmar | 115 |
| Чайхана | 118 |

## количество сообщей пользователей в команндах
### описание
### запрос
```
select teams.displayname    as team,
       users.username as username,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
group by teams.displayname, users.username
```
### пример
| team | username | count |
| :--- | :--- | :--- |
| Tazmar | admin | 104 |
| Tazmar | anastasia | 2 |
| Tazmar | nikita | 7 |
| Tazmar | testusername | 2 |
| Чайхана | admin | 8 |
| Чайхана | anastasia | 2 |
| Чайхана | nikita | 108 |

## количество сообщей пользователей в команндах по определеному переиоду
### описание
### запрос
```
select teams.displayname    as team,
       users.username as username,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
where
    TO_TIMESTAMP(posts.createat / 1000)   > TIMESTAMP '2024-10-14' - interval '30 day'
group by teams.displayname, users.username
```
### пример

| team | username | count |
| :--- | :--- | :--- |
| Tazmar | admin | 5 |
| Tazmar | anastasia | 2 |
| Tazmar | nikita | 7 |
| Tazmar | testusername | 2 |
| Чайхана | admin | 8 |
| Чайхана | anastasia | 2 |
| Чайхана | nikita | 108 |

## количество сообщей пользователей в команндах по определеному переиоду
### описание
### запрос
```
select teams.displayname    as team,
       users.username as username,
        count(posts.createat) as count
from teams
        left join teammembers on teams.id = teammembers.teamid
         left join users on teammembers.userid = users.id
         left join channels on channels.teamid = teams.id
         LEFT join posts on posts.userid =  users.id and posts.channelid = channels.id
where
    TO_TIMESTAMP(posts.createat / 1000)   > TIMESTAMP '2024-10-14' - interval '30 day'
group by teams.displayname, users.username
```
### пример
| team | username | count |
| :--- | :--- | :--- |
| Tazmar | admin | 5 |
| Tazmar | anastasia | 2 |
| Tazmar | nikita | 7 |
| Tazmar | testusername | 2 |
| Чайхана | admin | 8 |
| Чайхана | anastasia | 2 |
| Чайхана | nikita | 108 |

## отображение исходящие сообщение пользователя

```
select CASE
           WHEN channels.displayname = '' THEN
               (select u.username
                from users u
                        join channels on channels.id = posts.channelid
                        join channelmembers on channelmembers.channelid = posts.channelid and channelmembers.userid = u.id
                where u.id != posts.userid)
           ELSE channels.displayname END                                                  as channel,
       TO_CHAR(TO_TIMESTAMP(posts.createat / 1000), 'DD/MM/YYYY HH24:MI:SS')              as createat,
       Case
           when posts.updateat = posts.createat then null
           else
               TO_CHAR(TO_TIMESTAMP(posts.updateat / 1000), 'DD/MM/YYYY HH24:MI:SS') end  as updateat,
       CASE
           WHEN posts.deleteat = 0 THEN null
           ELSE TO_CHAR(TO_TIMESTAMP(posts.deleteat / 1000), 'DD/MM/YYYY HH24:MI:SS') END AS deleteat,
       posts.message,
       CASE
           WHEN posts.fileids = '[]' THEN null
           ELSE posts.fileids END AS fileids,
      CASE
           WHEN posts.filenames = '[]' THEN null
           ELSE posts.filenames END AS filenames
from posts
         join users on posts.userid = users.id
         join channels on posts.channelid = channels.id
where
  posts.type = ''
and
    users.username = 'admin'
```

### пример 
| channel | createat | updateat | deleteat | message | fileids | filenames |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Town Square | 16/07/2024 08:16:57 | null | null | Что-то пошло не так в потоке пересчета валют🎉 | null | null |
| Town Square | 16/07/2024 08:33:22 | null | null | Что-то пошло не так в потоке пересчета валют🎉 | null | null |
| Off-Topic | 17/09/2024 12:15:22 | null | null | hop | null | null |
| alex | 10/10/2024 14:31:01 | null | null | Тест для личных сообщений. Кажется, тут напрямую никто никому не писал | null | null |
