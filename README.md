# job_helper
職評管理

功能實作明細表

| 功能 | 說明 |
| ------------ | ----------- | 
| request      |  GET service/count_hours |  
| filter      |   manager(職評主管)    |         
| response  |     資料陣列 key=>value 人員id=>統計時數,年,月     | 
| controller  |     countHours@ServiceController      | 
| view  |     二個迴圈 (人員,資料)      | 
| menu  |     服務時數統計      | 

controller

1. 取得同公司的人員資料 
1. 針對每個人員取得服務的個案編號 
1. 用此個案編號作為條件取出case_arr資料表的資料,依年月群組統計時數


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
case_basic
case_assign belongsTo('CaseBasic','case_id','id')
case_arr belongsTo('CaseAssign','case_id','id')
