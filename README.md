내 Python 프로젝트에 오류가 있습니다. 새 IP 위치 추적입니다.
429 오류를 방지하기위한 Sleep 

rom bs4 import BeautifulSoup
from urllib.request import urlopen,Request
import os
import time
cmd = 'mode 35,13'
os.system(cmd) # 창 버퍼 조절!
print('\033[96m'+"Telegram:yblee\nEmail:yblee0816@naver.com"+'\033[96m')
print("Discord:이예빈#1924")
while True:   
    time.sleep(3)
    ip=input("\nTarget IP:")
    
    time.sleep(3)
    target_web=Request('https://whatismyipaddress.com/ip/'+ip,headers={'User-Agent': 'Mozilla/5.0'})
    response=urlopen(target_web)
    soup=BeautifulSoup(response,"html.parser")

    city=soup.select("#fl-post-1165 > div > div > div.fl-row.fl-row-fixed-width.fl-row-bg-none.fl-node-5d9c0c38837c0 > div > div.fl-row-content.fl-row-fixed-width.fl-node-content > div > div.fl-col.fl-node-5d9c0c3888731 > div > div.fl-module.fl-module-wipa-static-html.fl-node-5d9e84c8187fe > div > div > div > div > div.left > p:nth-child(11) > span:nth-child(2)")
    details_city=soup.select("#fl-post-1165 > div > div > div.fl-row.fl-row-fixed-width.fl-row-bg-none.fl-node-5d9c0c38837c0 > div > div.fl-row-content.fl-row-fixed-width.fl-node-content > div > div.fl-col.fl-node-5d9c0c3888731 > div > div.fl-module.fl-module-wipa-static-html.fl-node-5d9e84c8187fe > div > div > div > div > div.left > p:nth-child(12) > span:nth-child(2)")
    isp=soup.select("#fl-post-1165 > div > div > div.fl-row.fl-row-fixed-width.fl-row-bg-none.fl-node-5d9c0c38837c0 > div > div.fl-row-content.fl-row-fixed-width.fl-node-content > div > div.fl-col.fl-node-5d9c0c3888731 > div > div.fl-module.fl-module-wipa-static-html.fl-node-5d9e84c8187fe > div > div > div > div > div.left > p:nth-child(4) > span:nth-child(2)")
    country=soup.select("#fl-post-1165 > div > div > div.fl-row.fl-row-fixed-width.fl-row-bg-none.fl-node-5d9c0c38837c0 > div > div.fl-row-content.fl-row-fixed-width.fl-node-content > div > div.fl-col.fl-node-5d9c0c3888731 > div > div.fl-module.fl-module-wipa-static-html.fl-node-5d9e84c8187fe > div > div > div > div > div.left > p:nth-child(10) > span:nth-child(2)")
   

    if ip.count(".")==3:
        print("")
        print("ISP:",isp[0].text)
        print("Country:",country[0].text)
        print("City:",city[0].text,details_city[0].text)

    elif ip.count(".")!=3:
        print("Not IP or IPv6")
