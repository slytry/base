---
tags: 
aliases: null
date created: 2022-02-02 10:32
date modified: Thursday, March 31st 2022, 1:06:05 pm
date modified: Thursday, March 31st 2022, 1:06:05 pm
title: Добавление aliases(псевдонимы)
---

# Добавление aliases(псевдонимы)

### Добавление aliases(псевдонимы)

Шоркаты для команд гит

| Команда                                                                                       | алиас |     |     |
| --------------------------------------------------------------------------------------------- | ----- | --- | --- |
| git config --global alias.hist log --oneline                                                  | hist  |     |     |
| git config --global alias.hist log --pretty=format:"%h %ad ∣ %s%d [%an]" --graph --date=short | hist  |     |     |
| git config --global alias.co checkout                                                         | co    |     |     |
| git config --global alias.ci commit                                                           | ci    |     |     |
| git config --global alias.st status                                                           | st    |     |     |
| git config --global alias.br branch                                                           | br    |     |     |
| git config --global alias.type 'cat-file -t'                                                  | type  |     |     |
| git config --global alias.dump 'cat-file -p'                                                  | dump  |     |     |
| git config --global alias.reset reset --hard @                                                | reset | **    |     |


### Сложные алиасы с параметрами

https://jay.gooby.org/2021/07/13/positional-arguments-in-git-aliases

---

###### Citation

https://www.atlassian.com/ru/git/tutorials/git-alias

https://opensource.com/article/20/11/git-aliases

https://git.wiki.kernel.org/index.php/Aliases