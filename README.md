# -*- coding: utf-8 -*-
#BELE_Bot

import LINETCR
from LINETCR.lib.curve.ttypes import *
from datetime import datetime
from bs4 import BeautifulSoup
from threading import Thread
from googletrans import Translator
from gtts import gTTS
import time,random,sys,json,codecs,threading,glob,urllib,urllib2,urllib3,re,ast,os,subprocess,requests,tempfile

cl = LINETCR.LINE()
#cl.login(qr=True)
cl.login(token='token')
cl.loginResult()
print "Cl-Login Success\n"

ki = LINETCR.LINE()
#ki.login(qr=True)
ki.login(token='token')
ki.loginResult()
print "Ki-Login Success\n"

kk = LINETCR.LINE()
#kk.login(qr=True)
kk.login(token='token')
kk.loginResult()
print "Kk-Login Success\n"

kc = LINETCR.LINE()
#kc.login(qr=True)
kc.login(token='token')
kc.loginResult()
print "Kc-Login Success\n"

kr = LINETCR.LINE()
#kr.login(qr=True)
kr.login(token='token')
kr.loginResult()
print "Kr-Login Success\n"

vipro = LINETCR.LINE() #(isi dengan akun utama fungsinya biar akun utama di kick langsung di invite bot)
#vipro.login(qr=True)
vipro.login(token='token')
vipro.loginResult()
print "Vipro-Login Success\n"

km = LINETCR.LINE() #(bot ini di luar grup fungsinya jadi algojo kaya kicker siri)
#km.login(qr=True)
km.login(token='token')
km.loginResult()
print "Km-Login Success\n\n=====[Sukses All Login]====="

reload(sys)
sys.setdefaultencoding('utf-8')


selfMessage ="""
╔═════════════════════════
║ ☆☞ S E L F ☜☆
╠═════════════════════════
╠➩〘Hi〙
╠➩〘Me〙
╠➩〘Mymid〙
╠➩〘Mid @〙
╠➩〘SearchID: (ID LINE)〙
╠➩〘Checkdate (DD/MM/YY)〙
╠➩〘Kalender〙
╠➩〘Steal contact〙
╠➩〘Pp @〙
╠➩〘Cover @〙
╠➩〘Auto like〙
╠➩〘Scbc Text〙
╠➩〘Cbc Text〙
╠➩〘Gbc Text〙
╠➩〘Bio @〙
╠➩〘Info @〙
╠➩〘Name @〙
╠➩〘Profile @〙
╠➩〘Contact @〙
╠➩〘Getvid @〙
╠➩〘Friendlist〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""

botMessage ="""
╔═════════════════════════
║ ☆☞ B O T ☜☆
╠═════════════════════════
╠➩〘Absen〙
╠➩〘Respon〙
╠➩〘Runtime〙
╠➩〘copy @〙
╠➩〘Vipro1 copy @〙
╠➩〘Vipro2 copy @〙
╠➩〘Vipro3 copy @〙
╠➩〘Vipro4 copy @〙
╠➩〘Backup all〙
╠➩〘bio Text〙
╠➩〘@bye (Usir Bot Utama)〙
╠➩〘Bye bot (Usir Semua Bot)〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""

mediaMessage ="""
╔═════════════════════════
║ ☆☞ M E D I A ☜☆
╠═════════════════════════
╠➩〘Gift〙
╠➩〘Giftbycontact〙
╠➩〘Gif gore〙
╠➩〘Google (Text)〙
╠➩〘Playstore NamaApp〙
╠➩〘Fancytext Text〙
╠➩〘Musik Judul-Penyanyi〙
╠➩〘Lirik Judul-Penyanyi〙
╠➩〘Musrik Judul-Penyanyi〙
╠➩〘Ig UrsnameInstagram〙
╠➩〘Checkig UrsnameInstagram〙
╠➩〘Apakah Text (Kerang Ajaib)〙
╠➩〘Kapan Text (Kerang Ajaib)〙
╠➩〘Hari Text (Kerang Ajaib)〙
╠➩〘Berapa Text (Kerang Ajaib)〙
╠➩〘Berapakah Text〙
╠➩〘Youtube Judul Video〙
╠➩〘Youtubevideo Judul Video〙
╠➩〘Youtubesearch Judul Video〙
╠➩〘Image NamaGambar〙
╠➩〘Say Text〙
╠➩〘Say-en Text〙
╠➩〘Say-jp Text〙
╠➩〘Tr-id Text (Translate En Ke ID〙
╠➩〘Tr-en Text (Translate ID Ke En〙
╠➩〘Tr-th Text (Translate ID Ke Th〙
╠➩〘Id@en Text (Translate ID Ke En〙
╠➩〘Id@th Text (Translate ID Ke TH〙
╠➩〘En@id Text (Translate En Ke ID〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e 
╚═════════════════════════
"""

