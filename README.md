# WFBot

[![GitHub license](https://img.shields.io/github/license/Cansll/WFBot.svg)](https://github.com/Cansll/WFBot/blob/master/LICENSE) [![WFBot](https://img.shields.io/badge/BOT-@yorurinbot-green.svg?logo=telegram&style=flat)](https://t.me/yorurinbot)

一个中文Warframe信息查询TelegramBot（全平台）,可以用于在GAS(Google App Script)部署

API来自[WarframeStat.us API](https://api.warframestat.us/pc)，词典来自[Richasy/WFA_Lexicon](https://github.com/Richasy/WFA_Lexicon)，js模板来自[unnikked的Gist](https://gist.github.com/unnikked/828e45e52e217adc09478321225ec3de)。

## 命令
```
/ help | / Help: Ajuda da consulta.
/ time | / Time Broadcast: Consulte a hora e o clima das planícies e da terra.
/ wfbotinfo: Consultar informações do robô.

/ nw | / Rádio da meia-noite: Consultar informações sobre a missão do rádio da meia-noite.
/ vd | / Comerciante nulo: Consultar informações do comerciante nulo.
/ sortie | / Assault: Consulta informações diárias de assalto.
/ fissures | / fissures: Consultar informações sobre fissuras vazias.
/ conprogress | / Andamento da construção: Consultar as informações do andamento da construção da invasão.
/ darvo | / Promoções Diárias: Verifique as informações diárias da promoção Darvo.
/ kuva | / kuva: consulta as informações atuais da missão Kuva.
/ arbit | / arbitration: consulta as informações da tarefa de arbitragem atual.
/ invas | / Invasion: Consultar informações sobre a tarefa de invasão atual.
/ sentient | / S Ship: Consultar informações anormais atuais do Sentient.
/ buff | / Addition: Consultar as informações de bônus globais atuais.
/ simaris | / hunting: consulta as informações do alvo de caça atual.
/ update | / update: Consulte o registro de atualização mais recente (PC) da tradução.
/ changelog | / Atualização histórica: Consulte os 5 últimos registros de atualização (PC) da tradução.
/ news | / Últimas Notícias: Informe-se sobre as últimas notícias traduzidas (PC).
/ recentnews | / Notícias: Verifique as 5 últimas notícias (PC) traduzidas.

/ wm <item>: Consulta as estatísticas de preços de mercado dos itens WM.
/ price <item>: Consulte o preço WM de um item.
/ drop <item>: Consulta informações sobre o descarte do item.

/ setplatform <pc | xb1 | ps4 | swi>: modifica a plataforma a ser consultada quando o bot o atende.
/ getplatform: Visualize a plataforma que o bot atual consulta ao atendê-lo.
Se você precisa preencher uma lista de comandos no Bot, use esta lista
```

<details>
<summary>如果需要在BotFather中填写命令列表，请使用这个列表</summary>

```
/ help | / Help: Ajuda da consulta.
/ time | / Time Broadcast: Consulte a hora e o clima das planícies e da terra.
/ wfbotinfo: Consultar informações do robô.

/ nw | / Rádio da meia-noite: Consultar informações sobre a missão do rádio da meia-noite.
/ vd | / Comerciante nulo: Consultar informações do comerciante nulo.
/ sortie | / Assault: Consulta informações diárias de assalto.
/ fissures | / fissures: Consultar informações sobre fissuras vazias.
/ conprogress | / Andamento da construção: Consultar as informações do andamento da construção da invasão.
/ darvo | / Promoções Diárias: Verifique as informações diárias da promoção Darvo.
/ kuva | / kuva: consulta as informações atuais da missão Kuva.
/ arbit | / arbitration: consulta as informações da tarefa de arbitragem atual.
/ invas | / Invasion: Consultar informações sobre a tarefa de invasão atual.
/ sentient | / S Ship: Consultar informações anormais atuais do Sentient.
/ buff | / Addition: Consultar as informações de bônus globais atuais.
/ simaris | / hunting: consulta as informações do alvo de caça atual.
/ update | / update: Consulte o registro de atualização mais recente (PC) da tradução.
/ changelog | / Atualização histórica: Consulte os 5 últimos registros de atualização (PC) da tradução.
/ news | / Últimas Notícias: Informe-se sobre as últimas notícias traduzidas (PC).
/ recentnews | / Notícias: Verifique as 5 últimas notícias (PC) traduzidas.

/ wm <item>: Consulta as estatísticas de preços de mercado dos itens WM.
/ price <item>: Consulte o preço WM de um item.
/ drop <item>: Consulta informações sobre o descarte do item.

/ setplatform <pc | xb1 | ps4 | swi>: modifica a plataforma a ser consultada quando o bot o atende.
/ getplatform: Visualize a plataforma que o bot atual consulta ao atendê-lo.
Se você precisa preencher uma lista de comandos no Bot, use esta lista
```

</details>

## 选项

 * [showWaitMsg](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L6) (boolean)
   - 此选项用于开关是否在用户发送正确的命令后立刻回复一条"正在获取数据..."。这在使用获取信息缓慢的命令时可以告诉用户你的命令被收到了，而不是干等。

 * [token](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L4) (string)
   - 此选项用于设定你的机器人token。

 * [usetimezone](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L12) (boolean)
   - 此选项用于设定是否启用时区修正。

 * [utc](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L16) (int)
   - 此选项在开启时区修正后可以自动转换时区时间。填写数字(UTC+?)。

 * [defaultPlatform ](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L20) (string)
   - 默认查询平台。此字串将拼接到地址中，请勿乱填。支持的参数："pc" "ps4" "xb1" "swi"
   - 此选项设定bot默认情况下的平台，每个用户可以通过`/setplatform`命令设置自己需要查询的平台。
   
## 极其简陋的配置方法步骤教学

1. 访问[BotFather](https://t.me/botfather)，输入`/newbot`，然后跟着提示创建一个Bot。
2. 输入`/mybots`，选择你刚刚创建的Bot，然后点击`API Token`，记下那一串字符串。
3. 登陆[Google Apps Script](https://script.google.com/home/my)后台，然后点击左边的新建脚本按钮。
4. 复制[Telebot.js](https://github.com/Cansll/WFBot/raw/master/Telebot.js)的所有内容到GAS。
5. 修改[Token](https://github.com/Cansll/WFBot/blob/master/Telebot.js#L4)变量内容为你刚刚创建Bot时给你的那一串字符串。
6. 保存，点击发布-部署为网络应用，输入项目名字。期间可能会提示你授权，请跟着提示确认。
7. 回到编辑器，找到工具条上的选择函数(或显示`myFunction`)，选择`setWebHook`。
8. 点击左侧三角形按钮运行一次。
9. 现在可以看看你的bot是不是可以响应你的指令了?
