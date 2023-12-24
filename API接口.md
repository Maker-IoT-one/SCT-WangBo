# API接口

基于鸿蒙前端需求（只能由云端发送JSON数据，鸿蒙前端接收）  
后端撰写测试用接口，定义视图函数`test_api`

请求地址：http://123.60.166.120:9003/harmonyos/test_api/  
说明：
  
data：
| 字段             |   说明   | 类型 | 备注                 | 是否必填 | 其他 |
| :--------------- | :------: | ---: | :------------------- | :------: | ---: |
| random_date      |   日期   |  str | 随机数，当前日期     |    是    |   无 |
| carbon_price     |   碳价   |  int | 随机数，当日碳价     |    是    |   无 |
| carbon_emissions | 碳排放量 |  int | 随机数，当日碳排放量 |    是    |   无 |
源码
```python
from django.shortcuts import HttpResponse
import random, time
from datetime import datetime, timedelta
from django.shortcuts import render
from django.http import JsonResponse


def test_apps(request):
    return HttpResponse("测试多App成功-api_views")


def test_api(request):
    def generate_random_date(start_date, end_date):
        start_date = datetime.strptime(start_date, "%Y-%m-%d")
        end_date = datetime.strptime(end_date, "%Y-%m-%d")
        delta = end_date - start_date
        random_offset = random.randrange(delta.days)
        random_date = start_date + timedelta(days=random_offset)
        return random_date.strftime("%Y-%m-%d")

    start_date = "2023-12-01"
    end_date = "2023-12-16"

    random_date = generate_random_date(start_date, end_date)
    carbon_price = random.randint(20, 100)
    carbon_emissions = random.randint(20, 100)

    data = {
        'random_date': random_date,
        'carbon_price': carbon_price,
        'carbon_emissions': carbon_emissions
    }

    time.sleep(1)  # 延时1秒
    print(data)
    return JsonResponse(data)

```
