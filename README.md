- 👋 Hi, I’m @AlyssSix
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
AlyssSix/AlyssSix is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

學校	學系	在職/一般生	成績單正本	推薦函	初審	複審	錄取率	今年錄取人數	報名人數	在職證明書	舊機構	remark	缺額
交通大學	網路工程研究所碩士班(聯招)	在職生	正本	2	100%	NA	22%	(混合)150人	148/668	正本1年(寄)		書面紙本	聯招
交通大學	數據科學與工程研究所	在職生	正本	2	100%	NA	10%	(混合)35人	25/247	正本1年(寄)		書面紙本	↑增加10人
交通大學	資訊科學與工程研究所丙組	在職生	正本	2	33%	66%	13%	(混合)12人	10/76	正本1年(寄)			↑增加2人 
交通大學	資訊科學與工程研究所戊組	在職生	正本	2	33%	66%	10%	(混合)7人	7/68	正本1年(寄)			
交通大學	智能系統研究所碩士班春(聯招)	一般生	上傳	2	100%	NA	NA	NA	NA				聯招
成功大學	工業與資訊管理學系碩士班	一般生	上傳	至多2	60%	40%	18%	24人	133				
成功大學	資訊管理研究所	一般生	上傳	2	40%	60%	14%	14人					
成功大學	人工智慧科技碩士學位學程	一般生	上傳	NA	50%	50%	11%	9人					
清華大學	資訊工程學系碩士班 (甲組) 英文計劃書	在職生	上傳	2	100%	NA	42%	3人	7	正本2年	勞保局		
清華大學	資訊安全研究所碩士班	在職生	上傳	2	50%	50%	50%	1人	2	正本2年	勞保局		
清華大學	資訊系統與應用研究所碩士班	在職生	上傳	2	50%	50%	50%	1人	2	正本2年	勞保局		
清華大學	資訊工程學系碩士班 丙組(人工智慧組) 	在職生	上傳	2	50%	50%	50%	1人	2	正本2年	勞保局		
政治大學	資訊科學系資訊科學與工程組(一般組)一般生	一般生	上傳	2	60%	40%	0.3	21人	33/107			成績有特別要求	↓減少12
政治大學	科技管理與智慧財產研究所智慧財產組	一般生	上傳	2	30%	70%	25%	8人	35人				↓減少1
政治大學	資訊管理學系(科技組)	一般生	上傳	至多2	40%	60%	0.18	7人	39			成績有特別要求	
政治大學	資訊科學系智慧計算組一般生	一般生	上傳	2	60%	40%	32%	8人	25				
政治大學	資訊管理學系(資管組)	一般生	上傳	至多2	40%	60%	13%	18人	17/127				
中興	科技管理研究所電子商務	一般生	上傳	至多2	60%	40%	13%	4人	29				
中興	科技管理研究所科技管理	一般生	上傳	至多2	60%	40%	12%	4人	31				
中央	資訊管理學系碩士班 (自傳用本系自訂表格)	一般生	上傳	NA	50%	50%	21%	46人	224				
中央	資訊工程學系軟體工程碩士班(兩千字內)	一般生	上傳	2	50%	50%	20%	20人	10/42				↑增加10人
中正	資訊工程學系	在職生\一般生	上傳	2	50%	50%	100%	2人	1人	正本2年	勞保局	一般生26% 75人	可以報同時兩組
中正	資訊管理學系	一般生	上傳	3	50%	50%	0.21	16人	70人				
中山	資訊工程學系甲組	一般生	上傳	可放	50%	50%	0.17	47人	51/292			A~E	↓減少４
中山	資訊管理學系	一般生	上傳	彌封推薦信2封	50%	50%	0.22	27人	30/136				↓減少３ 




import random
import time
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.chrome.options import Options
options = webdriver.ChromeOptions()
options.add_argument("-incognito")
driver = webdriver.Chrome(executable_path='.\chromedriver', options=options)
driver.get('https://zh.surveymonkey.com/r/JM7JH5Q')
opentxt=open('TEMP.txt',encoding="utf-8") #開記事本config
text = []
for line in opentxt.read().splitlines():
    text.append(line)
