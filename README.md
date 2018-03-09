# 建材顾问反馈接口

### http地址
* 外测:http://prezx.admin.51youjuke.com
* 正式:https://zx.youjuke.com/

### 1.获取建材预约时间分单列表
* 接口地址: /actionapi/get\_jc\_allot\_baomings\_info
* 传递参数 

| 参数名 | 类型 | 备注 |
| ---- | --- | --- |
| baoming_id | int | 业主报名id |
| uid | int | 用户id |
| token | string | 用户token |
* data数据

| 名称 | 类型 | 备注 |
| ---- | --- | --- |
| list | list | 该分单id:分单时间 |
| is_fwsc | int | 是否已经发放业主服务手册，0:无，1:是 |

<font color="006400">e.g: 已经发放服务手册则不用显示服务手册选框</font>

* baoming_id	4505470
* uid	690
* token	phlQqrwm59-pbO0rpaqb-lJOrL7Bga-fL6FamwLNq-1505713999
* {"status":200,"error_code":0,"data":{"list":[{"allot_id":91,"appoint_measure_time":"1517328000"},{"allot_id":89,"appoint_measure_time":"1517068800"}],"is_fwsc":"1"},"message":"\u64cd\u4f5c\u6210\u529f"}


### 2.设定反馈信息
* 接口地址: /actionapi/set\_fk\_info
* 传递参数 

| 参数名 | 类型 | 备注 |
| ---- | --- | --- |
| allot_id | int | 分单id |
| fk_type | int | 反馈类型(0:无,1:量房,2:取消量房,3:量房改约,4:正常反馈) |
| fk_content | string | 反馈内容 |
| is_fwsc | int | 是否发放服务手册, 1为发放，0为未发放 注：如果已经发放了则不需要传递该参数 |
| uid | int | 用户id |
| token | string | 用户token |

* allot_id 61
* fk_type 1
* fk_content 123
* is_fwsc 1
* uid	690
* token	phlQqrwm59-pbO0rpaqb-lJOrL7Bga-fL6FamwLNq-1505713999
* {"status":200,"error_code":0,"message":"\u64cd\u4f5c\u6210\u529f"}

### 3.获取建材配置信息
* 接口地址: /actionapi/get\_jc\_config
* 传递参数 

| 参数名 | 类型 | 备注 |
| ---- | --- | --- |
| uid | int | 用户id |
| token | string | 用户token |

* data数据

| 名称 | 类型 | 备注 |
| ---- | --- | --- |
| fk_type | list | 反馈类型配置 |

* uid	690
* token	phlQqrwm59-pbO0rpaqb-lJOrL7Bga-fL6FamwLNq-1505713999
* {"status":200,"error_code":0,"data":{"fk_type":[{"id":1,"type":"\u91cf\u623f"},{"id":2,"type":"\u53d6\u6d88\u91cf\u623f"},{"id":3,"type":"\u91cf\u623f\u6539\u7ea6"},{"id":4,"type":"\u6b63\u5e38\u53cd\u9988"}]},"message":"\u64cd\u4f5c\u6210\u529f"}
