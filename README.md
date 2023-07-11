# lanqiaoOJ_pythony
#日期问题
#1901年1月1日至2000年12月31日，一共有多少星期一？
from datetime import *
dt1 = datetime(1901,1,1)
dt2 = datetime(2000,12,31）
print(dt1.weekday())#输出1，表示周二。注意，周一用0表示，周日用6表示。
td = dt2 - dt1
print(td.days//7)
print("------------------")
#顺子日期
from datetime import *
dt1 = datetime(2022,1,1)
cnt = 0
for i in range(0,365):
s = "%02d%02d%02d%"%(dt1.year,dt1.month,dt1.day)
dt1 += timedelta(days=1)
if "012" in s or "123" in s or "234" in s or "345" in s or "456" in s or "567" in s \
   or "678" in s  or "789" in s:
   cnt +=1
print(cnt)
print("-----------------")
#特殊时间
def check(n):          #检查数字是否合法，n是排序后的
    if n[0] ==n[3]:
        return  False
    if n[1] != n[2]:
        return False
    if n[0] == n[1] or n[2] == n[3]:
        return True
    return False
year = []
for y in range(1,10000):      #0001年~9999年
    s = "%04d"%(y)
    s1 = sorted(s)
    if check(s1):
        year.append(s1)
day = [ ]
for m in range(1,13):            #12个月
    for d in range(1,31):        #30日,31日都不符合要求，不用管。同理2月29日，2月30日也不管。
        s = "%02d%02d"%(m,d)
        s1 = sorted(s)
        if check(s1):
            day.append(s1)
hour = []
for h in range(0,24):
    for m in range(0,60):
        s ="%02d%02d"%(h,m)
        s1 = sorted(s)
        if check(s1):
            hour.append(s1)
cnt = 0
for i in year:                 #遍历年
    for j in day:              #遍历月日
        for k in hour:         #遍历时分
            if i==j and j==k:
                cnt+=1
print(cnt)                    #输出212