limit_low=35
limit_high=36
floatt=random.uniform(limit_low,limit_high)
C=1
TEMPP=round(floatt,C) #隨機溫度
EIDD = (text[0])
time.sleep(10)

agree = driver.find_element_by_xpath(('//*[@id="109162016_829124879_label"]/span[1]')
agree.click()

EID = driver.find_element_by_xpath('//*[@id="109161976"]')
EID.send_keys(EIDD) 

way = driver.find_element_by_xpath('//*[@id="109162187_829126208_label"]/span[1]')
way.click()

temp = driver.find_element_by_xpath('//*[@id="109162340_829127102_label"]/span[1]')
temp.click()

EIDT = driver.find_element_by_xpath('//*[@id="109162245"]')
EIDT.send_keys(int(TEMPP))

finalagree = driver.find_element_by_xpath('//*[@id="109162340_829127102_label"]/span[1]')
finalagree.click()

time.sleep(10)  #延遲
nxt_btn = driver.find_element_by_xpath('//*[@id="patas"]/main/article/section/form/div[2]/button')
nxt_btn.click()

time.sleep(7)  #延遲
driver.close() # 關瀏覽器
*-----------------------------***********************************-------*--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--*--*

from DBSrv5ConnPy.db_object import DBObject ##DB連線工具
from jira import JIRA ##JIRA套件
import getpass ##加解密工具
import requests ##爬蟲工具
import pandas as pd ##潘達


opentxt=open('Jira.txt',encoding="utf-8") ##開記事本config
text = []
for line in opentxt.read().splitlines(): ##列出記事本資料
    text.append(line)
    


##抓帳密
account = (text[1])
password = (text[3])

##解密碼
def dectry(p):
    decodtool = 'djq%5cu#-jeq15abg$z9_i#_w=$o88m!*alpbedlbat8cr74sd'
    password_decoded = ""
    for i,j in zip(p.split("_")[:-1],decodtool):
        # i 為加密字元，j為祕鑰字元
        temp = chr(int(i) - ord(j)) # 解密字元 = (加密Unicode碼字元 - 祕鑰字元的Unicode碼)的單位元組字元
        password_decoded = password_decoded+temp
    return password_decoded
password_decoded = dectry(password)
password = password_decoded
authority = (account , password)

if (text[9])=='False':
    testserver=False
    testshow="正式環境(PROD)"
else :
    testserver=True
    testshow="測試環境(TEST)"
print ("目前是:",testshow)
print ("DB廠區:",text[7])
mes_obj = DBObject(fab=(text[7]), is_test_db=testserver)   ##連入資料庫廠區&Test
login = requests.get('http://300jira:8080/', auth=authority) ##進入jira網頁
if login.status_code == requests.codes.ok:  ##檢查網路&登入是否正常
    print("成功登入JIRA")
    print("生成空間中...")
    jira = JIRA( {'server': 'http://300jira:8080/'}, basic_auth=authority) ##登入jira       
    TABLE_BT = {}
    BT_KEY_NUMBER=[]
    BT_SUMMARY_TITLE=[]    ##只是一堆倉庫
    BT_REPORTER=[]
    BT_ASSIGNEE=[]
    BT_ISSUE_TYPE=[]
    BT_DUE_DATE=[]
    BT_STATUS=[]
    BT_COMPONENTS=[]
    BT_ATTACHMENT=[]
    
    TABLE_BTHHH = {}
    KEY_NUMBER=[]
    SUMMARY_TITLE=[]    ##只是一堆倉庫
    REPORTER=[]
    ASSIGNEE=[]
    ISSUE_TYPE=[]
    DUE_DATE=[]
    STATUS=[]
    COMPONENTS=[]
    ATTACHMENT=[]
    YC=0
    CC=0
    new =0
    up = 0
    i=-1
    
    print("你的JIRA搜尋語法: ",text[5])
    print("生成完畢，抓取資料中.....")
    
    for issue in jira.search_issues(text[5],fields='*all',maxResults=500): ##搜尋JIRA下JQL指令
       
        container = ('{}'.format(issue.key))
        KEY_NUMBER.append(container)          ##往下抓各類資料&存放
        container = ('{}'.format(issue.fields.summary)) 
        SUMMARY_TITLE.append(container)
        container = ('{}'.format(issue.fields.reporter))
        REPORTER.append(container)

        container = ('{}'.format(issue.fields.assignee))
        ASSIGNEE.append(container)

        container = ('{}'.format(issue.fields.issuetype))
        ISSUE_TYPE.append(container)

        container = ('{}'.format(issue.fields.duedate))
        DUE_DATE.append(container)

        container = ('{}'.format(issue.fields.status))
        STATUS.append(container)
        
        containerA= ('{}'.format(issue.fields.attachment))
        if len(issue.fields.attachment):   #判斷網頁有無附圖，有即存入Y，無則N
            ATTACHMENT.append('Y')
            
        else:
            ATTACHMENT.append('N')
           
        i=i+1
        
## Query找出TABLE的KEY跟網頁的KEY相同之 TABLE的KEY   
        sql = ("select KEY_NUMBER from INFRA_JIRA_ORDER_BT where KEY_NUMBER = '{}'").format(issue.key) 
        Qkey=mes_obj.query(sql=sql,debug=False)
        
 
    ##如果是TABLE不存在的KEY則
        
        if Qkey.empty == True:
            
            container = ('{}'.format(issue.key))
            BT_KEY_NUMBER.append(container)          ##往下抓各類資料&存放
            container = ('{}'.format(issue.fields.summary)) 
            BT_SUMMARY_TITLE.append(container)
            container = ('{}'.format(issue.fields.reporter))
            BT_REPORTER.append(container)

            container = ('{}'.format(issue.fields.assignee))
            BT_ASSIGNEE.append(container)

            container = ('{}'.format(issue.fields.issuetype))
            BT_ISSUE_TYPE.append(container)

            container = ('{}'.format(issue.fields.duedate))
            BT_DUE_DATE.append(container)

            container = ('{}'.format(issue.fields.status))
            BT_STATUS.append(container)
            
            containerA= ('{}'.format(issue.fields.attachment))
            if len(issue.fields.attachment):   #判斷網頁有無附圖，有即存入Y，無則N
                BT_ATTACHMENT.append('Y')
            
            else:
                BT_ATTACHMENT.append('N')
            
            TABLE_BT['KEY_NUMBER'] = BT_KEY_NUMBER
            TABLE_BT['SUMMARY_TITLE'] = BT_SUMMARY_TITLE
            TABLE_BT['REPORTER']=BT_REPORTER
            TABLE_BT['ASSIGNEE']=BT_ASSIGNEE
            TABLE_BT['ISSUE_TYPE']=BT_ISSUE_TYPE
            TABLE_BT['DUE_DATE']=BT_DUE_DATE
            TABLE_BT['STATUS']=BT_STATUS
            TABLE_BT['ATTACHMENT']=BT_ATTACHMENT
            new=new+1
            
            
            
            
  
            
##如果是TABLE存在的KEY則
        else:                       
            ##篩選網頁抓到的KEY在TABLE中的 ATTACHMENT 以及 STATUS
            sql = ("select ATTACHMENT,STATUS from INFRA_JIRA_ORDER_BT where KEY_NUMBER = '{}'").format(issue.key) 
            Qattachment=mes_obj.query(sql=sql,debug=False)
            #print('*********************', Qattachment)
            
            ##如果Attachment 是 Y 以及 STATUS 是 CLOSE 則不動作
            if Qattachment.iloc[0,0] == 'Y' and Qattachment.iloc[0,1] =='Close':
              
                #print(issue.key,"是Y也是CLOSE")
                YC=YC+1
                #print(YC)
             
            elif Qattachment.iloc[0,1] =='Cancelled':
                
                #print(issue.key,"已Cancelled")
                CC=CC+1
                #print(CC)
            else:
                ##update TABLE裡單筆資料
                update_sql = "UPDATE INFRA_JIRA_ORDER_BT SET KEY_NUMBER='{}',SUMMARY_TITLE='{}',REPORTER='{}',ASSIGNEE='{}',ISSUE_TYPE='{}',DUE_DATE='{}',STATUS='{}',ATTACHMENT='{}',RECTIME=SYSDATE WHERE KEY_NUMBER = '{}'".format(issue.key,issue.fields.summary,issue.fields.reporter,issue.fields.assignee,issue.fields.issuetype,issue.fields.duedate,issue.fields.status,ATTACHMENT[i],issue.key) 
                mes_obj.non_query(sql=update_sql,debug=False)   
                #print(issue.key,"因為是非Y非CLOSE")
                up=up+1
                #print(up)
   
    print("資料抓取完畢")
    print("更新BT DB 中")
           
                ##塞進網頁資料 insert
    df= pd.DataFrame(TABLE_BT,columns=['KEY_NUMBER','SUMMARY_TITLE','REPORTER','ASSIGNEE',
                                               'ISSUE_TYPE','DUE_DATE','STATUS','ATTACHMENT'] )
    mes_obj.non_query(df=df, cols=['KEY_NUMBER','SUMMARY_TITLE','REPORTER','ASSIGNEE',
                                       'ISSUE_TYPE','DUE_DATE','STATUS','ATTACHMENT'],
    table='INFRA_JIRA_ORDER_BT',nqtype='insert',debug=False)
            

        
    ##全部一包存入History
        ##列出資料格式
        
    TABLE_BTHHH['KEY_NUMBER'] = KEY_NUMBER
    TABLE_BTHHH['SUMMARY_TITLE'] = SUMMARY_TITLE
    TABLE_BTHHH['REPORTER']=REPORTER
    TABLE_BTHHH['ASSIGNEE']=ASSIGNEE
    TABLE_BTHHH['ISSUE_TYPE']=ISSUE_TYPE
    TABLE_BTHHH['DUE_DATE']=DUE_DATE
    TABLE_BTHHH['STATUS']=STATUS
    TABLE_BTHHH['ATTACHMENT']=ATTACHMENT

    print("更新BTH DB 中")
    ##一次存入DB[INFRA_JIRA_ORDER_BTH]
    df = pd.DataFrame(TABLE_BTHHH,columns=['KEY_NUMBER','SUMMARY_TITLE','REPORTER','ASSIGNEE',
                                       'ISSUE_TYPE','DUE_DATE','STATUS','ATTACHMENT'] )
    mes_obj.non_query(df=df, cols=['KEY_NUMBER','SUMMARY_TITLE','REPORTER','ASSIGNEE',
                                       'ISSUE_TYPE','DUE_DATE','STATUS','ATTACHMENT'],
                      table='INFRA_JIRA_ORDER_BTH',nqtype='insert',debug=False)
    print("DB資料存取完畢，開始統計資料")
    
    print ("JIRA抓出共 ",i+1,"  條")  
    print ("JIRA新增     ",new,"  條")
    print ("JIRA更新     ",up,"  條")
    print ("已結案",YC,"條","取消",CC,"條")
    print ("歷史新增   ",new+up+YC+CC,"  條")
    print("全部跑完囉!")
   
 ##登入失敗偵錯
elif login.status_code == 400:  #網頁Error Code
    print(login.status_code)
    print('Bad Request，網頁錯誤')
else:
    print('Error',login.status_code) #登入失敗Error Code
    print('帳號密碼錯誤','請重新輸入')

opentxt.close
text.clear() #關閉記事本 Config

*--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--*--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--**--*--*

#!/usr/bin/env python
# coding: utf-8

# In[ ]:


from DBSrv5ConnPy.db_object import DBObject ##DB連線工具
from jira import JIRA ##JIRA套件
import getpass ##加解密工具
import requests ##爬蟲工具
import pandas as pd ##潘達
import json
import socket
import logging
from flask import Flask
 
app = Flask(__name__)
@app.route('/JIRAGOJI')



def JIRAGOJI():

     ##抓帳密
    account = (text[1])
    password = (text[3])



    ##解密碼
    def dectry(p):
        decodtool = 'djq%5cu#-jeq15abg$z9_i#_w=$o88m!*alpbedlbat8cr74sd'
        password_decoded = ""
        for i,j in zip(p.split("_")[:-1],decodtool):
            # i 為加密字元，j為祕鑰字元
            temp = chr(int(i) - ord(j)) # 解密字元 = (加密Unicode碼字元 - 祕鑰字元的Unicode碼)的單位元組字元
            password_decoded = password_decoded+temp
        return password_decoded
    password_decoded = dectry(password)
    password = password_decoded
    authority = (account , password)



    if (text[9])=='False':
        testserver=0
    else :
        testserver=1




    mes_obj = DBObject(fab=(text[7]), is_test_db=testserver)   ##連入資料庫廠區&Test
    login = requests.get('http://300jira:8080/', auth=authority) ##進入jira網頁
    if login.status_code == requests.codes.ok:  ##檢查網路&登入是否正常

        jira = JIRA( {'server': 'http://300jira:8080/'}, basic_auth=authority) ##登入jira       
                                  #建倉庫　↓



        python_dict = []




        allfields=jira.fields() ##爬出網頁全部欄位
        nameMap = {field['name']:field['id'] for field in allfields} ##爬出網頁全部欄位0

        for issue in jira.search_issues(text[5],fields='*all',maxResults=100): ##搜尋JIRA下JQL指令


            container = (issue.key)
            KEY_NUMBER=(container)          ##往下抓各類資料&存放

            container = ('{}'.format(issue.fields.summary))
            SUMMARY_TITLE=container

            container = ('{}'.format(issue.fields.status))
            STATUS=container        

            try:
                sql = ("select TW_USERNAME from F14MGR_CUR_EMPLOYEES_V2 where name = '{}'").format(issue.fields.reporter) 
                Qreporter=mes_obj.query(sql=sql,debug=False)
                REPORTER=Qreporter.iloc[0,0]
            except:
                container = ('{}'.format(issue.fields.reporter))
                REPORTER=container     

            try:
                sql = ("select TW_USERNAME from F14MGR_CUR_EMPLOYEES_V2 where name = '{}'").format(issue.fields.assignee) 
                Qassignee=mes_obj.query(sql=sql,debug=False)
                ASSIGNEE=Qassignee.iloc[0,0]
            except:
                container = ('{}'.format(issue.fields.reporter))
                ASSIGNEE=container


            container = ('{}'.format(issue.fields.issuetype))
            ISSUE_TYPE=(container)

            container = (issue.fields.customfield_13612)
            START_TIME=(container)

            container = (issue.fields.customfield_11614)
            END_TIME=(container)

            container = ('{}'.format(issue.fields.description))
            DESCRIPTION=(container)

            container = (issue.fields.customfield_13624)
            IMPACT_HOST=(container)

            container = (issue.fields.customfield_13608)
            SOC_IP=(container)





            python_dict.append({'issue_key':KEY_NUMBER,'subject':SUMMARY_TITLE,'status':STATUS,'reporter':REPORTER,'assignee':ASSIGNEE
                         ,'issue_type':ISSUE_TYPE,'planned_start_date':START_TIME,'planned_end_date':END_TIME,'description':DESCRIPTION,
                         'impact_host':IMPACT_HOST})


        python2J= json.dumps(python_dict,ensure_ascii=False,indent=0)
        
        
        

        logging.info(json.dumps(python_dict,ensure_ascii=False,indent=0))

        return json.dumps(python_dict,ensure_ascii=False,indent=0)
        
        print ("FLASK OK")
        
        

 
    

 

        
             

 

   
     ##登入失敗偵錯
    elif login.status_code == 400:  #網頁Error Code
        print(login.status_code)
        print('Bad Request，網頁錯誤')
    else:
        print('Error',login.status_code) #登入失敗Error Code
        print('帳號密碼錯誤','請重新輸入')



    opentxt.close
    text.clear() #關閉記事本 Config

if __name__ == '__main__':
    opentxt=open('Jira_IT.txt',encoding="utf-8") ##開記事本config
    text = []
    for line in opentxt.read().splitlines(): ##列出記事本資料
        text.append(line)
    
    FORMAT = '%(asctime)s %(levelname)s: %(message)s'
    logging.basicConfig(level=logging.DEBUG,filename='JIRAGI.log', format=FORMAT)

    logging.debug('debug message')
    logging.info('info message')
    logging.warning('warning message')
    logging.error('error message')
    logging.critical('critical message')

    app.run(host=text[11], port=5000)
   
 





# In[ ]:

*---------------------**********---------------------**********---------------------**********---------------------**********---------------------*********

學校	學系	在職/一般生	成績單正本	推薦函	初審	複審	錄取率	今年錄取人數	報名人數	在職證明書	舊機構	remark	缺額
交通大學	網路工程研究所碩士班(聯招) OK	在職生	正本	2	100%	NA	22%	(混合)150人	148/668	正本1年(寄)		書面紙本	聯招
交通大學	數據科學與工程研究所	在職生	正本	2	100%	NA	10%	(混合)35人	25/247	正本1年(寄)		書面紙本	↑增加10人
交通大學	資訊科學與工程研究所丙組	在職生	正本	2	33%	66%	13%	(混合)12人	10/76	正本1年(寄)			↑增加2人 
交通大學	"智能系統研究所碩士班春(聯招)
(填寫推薦人資料後點選寄發通知信)"	一般生	上傳	2	100%	NA	NA	NA	NA				聯招
清華大學	資訊工程學系碩士班 (甲組) (缺翻譯成英文)	在職生	上傳	2	100%	NA	42%	3人	7	正本2年	勞保局		
清華大學	"資訊安全研究所碩士班  OK
(填寫推薦人資料後點選寄發通知信)"	在職生	上傳	2	50%	50%	50%	1人	2	正本2年	勞保局		
中央	資訊管理學系碩士班 (自傳&簡介用本系自訂表格)	一般生	上傳	NA	50%	50%	21%	46人	224				
中央	"資訊工程學系軟體工程碩士班(兩千字內)
系統發出一封推薦信邀請之電子郵件"	一般生	上傳	2	50%	50%	20%	20人	10/42				↑增加10人
中正	"資訊工程學系(推薦函系統上傳)
系統發送通知至電子信箱，通知推薦人上傳"	在職生\一般生	上傳	2	50%	50%	100%	2人	1人	正本2年	勞保局	一般生26% 75人	可以報同時兩組


*---------------------**********---------------------**********---------------------**********---------------------**********---------------------*********

清大資安
II.	選擇清大資安
清華大學校史悠久、校友人脈涵蓋各產業，同時擁有豐富的學術資源與優秀的師資，而清大資安重視理論與實務的結合，學術風氣鼎盛，師資陣容也來自不同專業領域背景，展現跨領域能力，不論是資料探勘、網路安全、系統資源管理等皆有專攻，使我可以更精進感興趣的領域，總結以上，清大資安實乃我心目中的第一志願。

二、	研究方向
現今正值全球資訊爆炸時代，人工智慧及深度學習，皆為各產業未來發展帶來無限可能，資訊安全也更顯得重要，再安全的機制如區塊鏈交易領域、微軟Print Spooler漏洞、雷蛇產品0-day取得最高權限，都會讓使用者的重要資訊陷入危險之中。
在進入業界後，因擔任Driver分析工程師，必須快速除錯使產能繼續運行，使我對導致錯誤的Root Cause分析與抓取能有一定的敏感度，於台積電任職後，在資訊安全、機密資訊保護更是重視。
計畫進入研究所就讀後，以資訊安全、網路安全為主要方向，這是許多網路攻擊發生的第一戰場，也能獲得許多重要訊息，建立一個安全的網路環境，如何讓使用者無須憂慮，保護弱勢使用者資訊不被惡意竊取，一直是我心目中的理想。

-*---------------------**********---------------------**********---------------------**********---------------------**********---------------------*********

交大數據

選擇交大數科
交通大學校史悠久，尤其交大數科更是國立大學中第一所專注於數據科學的研究所，校友人脈涵蓋各產業，擁有豐富的學術資源，師資陣容也來自不同專業領域背景，展現跨領域能力，且交大數科對於機器學習、巨量資料探勘、人工智慧皆有所專攻，使我可以更精進感興趣的領域，令我十分嚮往。

研究方向
現今正值全球資訊爆炸時代，人工智慧為世界帶來巨大衝擊變革，而不論人工智慧、深度學習，仰賴的都是巨量資料的輔助，特別是深度學習透過許多資料進行模組化的分析，不論是，聊天機器人、Alphago、自動駕駛等，都大量使用這項技術，而在台積電的工作經驗，部門內每日皆有上萬筆的資料被使用，如何降低資源使用率，提升整體效率，是非常重要的一環，確保資料正確性以及時效性，也是部門內的鐵則。
所以有效率的運用巨量資料，到未來深度學習等等範圍，是非常重要的，計畫進入研究所後，透過巨量分析的輔助，搭配人工智慧/深度學習來讓資料能被更有效的被運用，。 


-*---------------------**********---------------------**********---------------------**********---------------------**********---------------------*********
https://app.wordtune.com/editor

1.	Motivation
I.	Self-assessment: 
I have been interested in computer science ever since I was a child. Therefore, I studied the Department of Information Management at college. After graduation, I have continued to work with what I love. However, when I was worked in Inventec, I found I have to enhance my ability to solve problems quickly. I also found that I still have a lot to learn when working with many outstanding colleagues. I want to enhance my value and learn lots of things. Therefore, I am very firm in my volition to study in graduate school.
	
II.	Why I choose NTHUCS
The National Tsing Hua University is a university with a long history, alumni connections covering various industries. Also, The NTHU has top academic resources and excellent teachers in computer vision, computer systems, artificial intelligence, and many fields of computer technology. To sum up the above advantages, NTHUCS is my first choice.
 
2.	The Direction of research
The world today is experiencing an information explosion. Image recognition is bound to become more widespread. As part of my independent study at my university, I developed a mobile app that can scan QR codes in invoices to quickly identify what items were purchased. It can perform simple image analysis and identification. Having worked with AMD and Intel, I have a better understanding of the applications of graphics. Additionally, working at TSMC gave me a chance to experience the benefits of computer vision. These experiences make me very interested in computer vision.
If I enter graduate school, I plan to concentrate on image recognition and computer vision then look forward to utilizing the collected data in the most effective way. In addition, I will supplement with artificial intelligence and deep learning, hoping that computer vision can make life easier and smarter.
3.	Time Plan


Early goal  
Studying Advanced Placement  
Studying Open Course what include the Operating System Engineering by CHOU, JERRY. Computer Vision for Visual Effects by CHEN, HWANN-TZONG. Enhancing my theoretical basis 

Strengthen programming capabilities
make an effort to program at work (python、SQL、JAVA)

improve my English abilities 
Listening to English podcasts and reading English news to enhance my English abilities 
  
  
 
STATEMENT OF PURPOSE
1.	Motivation
I have been interested in computer science ever since I was a child. Therefore, I joined the technology industry after graduated. When I was worked in Inventec, Graphics Driver is my main work content. Having worked with AMD and Intel, I have a better understanding of the applications of graphics technology. Additionally, being part of TSMC has given me the opportunity to see how computer vision can benefit companies by Improve yield. To sum up, I want to improve my self-worth and improve related knowledge. Therefore, I am very firm in my volition to study in graduate.

2.	Study Plan
The world today, Image recognition is bound to become more widespread. As part of my independent study at my college, I developed a mobile app that can scan QR codes in invoices what items were purchased and save them into your account. In TSMC, I use RPA to automatically detect desktop items and install the required applications automatically with a CMD script. This project saves us many human resources and reduces human error. 
I will focus on image recognition and computer vision in graduate school then I will supplement with artificial intelligence. Below courses is what I prefer to dig in:
I.	Early goal - Enhancing my theoretical basis (open course) 
	Operating System Engineering. 
	Computer Vision for Visual Effects. 
II.	Mid-term Goal
	Deep Learning
	Topics on Design Automation
	




3.	Research proposal


