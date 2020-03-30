EverydayWechat is a WeChat gadget based on Python3 and Itchat .
You can send daily weather, reminders, and a sentence to your friends or group chats at regular intervals, and you can also intelligently and automatically reply to friend information. There is also a group assistant function that allows you to install X in your group of friends. Simple operation, Xiaobai users can quickly get started.

This project relies on the web version of WeChat for development. If you cannot log in, you cannot use this project; there is no solution.
This project relies on the web version of WeChat for development. If you cannot log in, you cannot use this project; there is no solution.
This project relies on the web version of WeChat for development. If you cannot log in, you cannot use this project; there is no solution.
Web version of WeChat address: https://wx.qq.com/ .

Find a Python & Android job in Beijing.
Add WeChat: address .

Version update log

Recently, a similar project with different functions was launched: WeChat plus group assistant .
Welcome everyone star.

It is forbidden to use this tool for commercial purposes , such as legal disputes have nothing to do with me.

Note: If you add a Turing Robot reply to your girlfriend, please consider it carefully! !! !! !!
Not every one of your girlfriends can accept it. You use robots to reply to "heartwarming words" and comfort her. Artificial intelligence may also be a mentally handicapped robot. Think about it if the robot responds to your girlfriend: "Let's break up." Maybe you really broke up. Although I will silently like in my heart (confessions of a single dog)

GitHub stars GitHub forks 请点击页面顶部靠右 star 与 fork

Function Description
Support automatic reply to multiple WeChat friends.
Send reminders to friends and group chat groups at regular intervals, including (weather, aphorisms, custom words).
Group assistant function, you can automatically reply to the group, query the most popular garbage classification, weather, calendar, real-time box office, courier information, PM2.5 and so on.
If you have no friends to test and send reminders, and only one person can't play the auto reply, what should I do (cry.jpg).
You can add "File Transfer Assistant" as a girlfriend (what is the girlfriend you said is your hands.jpg). Such a number can also be tested, send a reminder to the file transfer assistant, and chat intelligently with the file transfer assistant.

Related data sources
Weather Information:
SOJSON: https://www.sojson.com/blog/305.html
RollToolsApi: Get Today's Weather in Specific Cities
Sentence of the day:
ONE ● One: http://wufazhuce.com/
Kingsoft PowerWord ● Daily sentence (Bilingual): http://open.iciba.com/?c=api
In a word: https://hitokoto.cn/
Soil flavor love words: https://www.v2ex.com/t/569853 (soil)
Sentence Fan-Love Letter of the Republic of China: https://www.juzimi.com/ (elegant, but not available recently)
RollToolsApi: Randomly get a list of jokes
Rainbow fart: https://chp.shadiao.app
Artificial intelligence robot
Turing robot: http://www.turingapi.com/ (requires real-name certification, and only 100 free daily)
Qingyunke Intelligent Chat Robot: http://api.qingyunke.com/ (No application is required, there is no limit on the number, but it is a bit mentally handicapped, break up the artifact. Break up the artifact, use it with caution)
Smart chat (Tencent): https://ai.qq.com/product/nlpchat.shtml (Apply for use, free and unlimited. Big factories are reliable.)
Tianxing Robot: https://www.tianapi.com/apiview/47 (70,000 pieces are free to use after authentication. Afterwards charge: 10,000 pieces per 1 yuan)
Haizhi Smart: https://ruyi.ai/ (very powerful, not just for chatting. Need to apply for a key, free of charge)
Sizhi Dialogue Robot: https://www.ownthink.com/ (free, no need to apply for appid)
An AI: http://www.yige.ai/ (free and unlimited). Can customize replies, conversations, and scenes. But the use of advanced features is more complicated. But it has not been maintained for a long time.
Horoscope
Constellation House: https://www.xzw.com/ (based on crawler data)
Perpetual calendar
RollToolsApi: Holidays and Perpetual Calendar Information for a Specified Date
SOJSON: https://www.sojson.com/api/lunar.html
Box office data:
Cat Eye Real-time Box Office: https://piaofang.maoyan.com/dashboard
Garbage classification query:
atoolbox garbage classification query: http://www.atoolbox.net/Tool.php?Id=804
Air quality PM2.5 query:
aqicn: http://aqicn.org/here/
Project configuration
All the current configuration of the project is in the _config.yaml file.
The configuration file should strictly follow the yaml syntax format. The yaml learning address:
https://ansible-tran.readthedocs.io/en/latest/docs/YAMLSyntax.html
http://einverne.github.io/post/2015/08/ yaml.html