groupMessage ="""
╔═════════════════════════
║ ☆☞ G R O U P ☜☆
╠═════════════════════════
╠➩〘Welcome〙
╠➩〘Say:welcome〙
╠➩〘Invite creator〙
╠➩〘Setview/Cctv〙
╠➩〘Viewseen/Ciduk〙
╠➩〘Gn: (NamaGroup)〙
╠➩〘Tag all〙
╠➩〘Sepi〙
╠➩〘lurk on/off〙
╠➩〘lurkers〙
╠➩〘Recover〙
╠➩〘Cancel〙
╠➩〘Cancelall〙
╠➩〘Gcreator〙
╠➩〘Ginfo〙
╠➩〘Gurl〙
╠➩〘List group〙
╠➩〘Pict group: (NamaGroup)〙
╠➩〘Spam: (Text)〙
╠➩〘Spam〙
╠➩〘Add all〙
╠➩〘Kick: (Mid)〙
╠➩〘Invite: (Mid)〙
╠➩〘Invite〙
╠➩〘Memlist〙
╠➩〘Getgroup image〙
╠➩〘Urlgroup Image〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""
BELE="ua6c3df5aac33852251f8acee1bab0b50"

setMessage ="""
╔═════════════════════════
║ ☆☞ S E T ☜☆
╠═════════════════════════
╠➩〘Notif on/off〙
╠➩〘Url on/off〙
╠➩〘Alwaysread on/off〙
╠➩〘Sider on/off〙
╠➩〘Contact on/off〙
╠➩〘Simisimi on/off〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""

creatorMessage ="""
╔═════════════════════════
║ ☆☞ C R E A T O R ☜☆
╠═════════════════════════
╠➩〘Admin add @〙
╠➩〘Admin remove @〙
╠➩〘/vipro〙
╠➩〘/vipro1〙
╠➩〘/vipro2〙
╠➩〘/vipro3〙
╠➩〘/vipro4〙
╠➩〘Crash〙
╠➩〘Kickall〙
╠➩〘Bc: (Text)〙
╠➩〘Nk: @〙
╠➩〘Ulti @〙
╠➩〘Join group: (NamaGroup〙
╠➩〘Leave group: (NamaGroup〙
╠➩〘Leave all group〙
╠➩〘Bot restart〙
╠➩〘Turn off〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e 
╚═════════════════════════
"""

