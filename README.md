# lanqiaoOJ_pythony
#日期问题
#1901年1月1日至2000年12月31日，一共有多少星期一？
from datetime import *
dt1 = datetime(1901,1,1)
dt2 = datetime(2000,12,31）
print(dt1.weekday())#输出1，表示周二。注意，周一用0表示，周日用6表示。
td = dt2 - dt1
print(td.days//7)
