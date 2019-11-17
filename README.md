![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 有关Right Of Slash的一切
#### Everything To Right Of Slash
**发布-日期: 2014年05月27日 (评论)**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
如果你曾在MSDB系统表中看到完整的文件夹路径和文件名，你首先需要做的第一件事就是获取路径，或仅获取文件名。 有几种方法可以返回路径和文件名，但这只是我使用的方式。

## English
If you’ve ever seen a full folder path, and file name in the MSDB system tables; one of the first things you need to do is get just the path, or just the file name. There’s a few ways you can get these returned, but this is the way I use.

---
## Logic
```SQL

-- 	get only the file names to the right of the slash.
-- 只获取斜杠右侧的文件名。
select
    right(physical_device_name, charindex('\', reverse('\' + physical_device_name)) - 1) from 
    msdb..backupmediafamily
 
-- 	get the path to the left of the last slash.  basically gives you the full path to where the file resides.
-- 获取最后一个斜杠左侧的路径。 基本上都能为你提供文件所在位置的完整路径。
select 
    reverse(right(reverse(physical_device_name), len(physical_device_name) - charindex('\',reverse(physical_device_name),1) + 1)) from
    msdb..backupmediafamily

```



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