Configure an auto-reply robot.
Turn on automatic reply
Set is_auto_relay to: True.
2. Choose a channel
机器人渠道（1: 图灵机器人，2: 一个AI ,3 : 青云客，4 腾讯智能闲聊，5:天行机器人，6：海知智能，7：思知机器人)
bot_channel: 7
By default, it is a smart robot, but it is the smartest without applying for a key. .

3. Specify the list of friends to auto-reply
There are two modes

(1) In the case of not using automatic reply to all friends, that is: when is_auto_reply_all: False.
At this time, you can set the members of the whitelist that can reply, as follows:

is_auto_reply_all：False
# 指定自动回复的好友名单。
auto_reply_white_list:
  - '好友1'
  - '好友2'
(2) When auto reply is enabled for all friends, that is: when is_auto_reply_all: True.
Choose not to automatically reply to blacklist members: as follows

is_auto_reply_all：True
auto_reply_black_list:
    - '好友1'
    - '好友2'
4. Configure correlators
In addition to Qingyunke, other robots need to go to the corresponding official website, register and obtain the corresponding key. Configure whichever you need.

I. Turing robot
Open the Turing Robot official website: http://www.turingapi.com to register.
Create a robot and get apikey. Fill in the _config.yaml file:
Note: Do not turn on the "Key" option.

turing_conf:
  apiKey: '你所获取apikey'
The Turing robot must be authenticated before it can be used. The free version users can use 100 messages a day, and use and cherish.

II. Skywalk Robot
Open the Tianxing Data Registration page: https://www.tianapi.com/signup.html to register.
In the first line of the personal center, you can get apikey.
txapi_conf:
  app_key: '个人中心中的key'
  reply_name: '宝宝' # 回复的人的名字(可空)（也可在个人中心->机器人管理 修改）
  bot_name: '老公' # 机器人的名字（可空）
III. Smart Chat (Tencent)
Open https://ai.qq.com/product/nlpchat.shtml and log in.
Click Free Use-> Access Ability-> Create Application-> After the creation is successful, app_id and app_key will be displayed.
Click Application Management-> "Name of the project you created"-> Access capability-> Smart chat-> Learn more-> Access capability-> "Select project"-> Confirm interface.
Fill in app_id, app_key into yaml.
qqnlpchat_conf:
    app_id: '你申请的api_id'
    app_key: '你申请的app_key'
IV. Configure "One AI"
Open the Turing Robot official website: http://www.yige.ai to register.
Create the application, get the "Client Access Token" in the "API Key" and
fill it in the _config.yaml file:

yigeai_conf:
  client_token: '客户访问令牌'
V. Configure `` Thinking Robot ''
Open Sizhi official website: https://www.ownthink.com/ to register.
Create the robot and get the appid.
Fill in the _config.yaml file:

ownthink_conf:
    app_key: '你申请的api_id'
Regarding the auto-response, the information that can be disclosed at present:

Can only reply to text messages automatically;
If the message is sent too frequently, WeChat will restrict login to the web page. Rest assured, it will not be titled;
Friends can fill in the name "File Transfer Assistant", so you can send messages in the File Transfer Assistant and see the effect of automatic reply messages.
Configure timed reminders
1. Turn on and set reminder time
Set is_alarm to True . (When False, the timing is turned off)
alarm_info:
  is_alarm: True
2. Fill in the friend information to be sent
Fill in friend information, for example:

alarm_timed:
  - "9:00"
  - "12:30"
  - "22:00"
wechat_name:
  - '文件传输助手'
  - '诗风'
group_name:
  - 'EverydayWechat 交流群'
is_tomorrow: False
city_name: '桂林'
dictum_channel : 3
start_date: '2017-10-10'
start_date_msg: '爱你的第{}天'
calendar: True
horescope: "处女座"
sweet_words: '你脚下的蚂蚁'

Related parameter description:

