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
清華大學	資訊工程學系碩士班 (甲組)	在職生	上傳	2	100%	NA	42%	3人	7	正本2年	勞保局		
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
中央	資訊管理學系碩士班 	一般生	上傳	NA	50%	50%	21%	46人	224				
中央	資訊工程學系軟體工程碩士班	一般生	上傳	2	50%	50%	20%	20人	10/42				↑增加10人
中正	資訊工程學系	在職生\一般生	上傳	2	50%	50%	100%	2人	1人	正本2年	勞保局	一般生26% 75人	可以報同時兩組
中正	資訊管理學系	一般生	上傳	3	50%	50%	0.21	16人	70人				
中山	資訊工程學系甲組	一般生	上傳	可放	50%	50%	0.17	47人	51/292			A~E	↓減少４
中山	資訊管理學系	一般生	上傳	彌封推薦信2封	50%	50%	0.22	27人	30/136				↓減少３






 


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




