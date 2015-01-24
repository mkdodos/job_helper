# job_helper
職評管理

功能實作明細表

| 功能 | 人員服務時數統計 |
| ------------ | ----------- | 
| request      |  GET service/count_hours |  
| filter      |   manager(職評主管)    |         
| response  |     資料陣列 key=>value 人員id=>統計時數,年,月     | 
| controller  |     countHours@ServiceController      | 
| view  |     二個迴圈 (人員,資料)      | 
| menu  |     服務時數統計      | 

controller

1. 取得同公司的人員資料 
2. 針對每個人員取得服務的個案編號 
3. 用此個案編號作為條件取出case_arr資料表的資料,依年月群組統計時數


角色對照表
----------
| 角色名稱 | 說明 |
| ------------ | :-----------: | 
| manager      |  職評主管 |  
| worker      |   職評    |         
| gov_manger  |     政府職管主管      | 
| gov_worker  |     政府職管員      | 
| admin  |     站長      | 
| dada  |     (多角色)      | 

資料關連

* case_basic
* case_assign belongsTo('CaseBasic','case_id','id')
* case_arr belongsTo('CaseAssign','case_id','id')

欄位資料轉換

欄位資料:轉換資料(數字1代表10分鐘,數字6代表1小時)
```
0=>0:00,1=>0:10,2=>0:20,3=>0:30,4=>0:50,6=>1:00,
7=>1:10,8=>1:20,9=>1:30,10=>1:40,11=>1:50,12=>2:00,
...
```
網頁運作方式
送出請求 接受請求 送出回應