name	Example	Required	Description
wechat_name	'Wife'	Optional	Friend name: You can fill in more than one person. Friends WeChat nickname or remark name (WeChat cannot be entered)
alarm_timed	'9:30'	Required	Timing time, can fill multiple
alarm_jitter	300	Empty	Randomly sent within 300 seconds before and after the timing
group_name	'Exchange group'	Optional	Group chat name, you can fill in multiple. It is necessary to save the required group chat to the address book.
is_tomorrow	True	Empty	Whether to send tomorrow's information (such as weather, constellation, perpetual calendar).
city_name	'Chengdu'	Empty	City name: The city where the friend is located, used to send the weather.
air_quality_city	'Chengdu'	Empty	City with air quality PM25.
dictum_channel	2	Empty	Maxim Channels (see table below)
start_date	'2017-10-10'	Empty	Date of acquaintance: The number of days until the current day.
start_date_msg	'Love Your Day {}'	Empty	Date copy
sweet_words	'From your handsome husband'	Empty	Sweet suffix. (Direct description of straight steel man)
horescope	'Virgo'	Empty	Constellation name or friend's birthday. Used to send horoscope
calendar	True	Empty	Perpetual calendar information
wechat_name , at least one group_name .

Motto channels: 1: ONE ● 2: Ciba (Daily Bilingual), 3: Local flavor love words, 4: One word, 5: Joke, 6: Republic of China love letter, 7: Rainbow fart.

Tips: can wechat_name fill " file transfer assistant ", so that will be sent to remind yourself of the micro-letter file transfer assistant in. Quickly and easily view results without disturbing others.

alarm_time is set to the time that needs to be reminded. Later, if WeChat is not disconnected, reminders will be sent regularly at this time of day.
For a quick experience, set alarm_timed a few minutes after the current system time. For example, the current time is 11:35, and a reminder is sent after 5 minutes, that is: alarm_timed: 11:40

Of course, you can also set up a different set of solutions according to your needs. Specific reference code.

A reminder:

2019-06-29 星期六 农历五月廿七 
【宜】嫁娶,祭祀,沐浴,扫舍,修饰垣墙 
【忌】行丧,安葬 
桂林天气预报 
【今日天气】阵雨
【今日温度】低温 26.0℃,高温 33.0℃ 
【今日风速】南风<3级
【出行提示】阵雨来袭，出门记得带伞 
【桂林PM2.5】142 轻度污染
处女座今日运势 
【幸运颜色】2
【幸运数字】薄荷绿
【综合运势】今天的你有机会重逢旧同学、旧朋友，对方会为你带来一些小惊喜，可能是某个不错的商机，也可能是某个消息。工作/学习上，今天的你目标性很强，能把当初奋斗的初心捡回来，重新出发。感情方面，有伴者今天要提防烂桃花的挑拨离间，多给对方一些信任。
你知道五氧化二磷被氧化前是什么样子嘛，什么样子？五二磷。 
宝贝这是我们在一起的第628天 
你脚下的蚂蚁
Configure group assistant function
Just put the form description.

name	Example	Required	Description
is_open	True	Required	Whether to enable the group assistant function
is_all	True	Required	Whether to enable for all groups. When turned on, only the blacklisted list will not be affected (open carefully!)
group_name_white_list	"Group name"	Optional	Whitelisted users. When is_all: Fase. Only process messages in this group
group_name_black_list	"Group name"	Optional	Blacklisted users. When is_all: True. Users in this group are not affected.
is_at	True	Required	Ait marks. Messages will only be processed when someone else is Ait himself (close carefully!).
is_auto_reply	True	Required	# Turn on group auto-reply (caution!)
is_weather	True	Required	Whether to enable weather query.
is_calendar	True	Required	Whether to enable Wanli query
is_rubbish	True	Required	Whether to enable spam query
is_moviebox	True	Required	Whether to open the computer box office
is_express	True	Required	Whether to enable express information inquiry
is_air_quality	True	Required	Whether to enable air quality inquiry
Configuration database (optional)
First you have to install the mongodb database installation. Installation method, please Google it yourself.
There is also an official installation tutorial: https://docs.mongodb.com/v3.2/administration/install-community/

(1) Set is_open_db to "True".
(2) Set host and port. tips: There are no special requirements, or those who are not familiar with the database do not need to set it.

installation
First, install Python3 and configure the environment. Personally, it is recommended that novices install Anaconda. For specific installation tutorials, you can search Google by yourself ~

Download this project or clone project directly to local.

Install dependencies using pip:

pip3 install -r requirements.txt
# 或者是使用 pip
# pip install -r requirements.txt
run
In the local cmd, jump to the project directory and run:

python run.py
The first run will pop up the QR code and scan the code to log in. If the output log is printed as "Successful login", it means that the operation is successful.
After running successfully for a period of time after login, WeChat will remain logged in without scanning the code.
If you need to switch users, in the _config.yaml file, modify the attribute of is_forced_switch to True.

run under docker
Construct docker build -t everyday_wechat:v1 .
run docker run everyday_wechat:v1