adminMessage ="""
╔═════════════════════════
║ ☆☞ A D M I N ☜☆
╠═════════════════════════
╠➩〘Admin list〙
╠➩〘Ban〙
╠➩〘Unban〙
╠➩〘Ban @〙
╠➩〘Unban @〙
╠➩〘Ban list〙
╠➩〘Clear ban〙
╠➩〘Kill〙
╠➩〘Kick @〙
╠➩〘Set member: (Jumlah)〙
╠➩〘Ban group: (NamaGroup〙
╠➩〘Del ban: (NamaGroup〙
╠➩〘List ban〙
╠➩〘Kill ban〙
╠➩〘Glist〙
╠➩〘Glistmid〙
╠➩〘Details group: (Gid)〙
╠➩〘Cancel invite: (Gid)〙
╠➩〘Invitemeto: (Gid)〙
╠➩〘Kapten acc invite〙
╠➩〘Vipro1 acc invite〙
╠➩〘Vipro2 acc invite〙
╠➩〘Vipro3 acc invite〙
╠➩〘Vipro4 acc invite〙
╠➩〘Removechat〙
╠➩〘Join on/off〙
╠➩〘Joincancel on/off〙
╠➩〘Respon on/off〙
╠➩〘Responkick on/off〙
╠➩〘Leave on/off〙
╠➩〘All join / (Vipro1/2/3/4 Join)〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""

helpMessage ="""
╔═════════════════════════
║ ☆☞ H E L P ☜☆
╠═════════════════════════
╠➩〘Help protect〙
╠➩〘Help self〙
╠➩〘Help bot〙
╠➩〘Help group〙
╠➩〘Help set〙
╠➩〘Help media〙
╠➩〘Help admin〙
╠➩〘Help creator〙
╠➩〘Owner〙
╠➩〘Admin〙
╠➩〘Speed〙
╠➩〘Speed test〙
╠➩〘Status〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e
╚═════════════════════════
"""

protectMessage ="""
╔═════════════════════════
║ ☆☞ P R O T E C T ☜☆
╠═════════════════════════
╠➩〘Allprotect on/off〙
╠➩〘Autocancel on/off〙
╠➩〘Qr on/off〙
╠➩〘Autokick on/off〙
╠➩〘Ghost on/off〙
╠➩〘Invitepro on/off〙
╠═════════════════════════
║ By : BELE 
║ line.me/ti/p/~@baj6842e 
╚═════════════════════════
"""


KAC=[cl,ki,kk,kc,kr,km,vipro]
mid = cl.getProfile().mid
Amid = ki.getProfile().mid
Bmid = kk.getProfile().mid
Cmid = kc.getProfile().mid
Dmid = kr.getProfile().mid
Emid = km.getProfile().mid
Fmid = vipro.getProfile().mid
Bots=[mid,Amid,Bmid,Cmid,Dmid,Emid,Fmid,"ua6c3df5aac33852251f8acee1bab0b50"]
Creator=["ua6c3df5aac33852251f8acee1bab0b50"]
admin=["ua6c3df5aac33852251f8acee1bab0b50"]

contact = cl.getProfile()
backup1 = cl.getProfile()
backup1.displayName = contact.displayName
backup1.statusMessage = contact.statusMessage 
backup1.pictureStatus = contact.pictureStatus

contact = ki.getProfile()
backup2 = ki.getProfile()
backup2.displayName = contact.displayName
backup2.statusMessage = contact.statusMessage 
backup2.pictureStatus = contact.pictureStatus

contact = kk.getProfile()
backup3 = kk.getProfile()
backup3.displayName = contact.displayName
backup3.statusMessage = contact.statusMessage 
backup3.pictureStatus = contact.pictureStatus

contact = kc.getProfile()
backup4 = kc.getProfile()
backup4.displayName = contact.displayName
backup4.statusMessage = contact.statusMessage 
backup4.pictureStatus = contact.pictureStatus

contact = kr.getProfile()
backup5 = kr.getProfile()
backup5.displayName = contact.displayName
backup5.statusMessage = contact.statusMessage 
backup5.pictureStatus = contact.pictureStatus

responsename = cl.getProfile().displayName
responsename2 = ki.getProfile().displayName
responsename3 = kk.getProfile().displayName
responsename4 = kc.getProfile().displayName
responsename5 = kr.getProfile().displayName


wait = {
"LeaveRoom":True,
"AutoJoin":False,
"AutoJoinCancel":True,
"memberscancel":10,
"Members":1,
"AutoCancel":{},
"AutoCancelon":False, 
"joinkick":False,
"AutoKick":{},
"AutoKickon":False,
'pap':{},
'invite':{},
'steal':{},
'gift':{},
'likeOn':{},
'Leave':{}, 
'detectMention':False,
'kickMention':False, 
'timeline':True,
"Timeline":True,
"comment1":"Auto Like ©By : Bele\nContact Me : 👉 line.me/ti/p/~@baj6842e",
"comment2":"Auto Like ©By : Bele\nContact Me : 👉 line.me/ti/p/~@baj6842e",
"comment3":"Auto Like ©By : Bele\nContact Me : 👉 line.me/ti/p/~@baj6842e",
"comment4":"Auto Like ©By : Vele\nContact Me : 👉 line.me/ti/p/~@baj6842e",
"comment5":"Auto Like ©By : Bele\nContact Me : 👉 line.me/ti/p/~@baj6842e", 
"commentOn":True,
"commentBlack":{},
"message":"Thx For Add Me (^_^)", 
"blacklist":{},
"wblacklist":False,
"dblacklist":False,
"Qr":{},
"Qron":False,
"Contact":False,
"Sambutan":True,
"Ghost":True,
"inviteprotect":False, 
"alwaysRead":False, 
"Sider":{},
"Simi":{}, 
"lang":"JP",
"BlGroup":{}
}

settings = {
"simiSimi":{}
}

cctv = {
"cyduk":{},
"point":{},
"sidermem":{}
} 

wait2 = {
"readPoint":{},
"readMember":{},
"setTime":{},
"ROM":{}
}

setTime = {}
setTime = wait2['setTime']
mulai = time.time() 

def download_page(url):
version = (3,0)
cur_version = sys.version_info
if cur_version >= version: 
import urllib,request 
try:
headers = {}
headers['User-Agent'] = "Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2228.0 Safari/537.36"
req = urllib,request.Request(url, headers = headers)
resp = urllib,request.urlopen(req)
respData = str(resp.read())
return respData
except Exception as e:
print(str(e))
else: 
import urllib2
try:
headers…
